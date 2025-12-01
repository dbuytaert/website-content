---
title: 'Drupal 7 status update and release plan'
date: '2010-02-25T06:16:22-05:00'
author: Dries
tags:
  - Drupal
published: true
type: blog
url: /drupal-7-status-update-and-release-plan
id: 1501
---

Drupal 7 is moving along nicely, and is becoming increasingly stable. We just released [a second alpha release](https://www.drupal.org/drupal-7.0-alpha2), fixing a number of critical bugs, following our initial alpha release in January. Alpha releases are to give Drupalistas something to download and test, so they can report and help fix bugs.

When will we switch to betas? We will switch to betas when [the upgrade path from Drupal 6 to Drupal 7 is working](https://www.drupal.org/project/issues/search/drupal?status%5B%5D=Open&issue_tags=D7+upgrade+path). Once we hit beta, we will become increasingly strict about accepting any more changes and we'll also commit to making HEAD to HEAD upgrades work.

Finally, we'll start rolling release candidates once the [number of critical bugs](https://www.drupal.org/project/issues/search/drupal?version%5B0%5D=156281&status%5B0%5D=1&status%5B1%5D=8&status%5B2%5D=13&status%5B3%5D=14&priorities%5B0%5D=1&categories%5B0%5D=bug&categories%5B1%5D=task) is zero (or close to zero). To help us focus on critical bugs, we're working on [adding a 'major' severity level](https://www.drupal.org/node/175555) to our ticketing system, making the options 'critical', 'major', 'normal' and 'minor'. 'Major' bugs would be really bad, but not necessarily block a release. For example, bugs that don't prevent Drupal from working, or that only affect a fraction of the Drupal population would be prioritized for fixing in follow-up releases. Critical bugs are those that badly break Drupal, or that are a major regression compared to Drupal 6.

Where are we right now? There are currently about 150 remaining bugs that need to be fixed. These bugs are real, and not always trivial to fix because a lot of background and domain expertise can be required. As a result, some bug reports seemingly depend on one or two people to fix them. Therefore, it is very important that we encourage and mentor new people to help fix some of these difficult bugs. I'd like to ask all sub-system maintainers to watch their sub-system's issue queues closely (like [Moshe did recently](http://cyrve.com/criticals)), and to provide the leadership to help us make progress. If we do and we work hard, I think we can still release Drupal 7 in Q2. If not, I'm worried that Drupal 7 might not be released until Q3.

In other words, let's all try to put some extra time and effort into fixing the remaining bugs, and let's start to be laser-focused on the critical ones. It would make for quite a party if we could roll a first release candidate in time for [DrupalCon San Francisco on April 19th](https://sf2010.drupal.org/). I would have to sing on stage from happiness, or something. *Thanks!*
