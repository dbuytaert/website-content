---
title: 'Drupal 7, 8 and 9'
date: '2018-09-12T00:07:15-04:00'
author: Dries
summary: 'Drupal 7 will be end-of-life in November 2021, Drupal 9 will be released in 2020, and Drupal 8 will be end-of-life in November 2021.'
image: drupal/drupal-7-will-be-supported-until-november-2021
tags:
  - Drupal
published: true
type: blog
url: /drupal-7-8-and-9
id: 4511
---

We [just released Drupal 8.6.0](https://dri.es/drupal-8-6-0-released). With six minor releases behind us, it is time to talk about the long-term future of Drupal 8 (and therefore Drupal 7 and Drupal 9). I've written about [when to release Drupal 9](https://dri.es/when-should-we-release-drupal-9) in the past, but this time, I'm ready to provide further details.

The plan outlined in this blog has been discussed with the Drupal 7 Core Committers, the Drupal 8 Core Committers and the Drupal Security Team. While we feel good about this plan, we can't plan for every eventuality and we may continue to make adjustments.

### Drupal 8 will be end-of-life by November 2021

Drupal 8's innovation model depends on [introducing new functionality in minor versions while maintaining backwards compatibility](https://dri.es/the-transformation-of-drupal-8-for-continuous-innovation). This approach is working so well that some people have suggested we institute minor releases forever, and never release Drupal 9 at all.

However that approach is not feasible. We need to periodically remove deprecated functionality to keep Drupal modern, maintainable, and performant, and we need to stay on secure, supported versions of Drupal 8's third-party dependencies. As Nathaniel Catchpole explained in his post ["The Long Road to Drupal 9"](https://www.thirdandgrove.com/long-road-drupal-9), our use of various third party libraries such as Symfony, Twig, and Guzzle means that we need to be in sync with their release timelines.

Our biggest dependency in Drupal 8 is Symfony 3, and according to [Symfony's roadmap](https://symfony.com/roadmap), Symfony 3 has an end-of-life date in November 2021. This means that after November 2021, security bugs in Symfony 3 will not get fixed. To keep your Drupal sites secure, Drupal must adopt Symfony 4 or Symfony 5 before Symfony 3 goes end-of-life. A major Symfony upgrade will require us to release Drupal 9 (we don't want to fork Symfony 3 and have to backport Symfony 4 or Symfony 5 bug fixes). This means we have to end-of-life Drupal 8 no later than November 2021.

[image drupal/drupal-8-will-be-end-of-life-by-november-2021 resize=false]

### Drupal 9 will be released in 2020, and it will be an easy upgrade

If Drupal 8 will be end-of-life on November 2021, we have to release Drupal 9 before that. Working backwards from November 2021, we'd like to give site owners one year to upgrade from Drupal 8 to Drupal 9.

If November 2020 is the latest we could release Drupal 9, what is the earliest we could release Drupal 9?

We certainly can't release Drupal 9 next week or even next month. Preparing for Drupal 9 takes a lot of work: we need to [adopt Symfony 4 and/or Symfony 5](https://www.drupal.org/project/drupal/issues/2976394), we need to remove deprecated code, we need to allow modules and themes to declare compatibility with more than one major version, and possibly more. The Drupal 8 Core Committers believe we need more than one year to [prepare for Drupal 9](https://www.drupal.org/project/drupal/issues/2608496).

Therefore, our current plan is to release Drupal 9 in 2020. Because we still need to figure out important details, we can't be more specific at this time.

[image drupal/drupal-9-will-be-released-in-2020 resize=false]

If we release Drupal 9 in 2020, it means we'll certainly have Drupal 8.7 and 8.8 releases.

#### Wait, I will only have one year to migrate from Drupal 8 to 9?

Yes, but fortunately [moving from Drupal 8 to 9 will be far easier than previous major version upgrades](https://dri.es/making-drupal-upgrades-easy-forever). The first release of Drupal 9 will be very similar to the last minor release of Drupal 8, as the primary goal of the Drupal 9.0.0 release will be to remove deprecated code and update third-party dependencies. By keeping your Drupal 8 sites up to date, you should be well prepared for Drupal 9.

And what about contributed modules? The compatibility of contributed modules is historically one of the biggest blockers to upgrading, so we will also make it possible for contributed modules to be compatible with Drupal 8 and Drupal 9 at the same time. As long as contributed modules do not use [deprecated APIs](https://www.drupal.org/core/deprecation), they should work with Drupal 9 while still being compatible with Drupal 8.

### Drupal 7 will be supported until November 2021

Historically, our policy has been to only support two major versions of Drupal; Drupal 7 would ordinarily reach end of life when Drupal 9 is released. Because a large number of sites might still be using Drupal 7 by 2020, we have decided to extend support of Drupal 7 until November 2021. Drupal 7 will receive community support for three whole more years.

[image drupal/drupal-7-will-be-supported-until-november-2021 resize=false]

#### We'll launch a Drupal 7 commercial Long Term Support program

In the past, commercial vendors have extended Drupal's security support. In 2015, a [Drupal 6 commercial Long Term Support program was launched](https://www.drupal.org/project/d6lts) and continues to run to this day. We plan a similar paid program for Drupal 7 to extend support beyond November 2021. The Drupal Security Team will announce the Drupal 7 commercial LTS program information by mid-2019. Just like with the [Drupal 6 LTS](https://www.drupal.org/drupal-security-team/drupal-6-long-term-support) program, there will be an application for vendors.

#### We'll update Drupal 7 to support newer versions of PHP

The PHP team will stop supporting PHP 5.x on December 31st, 2018 (in 3 months), PHP 7.0 on December 3rd, 2018 (in 2 months), PHP 7.1 on December 1st, 2019 (in 1 year and 3 months) and PHP 7.2 on November 30th, 2020 (in 2 years and 2 months).

Drupal will drop official support for [unsupported PHP versions](https://php.net/supported-versions.php) along the way and Drupal 7 site owners may have to upgrade their PHP version. The details will be provided later.

We plan on updating Drupal 7 to support newer versions of PHP in line with their support schedule. Drupal 7 doesn't fully support PHP 7.2 yet as there have been [some backwards-incompatible changes since PHP 7.1](http://www.php.net/manual/en/migration72.incompatible.php). We will release [a version of Drupal 7 that supports PHP 7.2](https://www.drupal.org/project/drupal/issues/2947772). Contributed modules and custom modules will have to be updated too, if not already.

### Conclusion

If you are still using Drupal 7 and are wondering what to do, you currently have two options:

1. Stay on Drupal 7 while also updating your PHP version. If you stay on Drupal 7 until after 2021, you can either engage a vendor for a long term support contract, or migrate to Drupal 9.
2. Migrate to Drupal 8 by 2020, so that it's easier to update to Drupal 9 when it is released.

The announcements in this blog post made option (1) a lot more viable and/or hopefully helps you better evaluate option (2).

If you are on Drupal 8, you just have to keep your Drupal 8 site up-to-date and you'll be ready for Drupal 9.

**December 2018 update:** In a more recent blog post, I shared that [we target to release Drupal 9 on June 3rd, 2020](https://dri.es/plan-for-drupal-9).

*Thanks for the Drupal 7 Core Committers, the Drupal 8 Core Committers and the Drupal Security Team for their contributions to this blog post.*
