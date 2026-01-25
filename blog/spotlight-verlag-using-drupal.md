---
url: 'https://dri.es/spotlight-verlag-using-drupal'
title: 'Spotlight Verlag using Drupal'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2008-12-03T11:14:49-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
  - 'Drupal sites'
  - Publishing
published: true
id: 547
---

# Spotlight Verlag using Drupal

[Spotlight Verlag](https://www.spotlight-verlag.de/), a well-known German publisher, recently launched another Drupal site: <http://www.business-spotlight.de>.

Udo Gerhards, Project Manager Online at Spotlight Verlag, explained to me that the site is targeted at language learners and that they built a number of complex interactive language tests; see [here](https://www.business-spotlight.de/language-skills/business-skills/small-talk-%E2%80%94-but-job-talk) for a JavaScript based drag and drop test, and see [here](https://www.business-spotlight.de/language-skills/business-skills/chairing-a-meeting) for a regular multi-page HTML form test. Development of the site was done mainly by their in-house development team, with some help from [Auvica](http://www.auvica.com).

When asked, Udo told me that CCK, Views and Panels were the main reasons for using Drupal. Their biggest pain point was in staging their development environment to reliably push big changes to their production environment.

They use a multi-site install with a single master user database (every login in the different Drupal instances is checked against one central user database, so users share the same login data for different websites in their network). This master database is also connected to their magazine subscriber database. The multi-site setup makes it easier for them to roll out and maintain the additional Drupal sites that they have in the pipeline.

[image drupal/business-spotlight]
