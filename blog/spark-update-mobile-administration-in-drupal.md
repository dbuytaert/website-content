---
title: 'Spark update: mobile administration in Drupal'
date: '2012-08-13T21:37:35-04:00'
author: Dries
tags:
  - Drupal
  - 'Spark distribution'
published: true
type: blog
url: /spark-update-mobile-administration-in-drupal
id: 2736
---

Today, I'd like to share an HTML/JS prototype we've created for a mobile toolbar and dashboard for [Drupal](https://www.drupal.org/) that we hope to include as part of the [Spark distribution](https://www.drupal.org/project/spark) and then propose for Drupal 8 core as part of the [Drupal 8 Mobile Initiaitve](https://groups.drupal.org/mobile/drupal-8).

Drupal 7's default administration tools (e.g. Toolbar module and Shortcut module) were not designed in a "mobile first" way, and as such can be difficult to work with on tablets or smartphones. For example, here is a screenshot of what happens to the Toolbar and Shortcut modules when using a responsive version of the Bartik theme on an iPhone:

[image drupal/drupal-7-toolbar-on-iphone]

Kevin O'Leary from the Spark team has come up with the following design. The toolbar design in particular takes heavy inspiration from efforts by [Lewis Nyman](http://lewisnyman.co.uk/) and his [mobile navigation prototype](https://groups.drupal.org/node/232653).

We set out to do justice to the complexites of Drupal's administration layer while accounting for the constantly evolving universe of devices. We think what we've come up with is scalable, responsive, and usable.

Here is Preston So, author of the prototype, demonstrating the functionality in a short, 7 minute video:

[video 7NlX41UYVVY]

As we begin work on this feature, it will live at the [Mobile friendly navigation toolbar project](https://www.drupal.org/project/navbar) as a contributed module for Drupal 7 first. If these changes are well-received, I hope we can target this functionality for Drupal 8 core, as a replacement for the Toolbar and Shortcut modules.
