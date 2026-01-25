---
url: 'https://dri.es/consumer-search-using-drupal'
title: 'Consumer Search running Drupal'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2008-11-26T05:09:48-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
  - 'Drupal sites'
  - 'Web performance'
  - 'Fortune 500'
published: true
id: 541
---

# Consumer Search running Drupal

[ConsumerSearch.com](http://consumersearch.com) has been redesigned and is now running [Drupal](https://www.drupal.org). The site is a part of the [About.com Group](http://about.com), a subsidiary of [The New York Times Company](https://www.nytco.com/).

ConsumerSearch.com gets about 5.5M unique visitors each month (and growing). I don't know what server infrastructure they run on, but with the help from Jeremy at [Tag1 Consulting](https://www.tag1consulting.com/), they configured Drupal to rely heavily on [memcached](http://www.danga.com/memcached/) and [Drupal's built-in aggressive caching mode](https://dri.es/drupal-5-performance). Knowing Jeremy, they are probably trying to serve cached pages from disk, rather than from the database.

[image drupal/consumer-search]
