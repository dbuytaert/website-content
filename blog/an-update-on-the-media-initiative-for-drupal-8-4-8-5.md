---
url: 'https://dri.es/an-update-on-the-media-initiative-for-drupal-8-4-8-5'
title: 'An update on the Media Initiative for Drupal 8.4/8.5'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2017-11-10T06:54:23-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'Want to know what has been happening with the Media Initiative in Drupal? Read my update.'
tags:
  - Drupal
image: blog/2016-product-survey-top-content-author-improvements
published: true
id: 4066
---

# An update on the Media Initiative for Drupal 8.4/8.5

In my blog post, "[A plan for media management in Drupal 8](https://dri.es/a-plan-for-media-management-in-drupal-8)", I talked about some of the challenges with media in Drupal, the hopes of end users of Drupal, and the plan that the team working on the Media Initiative was targeting for future versions of Drupal 8. That blog post is one year old today. Since that time we released both Drupal 8.3 and Drupal 8.4, and Drupal 8.5 development is in full swing. In other words, it's time for an update on this initiative's progress and next steps.

### 8.4: A Media API in core

Drupal 8.4 introduced a new Media API to core. For site builders, this means that Drupal 8.4 ships with the new [Media module](https://www.drupal.org/docs/8/core/modules/media/overview) (albeit still hidden from the UI, pending necessary user experience improvements), which is an adaptation of the [contributed Media Entity module](https://www.drupal.org/project/media_entity). The new Media module provides a "base media entity". Having a "base media entity" means that all media assets – local images, PDF documents, YouTube videos, tweets, and so on – are revisable, extendable (*fieldable*), translatable and much more. It allows all media to be treated in a common way, regardless of where the media resource itself is stored. For end users, this translates into a more cohesive content authoring experience; you can use consistent tools for managing images, videos, and other media rather than different interfaces for each media type.

### 8.4+: Porting contributed modules to the new Media API

The [contributed Media Entity module](https://www.drupal.org/project/media_entity) was a "foundational module" used by [a large number of other contributed modules](https://www.drupal.org/node/2860796). It enables Drupal to integrate with [Pinterest](https://www.drupal.org/project/media_entity_pinterest), [Vimeo](https://www.drupal.org/project/media_entity_vimeo), [Instagram](https://www.drupal.org/project/media_entity_instagram), [Twitter](https://www.drupal.org/project/media_entity_twitter) and much more. The next step is for all of these modules to adopt the new Media module in core. The required changes are laid out in the API change record, and typically only require a couple of hours to complete. The sooner these modules are updated, the sooner Drupal's rich media ecosystem can start benefitting from the new API in Drupal core. This is a great opportunity for intermediate contributors to pitch in.

### 8.5+: Add support for remote video in core

As proof of the power of the new Media API, the team is hoping to bring in support for remote video using the [oEmbed format](https://oembed.com). This allows content authors to easily add e.g. YouTube videos to their posts. This has been a long-standing gap in Drupal's out-of-the-box media and asset handling, and would be a nice win.

### 8.6+: A Media Library in core

The top two requested features for the content creator persona are richer image and media integration and [digital asset management](https://en.wikipedia.org/wiki/Digital_asset_management).

[image blog/2016-state-of-drupal-survey-top-content-author-improvements resize=false]

With a Media Library content authors can select pre-existing media from a library and easily embed it in their posts. Having a Media Library in core would be very impactful for content authors as it helps with both these feature requests.

During the 8.4 development cycle, a lot of great work was done to prototype the Media Library discussed in [my previous Media Initiative blog post](https://dri.es/a-plan-for-media-management-in-drupal-8). I was able to show that progress in [my DrupalCon Vienna keynote](https://dri.es/state-of-drupal-presentation-september-2017):

[video S82paYMycNE]

The Media Library work uses the new Media API in core. Now that the new Media API landed in Drupal 8.4 we can start focusing more on the Media Library. Due to bandwidth constraints, we don't think the Media Library will be ready in time for the Drupal 8.5 release. If you want to help contribute time or funding to the development of the Media Library, have a look at the [roadmap of the Media Initiative](https://www.drupal.org/node/2825215) or [let me know](https://dri.es/contact) and I'll get you in touch with the team behind the Media Initiative.

*Special thanks to [Angie Byron](https://www.drupal.org/u/webchick) for contributions to this blog post and to [Janez Urevc](https://www.drupal.org/u/slashrsm), [Sean Blommaert](https://www.drupal.org/u/seanb), [Marcos Cano Miranda](https://www.drupal.org/u/marcoscano), [Adam G-H](https://www.drupal.org/u/phenaproxima) and [Gábor Hojtsy](https://www.drupal.org/u/g%C3%A1bor-hojtsy) for their feedback during the writing process.*
