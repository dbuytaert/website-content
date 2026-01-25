---
url: 'https://dri.es/twitter-drupal-and-jabber'
title: 'Twitter, Drupal and Jabber'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2007-03-21T09:35:59-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
published: true
id: 239
---

# Twitter, Drupal and Jabber

It would be great if Drupal could interface with [Twitter](https://twitter.com/). Twitter supports several methods of delivering messages; using instant messaging, using RSS, using SMS to your mobile phone, and more. For small sites like mine, it would be great to get notified about new comments through MSN or Jabber. Drupal event notifications to the desktop!

Who says I want to track my friends? I want to track my websites. ;-)

It's pretty obvious that Twitter-like services with less focus on social networking will arrive soon. It fits the line of existing web services rather well, and enables these services to better talk to the user.

The question is; who is going to offer this service so we don't have to *abuse* Twitter? And when it gets built, let's hope it will be based on [Jabber](https://www.jabber.org/), so it is truly open, standard, decentralized, secure and extensible.

(Actually, I know some people who have built exactly that, but I don't know whether they are going to open it up, or make it available as a service.)

If anything, this begs for Drupal's logging functionality to be refactored so messages can selectively be delivered to multiple registered output channels, be it database logging, Twitter, Jabber, MSN, e-mail or [syslog](https://en.wikipedia.org/wiki/Syslog).
