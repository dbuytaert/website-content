---
url: 'https://dri.es/when-should-we-release-drupal-9'
title: 'When should we release Drupal 9?'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2018-05-25T06:28:46-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'Thoughts about Drupal 9 release timelines, including how this might impact Drupal 7, Drupal 8 and even Drupal 10.'
tags:
  - Drupal
published: true
id: 4376
---

# When should we release Drupal 9?

Since the release of Drupal 8.0.0 in November 2015, the Drupal 8 core committers have been discussing when and how we'll release Drupal 9. [Nat Catchpole](https://www.drupal.org/u/catch), one of Drupal 8's core committers, shared [some excellent thoughts](https://www.thirdandgrove.com/long-road-drupal-9) about what goes into making that decision.

The driving factor in that discussion is security support for Drupal 8's third party dependencies (e.g. Symfony, Twig, Guzzle, jQuery, etc). Our top priority is to ensure that all Drupal users are using supported versions of these components so that all Drupal sites remain secure.

In his blog, Nat uses Symfony as an example. The Symfony project announced that it will stop supporting Symfony 3 in November 2021, which means that Symfony 3 won't receive security updates after that date. Consequently, by November 2021, we need to prepare all Drupal sites to use Symfony 4 or later.

Nothing has been decided yet, but the current thinking is that we have to move Drupal to Symfony 4 or later, release that as Drupal 9, and allow enough time for everyone to upgrade to Drupal 9 by November 2021. Keep in mind that this is just looking at Symfony, and none of the other components.

This proposal builds on top of work we've already done to [make Drupal upgrades easy](https://dri.es/making-drupal-upgrades-easy-forever), so upgrades from Drupal 8 to Drupal 9 should be smooth and much simpler than previous upgrades.

If you're interested in the topic, [check out Nat's post](https://www.thirdandgrove.com/long-road-drupal-9). He goes in more detail about potential release timelines, including how this impacts our thinking about Drupal 7, Drupal 8 and even Drupal 10. It's a complicated topic, but the goal of Nat's post is to raise awareness and to solicit input from the broader community before [we decide our official timeline and release dates on Drupal.org](https://www.drupal.org/project/drupal/issues/2608496).
