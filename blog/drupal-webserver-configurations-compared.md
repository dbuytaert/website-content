---
url: 'https://dri.es/drupal-webserver-configurations-compared'
title: 'Drupal webserver configurations compared'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2006-06-08T06:28:50-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
  - 'Web performance'
  - Statistics
published: true
id: 89
---

# Drupal webserver configurations compared

Opinions on the best webserver configuration for [Drupal](https://www.drupal.org/) vary from one user to the next. Thus, I set out to compare and document the performance of difference combinations of webserver options.

### Experimental setup

I setup a Drupal 4.7 site with 2,000 users, 5,000 nodes, 5,000 path aliases, 10,000 comments and 250 vocabulary terms spread over 15 vocabularies. If you don't know what that means, you're probably not a Drupal user. That is OK. If you have basic technical knowledge of webservers the results might still be interesting.

Next, I configured the main page to show 10 nodes, enabled some blocks in both the left and the right sidebar, setup some primary links, and added a search function at the top of the page. I also setup a contact page using Drupal 4.7's contact module. The image below depicts how my final main page was configured.

[image drupal/drupal-4.7-main-page resize=false]

Benchmarks were done on a 3 year old Pentium IV 3Ghz with 2 GB of RAM running Gentoo Linux. I used the following software: Apache 2.0.55, Lighttpd 1.3.16, PHP 4.4.2, PHP 5.1.4, and MySQL 4.1.4 without special configuration or tweaking other than strictly necessary to get things up an running.

Apache's [ab2](http://httpd.apache.org/docs/2.0/programs/ab.html) was used to compute how many requests per second the above setup is capable of serving.

### Drupal page caching?

Drupal has a page cache mechanism which stores dynamically generated web pages in the database. By caching a web page, Drupal does not have to create the page each time it is requested. Only pages requested by *anonymous visitors* (users that have not logged on) are cached. Once users have logged on, caching is disabled for them since the pages are personalized in various ways.

On some websites, like this weblog, everyone but me is an anonymous visitor, while on other websites there might be a good mix of both anonymous and *authenticated visitors*.

When presenting the benchmark results, I'll make a distinction between anonymous visitors and authenticated visitors. This allows you to interpret the results with the dynamics of your own Drupal websites in mind.

### APC?

APC, which stands for [Alternative PHP Cache](http://pecl.php.net/package/APC), is a free PHP extension that will optimize the performance of PHP applications by caching PHP code in a compiled state.

[image drupal/drupal-4.7-apc-vs-noapc resize=false]

With APC, my configuration could serve 4 times as many pages to anonymous visitors, and 2 times as many pages to authenticated visitors.

### PHP4 or PHP5?

The figure below depicts a comparison between PHP4 and PHP5. It shows that on average, PHP5 can handle 13% fewer requests per second than PHP4 for anonymous visitors, and 4% fewer requests for authenticated visitors.

[image drupal/drupal-4.7-php4-vs-php5 resize=false]

### Reverse proxy?

When a proxy, like [Squid](http://www.squid-cache.org/), is configured as a *reverse proxy* it can act as a caching mechanism for web pages. Because the reverse proxy sits between the internet and the webserver, it can intercept all requests and respond to them by serving cached content. This reduces the load on the webserver (and the database).

I haven't setup a reverse proxy for these experiments because, currently, Drupal doesn't generate the proper HTTP headers to control the cache mechanism. Also, because of the way Drupal works, it is quite a challenge to setup and configure a reverse proxy.

The one scenario where it would be easy to setup, and likely to be beneficial, is where all visitors are anonymous visitors.

### mod\_php or FastCGI?

There are many ways to run PHP. `FastCGI` and `mod_php` are two of the most commonly used approaches. Most people are using `mod_php` because that is the default on nearly all Linux distributions. With `mod_php`, PHP runs as an Apache module and as a result, all PHP applications are executed with the privileges of Apache. This means that your Drupal files need to be readable (and sometimes writable) by Apache.

When using `FastCGI`, the web applications can run under different privileges than that of Apache. Hence, `FastCGI` is often used on shared hosts to provide additional security. Using `FastCGI` you can prevent that other users on the system, can read or write your files. The downside, however, is that `FastCGI` has an additional performance cost.

So when choosing between `mod_php` or `FastCGI`, you are making a trade-off between security and performance. The figure below shows the relative performance of the two approaches, and can help you understand the trade-off. When switching from `mod_php` to `FastCGI` we observe a 63% slowdown for anonymous visitors, and a 18% slowdown for authenticated visitors.

[image drupal/drupal-4.7-fastcgi-vs-mod_php resize=false]

### Apache or Lighttpd?

[Lighttpd](http://www.lighttpd.net/) (or *Lighty*) is a HTTP daemon designed for high-performance environments. Its goal is to be fast and have a small memory footprint. The figure below shows how Apache compares to Lighttpd.

[image drupal/drupal-4.7-apache-vs-lighttpd resize=false]

### Conclusions

So what are the best and worst configurations of those i have tested? And what is the fastest configuration, while still being secure? Turns out that the slowest configuration is Apache 2 running PHP5 as an Apache module without using APC. Unfortunately, this is one of the most common configurations.

The fastest configuration using the more secure FastCGI method, on the other hand, is Lighttpd with PHP4 in FastCGI mode using APC. For anonymous visitors, the latter is almost 4 times faster than the former, while being more secure. This is illustrated by the figure below.

If you are not on a shared host, you might not care about the security options provided by `FastCGI`. In that case, the next and last figure might be of interest. Turns out that for anonymous visitors my fastest Apache configuration is 3% faster than the fastest Lighttpd configuration.

[image drupal/drupal-4.7-slow-vs-fast-2 resize=false]
