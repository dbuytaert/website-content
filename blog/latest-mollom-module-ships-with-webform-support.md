---
title: 'Latest Mollom module ships with Webform support'
date: '2010-04-05T02:49:26-04:00'
author: Dries
tags:
  - Drupal
  - Mollom
  - 'Drupal Gardens'
published: true
type: blog
url: /latest-mollom-module-ships-with-webform-support
id: 1566
---

We've just published the new 6.x-1.13 release for the [Mollom module for Drupal](https://www.drupal.org/project/mollom). Coming about a month and a half after [our last release](https://dri.es/new-features-for-drupal-mollom-module), this release tweaks, extends, and improves the module code, and makes some important bug fixes.

First, the blacklisting UI has been enhanced to make it a much cleaner and more intuitive user experience and to allow for more granular blacklisting. To do so, we had to extend the [underlying blacklist API](https://www.mollom.com/api/addBlacklistText) with a new `context` parameter.

Work on [Webform module](https://www.drupal.org/project/webform) integration also continued. To support users that have thousands of Webforms (apparently such users exist), we had to make some scalability improvements to the Mollom module's integration API. We're pleased to share that, thanks to these changes, [Mollom integration has been committed to the Webform module](https://www.drupal.org/cvs?commit=346466) and that Mollom support is part of the [6.x-3.0-beta4 release of Webform module](https://www.drupal.org/node/760868).

A number of important bug fixes are present in this release as well, including several that involve audio CAPTCHAs and the upgrade path not working correctly. Upgrading to the [new Mollom 6.x-1.13 release](https://www.drupal.org/node/762142) is highly recommended, especially if you experienced problems the last weeks. The Mollom module's unit tests have been improved and extended – we now have more than 1400 assertions for the Mollom module alone!

Last but not least, we released a first alpha release of the Mollom module for Drupal 7. All of our automated tests pass, so we believe the module is in really good shape. In addition, the Drupal 7 alpha module was installed on [Drupal Gardens sites](http://drupalgardens.com) so that should result in more real-life feedback too.

Thanks [Daniel Kudwien (sun)](http://www.unleashedmind.com/en/user/sun), [Nathan Haug (quicksketch)](https://www.drupal.org/user/35821), [Dave Reid](https://www.drupal.org/user/53892), and others from the Mollom issue queue for their contributions to this latest release.
