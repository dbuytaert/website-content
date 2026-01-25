---
url: 'https://dri.es/acquia-hosting-adds-memcache-support'
title: 'Acquia Hosting adds memcache support'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2010-10-07T11:53:22-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
  - Acquia
  - 'Acquia Cloud'
published: true
id: 1881
---

# Acquia Hosting adds memcache support

On our quest to offer the best possible hosting solution for large-scale Drupal sites here at [Acquia](https://www.acquia.com), we recently added support for memcache to our [Acquia Hosting platform](https://www.acquia.com/products-services/acquia-managed-cloud).

For those that don't know [memcache](http://memcached.org/), it is a high-performance memory object caching system. Oftentimes it's used to speed up database-driven websites by caching data and objects in RAM. This is very effective in managing the load on your database, which for most web applications including [Drupal](https://www.drupal.org), is the biggest performance bottleneck and risk to scalability.

Memcache is a natural addition to Acquia Hosting. The [Memcache module for Drupal](https://www.drupal.org/project/memcache) was originally written by Acquia's Robert Douglass, and continues to be maintained with Acquia's help. So it only makes sense for us to add support memcahe as a hosting option. Combined with all of the other high-performance and scalability features (e.g. Varnish, NginX, etc), it makes Acquia Hosting a very powerful offering.

We run memcache on the existing web servers to take advantage of spare free memory. As such, it is available for every Acquia Hosting customer at no additional cost. Memcache uses a client–server architecture so, if preferred, we can also spin up dedicated memcache servers for our customers. Drupal then talks to the memcache server over a network socket.

A number of Acquia Hosting customers are currently using it in production. Now I still need to take advantage of the new memcache support for my own site. Sounds like another weekend project. :-)
