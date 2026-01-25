---
url: 'https://dri.es/drupal-7-code-freeze-almost-upon-us'
title: 'Drupal 7 code freeze almost upon us'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2009-09-02T18:21:49-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
published: true
id: 961
---

# Drupal 7 code freeze almost upon us

After some 82 weeks of development [ beginning in February 2008](https://dri.es/starting-to-work-on-drupal-7), no one should be caught by surprise that we are near a code freeze for a release of Drupal 7, the next and best release of Drupal yet. In fact, [the Drupal 7 code freeze was originally announced to be on September 1st](https://dri.es/drupal-7-code-freeze-september-1st).

However, as we all know, some of the best patches always happen at the last minute, and there are always last-minute patches that must happen. As part of my State of Drupal presentation at DrupalCon Paris today, I talked about the Drupal 7 code freeze. Since not all of us can be at Paris (and for those that aren't there, we miss you!), I wanted to share [the relevant slides](https://dri.es/files/drupal-7-code-freeze-plan.pdf%20) (PDF, 85 KB) in this blog post.

Important to know is that I extended the code freeze to Monday, September 7th. At this point all patches are still "acceptable". After the end of DrupalCon Paris, [Angela "webchick" Byron](https://dri.es/angela-webchick-byron) and I will review everything that is marked "ready to be committed" and commit all those patches that are really ready.

After this one week extension, we enter a phase we're calling "code slush", to be time-boxed at a strict five weeks. In this period, most patches are allowed, except those that implement new features or functionality – with some very important exceptions. Up to ten carefully selected exceptions for new functionality (see [slides for details](https://dri.es/files/drupal-7-code-freeze-plan.pdf%20)), patches that implement important and necessary API changes for existing functionality, and patches that improve usability, accessibility, documentation, and performance will still be accepted. As such, it is important that you start upgrading your contributed modules as soon as possible – you never know what API issues you might run into and we only have a limited window to address those. After October 15, we will become a lot more strict and focus on the final polish.

As always, Drupal 7 will be ready when it's ready, but not before. We expect – and hope – that [our huge investment in SimpleTest tests and our automated testing platform](https://dri.es/drupal-7-testing-status-update-and-next-steps), though, will make this the easiest transition from development to release yet. We'll see!

[image drupal/drupal-7-code-freeze-plan resize=false]
