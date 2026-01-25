---
url: 'https://dri.es/a-plan-for-media-management-in-drupal-8'
title: 'A plan for media management in Drupal 8'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2016-11-08T04:23:35-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
  - Entertainment
  - Publishing
published: true
id: 3811
---

# A plan for media management in Drupal 8

Today, when you install Drupal 8.2, the out-of-the-box media handling is very basic. For example, you can upload and insert images in posts using a WYSIWYG editor, but there is no way to reuse files across posts, there is no built-in media manager, no support for "remote media" such as YouTube videos or tweets, etc. While all of these media features can be added using contributed modules, it is not ideal.

This was validated by my "State of Drupal 2016 survey" which 2,900 people participated in; the top two requested features for the content creator persona are richer image and media integration and [digital asset management](https://en.wikipedia.org/wiki/Digital_asset_management) (see [slide 44 of my DrupalCon New Orleans presentation](https://dri.es/state-of-drupal-presentation-may-2016)).

This led me to propose a "media initiative" for Drupal 8 at DrupalCon New Orleans. Since then a dedicated group of people worked on [a plan for the Drupal 8 media initiative](https://www.drupal.org/node/2786785). I'm happy to share that we now have good alignment for that initiative. We want to provide extensible base functionality for media handling in core that supports the reuse of media assets, media browsing, and remote media, and that can be cleanly extended by contributed modules for various additional functionality and integrations. That is a mouthful so in this blog post, I'll discuss the problem we're trying to solve and how we hope to address that in Drupal 8.

### Problem statement

While Drupal core provides basic media capabilities, contributed modules have to be used to meet the media management requirements of most websites. These contributed modules are powerful – look at Drupal's massive adoption in the media and entertainment market – but they are also not without some challenges.

First, it is hard for end-users to figure out what combination of modules to use. Even after the right modules are selected, the installation and configuration of various modules can be daunting. Fortunately, there are a number of Drupal distributions that select and configure various contributed modules to offer better out-of-the-box experience for media handling. Acquia maintains [the Lightning distribution](https://www.drupal.org/project/lightning) as a general purpose set of components including media best practices. Hubert Burda Media [built the Thunder distribution](https://dri.es/thunder-a-drupal-distribution-for-publishers) and offers publishers strong media management capabilities. MD Systems [created the NP8 distribution](https://www.md-systems.ch/en/blog/md-systems/2016/08/09/md-systems-introduced-np8-to-the-big-apple) for news publishers which also bundles strong media features. While [I'm a big believer in Drupal distributions](https://dri.es/drupal-distributions), the vast majority of Drupal sites are not built with one of these distributions. Incorporating some of these media best practices in core would make them available to all end-users.

Second, the current situation is not ideal for module developers either. Competing solutions and architectures exist for how to store media data and how to display a library of the available media assets. The lack of standardization means that developers who build and maintain media-related modules must decide which of the competing approaches to integrate with, or spend time and effort integrating with all of them.

### The current plan

In a way, Drupal's media management today is comparable to the [state of multilingual in Drupal 7](https://dri.es/multilingual-support-in-drupal-8); it took 22 or more contributed modules to make Drupal 7 truly multilingual and some of those provided conflicting solutions. Multilingual in Drupal 7 was challenging for both end-users and developers. We fixed that in Drupal 8 by adding a base layer of services in Drupal 8 core, while contributed modules still cover the more complex scenarios. That is exactly what we hope to do with media in a future version of Drupal 8.

The [plan for the Drupal 8 media initiative](https://www.drupal.org/node/2786785) is to provide extensible base functionality for media handling in core that supports the reuse of media assets, media browsing, and remote media, and that can be cleanly extended by contributed modules for various additional functionality and integrations.

In order to do so, we're introducing a media entity type which supports plugins for various media types. We're currently aiming to support images and YouTube videos in core, while contributed modules will continue to provide more, like audio, Facebook, Twitter, etc. To facilitate media reuse, WYSIWYG image embedding will be rebuilt using media entities and a media library will be included to allow selecting from pre-existing media.

We consider this functionality to be the [minimum viable product](https://en.wikipedia.org/wiki/Minimum_viable_product) for media in Drupal 8 core. The objective is to provide a simple media solution to make Drupal 8 easy to use out of the box for basic use cases. This would help users of sites large and small.

[image drupal/media-library-prototype-2016]

### Expected timeline and call for help

We believe this could be achieved in a relatively short time – to be included in Drupal 8.3 or Drupal 8.4 as [experimental modules](https://dri.es/the-transformation-of-drupal-8-for-continuous-innovation). To help make this happen, we are looking for organizations to help fund two dedicated code sprints. The existing contributors are doing an amazing job but dedicated in-person sprints would go a long way to make the plans actually happen. If you are willing to help fund this project, let me know! Looking to help with the implementation itself? The media team meets at 2pm UTC every Wednesday. I also recommend you follow [@drupalmedia](https://twitter.com/drupalmedia) for updates.

*I tried to make a list of all people and organizations to thank for their work on the media initiative but couldn't. The Drupal 8 initiative borrows heavily from years of hard work and learnings on media related modules from many people and organizations. In addition, there are many people actively working on various aspects of the Drupal 8 media initiative. Special thanks to everyone who has contributed now and in the past. Also thank you to [Gábor Hojtsy](https://www.drupal.org/u/g%C3%A1bor-hojtsy), [Alex Bronstein](https://www.drupal.org/u/effulgentsia) and [Janez Urevc](https://www.drupal.org/u/slashrsm) for their contributions to this blog post.*
