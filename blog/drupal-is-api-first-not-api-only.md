---
title: 'Drupal is API-first, not API-only'
date: '2017-04-25T12:59:36-04:00'
author: Dries
summary: 'Drupal is both a coupled CMS for editors who need control over the presentation as well as a headless CMS for developers who want to build a custom front-end.'
image: drupal/drupal-is-api-first-drupal-site-and-content-service
tags:
  - Drupal
  - 'Headless Drupal'
  - 'Web services'
featured: true
published: true
type: blog
url: /drupal-is-api-first-not-api-only
id: 3916
---

More and more developers are choosing content-as-a-service solutions known as headless CMSes – content repositories which offer no-frills editorial interfaces and expose content APIs for consumption by an expanding array of applications. Headless CMSes share a few common traits: they lack end-user front ends, provide few to no editorial tools for display and layout, and as such leave presentational concerns almost entirely up to the front-end developer. Headless CMSes have gained popularity because:

- A desire to separate concerns of structure and presentation so that front-end teams and back-end teams can work independently from each other.
- Editors and marketers are looking for solutions that can serve content to a growing list of channels, including websites, back-end systems, single-page applications, native applications, and even emerging devices such as wearables, conversational interfaces, and IoT devices.

Due to this trend among developers, many are rightfully asking whether headless CMSes are challenging the market for traditional CMSes. I'm not convinced that headless CMSes as they stand today are where the CMS world in general is headed. In fact, I believe a nuanced view is needed.

In this blog post, I'll explain why Drupal has one crucial advantage that propels it beyond the emerging headless competitors: it can be an exceptional CMS for editors who need control over the presentation of their content *and* a rich headless CMS for developers building out large content ecosystems in a single package.

As Drupal continues to power the websites that have long been its bread and butter, it is also used more and more to serve content to other back-end systems, single-page applications, native applications, and even conversational interfaces – all at the same time.

### Headless CMSes are leaving editors behind

[image drupal/drupal-is-api-first-coupled-drupal-vs-headless-cms resize=false]

Some claim that headless CMSes will replace traditional CMSes like Drupal and WordPress when it comes to content editors and marketers. I'm not so sure.

Where headless CMSes fall flat is in the areas of in-context administration and in-place editing of content. Our [outside-in efforts](https://dri.es/turning-drupal-outside-in), in contrast, aim to allow an editor to administer content and page structure in an interface alongside a live preview rather than in an interface that is completely separate from the end user experience. Some [examples of this paradigm](https://dri.es/examples-of-how-to-make-drupal-outside-in) include dragging blocks directly into regions or reordering menu items and then seeing both of these changes apply live.

By their nature, headless CMSes lack full-fledged editorial experience integrated into the front ends to which they serve content. Unless they expose a content editing interface tied to each front end, in-context administration and in-place editing are impossible. In other words, to provide an editorial experience on the front end, that front end *must* be aware of that content editing interface – hence the necessity of coupling.

Display and layout manipulation is another area that is key to making marketers successful. One of Drupal's key features is the ability to control where content appears in a layout structure. Headless CMSes are unopinionated about display and layout settings. But just like in-place editing and in-context administration, editorial tools that enable this need to be integrated into the front end that faces the end user in order to be useful.

In addition, editors and marketers are particularly concerned about how content will look once it's published. Access to an easy end-to-end preview system, especially for unpublished content, is essential to many editors' workflows. In the headless CMS paradigm, developers have to jump through fairly significant hoops to enable seamless preview, including setting up a new API endpoint or staging environment and deploying a separate version of their application that issues requests against new paths. As a result, I believe seamless preview – without having to tap on a developer's shoulder – is still necessary.

Features like in-place editing, in-context administration, layout manipulation, and seamless but faithful preview are essential building blocks for an optimal editorial experience for content creators and marketers. For some use cases, these drawbacks are totally manageable, especially where an application needs little editorial interaction and is more developer-focused. But for content editors, headless CMSes simply don't offer the toolkits they have come to expect; they fall short where Drupal shines.

### Drupal empowers both editors and application developers

[image drupal/drupal-is-api-first-api-first-drupal-vs-headless-cms resize=false]

All of this isn't to say that headless isn't important. Headless is important, but supporting both headless and traditional approaches is one of the biggest advantages of Drupal. After all, content management systems need to serve content beyond editor-focused websites to single-page applications, native applications, and even emerging devices such as wearables, conversational interfaces, and IoT devices.

Fortunately, the ongoing API-first initiative is actively working to [advance existing and new web services efforts](https://dri.es/advancing-drupal-web-services) that make using Drupal as a content service much easier and more optimal for developers. We're working on making developers of these applications more productive, whether through web services that provide a great developer experience like [JSON API](https://www.drupal.org/project/jsonapi) and [GraphQL](https://www.drupal.org/project/graphql) or through tooling that accelerates headless application development like [the Waterwheel ecosystem](https://dev.acquia.com/article/waterwheel-drupal-sdk-ecosystem).

For me, the key takeaway of this discussion is: *Drupal is great for both editors and developers*. But there are some caveats. For web experiences that need significant focus on the editor or assembler experience, you should use a coupled Drupal front end which gives you the ability to edit and manipulate the front end without involving a developer. For web experiences where you don't need editors to be involved, Drupal is still ideal. In an API-first approach, Drupal provides for other digital experiences that it can't explicitly support (those that aren't web-based). This keeps both options open to you.

### Drupal for your site, headless Drupal for your apps

[image drupal/drupal-is-api-first-drupal-site-and-content-service resize=false]

In this day and age, having all channels served by a single source of truth for content is important. But what architecture is optimal for this approach? While reading this you might have also experienced some déjà-vu from a blog post I wrote last year about [how you should decouple Drupal](https://dri.es/how-should-you-decouple-drupal), which is still solid advice nearly a year after I first posted it.

Ultimately, I recommend an architecture where Drupal is simultaneously coupled and decoupled; in short, Drupal shines when it's positioned both for editors and for application developers, because Drupal is great at both roles. In other words, your content repository should also be your public-facing website – a contiguous site with full editorial capabilities. At the same time, it should be the centerpiece for your collection of applications, which don't necessitate editorial tools but do offer your developers the experience they want. Keeping Drupal as a coupled website, while concurrently adding decoupled applications, isn't a limitation; it's an enhancement.

### Conclusion

Today's goal isn't to make Drupal API-only, but rather API-first. It doesn't limit you to a coupled approach like CMSes without APIs, and it doesn't limit you to an API-only approach like Contentful and other headless CMSes. To me, that is the most important conclusion to draw from this: Drupal supports an entire *spectrum* of possibilities. This allows you to make the proper trade-off between optimizing for your editors and marketers, or for your developers, and to shift elsewhere on that spectrum as your needs change.

It's a spectrum that encompasses both extremes of the scenarios that a coupled approach and headless approach represent. You can use Drupal to power a single website as we have for many years. At the same time, you can use Drupal to power a long list of applications beyond a traditional website. In doing so, Drupal can be adjusted up and down along this spectrum according to the requirements of your developers and editors.

In other words, Drupal is API-first, not API-only, and rather than leave editors and marketers behind in favor of developers, it gives everyone what they need in one single package.

*Special thanks to [Preston So](https://www.drupal.org/u/prestonso) for contributions to this blog post and to [Wim Leers](https://www.drupal.org/u/wim-leers), [Ted Bowman](https://www.drupal.org/u/tedbow), [Chris Hamper](https://www.drupal.org/u/hampercm) and [Matt Grill](https://www.drupal.org/u/drpal) for their feedback during the writing process.*
