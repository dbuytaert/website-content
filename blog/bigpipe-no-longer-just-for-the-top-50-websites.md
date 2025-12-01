---
title: 'BigPipe, no longer just for the top 50 websites'
date: '2015-11-27T10:27:07-05:00'
author: Dries
tags:
  - Drupal
  - Performance
published: true
type: blog
url: /bigpipe-no-longer-just-for-the-top-50-websites
id: 3511
---

One thing that is exciting to me, is how much we appear to have gotten right in Drupal 8. The other day, for example, I stumbled upon a recent article from the LinkedIn engineering team describing how [they completely changed how their homepage is built](https://engineering.linkedin.com/frontend/new-technologies-new-linkedin-home-page). Their primary engineering objective was to deliver the fastest page load time possible, and one of the crucial ingredients to achieve that was [Facebook's BigPipe](https://www.facebook.com/notes/facebook-engineering/bigpipe-pipelining-web-pages-for-high-performance/389414033919).

I discussed BigPipe on my blog before: first when I wrote about [making Drupal 8 fly](https://dri.es/making-drupal-8-fly) and later when I wrote about [decoupled Drupal](https://dri.es/the-future-of-decoupled-drupal). Since then, [Drupal 8 shipped with BigPipe support](https://wimleers.com/blog/drupal-8-bigpipe-module-ready).

When a very high-profile, very high-traffic, highly personalized site like LinkedIn uses the same technique as Drupal 8, that solidifies my belief in Drupal 8.

[video JwzX0Qv6u3A]

LinkedIn [supports both server-side and client-side rendering](https://github.com/brikis98/ping-play#client-side-vs-server-side-rendering). While Drupal 8 does server-side rendering, we're still missing explicit support for client-side rendering. The advantage of client-side rendering versus server-side rendering is debatable. I've touched upon it in my blog post on [progressive decoupling](https://dri.es/the-future-of-decoupled-drupal), but I'll address the topic of client-side rendering in a future blog post.

However, there is also something LinkedIn could learn from Drupal! Every component of a LinkedIn page that should be delivered via BigPipe needs to write BigPipe-specific code which is prone to errors and requires all engineers to be familiar with BigPipe. Drupal 8 on the other hand has a level of abstraction that allows BigPipe to work without the need for BigPipe-specific code. Thanks to Drupal's higher-level API, Drupal module developers don't have to understand BigPipe: Drupal 8 knows what page components are poorly cacheable or not cacheable at all, and what page components are renderable in isolation, and uses that information to automatically optimize the delivery of page components using BigPipe.

It is exciting to see Drupal support the advanced techniques that were previously only within reach of the top 50 most visited sites of the world! Drupal's BigPipe support will benefit websites small and large.
