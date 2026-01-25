---
url: 'https://dri.es/mollom-gets-a-new-backend'
title: 'Mollom gets a new backend'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2010-12-14T09:41:39-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Mollom
published: true
id: 2036
---

# Mollom gets a new backend

Over the past five months, we've been giving the Mollom backend a massive overhaul. To support this effort, we've extended the team with two part-time engineers; [Johan Vos](http://blogs.lodgon.com/johan/) and [Thomas Meire](https://twitter.com/blackskad), who jointly took on the task of converting our old Java backend to a new Java EE backend based on [Glassfish](http://javaee.github.io/glassfish). (Glassfish is the Open Source Reference Implementation of the [Java EE specification](https://en.wikipedia.org/wiki/Java_Platform,_Enterprise_Edition).) Along the way, we upgraded our servers and rolled out [Hudson](http://hudson-ci.org/) to provide for continuous testing and deployment of the backend across all our servers. All in all, it's been a productive summer and fall at [Mollom](https://mollom.com).

Most projects are a mix between domain-specific problems and common, mostly infrastructure related, problems. The Mollom backend isn't any different; in fact, we may have more infrastructure related issues than your average project. With our move to Glassfish, we'll have to worry a lot less about memory management, REST handling, XML parsing, database connection pooling, and all the other ancillary things that make big systems work. That frees us up to focus on the domain-specific problems – the actual moving parts of Mollom itself – and will help both support our growth and allow us to implement new features and improve the old ones.

Earlier today, we rolled out the new Glassfish-based backend on all of our servers. Though these changes should be transparent to our users, it's possible you might notice a short blip in Mollom's effectiveness. It is never easy to migrate large amounts of data in a running system, while simultaneously keeping it running. So, though it may take a few days for Mollom to build back up to its normal levels of accuracy, we're confident it will do so in short order.

We're confident that the backend changes we've implemented will pay – and that should be a win-win for all of us.
