---
title: 'Web services in Drupal 8'
date: '2011-04-11T16:53:06-04:00'
author: Dries
tags:
  - Drupal
published: true
type: blog
url: /web-services-in-drupal-8
id: 2296
---

In [my DrupalCon keynote in Chicago](https://dri.es/state-of-drupal-presentation-march-2011), I talked about the key initiatives that I believe we should focus on for Drupal 8 core. One of those key initiatives that I talked about was *web services*.

The future is a world where content management systems need to output data to many more devices and integrate with more and more systems and services. Today, Drupal is optimized for outputting HTML and core ships with an old XML-RPC backend. If we want [Drupal](https://www.drupal.org) to be the go-to platform in a world with many different devices and integrated services, we need to fundamentally change that.

The goal of Drupal 8's Web Service Initiative is to make Drupal equally good at outputting data as XML, JSON and other non-HTML formats, to expose Drupal's functionality through a RESTful interface, but also for Drupal to better support different page layouts when delivering HTML pages to different devices.

HTML5 is obviously a big part of such a future as well, however, for that I'll setup a dedicated initiative. I believe both can be worked on (mostly) in parallel and by different people. I'm still talking to different people about the HTML5 initiative. Both initiatives combined should get us in a great position with Drupal 8.

### Larry Garfield

I've decided to make [Larry Garfield](https://www.garfieldtech.com) (aka [Crell](https://www.drupal.org/user/26398)) the *Initiative Owner* for the Web Services Initiative in Drupal 8. As the Initiative Owner Larry will act as the project manager and/or technical lead. In this role, Larry and myself will work closely together on defining the architecture and approach. This means I don't need to be involved in every small conversation myself, but that I still need to sign off on the approach and implementation.

Larry was the obvious choice for two reasons. First, he is a great architect able to tackle complex problems, as demonstrated by his work on Drupal 7's database abstraction layer. Second, Larry has [already](https://groups.drupal.org/node/63708) put in a [lot of thought](https://groups.drupal.org/node/93039) and [effort](https://groups.drupal.org/node/136089) into this.

As many of you know, this initiative is near and dear to my heart. I trust that Larry will do a great job. For more details, please read [Larry's announcement blog post](https://www.garfieldtech.com/blog/web-services-initiative) or [join the technical conversation](https://groups.drupal.org/wscci).
