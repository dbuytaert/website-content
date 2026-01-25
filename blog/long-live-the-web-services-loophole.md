---
url: 'https://dri.es/long-live-the-web-services-loophole'
title: 'Long live the web services loophole'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2006-11-13T05:11:49-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
  - 'Drupal distributions'
published: true
id: 177
---

# Long live the web services loophole

You can't sell Drupal, or any modification you made to Drupal. You can charge money for having to make these changes but you can't make these changes available under a commercial license. Why not? Because Drupal's license, the [General Public License 2](https://www.gnu.org/licenses/gpl.txt) (GPL 2), mandates that all modifications also be distributed under the GPL.

But when you are providing a service through the web using GPL'ed software like Drupal, you are not actually *distributing* the software. You are providing access to the software. Thus, a way to make money with Drupal is to sell access to a web service built on top of Drupal. This is commonly referred to as the *web services loophole*.

Some people say this loophole is inconsistent with the values of the [Free Software movement](https://www.fsf.org/). Others think of this loophole as an interesting feature. I'm in the latter camp. In fact, I predict that 2007 will bring a small tsunami of [Drupal distributions](/drupal-distributions) built around a hosted service model.

Fact is, when the GPL was created 15 years ago, it did not really predict a world of web services. Version 3 of the GPL, expected to be released in 2007, will tackle this issue. It will allow developers to add an optional clause to the license that requires hosted service providers to share the source code and their modifications. This optional clause can be found in [section 7.b.4 of the most recent draft of the GPL 3](http://gplv3.fsf.org/) (subject to change):

> Additional requirements are terms that further constrain use, modification or propagation of covered works. This License affects only the procedure for enforcing additional requirements, and does not assert that they can be successfully enforced by the copyright holder. Only these kinds of additional requirements are allowed by this License: ... snip ... 4) terms that require, if a modified version of the material they cover is a work intended to interact with users through a computer network, that those users be able to obtain copies of the Corresponding Source of the work through the same network session.

Personally, I don't see us adding such a clause to Drupal. It doesn't bode well with the way people use Drupal, or any content management system for that matter. Here is just one example: most people theme their sites by downloading and modifying one of the available GPL themes. If we were to add the additional clause, this would no longer be desirable, because you'd be forced to share all your modifications, including your theme's. It is problematic when you want to create a unique site or brand.

So long live the web services loophole!
