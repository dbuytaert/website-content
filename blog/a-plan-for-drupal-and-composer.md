---
url: 'https://dri.es/a-plan-for-drupal-and-composer'
title: 'A plan for Drupal and Composer'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2018-06-15T10:08:45-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'A plan how we can make Composer easier to use with Drupal'
tags:
  - Drupal
image: drupal/drupal-composer-initiative
published: true
id: 4416
---

# A plan for Drupal and Composer

[image drupal/drupal-composer-initiative]

At DrupalCon Nashville, we launched a strategic initiative to improve support for [Composer](https://getcomposer.org/) in Drupal 8. To learn more, you can [watch the recording of my DrupalCon Nashville keynote](https://dri.es/state-of-drupal-presentation-april-2018) or read the [Composer Initiative issue on Drupal.org](https://www.drupal.org/project/ideas/issues/2958021).

While Composer isn't required when using Drupal core, many Drupal site builders use it as the preferred way of assembling websites (myself included). A growing number of contributed modules also require the use of Composer, which increases the need to make Composer easier to use with Drupal.

The first step of the Composer Initiative was to develop a plan to simplify Drupal's Composer experience. Since DrupalCon Nashville, [Mixologic](https://www.drupal.org/u/mixologic), [Mile23](https://www.drupal.org/u/mile23), [Bojanz](https://www.drupal.org/u/bojanz), [Webflo](https://www.drupal.org/u/webflo), and other Drupal community members have worked on this plan. I was excited to see that last week, [they shared their proposal](https://www.drupal.org/project/ideas/issues/2958021).

The first phase of the proposal is focused on a series of changes in the main Drupal core repository. The directory structure will remain the same, but it will include scripts, plugins, and embedded packages that enable the bundled Drupal product to be built from the core repository using Composer. This provides users who download Drupal from [Drupal.org](https://www.drupal.org) a clear path to [manage their Drupal codebase with Composer](https://github.com/drupal-composer/drupal-project) if they choose.

I'm excited about this first step because it will establish a default, official approach for using Composer with Drupal. That makes using Composer more straightforward, less confusing, and could theoretically lower the bar for evaluators and newcomers who are familiar with other PHP frameworks. Making things easier for site builders is a very important goal; web development has become a difficult task, and removing complexity out of the process is crucial.

It's also worth noting that we are planning the [Automatic Updates Initiative](https://www.drupal.org/project/ideas/issues/2940731). We are exploring if an automated update system can be build on top of the Composer Initiative's work, and provide an abstraction layer for those that don't want to use Composer directly. I believe that could be truly game-changing for Drupal, as it would remove a great deal of complexity.

If you're interested in learning more about the Composer plan, or if you want to provide feedback on the proposal, I recommend you check out the [Composer Initiative issue](https://www.drupal.org/project/ideas/issues/2958021) and [comment 37 on that issue](https://www.drupal.org/project/ideas/issues/2958021#comment-12644688).

Implementing this plan will be a lot of work. How fast we execute these changes depends on how many people will help. There are a number of different [third-party Composer related efforts](https://www.drupal.org/docs/develop/using-composer/using-composer-to-manage-drupal-site-dependencies), and my hope is to see many of them redirect their efforts to make Drupal's out-of-the-box Composer effort better. If you're interested in getting involved or sponsoring this work, let me know and I'd be happy to connect you with the right people!
