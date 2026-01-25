---
url: 'https://dri.es/streamlining-drupal-core-decision-making'
title: 'Streamlining Drupal core decision-making'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2012-03-27T13:52:51-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
published: true
id: 2666
---

# Streamlining Drupal core decision-making

We've already made a [number](https://dri.es/jennifer-hodgdon) [of](https://dri.es/drupal-8-feature-freeze-december-1st-2012) [process](https://dri.es/issue-queue-thresholds-for-drupal-core) [improvements](https://dri.es/fast-tracking-drupal-7-bug-fixes) to help accelerate Drupal core's development velocity. Today, I'd like to talk about how we can better streamline the Drupal core decision-making process.

The Drupal core queue is filled with extremely passionate, intelligent and determined individuals who always strive to solve problems in the best possible way. However, we do sometimes come to disagreements about the best way to approach a particular solution, and when two or more individuals fundamentally disagree, issues can sometimes turn into stalemates; or worse, turn ugly. When this happens, it saps strength from the core development team, and makes it difficult (and scary) for new contributors to engage.

Going forward, I'd like to propose the following workflow change to help un-stick issues where opinions seem deadlocked:

1. Create a balanced [issue summary](https://www.drupal.org/node/1155816) at the top of the issue that reflects the current state and history of the discussion, and outlines the pros and cons of various options.
2. Move the "Assigned to" field to "Dries". (Note that access to do this is restricted to those contributors listed in [MAINTAINERS.txt](https://git.drupalcode.org/project/drupal.git/blob/refs/heads/8.x:/core/MAINTAINERS.txt); you can either ask one of them to do so on your behalf.)
3. Once per week (barring travel or other things that might come up), I will go through this list and either make a decision myself, or delegate the decision to another contributor, along with a date for a decision to be made. If there is still not agreement by that date, the person delegated the responsibility will make what they feel is the best decision, and we'll move forward. If it's particularly contentious, we can tag it "[revisit before release](https://www.drupal.org/project/issues/search/drupal?version%5B%5D=8.x&issue_tags=revisit+before+release)" and look at it again in November or so.

I hope that this process change will allow us to continue to make bold strides in Drupal 8, while giving dissenting opinions a chance to be heard.
