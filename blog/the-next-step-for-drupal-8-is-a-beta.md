---
url: 'https://dri.es/the-next-step-for-drupal-8-is-a-beta'
title: 'The next step for Drupal 8 is a beta'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2013-12-05T12:59:22-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
published: true
id: 3081
---

# The next step for Drupal 8 is a beta

Over the past two years, we've built [Drupal 8](https://www.drupal.org/8) into what will be the most flexible, future-proof Drupal version ever. Core developers have contributed thousands of hours of work to expanding Drupal 8's capabilities and modernizing our APIs.

We're several months into Drupal 8's [API completion phase](https://www.drupal.org/core/release-cycle#api-completion), and we're [releasing monthly alphas](https://groups.drupal.org/node/364138) as we nail down key APIs, refine the developer experience, and continue vital work on performance. To finish Drupal 8, we must focus on essentials, so I'd like to ask the Drupal developer community to look ahead to the next big step: the first Drupal 8 beta.

### When does alpha become beta?

Earlier in the year, we announced that Drupal 8's first beta would be released once we had a stable data upgrade path from Drupal 7. At DrupalCon Prague, however, the Drupal core developer team made a bold decision: instead of using Drupal's `update.php` database update script to convert Drupal 7 sites to Drupal 8 on the fly, Drupal 8 core will instead include a robust [data migration API](https://groups.drupal.org/imp) (based on the popular [migrate module](https://www.drupal.org/project/migrate)) to migrate data from existing sites into new Drupal 8 installations. This means that Drupal 8 core will provide reliable, extensible migration from *Drupal 6* as well as Drupal 7. We believe this to be important for organizations running older versions of Drupal can reliably modernize their sites.

#### Data migration no longer blocks a beta release

In order to make this important data migration change possible for Drupal 8, the initial Drupal 8.0 release will be primarily intended for building *new* Drupal sites, and the finished data migration path for *existing* Drupal 6 or 7 sites may be provided in a later Drupal 8 release, like Drupal 8.1. (For more information on how we might improve the Drupal release cycle after the release of Drupal 8, see the [proposal to manage the Drupal 8 release cycle](https://www.drupal.org/node/2135189).)

This means that a data upgrade path from Drupal 7 is no longer a prerequisite for releasing Drupal 8.0-beta1. Instead, we will focus on what testers and contributed module authors most need from a Drupal 8 beta: (1) a stable data model and (2) stable critical APIs.

#### Stable data model

A stable data model means that developers should not need to perform data migrations *between* beta releases of Drupal 8 (except where necessary to resolve critical issues). The Drupal 8 data model includes database schemas, file-based configuration storage, and storage services like the Entity and State systems.

#### Stable critical APIs

To provide contributed module developers with a useful milestone for module porting, beta 1 will include stable critical APIs. These are fundamental APIs that most or all contributed modules depend on, including the configuration system, the Entity and Field API, the Plugin API, and the Routing and Menu systems.

Other API changes approved by core maintainers will continue through the end of the API completion phase, but after the first beta, we will shift from away removing deprecated code and instead retain more backward compatibility layers. (Module/theme developers who wish to go through the porting process only once should wait for the first [release candidate](https://www.drupal.org/core/release-cycle#rc).)

### What issues are blocking beta1?

Drupal core maintainers determine which specific issues must be resolved to meet the criteria above. We have worked with core developers to identify a [list of beta-blocking issues](https://www.drupal.org/project/issues/search/drupal?version%5B%5D=8.x&issue_tags_op=%3D&issue_tags=beta+blocker). There are currently [48 of these "beta blockers" outstanding](https://www.drupal.org/project/issues/search/drupal?status%5B%5D=1&status%5B%5D=13&status%5B%5D=8&status%5B%5D=14&status%5B%5D=4&version%5B%5D=8.x&issue_tags_op=%3D&issue_tags=beta+blocker). As you can see, there are many difficult problems in this list that need to be solved. **We need your help to resolve these issues** so that we can release beta1 and expand Drupal 8's reach to new testers and contributors.

### It's focus time!

While the end of Drupal 8's development cycle is in sight, there's still a lot of work to do. Now more than ever it's essential to focus on the critical issues that will bring Drupal 8 closer to release. If we don't, we risk pushing Drupal 8's release off for many more months. The sooner we create a beta, the sooner we can release Drupal 8 to the world.

Many people looking forward to Drupal 8's release aren't sure how best to help out. I'd like to ask all [sub-system maintainers](https://cgit.drupalcode.org/project/drupal.git/blob_plain/refs/heads/8.x:/core/MAINTAINERS.txt) to watch their sub-system's issue queues closely to help new contributors triage issues and fix bugs, especially for [beta-blocking issues](https://www.drupal.org/project/issues/search/drupal?status%5B%5D=1&status%5B%5D=13&status%5B%5D=8&status%5B%5D=14&status%5B%5D=4&version%5B%5D=8.x&issue_tags_op=%3D&issue_tags=beta+blocker). I'd also like to ask everyone to review patches carefully, [make only necessary API changes](https://www.drupal.org/core/release-cycle/api-completion), and document APIs clearly. Or, if you aren't able to work on Drupal 8 issues directly, consider sponsoring core developers for Drupal 8 contribution.

Help us make Drupal 8 the best release of Drupal yet by working on our alpha releases and toward a Drupal 8 beta!
