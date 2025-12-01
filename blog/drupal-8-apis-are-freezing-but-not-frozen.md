---
title: 'Drupal 8 APIs are freezing but not frozen'
date: '2013-08-28T11:02:55-04:00'
author: Dries
tags:
  - Drupal
published: true
type: blog
url: /drupal-8-apis-are-freezing-but-not-frozen
id: 3011
---

Since Drupal 8's [API freeze was announced](https://dri.es/drupal-8-api-freeze) on July 1, there has been some confusion about what API freeze means, from core developers as well as module and theme developers starting Drupal 8 upgrades of their projects. This post clarifies the API completion process, and documents what different audiences can expect from Drupal 8's development cycle and when.

### API freezing is a process, not a point in time

As noted in the original API freeze announcement, as well as [the Drupal core release cycle page](https://www.drupal.org/core/release-cycle), API freeze marks the point at which API changes are only allowed when needed to fix a major or critical issue. The process of completing the necessary remaining changes, however, will take time, and while that is happening, [many important APIs are still changing](https://groups.drupal.org/node/313408).

The chart below illustrates the API freezing process, as well as what various groups of people affected by Drupal 8 development can expect during the rest of the release cycle:

[image drupal/drupal-8-api-freezing]

For core developers, July 1 marked the point at which core maintainers began to postpone API changes not necessary for solving critical and major issues to Drupal 9, so that module and theme developers who've already started porting their projects only need to keep up with changes that are sufficiently important to a healthy Drupal 8 release. We've labeled this part of the release cycle the "API completion" to clarify this process. During this phase, any proposed API changes must go through [a process involving core committer approval](https://www.drupal.org/core/release-cycle/api-freeze). Core committers will increasingly restrict what sorts of changes are allowed as time goes on.

### I'd like to start porting my module or theme now. What can I expect?

Module and theme developers are encouraged to *start* porting now so they can uncover critical and major API problems while they can still be fixed. But if you are hoping to go through the process of porting your module or theme only once, the best time for that is after the first *release candidate* (see "What can I expect for beta?" below). At that point, the number of critical issues should be at or just above zero, meaning API changes should be extremely rare and only occur if there's no other way to resolve a severe problem.

You can read a summary of the [most important outstanding API changes](https://groups.drupal.org/node/313408), or view the ongoing list of [approved API change issues](https://www.drupal.org/project/issues/search/drupal?status%5B%5D=Open&version%5B%5D=8.x&issue_tags=Approved+API+change) to see if your module is affected by changes that are still in progress. The list currently includes many issues related to the routing system, the entity field API, and the theme system/markup. If your project touches these systems, you may want to hold off porting a while longer, or at least be aware that these elements (as well as others) are still in flux and might change significantly before Drupal 8 is released.

### What can I expect from beta releases?

Beta 1 will still be the point at which we encourage any interested site builders to try out the beta and provide feedback on it, so it will include an upgrade path from Drupal 7 for testing. It's a great time for site builders to set up test sites in order to take Drupal 8 for a spin and provide feedback while things are still somewhat malleable. Just know that because Drupal 8 is still in development, critical upgrade path issues *may* arise that cause data loss, so make sure you're backed up!

Previously, we also identified beta as the point at which we'd have a stable API against which module and theme developers could port code. However, after evaluating the list of major and critical API changes still outstanding, we realize that those changes will take more time to complete than we would like to wait to release our first beta. Therefore, we now recommend that developers who are not interested in providing early API feedback on Drupal 8 wait until the first release candidate.

### Closing thoughts

Release management is difficult, especially in a large distributed Open Source community like Drupal. Getting Drupal 8 released involves many people, many processes, and even technology challenges. The quality of the Drupal 8 release is really important so as a result, there are no hard-and-fast rules and we'll continue to adjust in the best interest of the Drupal project. I hope this update proves that point, and that it clarifies how and when we would like you to get involved. Let's make Drupal 8 our best release to date - in a timely manner!
