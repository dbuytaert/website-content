---
title: 'Making Drupal upgrades easy forever'
date: '2017-03-08T07:54:31-05:00'
author: Dries
summary: 'We found a way to innovate fast yet provide a smooth learning curve and upgrade path from Drupal 8 to Drupal 9'
image: drupal/the-promise-of-making-drupal-upgrades-easy
tags:
  - Drupal
published: true
type: blog
url: /making-drupal-upgrades-easy-forever
id: 3886
---

[image drupal/the-promise-of-making-drupal-upgrades-easy resize=false]

One of the key reasons that Drupal has been successful is because we always made big, forward-looking changes. As a result, Drupal is one of very few CMSes that has stayed relevant for 15+ years. The downside is that with every major release of Drupal, we've gone through [a lot of pain adjusting to these changes](https://dri.es/the-pain-before-the-payoff). The learning curve and difficult upgrade path from one major version of Drupal to the next (e.g. from Drupal 7 to Drupal 8) has also held back Drupal's momentum. In an ideal world, we'd be able to innovate fast yet provide a smooth learning curve and upgrade path from Drupal 8 to Drupal 9. We believe we've found a way to do both!

### Upgrading from Drupal 8.2 to Drupal 8.3

Before we can talk about the upgrade path to Drupal 9, it's important to understand how we do releases in Drupal 8. With the release of Drupal 8, we [moved Drupal core to use a continuous innovation model](https://dri.es/the-transformation-of-drupal-8-for-continuous-innovation). Rather than having to wait for years to get new features, users now get sizable advances in functionality every six months. Furthermore, we committed to providing a smooth upgrade for modules, themes, and distributions from one six-month release to the next.

This new approach is starting to work really well. With the 8.1 and 8.2 updates behind us and 8.3 close to release, we have added some stable improvements like [BigPipe](https://dri.es/bigpipe-no-longer-just-for-the-top-50-websites) and a [new status report page](https://www.drupal.org/node/665790), as well as experimental improvements for [outside-in](https://dri.es/drupal-8-2-now-with-more-outside-in), [workflows](https://dri.es/moving-the-drupal-8-workflow-initiative-along), [layouts](https://www.drupal.org/node/2811175), and more. We also plan to add [important media improvements](https://dri.es/a-plan-for-media-management-in-drupal-8) in 8.4.

Most importantly, upgrading from 8.2 to 8.3 for these new features is not much more complicated than simply updating for a bugfix or security release.

### Upgrading from Drupal 8 to Drupal 9

After a lot of discussion among the Drupal core committers and developers, and studying projects like [Symfony](https://symfony.com), we believe that the advantages of Drupal's minor upgrade model (e.g. from Drupal 8.2 to Drupal 8.3) can be translated to major upgrades (e.g. from Drupal 8 to Drupal 9). We see a way to keep innovating while providing a smooth upgrade path and learning curve from Drupal 8 to Drupal 9.

Here is how we will accomplish this: we will continue to introduce new features and backwards-compatible changes in Drupal 8 releases. In the process, we sometimes have to [deprecate old systems](https://en.wikipedia.org/wiki/Deprecation). Instead of removing old systems, we will keep them in place and encourage module maintainers to update to the new systems. This means that modules and custom code will continue to work. The more we innovate, the more deprecated code there will be in Drupal 8. Over time, maintaining backwards compatibility will become increasingly complex. Eventually, we will reach a point where we simply have too much deprecated code in Drupal 8. At that point, we will choose to remove the deprecated systems and release that as Drupal 9.

This means that Drupal 9.0 should be almost identical to the last Drupal 8 release, minus the deprecated code. It means that when modules take advantage of the latest Drupal 8 APIs and avoid using deprecated code, they should work on Drupal 9. Updating from Drupal 8's latest version to Drupal 9.0.0 should be as easy as updating between minor versions of Drupal 8. It also means that Drupal 9 gives us a clean slate to start innovating more rapidly again.

Why would you upgrade to Drupal 9 then? For the great new features in 9.1. No more features will be added to Drupal 8 after Drupal 9.0. Instead, they will go into Drupal 9.1, 9.2, and so on.

To get the most out of this new approach, we need to make two more improvements. We need to change core so that the exact same module can work with Drupal 8 *and* 9 if the module developer uses the latest APIs. We also need to provide full data migration from Drupal 6, 7 and 8 to *any* future release. So long as we make these changes before Drupal 9 and contributed or custom modules take advantage of the latest Drupal 8 APIs, up-to-date sites and modules may just *begin using 9.0.0 the day it is is released*.

### What does this mean for Drupal 7 users?

If you are one of the more than a million sites successfully running on Drupal 7, you might only have one more big upgrade ahead of you.

If you are planning to migrate directly from Drupal 7 to Drupal 9, you should reconsider that approach. In this new model, it might be more beneficial to upgrade to Drupal 8. Once you've migrated your site to Drupal 8, subsequent upgrades will be much simpler.

We have more work to do to complete the [Drupal 7 to Drupal 8 data migration](https://www.drupal.org/docs/8/upgrade/upgrading-from-drupal-6-or-7-to-drupal-8), but the first Drupal 8 minor release that fully supports it could be 8.4.0, scheduled to be released in October 2017.

### What does this mean for Drupal developers?

If you are a module or theme developer, you can continually update to the latest APIs each minor release. Avoid using [deprecated code](https://www.drupal.org/core/deprecation) and your module will be compatible with Drupal 9 the day Drupal 9 is released. We have plans to make it easy for developers to [identify and update deprecated code](https://www.drupal.org/node/2488860).

### What does this mean for Drupal core contributors?

If you are a Drupal core contributor and want to introduce new improvements in Drupal core, Drupal 8 is the place to do it! With backwards compatibility layers, even pretty big changes are possible in Drupal 8.

### When will Drupal 9 will be released?

We don't know yet, but it shouldn't matter as much either. Innovative Drupal 8 releases will go out on schedule every six months and upgrading to Drupal 9 should become easy. I don't believe we will release Drupal 9 any time soon; we have plenty of features in the works for Drupal 8. Once we know more, we'll follow up with more details.

### Thank you

*Special thanks to [Alex Bronstein](https://www.drupal.org/u/effulgentsia), [Alex Pott](https://www.drupal.org/u/alexpott), [Gábor Hojtsy](https://www.drupal.org/u/g%C3%A1bor-hojtsy), [Nathaniel Catchpole](https://www.drupal.org/u/catch) and [Jess (xjm)](https://www.drupal.org/u/xjm) for their contributions to this post.*
