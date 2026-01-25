---
url: 'https://dri.es/how-to-prepare-for-drupal-9'
title: 'How to prepare for Drupal 9'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2019-04-11T16:00:58-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'Upgrading from Drupal 8 to Drupal 9 should be easy if you regularly check for and remove the use of deprecated code.'
tags:
  - Drupal
image: drupal/drupal-8-timeline-april-2019
published: true
id: 4816
---

# How to prepare for Drupal 9

With [Drupal 9 targeted to be released in June of 2020](https://dri.es/plan-for-drupal-9), many people are wondering what they need to do to prepare.

The good and important news is that [upgrading from Drupal 8 to Drupal 9 should be really easy](https://dri.es/making-drupal-upgrades-easy-forever) – radically easier than upgrading from Drupal 7 to Drupal 8.

The only caveat is that you need to manage "deprecated code" well.

If your site doesn't use deprecated code that is scheduled for removal in Drupal 9, your upgrade to Drupal 9 will be easy. In fact, it should be as easy as a minor version upgrade (like upgrading from Drupal 8.6 to Drupal 8.7).

### What is deprecated code?

Code in Drupal is marked as "deprecated" when it should no longer be used. Typically, code is deprecated because there is a better alternative that should be used instead.

For example, in Drupal 8.0.0, we deprecated `\Drupal::l($text, $url)`. Instead of using `\Drupal::l()`, you should use `Link::fromTextAndUrl($text, $url)`. The `\Drupal::l()` function was marked for removal as part of some clean-up work; Drupal 8 had too many ways to generate links.

Deprecated code will continue to work for some time before it gets removed. For example, `\Drupal::l()` continues to work in Drupal 8.7 despite the fact that it was deprecated in Drupal 8.0.0 more than three years ago. This gives module maintainers ample time to update their code.

When we release Drupal 9, we will "drop" most deprecated code. In our example, this means that `\Drupal::l()` will not be available anymore in Drupal 9.

In other words:

- Any Drupal 8 module that does not use deprecated code will continue to work with Drupal 9.
- Any Drupal 8 module that uses deprecated code needs to be updated before Drupal 9 is released, or it will stop working with Drupal 9.

If you're interested, you can read more about Drupal's deprecation policy at <https://www.drupal.org/core/deprecation>.

### How do I know if my site uses deprecated code?

There are a few ways to check if your site is using deprecated code.

If you work on a Drupal site as a developer, **run `drupal-check`**. [Matt Glaman](https://www.drupal.org/u/mglaman) ([Centarro](https://www.centarro.io/)) developed a static PHP analysis tool called [`drupal-check`](https://github.com/mglaman/drupal-check), which you can run against your codebase to check for deprecated code. I recommend running `drupal-check` in an automated fashion as part of your development workflow.

[video _m3uvGNb3O4]

If you are a site owner, **[install the Upgrade Status module](https://drupal.org/project/upgrade_status)**. This module was built by [Acquia](https://www.acquia.com). The module provides a graphical user interface on top of `drupal-check`. The goal is to provide an easy-to-use readiness assessment for your site's migration to Drupal 9.

[video 2GoKOB1OmAU]

If you maintain a project on Drupal.org, **enable Drupal.org's testing infrastructure to detect the use of deprecated code**. There are two complementary ways to do so: you can run a static deprecation analysis and/or configure your existing tests to fail when calling deprecated code. Both can be [set up in your `drupalci.yml` configuration file](https://www.drupal.org/drupalorg/docs/drupal-ci/customizing-drupalci-testing).

If you find deprecated code in a contributed module used on your site, consider filing an issue in the module's issue queue on Drupal.org (after having checked no issue has been created yet). If you can, provide a patch to fix the deprecation and engage with the maintainer to get it committed.

### How hard is it to update my code?

While there are some deprecations that require more detailed refactoring, many are a simple matter of search-and-replace.

You can [check the API documentation](https://api.drupal.org/) for instructions on how to remedy the deprecation.

### When can I start updating my code?

I encourage you to start today. When you update your Drupal 8 code to use the latest and greatest APIs, you can benefit from those improvements immediately. There is no reason to wait until Drupal 9 is released.

Drupal 8.8.0 will be the last release to deprecate for Drupal 9. Today, we don't know the full set of deprecations yet.

### How much time do I have to update my code?

The current plan is to [release Drupal 9 in June of 2020](https://dri.es/plan-for-drupal-9), and to [end-of-life Drupal 8 in November of 2021](https://dri.es/plan-for-drupal-9).

Contributed module maintainers are encouraged to remove the use of deprecated code by June of 2020 so everyone can upgrade to Drupal 9 the day it is released.

[image drupal/drupal-8-timeline-april-2019]

Drupal.org project maintainers should keep [the extended security coverage policy](https://dri.es/extended-security-coverage-for-drupal-8-minor-releases) in mind, which means that Drupal 8.8 will still be supported until Drupal 9.1 is released. Contributed projects looking to support both Drupal 8.8 and Drupal 9.0 might need to use two branches.

### How ready are the contributed modules?

[Dwayne McDaniel](https://www.drupal.org/u/mcdwayne) ([Pantheon](https://pantheon.io)) analyzed all 7,000 contributed module for Drupal 8 using `drupal-check`.

As it stands today, 44% of the modules have no deprecation warnings. The remaining 56% of the modules need to be updated, but the majority have less than three deprecation warnings.
