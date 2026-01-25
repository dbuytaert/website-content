---
url: 'https://dri.es/code-freeze-module-maintainers-and-veggies'
title: 'Code freeze, module maintainers and veggies'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2010-09-09T12:01:36-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
  - Mollom
published: true
id: 1796
---

# Code freeze, module maintainers and veggies

Besides working on [Drupal core](https://www.drupal.org/project/drupal), I help maintain one contributed module: the [Mollom module](https://www.drupal.org/project/mollom). It reminds me what it's like to maintain a contributed module and to depend on Drupal core, what it's like to develop a module with a constantly and sometimes rapidly changing core. It is healthy.

I was involved in maintaining the Mollom module throughout the entire life of Drupal 6, while Drupal 6's API was strictly frozen. We ran into a number of Drupal 6 bugs and limitations, but worked around them as best as we could in less than elegant, but in creative ways. The Mollom module may seem simple, but I can assure anyone that it's not. For example, to insert a CAPTCHA it dynamically alters the forms in a way that pushes the limits of Drupal's Form API and implements advanced client-server communication over XML-RPC.

We began the Drupal 7 port of the Mollom module in January 2010, roughly 9 months ago, shortly after we put our pencils down on Drupal 7 development and started working towards the final Drupal 7.0 release. We have maintained and improved the Drupal 7 version of the Mollom module ever since. We even added features not available in the Drupal 6 version of Mollom, and we're using it to [protect thousands of Drupal Gardens sites](https://dri.es/mollom-protecting-drupal-gardens-against-spam). Of course, this meant that we had to keep up with last minute API changes in Drupal core. But, in the end I think the energy and time we expended were justified.

Not only is the Drupal 7 API much improved and we were able to throw away large chunks of code, we were also able to make both Drupal core and the Mollom module better along the way. Through our work on the Mollom module, we were able to fix bugs in both Drupal's Form API and XML-RPC backend, to name two examples. This includes the kind of bugs that we would not be able to fix after Drupal 7 has been released. The result is not only a better core, but also a better module that is easier to maintain. To me, this approach is well worth the extra effort it takes to make some Drupal core API changes.

So I wonder why so many module maintainers wait to upgrade until Drupal 7 is released. We've learned important lessons from the Drupal 6 release cycle, but we can still do better; only 10% of the Drupal 6 modules have some sort of Drupal 7 release at this point. Code freeze is an ideal time for module maintainers; it provides a chance for module maintainers to catch up, fix problems and to make their modules shine.

Upgrading modules early during a code freeze is like eating vegetables; you should do it!
