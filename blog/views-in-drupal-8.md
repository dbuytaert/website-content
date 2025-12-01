---
title: 'Views in Drupal 8'
date: '2012-09-26T14:12:34-04:00'
author: Dries
tags:
  - Drupal
published: true
type: blog
url: /views-in-drupal-8
id: 2801
---

[Views](https://www.drupal.org/project/views) is the #1 most-used contributed module, installed on nearly 70% of all Drupal websites. The ability for non-developers to create listings for pages, blocks, calendars, photo galleries, and more through a web interface, complete with developer-friendly features such as caching, is one of the primary differentiating factors that makes Drupal shine.

While Views has excelled as a contributed module, bringing Views into Drupal core is now a clear strategic decision. Having Views in core will present many advantages:

- **Consistency**: Many disparate, legacy solutions are currently used for data listings in core modules. Converting these listings to Views will both improve the Drupal developer experience and make it easier for site builders to customize their sites.
- **Learnability**: First-time users of Drupal often don't realize what is possible with contributed modules. Having Views in core will mean that new site builders can more quickly understand Drupal's capabilities out-of-the-box.
- **Release cycle**: The stability of Views has in the past been an indicator of when the community considers a release of Drupal "ready". Drupal 7 usage did not start to increase until a development version of Views was available for D7, and it did not pass Drupal 6 usage until Views was stable.
- **Contributor experience**: Hundreds of contributed modules rely on the Views API, so these modules are blocked on Views for each release.
- **Stability**: If Views is in core, changes that cause Views regressions will be core release blockers, and Views bugs will be treated as core bugs.

A grassroots [Views in Drupal Core](http://www.angrydonuts.com/help-fund-views-in-core) initiative (VDC) was announced back in May. In the meantime, the team has been very busy with getting the necessary pre-requisites into place. These include various dependencies from the [CTools](https://www.drupal.org/project/ctools) project, as well as a Drupal 8 port of the Views module in contrib.

In this post, I'd like to make Views in Core an official initiative for Drupal 8, alongside initiatives such as [Configuration Management](https://dri.es/configuration-management-in-drupal-8), [Web Services](https://dri.es/web-services-in-drupal-8), and [Mobile](https://dri.es/mobile-for-drupal-8).

Unlike previous initiatives, Views in Core has an initiative team, rather than a single initiative lead. That team consists of:

- Earl Miles ([merlinofchaos](https://www.drupal.org/user/26979)) – Views creator, VDC chief architect
- Daniel Wehner ([dawehner](https://www.drupal.org/user/99340)) – Views maintainer, VDC technical lead
- Jess M. ([xjm](https://www.drupal.org/user/65776)) – top D8 core developer, VDC patch review &amp; QA, contribution facilitator
- Tim Plunkett ([tim.plunkett](https://www.drupal.org/user/241634)) – top D8 core developer and Views contributor, senior VDC developer
- Damian Lee ([damiankloip](https://www.drupal.org/user/1037976)) – top Views contributor, senior VDC developer

In addition to these people, over a dozen other developers have also contributed to the initiative with the team's coordination and guidance.

For more information about the Views in Core initiative, check out [Earl's report on VDC](http://www.angrydonuts.com/vdc-update-and-announcement). It provides a detailed roadmap on what needs to be done to get Views in Drupal 8, and information about how you can help.
