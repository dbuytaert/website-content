---
title: 'How Drupal continues to evolve towards an API-first platform'
date: '2018-07-19T07:06:36-04:00'
author: Dries
summary: "A progress report on Drupal's API-first strategy"
tags:
  - Drupal
  - 'Web services'
  - 'Headless Drupal'
published: true
type: blog
url: /how-drupal-continues-to-evolve-towards-an-api-first-platform
id: 4451
---

It's been 12 months since [my last progress report on Drupal core's API-first initiative](https://dri.es/improving-drupal-8-api-first-json-api-oauth2). Over the past year, we've made a lot of important progress, so I wanted to provide another update.

Two and a half years ago, we shipped Drupal 8.0 with a built-in REST API. It marked the start of Drupal's evolution to an API-first platform. Since then, each of the five new releases of Drupal 8 introduced significant web service API improvements.

While I was an early advocate for adding web services to Drupal 8 five years ago, I'm even more certain about it today. Important market trends endorse this strategy, including integration with other technology solutions, the proliferation of new devices and digital channels, [the growing adoption of JavaScript frameworks](https://dri.es/a-history-of-javascript-across-the-stack), and more.

In fact, I believe that this functionality is so crucial to the success of Drupal, that for several years now, [Acquia](https://acquia.com) has sponsored one or more full-time software developers to contribute to Drupal's web service APIs, in addition to funding different community contributors. Today, two Acquia developers work on Drupal web service APIs full time.

### Drupal core's REST API

While Drupal 8.0 shipped with a basic REST API, the community has worked hard to improve its capabilities, robustness and test coverage. Drupal 8.5 shipped 5 months ago and included [new REST API features and significant improvements](https://wimleers.com/blog/api-first-drupal-8.5). Drupal 8.6 will ship in September with a new batch of improvements.

One Drupal 8.6 improvement is the move of the API-first code to the individual modules, instead of the REST module providing it on their behalf. This might not seem like a significant change, but it is. In the long term, all Drupal modules should ship with web service APIs rather than depending on a central API module to provide their APIs – that forces them to consider the impact on REST API clients when making changes.

Another improvement we've made to the REST API in Drupal 8.6 is [support for file uploads](https://www.drupal.org/node/2941420). If you want to understand how much thought and care went into REST support for file uploads, check out [API-first Drupal: file uploads](https://wimleers.com/blog/api-first-drupal-file-uploads). It's hard work to make file uploads secure, support large files, optimize for performance, and provide a good developer experience.

### JSON API

Adopting the [JSON API module](https://www.drupal.org/project/jsonapi) into core is important because JSON API is increasingly common in the JavaScript community.

We had [originally planned to add JSON API to Drupal 8.3](https://dri.es/a-roadmap-for-making-drupal-more-api-first), which didn't happen. When that plan was originally conceived, we were only beginning to discover the extent to which Drupal's Routing, Entity, Field and Typed Data subsystems were insufficiently prepared for an API-first world. It's taken until the end of 2017 to prepare and solidify those foundational subsystems.

The same shortcomings that prevented the REST API to mature also manifested themselves in JSON API, GraphQL and other API-first modules. Properly solving them at the root rather than adding workarounds takes time. However, this approach will make for a stronger API-first ecosystem and increasingly faster progress!

Despite the delay, the JSON API team has been making incredible strides. In just the last six months, they have released 15 versions of their module. They have delivered improvements at a breathtaking pace, including comprehensive test coverage, better compliance with the [JSON API specification](https://jsonapi.org/format/), and numerous stability improvements.

The Drupal community has been eager for these improvements, and the usage of the [JSON API module](https://www.drupal.org/project/jsonapi) has grown 50% in the first half of 2018. The fact that module usage has increased while the total number of open issues has gone down is proof that the JSON API module has become stable and mature.

As excited as I am about this growth in adoption, the rapid pace of development, and the maturity of the JSON API module, [we have decided not to add JSON API as an experimental module to Drupal 8.6](https://wimleers.com/blog/state-of-jsonapi-2018-07). Instead, we plan to commit it to Drupal core early in the Drupal 8.7 development cycle and ship it as stable in Drupal 8.7.

### GraphQL

For more than two years [I've advocated that we consider adding GraphQL to Drupal core](https://dri.es/advancing-drupal-web-services).

While core committers and core contributors haven't made GraphQL a priority yet, a lot of great progress has been made on the contributed [GraphQL module](https://www.drupal.org/project/graphql), which has been getting closer to its first stable release. Despite not having a stable release, its adoption has grown an impressive 200% in the first six months of 2018 (though its usage is still measured in the hundreds of sites rather than thousands).

I'm also excited that the GraphQL specification has finally seen a [new edition](https://github.com/facebook/graphql/releases/tag/June2018) that is [no longer encumbered by licensing concerns](https://code.fb.com/core-data/relicensing-the-graphql-specification/). This is great news for the Open Source community, and can only benefit GraphQL's adoption.

Admittedly, I don't know yet if the GraphQL module maintainers are on board with my recommendation to add GraphQL to core. We purposely postponed these conversations until we stabilized the REST API and added JSON API support. I'd still love to see the GraphQL module added to a future release of Drupal 8. Regardless of what we decide, GraphQL is an important component to an API-first Drupal, and I'm excited about its progress.

### OAuth 2.0

A web services API update would not be complete without touching on the topic of authentication. Last year, I explained [how the OAuth 2.0 module would be another logical addition to Drupal core](https://dri.es/improving-drupal-8-api-first-json-api-oauth2).

Since then, the [OAuth 2.0 module](https://www.drupal.org/project/simple_oauth) was revised to exclude its own OAuth 2.0 implementation, and to adopt [The PHP League's OAuth 2.0 Server](https://oauth2.thephpleague.com/) instead. That implementation is widely used, with over 5 million installs. Instead of having a separate Drupal-specific implementation that we have to maintain, we can leverage a de facto standard implementation maintained by others.

### API-first ecosystem

While I've personally been most focused on the REST API and JSON API work, with GraphQL a close second, it's also encouraging to see that many other API-first modules are being developed:

- [OpenAPI](https://www.drupal.org/project/openapi), for standards-based API documentation, now at beta 1
- [JSON API Extras](https://www.drupal.org/project/jsonapi_extras), for shaping JSON API to your site's specific needs (aliasing fields, removing fields, etc)
- [JSON-RPC](https://www.drupal.org/project/jsonrpc), for help with executing common Drupal site administration actions, for example clearing the cache
- ... and [many more](https://www.drupal.org/project/project_module?f%5B0%5D=&f%5B1%5D=&f%5B2%5D=im_vid_3%3A186018&f%5B3%5D=drupal_core%3A7234&f%5B4%5D=sm_field_project_type%3Afull&f%5B5%5D=&f%5B6%5D=&text=&solrsort=iss_project_release_usage+desc&op=Search)

### Conclusion

Hopefully, you are as excited for the upcoming release of Drupal 8.6 as I am, and all of the web service improvements that it will bring. I am very thankful for all of the contributions that have been made in our continued efforts to make Drupal API-first, and for the incredible momentum these projects and initiatives have achieved.

*Special thanks to [Wim Leers](https://www.drupal.org/u/wim-leers) (Acquia) and [Gabe Sullice](https://www.drupal.org/u/gabesullice) (Acquia) for contributions to this blog post and to [Mark Winberry](https://www.drupal.org/u/markwin) (Acquia) and [Jeff Beeman](https://www.drupal.org/u/jrbeeman) (Acquia) for their feedback during the writing process.*
