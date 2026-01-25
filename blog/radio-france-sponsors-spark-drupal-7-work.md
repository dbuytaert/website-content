---
url: 'https://dri.es/radio-france-sponsors-spark-drupal-7-work'
title: 'Radio France sponsors Spark Drupal 7 work'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2013-01-29T13:13:59-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
  - Acquia
  - 'Spark distribution'
published: true
id: 2876
---

# Radio France sponsors Spark Drupal 7 work

When we first announced the [Spark authoring experience initiative for Drupal](https://dri.es/announcing-spark-authoring-improvements-for-drupal-7-and-drupal-8) in May of last year, we chose Drupal 7 as our target in order to develop the features and get them in front of testers as quickly as possible. After DrupalCon Munich in August, the team shifted efforts towards Drupal 8 core instead, in order to more directly improve the experience of Drupal itself. Since then, we have successfully worked with the community to drive home [a redesigned and mobile-friendly toolbar](https://www.drupal.org/node/1137920), [support for draft revisions](https://www.drupal.org/node/218755), [in-place editing](https://www.drupal.org/node/1824500), numerous mobile improvements, and have [WYSIWYG](https://www.drupal.org/node/1890502) and [unified in-place editing](https://www.drupal.org/node/1882482) on the way.

This has kept the team pretty busy, however, and so the Drupal 7 version of Spark has not been receiving many updates in the meantime. [Olivier Friesse (noisetteprod)](https://www.drupal.org/user/144997) of [Radio France](https://www.drupal.org/node/1604758) graciously offered to sponsor work to help things along. Thanks to this sponsorship, we were able to have [Théodore Biadala (nod\_)](https://www.drupal.org/user/598310) of Acquia's Professional Services team spend 3 weeks on [getting the in-place editing feature production-ready for Drupal 7](https://www.drupal.org/node/1879820), including:

- Full backport of Drupal 8 code, including Create.js/VIE.js integration
- Integration with CKEditor module to provide WYSIWYG support for rich text areas, which resulted in numerous upstream improvements
- Removed requirement on jQuery 1.7 so that Edit module can work on stock Drupal 7 installations without jquery\_update module
- Removed requirement on PHP 5.3 so Edit module can also work in PHP 5.2 environments
- Basic support for Views/Panels in-place editing
- Numerous bug fixes to help further stabilize the code base

Working towards a stable release for Drupal 7 naturally identified bugs with the Drupal 8 implementation of inline editing, which are being tracked in this issue: https://www.drupal.org/node/1894454.

In short, the needs of Radio France have brought tremendous value for the entire community, in both Drupal 7 and Drupal 8. If you'd like to try out the work that we've done, download the [7.x-1.0-alpha7 release of Spark](https://www.drupal.org/node/1901600) or [Edit 7.x-1.0-alpha6](https://www.drupal.org/node/1901356)!

Thanks once again, Olivier and Radio France, for your support! If other companies would like to sponsor further work on Spark, please [let me know](https://dri.es/contact).
