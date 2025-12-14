---
title: "Drupal's database interaction"
date: '2006-06-23T07:41:46-04:00'
author: Dries
tags:
  - Drupal
  - 'Web performance'
  - Statistics
  - MySQL
published: true
type: blog
url: /drupal-database-interaction
id: 96
---

I used [XDebug](https://xdebug.org/) to profile the behavior of [Drupal](https://www.drupal.org/), and to study the interaction with the database server. I aggregated the profile information of 100 requests to the main page using the "Apache, mod\_php, PHP4, APC" configuration used for [previous benchmark experiments](/drupal-webserver-configurations-compared). More information about my experimental setup is available at [that page](/drupal-webserver-configurations-compared). XDebug generates a trace file with all the profile information which I visualized using [KCacheGrind](http://kcachegrind.sourceforge.net/cgi-bin/show.cgi/KcacheGrindIndex).

Drupal has a page cache mechanism which stores dynamically generated web pages in the database. By caching a web page, Drupal does not have to create the page each time it is requested. Only pages requested by anonymous visitors (users that have not logged on) are cached. Once users have logged on, caching is disabled for them since the pages are personalized in various ways. Because this represents two different modes of operation, I investigated Drupal's behavior with and without page caching.

### With page caching

[image drupal/functions-cache resize=false]

We observe that more than 45% (14.37% + 14.18% + 8.9% + 5.54% + 2.9% + ...) of the execution time is spent in the database related functions. Sending the SQL queries to the database server and waiting for the results takes 14% of the total execution time. Drupal preparing the queries (eg. database prefixing, sanitizing the input to prevent SQL query injection, etc) takes more than 31% of the total execution time. We should look into optimizing the functions that prepare the queries (`db_query()`, `_db_query` and `_db_query_callback()`).

The figure above depicts that PHP's `mysql_query()` function is called 1401 times. This means that we need 14 SQL queries to serve a cached page. This is where these SQL queries come from:

[image drupal/queries-cache resize=false]

### Without page caching

[image drupal/functions-nocache resize=false]

When the page cache is disabled, we see that on average we need 144 SQL queries to generate the main page.  That is a lot.  We also observe that 25% of the total execution time is spent in database related functions: 13% of the total execution time is spent executing queries, and 12% of the total execution time is spent preparing the queries.  This is where the SQL queries come from:

[image drupal/queries-nocache resize=false]
