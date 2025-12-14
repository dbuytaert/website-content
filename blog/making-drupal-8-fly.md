---
title: 'Making Drupal 8 fly'
date: '2015-02-19T14:57:32-05:00'
author: Dries
summary: 'An overview of the biggest performance and scalability improvements in Drupal 8.'
image: drupal/drupal-8-render-pipeline
tags:
  - Drupal
  - 'Web performance'
published: true
type: blog
url: /making-drupal-8-fly
id: 3336
---

In my travels to talk about Drupal, everyone asks me about Drupal 8's performance and scalability. Modern websites are much [more dynamic and interactive than 10 years ago](https://dri.es/from-content-management-to-digital-experience-management), making it more difficult to build modern sites while also being fast. It made me realize that maybe I should write up a summary of some of the most exciting performance and scalability improvements in Drupal 8. After all, Drupal 8 will leapfrog many of its competitors in terms of how to architect and scale modern web applications. Many of these improvements benefit both small and large websites, but also allow us to build even bigger websites with Drupal.

### More precise cache invalidation

One of the strategies we employ in making Drupal fast is ["caching"](https://en.wikipedia.org/wiki/Cache_(computing)). This means we try to generate pages or page elements one time and then store them so future requests for those pages or page elements can be served faster. If an item is already cached, we can simply grab it without going through the building process again (known as a "cache hit"). Drupal stores each cache item in a "cache bin" (a database table, Memcache object, or whatever else is appropriate for the cache backend in use).

In Drupal 7 and before, when one of these cache items changes and it needs to be re-generated and re-stored (the cache gets "invalidated"), you can only delete a specific cache item, clear an entire cache bin, or use prefix-based invalidation. None of these three methods allow you to invalidate all cache items that contain data of, say, user 200. The only method that is going to suffice is clearing the entire cache bin, and this means that usually we invalidate way too much, resulting in poor cache hit ratios and wasted effort rebuilding cache items that haven't actually changed.

This problem is solved in Drupal 8 thanks to the concept of ["cache tags"](https://www.drupal.org/node/1534648): each cache item can have any number of cache tags. A cache tag is a compact string that describes the object being cached. Thanks to this extra metadata, we can now delete all cache items that use the `user:200` cache tag, for example. This means we've deleted all the cache items we must delete, but not a single one more: optimal cache invalidation!

[image drupal/drupal-8-cache-tags]

And don't worry, we also made sure to [expose the cache tags to reverse proxies](https://www.drupal.org/node/2222835), so that efficient and accurate invalidation can happen throughout a site's entire delivery architecture.

### More precise cache variation

While accurate cache *invalidation* makes caching more efficient, there is more we did to improve Drupal's caching. We also make sure that cached items are optimally *varied*. If you vary too much, duplicate cache entries will exist with the exact same content, resulting in inefficient usage of caches (low cache hit ratios). For example, we don't want a piece of content to be cached per user if it is the same for many users. If you vary too little, users might see incorrect content as two different cache entries might collide. In other words, you don't want to vary too much nor too little.

In Drupal 7 and before, it's easy to program any cached item to vary by user, by user role, and/or by page, and could even be configured through the UI for blocks. However, more targeted variations (such as by language, by country, or by content access permissions) were more difficult to program and not typically exposed in a configuration UI.

In Drupal 8, we introduced a [Cache Context API](https://www.drupal.org/node/2222293) to allow developers and site builders to express these variations and to make them automatically available in the configuration UI.

[image drupal/drupal-8-cache-contexts]

### Server-side dynamic content substitution

Usually a page can be cached almost entirely except for a few dynamic elements. Often a page served to two different authenticated users looks identical except for a small "Welcome $name!" and perhaps their profile picture. In Drupal 7, this small personalization breaks the cacheability of the entire page (or rather, requires a cache context that's way too granular). Most parts of the page, like the header, the footer and certain blocks in the sidebars don't change often nor vary for each user, so why should you regenerate all those parts at every request?

In Drupal 8, thanks to the addition of [\#post\_render\_cache](https://www.drupal.org/node/2151609), that is no longer the case. Drupal 8 can render the entire page with some placeholder HTML for the name and profile picture. That page can then be cached. When Drupal has to serve that page to an authenticated user, it will retrieve it from the cache, and just before sending the HTML response to the client, it will substitute the placeholders with the dynamically rendered bits. This means we can avoid having to render the page over and over again, which is the expensive part, and only render those bits that *need* to be generated dynamically!

### Client-side dynamic content substitution

Some things that Drupal has been rendering for the better part of a decade, such as the "new" and "updated" markers on comments, have always been rendered on the server. That is not ideal because these markers are different for every visitor and as a result, it makes caching pages with comments difficult.

The just-in-time substitution of placeholders with dynamic elements that `#post_render_cache` provides us can help address this. In some cases, as is the case with the comment markers, we can even do better and offload more work from the server to the client. In the case for comment markers, a certain comment is posted at a certain time – that doesn't vary per user. By embedding the comment timestamps as metadata in the DOM with a `data-comment-timestamp="1424286665"` attribute, we enable client-side JavaScript to render the comment markers, by fetching (and caching on the client side) the "last read" timestamp for the current user and simply comparing these numbers. Drupal 8 provides some [framework code and API](https://www.drupal.org/node/2086767) to make this easy.

### A "Facebook BigPipe" render pipeline

With Drupal 8, we're very close to taking the client-side dynamic content substitution a step further, just like some of the world's largest dynamic websites do. Facebook has 1.35 billion monthly active users all requesting dynamic content, so why not learn from them?

The traditional page serving model has not kept up with the increase of [highly personalized websites where different content is served to different users](https://dri.es/from-content-management-to-digital-experience-management). In the traditional model, such as Drupal 7, the entire page is generated before it is sent to the browser: while Drupal is generating a page, the browser is idle and wasting its cycles doing nothing. When Drupal finishes generating the page and sends it to the browser, the browser kicks into action, and the web server is idle. In the case of Facebook, they use [BigPipe](https://www.facebook.com/notes/facebook-engineering/bigpipe-pipelining-web-pages-for-high-performance/389414033919). BigPipe delivers pages asynchronously instead; it parallelizes browser rendering and server processing. Instead of waiting for the entire page to be generated, BigPipe immediately sends a page skeleton to the the client so it can start rendering that. Then the remaining content elements are requested and injected into their correct place. From the user's perspective the page is rendered progressively. The initial page content becomes visible much earlier, which improves the perceived speed of the site.

We've made significant improvements to [the way Drupal 8 renders pages](https://www.drupal.org/node/2373741) ([presentation](https://wimleers.com/talk/drupal-8-render-pipeline)). By default, Drupal 8 core still implements the traditional model of assembling these pieces into a complete page in a single server-side request, but the independence of each piece and the architecture of the new rendering pipeline enable different "render strategies" to be experimented with – different methods for dynamic content assembly, such as BigPipe, [Edge Side Includes](https://en.wikipedia.org/wiki/Edge_Side_Includes), or other ideas for making the most optimal use of client, server, content delivery networks and reverse proxies. In all those examples, the idea is that we can send the primary content first so the client can start rendering that. Then we send the remaining Drupal blocks, such as the navigation menu or a 'Related articles' block, and have the browser, content delivery network or reverse proxy assemble or combine these blocks into a page.

[image drupal/drupal-8-render-pipeline]

Some early experiments by [Wim Leers](http://wimleers.com) in [Acquia's OCTO](https://www.acquia.com/blog/announcing-office-cto-acquia) show that [we can improve performance by a factor of about 2](https://www.drupal.org/node/2429617) compared to a recent Drupal 8 development snapshot. These breakthroughs are enabled by leveraging the various improvements we made to Drupal 8.

### And much more

But that is not all. The Drupal community has actually done much more, including: complete asset dependency information (which allowed us to ensure zero JavaScript is loaded by default for anonymous users and [send less data on AJAX requests](https://www.drupal.org/node/2368797)), [pluggable CSS/JS aggregation and minification](https://www.drupal.org/node/2034675) (to support more optimal optimization algorithms), and more. We've also made sure Drupal 8 is [fast by default](https://wimleers.com/article/performance-calendar-2013-making-the-entire-web-fast), by having better defaults: [CSS/JS aggregation enabled](https://www.drupal.org/node/2259531), [JS assets being loaded from the bottom](https://www.drupal.org/node/2412769), block caching enabled, and so on.

All in all, there is a lot to look forward to in Drupal 8!

*Special thanks to [Acquia](https://www.acquia.com)'s [Wim Leers](https://www.drupal.org/u/wim-leers), [Alex Bronstein](https://www.drupal.org/u/effulgentsia) and [Angie Byron](https://www.drupal.org/u/webchick) for their contributions to this blog post.*
