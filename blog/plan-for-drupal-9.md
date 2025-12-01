---
title: 'Plan for Drupal 9'
date: '2018-12-12T08:13:26-05:00'
author: Dries
image: drupal/drupal-9-targeting-june-2020
tags:
  - Drupal
published: true
type: blog
url: /plan-for-drupal-9
id: 4666
---

At [Drupal Europe](https://www.drupaleurope.org/), I announced that Drupal 9 will be released in 2020. Although I explained [why we plan to release in 2020](https://dri.es/drupal-7-8-and-9), I wasn't very specific about when we plan to release Drupal 9 in 2020. Given that 2020 is less than thirteen months away (gasp!), it's time to be more specific.

### Shifting Drupal's six month release cycle

[image drupal/drupal-8-shifted-release-windows]

Before I talk about the Drupal 9 release date, I want to explain another change we made, which has a minor impact on the Drupal 9 release date.

As announced over two years ago, [Drupal 8 adopted a 6-month release cycle](https://dri.es/the-transformation-of-drupal-8-for-continuous-innovation) (two releases a year). [Symfony](https://symfony.com/), a PHP framework which Drupal depends on, uses a similar release schedule. Unfortunately the timing of Drupal's releases has historically occurred 1-2 months before Symfony's releases, which forces us to wait six months to adopt the latest Symfony release. To be able to adopt the latest Symfony releases faster, we are moving Drupal's minor releases to June and December. This will allow us to adopt the latest Symfony releases within one month. For example, Drupal 8.8.0 is now scheduled for December 2019.

### We hope to release Drupal 9 on June 3, 2020

Drupal 8's biggest dependency is Symfony 3, which has an end-of-life date in November 2021. This means that after November 2021, security bugs in Symfony 3 will not get fixed. Therefore, we have to end-of-life Drupal 8 no later than November 2021. Or put differently, by November 2021, *everyone* should be on Drupal 9.

Working backwards from November 2021, we'd like to give site owners at least one year to upgrade from Drupal 8 to Drupal 9. While we could release Drupal 9 in December 2020, we decided it was better to [try to release Drupal 9 on June 3, 2020](https://www.drupal.org/project/drupal/issues/3007300). This gives site owners 18 months to upgrade. Plus, it also gives the Drupal core contributors an extra buffer in case we can't finish Drupal 9 in time for a summer release.

[image drupal/drupal-9-targeting-june-2020]

### We are building Drupal 9 in Drupal 8

Instead of working on Drupal 9 in a separate codebase, we are building Drupal 9 in Drupal 8. This means that we are adding new functionality as backwards-compatible code and experimental features. Once the code becomes stable, we deprecate any old functionality.

Let's look at an example. As mentioned, Drupal 8 currently depends on Symfony 3. Our plan is to release Drupal 9 with Symfony 4 or 5. Symfony 5's release is less than one year away, while Symfony 4 was released a year ago. Ideally Drupal 9 would ship with Symfony 5, both for the latest Symfony improvements and for longer support. However, Symfony 5 hasn't been released yet, so we don't know the scope of its changes, and we will have limited time to try to adopt it before Symfony 3's end-of-life.

We are currently working on [making it possible to run Drupal 8 with Symfony 4](https://www.drupal.org/project/drupal/issues/2937984) (without requiring it). Supporting Symfony 4 is a valuable stepping stone to Symfony 5 as it brings new capabilities for sites that choose to use it, and it eases the amount of Symfony 5 upgrade work to do for Drupal core developers. In the end, our goal is for Drupal 8 to work with Symfony 3, 4 or 5 so we can identify and fix any issues before we start *requiring* Symfony 4 or 5 in Drupal 9.

Another example is our support for reusable media. Drupal 8.0.0 launched without a media library. We are currently working on [adding a media library to Drupal 8](https://dri.es/an-update-on-the-media-initiative-for-drupal-8-4-8-5) so content authors can select pre-existing media from a library and easily embed them in their posts. Once the media library becomes stable, we can deprecate the use of the old file upload functionality and make the new media library the default experience.

### The upgrade to Drupal 9 will be easy

Because we are building Drupal 9 in Drupal 8, the technology in Drupal 9 will have been battle-tested in Drupal 8.

For **Drupal core contributors**, this means that we have a limited set of tasks to do in Drupal 9 itself before we can release it. Releasing Drupal 9 will only depend on removing deprecated functionality and upgrading Drupal's dependencies, such as Symfony. This will make the release timing more predictable and the release quality more robust.

For **contributed module authors**, it means they already have the new technology at their service, so they can work on Drupal 9 compatibility earlier (e.g. they can start updating their media modules to use the new media library before Drupal 9 is released). Finally, their Drupal 8 know-how will remain highly relevant in Drupal 9, as there will not be a dramatic change in how Drupal is built.

But most importantly, for **Drupal site owners**, this means that it should be much easier to upgrade to Drupal 9 than it was to upgrade to Drupal 8. Drupal 9 will simply be the last version of Drupal 8, with its deprecations removed. This means we will not introduce new, backwards-compatibility breaking APIs or features in Drupal 9 except for our dependency updates. As long as modules and themes stay up-to-date with the latest Drupal 8 APIs, the upgrade to Drupal 9 should be easy. Therefore, we believe that a 12- to 18-month upgrade period should suffice.

### So what is the big deal about Drupal 9, then?

The big deal about Drupal 9 is ... that it should not be a big deal. The best way to be ready for Drupal 9 is to keep up with Drupal 8 updates. Make sure you are not using deprecated modules and APIs, and where possible, use the latest versions of dependencies. If you do that, your upgrade experience will be smooth, and that is a big deal for us.

*Special thanks to [Gábor Hojtsy](https://www.drupal.org/u/g%C3%A1bor-hojtsy) (Acquia), [Angie Byron](https://www.drupal.org/u/webchick) (Acquia), [xjm](https://www.drupal.org/u/xjm) (Acquia), and [catch](https://www.drupal.org/u/catch) for their input in this blog post.*
