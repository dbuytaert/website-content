---
title: 'Website spam and moderation queues'
date: '2008-04-18T03:07:54-04:00'
author: Dries
tags:
  - Drupal
  - Mollom
published: true
type: blog
url: /website-spam-and-moderation-queues
id: 429
---

Mollom is a web service that blocks website spam. Websites using [Mollom](https://mollom.com) send data they want checked to mollom.com, and Mollom replies with either a *spam* or *ham classification*. If Mollom is not certain, it will return an *unsure classification*, typically prompting websites to ask Mollom's CAPTCHA server for an audio or visual CAPTCHA challenge to present to the user. In other words, Mollom uses a classifier with three states: ham, spam and unsure. We explained that in detail on the ["How Mollom works" page](https://www.mollom.com/how-mollom-works).

Over at the [Mollom blog](https://www.mollom.com/blog), Ben wrote a [great post](https://www.mollom.com/spam-vs-ham) about why we believe this is a key difference, and how that allows Mollom to eliminate your moderation queue. A picture is worth more than a thousand words, so check out the plots below and check out [Ben's blog post](https://www.mollom.com/spam-vs-ham) for more details.

[image mollom/spam-versus-ham-1 resize=false]

As you can see on the first graph, a binary classifier with two states (ham, spam) is never going to be deadly accurate, and will require a moderation queue so the user can manually deal with legitimate comments that incorrectly got classified as spam. Unfortunately, moderation queues are not fun, and they don't make you any more productive. You'll still find yourself wading through thousands of spam comments looking for ham. In other words, a moderation queue doesn't really solve the problem – it just makes the problem look different.

[image mollom/spam-versus-ham-2 resize=false]

Time for something better. As you can see on the second graph, a classifier with three states is going to be a lot more accurate. In fact, Mollom is so accurate that the [Drupal module](https://www.mollom.com/download) doesn't come with a moderation queue! It an important distinction, and one of the many innovations that we have in store for you. *Bye bye moderation queue!*
