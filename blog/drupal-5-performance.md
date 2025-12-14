---
title: 'Drupal 5: performance'
date: '2007-02-07T09:15:21-05:00'
author: Dries
tags:
  - Drupal
  - 'Web performance'
  - Statistics
published: true
type: blog
url: /drupal-5-performance
id: 213
---

With the release of Drupal 5, you might be wondering which version of Drupal is faster – the latest release in the Drupal 4 series, or the new Drupal 5?

### Experimental setup

I setup a Drupal 4.7 site with 2,000 users, 5,000 nodes, 5,000 path aliases, 10,000 comments and 250 vocabulary terms spread over 15 vocabularies.

Next, I configured the main page to show 10 nodes, enabled some blocks in both the left and the right sidebar, setup some primary links, and added a search function at the top of the page. I also setup a contact page using Drupal's contact module. The image below depicts how my final main page was configured.

[image drupal/drupal-4.7-main-page resize=false]

Furthermore, I made an exact copy of the Drupal 4.7 site and upgraded it to the latest Drupal 5 release. The result is two identical websites; one using Drupal 4.7 and one using Drupal 5.

Benchmarks were conducted on a 3 year old Pentium IV 3Ghz with 2 GB of RAM running Gentoo Linux. I used a single tier web architecture with the following software: Apache 2.0.58, PHP 5.1.6 with APC, and MySQL 5.0.26. No special configuration or tweaking was done other than what was strictly necessary to get things up and running. My setup was CPU-bound, not I/O-bound or memory-bound.

Apache's [ab2](http://httpd.apache.org/docs/2.0/programs/ab.html) with 20 concurrent clients was used to compute how many requests per second the above setup was capable of serving.

### Drupal page caching

Drupal has a page cache mechanism that stores dynamically generated web pages in the database. By caching a web page, Drupal does not have to create the page each time it is requested. Only pages requested by *anonymous visitors* (users that have not logged on) are cached. Once users have logged on, caching is disabled for them since the pages are personalized in various ways. On some websites, like this weblog, everyone but me is an anonymous visitor, while on other websites there might be a good mix of both anonymous and *authenticated visitors*.

When presenting the benchmark results, I'll make a distinction between cached pages and non-cached paged. This will allow you to interpret the results with the dynamics of your own Drupal websites in mind.

Furthermore, a Drupal 5 installation has two caching modes: *normal database caching* and *aggressive database caching*. The normal database cache is suitable for all websites and does not cause any side effects. The aggressive database cache causes Drupal to skip the loading (*init*-hook) and unloading (*exit*-hook) of enabled modules when serving a cached page. This results in an additional performance boost but can cause unwanted side effects if you skip loading modules that shouldn't be skipped.

Through contributed modules, Drupal also supports *file caching* which should outperform *aggressive database caching*. I have not looked at file caching or any other caching strategies that are made available through contributed modules.

### Results

[image drupal/drupal-5-performance-1 resize=false]

The figure above shows that generating a page in Drupal 5 is 3% slower than in Drupal 4.7. However, when serving a cached page using the normal database cache, Drupal 5 is 73% faster than Drupal 4.7, and 268% faster when the aggressive database cache is used.

What does this mean when looking at the overall performance of a Drupal 5 website? Well, the effectiveness of Drupal's page cache depends on a number of parameters like your cache expiration time, the number of authenticated users, access patterns, etc. To emulate different Drupal configurations, we modified Drupal 4.7 and Drupal 5 so we could look at performance for a range of page cache miss rates.

[image drupal/drupal-5-performance-2 resize=false]

The figure above shows the relative performance improvement of Drupal 5 compared to Drupal 4.7. We observe that Drupal sites with relatively few cache misses (typically static Drupal websites accessed by anonymous users) will be significantly faster with Drupal 5. However, Drupal sites where more than 1 out of 2 page requests results in a cache miss (typically dynamic Drupal websites with a lot of authenticated users) will be slightly slower compared to an identical Drupal 4.7 website.

To me these graphs suggest that for most Drupal websites, upgrading to Drupal 5 will yield at least a small performance improvement – especially if you properly configure your page cache's expiration time. Furthermore, they suggest that for Drupal 6, we need to look at improving the page generation time of non-cached pages. Let's make that an action item.
