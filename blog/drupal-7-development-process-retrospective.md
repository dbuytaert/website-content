---
title: 'Drupal 7 development process retrospective'
date: '2011-02-01T15:45:22-05:00'
author: Dries
tags:
  - Drupal
published: true
type: blog
url: /drupal-7-development-process-retrospective
id: 2161
---

Drupal 7 was released three weeks ago. Now that we've all had chance to catch our breath, it's a good time to look back and reflect on the Drupal 7 release cycle. Since I'm about to open the Drupal 8 branch, this is an ideal time to inspect and adapt our processes.

In this post, I'd like everyone to chip in and share their thoughts about the Drupal 7 development path. How have things gone? What should we continue to do? What should we change? Should the release cycle be shorter or longer? Should we revisit our policy on backward compatibility? Look back and assess. Think about the interactions and patterns that contributed to both our successes and failures during the Drupal 7 development cycle. Then, taking everything into account, I'll try to set an optimized course for the upcoming Drupal 8 development cycle.

This blog post is only one step in determining that course. It could get a bit unwieldy to discuss this in the comments of a blog post, but that's alright. Let's give it a try and just gather data and insight and try to write a shared story of how things went and what we could improve possibly. If necessary, taking the comments on this blog post as input, I'll organize a more structured follow-up survey to help us prioritize and streamline our thoughts, and ultimately decide what to do. Keep in mind that the decision on what to do won't necessarily be a democratic vote. Good ideas and suggestions count more than mere quantity of affirmations.

One change that is already on its way is the migration from CVS to Git. It will address many of the problems we experienced getting to Drupal 7. I'm quite excited about that and eager to see how Git will change our development process. I'd really like to see us evolve to a [Linux kernel development model](https://en.wikipedia.org/wiki/Linux_kernel#Development_model) in which I maintain the official Drupal core tree from which official releases are made, but integrate major changes and bug fixes from different individuals and groups.

I want to be careful not to jump to solutions too quickly as there might be other things that could be changed. At the same time, switching from CVS to Git and adopting how we work together is a humongous change. It might be enough of a change for this release cycle that we don't need to make many more changes. I'd certainly be interested in your thoughts.

In a separate post, I'll organize our traditional 'battle plan discussion' for feature discussion. For now, the goal is just to brainstorm about the development process.
