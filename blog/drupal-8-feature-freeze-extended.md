---
title: 'Drupal 8 feature freeze extended'
date: '2012-11-27T22:18:25-05:00'
author: Dries
tags:
  - Drupal
published: true
type: blog
url: /drupal-8-feature-freeze-extended
id: 2821
---

*Note: some of the information on this page is out of date. For the latest information about how Drupal releases are managed, see <https://www.drupal.org/core/release-cycle>.*

Since [Drupal 8 opened for development](https://dri.es/starting-to-work-on-drupal-8) in March of 2011, the Drupal core team has been hard at work, marching towards a [feature freeze](https://dri.es/updated-drupal-8-release-schedule) of December 1, 2012, just a few short days away!

In that time, we've managed to commit a number of compelling features to Drupal 8: revamped core internals based on the Symfony framework, a new configuration management system, HTML5 form elements and responsive markup, a mobile-friendly administrative toolbar, built-in support for translation, a Twig-based templating system, the Views module, and countless under-the-hood improvements.

The momentum within the Drupal core queue right now is truly staggering, as embodied by this graph:

[image drupal/drupal-8-core-monthly-patch-volume resize=false]

There are still incredible features for Drupal 8 that are heavily in progress, but not quite there yet, including blocks and layouts, WYSIWYG and inline editing, several more "contributed module to core" projects such as Date, Pathauto, Profile2, and Entity Reference, native web services support, improvements to the entity and field systems, and much. I'm truly impressed by all of the great efforts I see happening in the queue right now.

Given these factors, I have decided – along with my Drupal 8 co-maintainers Nathaniel Catchpole and Angela Byron – to introduce a new phase into the Drupal core development cycle: "Feature Completion Phase", from December 1, 2012 until February 18, 2013 (to hit [DrupalCon Sydney](https://sydney2013.drupal.org/)).

The purpose of this phase will be to provide dedicated time to tie up loose ends on any features that have either been committed already, or features still in the queue that have demonstrated **substantial progress** before December 1, but are not quite "there" yet. While hard-and-fast rules around "substantial progress" are difficult to define, generally it means patches should be *well* underway, with a recent patch posted in the past two weeks, ideally with several community reviews, tests passing or nearly passing, and a clear path to getting the feature completed within the timeframe of Feature Completion Phase. Almost-working patches posted for the first time at 11:59pm on November 30 unfortunately won't cut it. :-) Neither will brand new initiatives starting on December 2 or later. Though ultimately, it will be up to the core committers to decide on any "borderline" issues. We also understand that there is some ambiguity around what constitutes a "feature" or not, and will work on a separate blog post to discuss that.

The hope is that this new release phase will both give the folks working so hard on various major strategic initiatives a bit more time in which to complete their work, and also help narrow the scope of overall development efforts in order to help us focus more as a team as we begin preparing for Drupal 8's release.

Here is a diagram showing an overview of the overall Drupal core release cycle, and where Feature Completion Phase fits in. Initiative owners and others who have already achieved their Drupal 8 feature goals are encouraged to use Feature Completion Phase to get started on their Clean-Up Phase tasks early.

[image drupal/release-funnel resize=false]

Of course, it's not possible to provide more time to complete Drupal 8 features without also impacting the remainder of the release timeline. Therefore, Code Freeze will be moved out 3 months as well to July 1, 2013. Drupal 8 will be released when there are no release-critical issues remaining.

I want to thank each and every one of Drupal 8's 960+ contributors for all of your astounding efforts so far. Keep up the great work!
