---
title: 'Drupal vs Joomla: performance'
date: '2006-08-11T08:04:06-04:00'
author: Dries
tags:
  - Drupal
  - Performance
  - Joomla
  - Statistics
published: true
type: blog
url: /drupal-vs-joomla-performance
id: 122
---

Which content management system is faster? [Drupal](https://www.drupal.org) or [Joomla](https://joomla.org)?

### Experimental setup

I used the "Apache, mod\_php, PHP4, APC" configuration from [previous benchmark experiments](/drupal-webserver-configurations-compared) to compare the performance of [Drupal](https://www.drupal.org/) and [Joomla](https://www.joomla.org/) on a 3 year old Pentium IV 3Ghz with 2 GB of RAM running Gentoo Linux. I used the following software: Apache 2.0.55, PHP 4.4.2, MySQL 4.1.4, Drupal 4.7.3 and Joomla 1.0.10.

I simply downloaded and installed the latest stable release of both Drupal and Joomla, and tried my best to make them act and look the same. To do so, I enabled the login form and the "Who's online" block. I also setup two links and a search widget in the top menu, enabled the hit counters for posts, and setup identical footers. Next, I created one author, one category and one post as shown in the images below.

[image drupal/drupal-post resize=false]
[image drupal/joomla-post resize=false]

Apache's [ab2](http://httpd.apache.org/docs/2.0/programs/ab.html) was used to compute how many requests per second both systems are capable of serving. The page was requested 1000 times with a concurrency of 5 (i.e. `ab2 -n 1000 -c 5`). To test the impact of gzip-compressing pages we specified whether ab2 can accept gzip-compressed pages (i.e. `ab2 -n 1000 -c 5 -H "Accept-Encoding: gzip;"`). Note that `ab2` did not request any images or CSS files; only the dynamically generated HTML document was retrieved.

### Requests per second

[image drupal/drupal-vs-joomla-rps resize=false]

When caching is disabled Joomla can serve 19 pages per second, while Drupal can serve 13 pages per second. Hence, Joomla is 44% faster than Drupal.

However, when caching is enabled Joomla can serve 21 pages per second, while Drupal can serve 67 pages per second. Here, Drupal is 319% faster than Joomla.

In other words, Joomla's cache system improves performance by 12%, while Drupal's cache system improves performance by 508%.

It is important to note that Drupal can only serve cached pages to anonymous visitors (users that have not logged on). Once users have logged on, caching is disabled for them since the pages are personalized in various ways. Hence, in practice, Drupal might not be 319% faster than Joomla; it depends on the ratio of anonymous visitors versus authenticated visitors, how often your site's page cache is flushed, and the hit-rate of your Drupal page cache.

Lastly, when serving gzip-compressed pages Drupal becomes slightly faster compared to having to serve non-compressed pages. Joomla, on the other hand, becomes a little bit slower. The reason is that Drupal's page cache stores its content directly in a compressed state; it has to uncompress the page when the client does not support gzip-compression, but can serve a page directly from the page cache when the client does support gzip-compression.

### Document length

[image drupal/drupal-vs-joomla-length resize=false]

The first figure shows that the cost of compressing or uncompressing pages is negligible. The second picture shows that it can, however, have significant impact on the document length, and hence, on bandwidth usage.

Drupal always attempts to send compressed pages. Joomla, on the other hand, doesn't compress pages unless this option is explicitly turned on.
