---
url: 'https://dri.es/drupal-database-interaction'
title: "Drupal's database interaction"
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2006-06-23T07:41:46-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
  - 'Web performance'
  - Statistics
  - MySQL
published: true
id: 96
---

# Drupal's database interaction

I used [XDebug](https://xdebug.org/) to profile the behavior of [Drupal](https://www.drupal.org/), and to study the interaction with the database server. I aggregated the profile information of 100 requests to the main page using the "Apache, mod\_php, PHP4, APC" configuration used for [previous benchmark experiments](/drupal-webserver-configurations-compared). More information about my experimental setup is available at [that page](/drupal-webserver-configurations-compared). XDebug generates a trace file with all the profile information which I visualized using [KCacheGrind](http://kcachegrind.sourceforge.net/cgi-bin/show.cgi/KcacheGrindIndex).

Drupal has a page cache mechanism which stores dynamically generated web pages in the database. By caching a web page, Drupal does not have to create the page each time it is requested. Only pages requested by anonymous visitors (users that have not logged on) are cached. Once users have logged on, caching is disabled for them since the pages are personalized in various ways. Because this represents two different modes of operation, I investigated Drupal's behavior with and without page caching.

## With page caching

![Table showing time spent in each function during page caching, sorted by self-time and call frequency for 100 requests.](http://default/files/images/drupal/functions-cache.jpg)
*This figure shows how much time is spent in each function when page caching is enabled. The functions are sorted by the 'Self' column, which shows the time spent in each function without the time spent in its children. The second column shows how often the function was called to serve 100 requests to the main page.*

We observe that more than 45% (14.37% + 14.18% + 8.9% + 5.54% + 2.9% + ...) of the execution time is spent in the database related functions. Sending the SQL queries to the database server and waiting for the results takes 14% of the total execution time. Drupal preparing the queries (eg. database prefixing, sanitizing the input to prevent SQL query injection, etc) takes more than 31% of the total execution time. We should look into optimizing the functions that prepare the queries (`db_query()`, `_db_query` and `_db_query_callback()`).

The figure above depicts that PHP's `mysql_query()` function is called 1401 times. This means that we need 14 SQL queries to serve a cached page. This is where these SQL queries come from:

![Table showing Drupal functions querying the database for 100 cached pages, with execution time, query count, and function names.](http://default/files/images/drupal/queries-cache.jpg)
*This figure shows the Drupal functions responsible for querying the database when serving 100 cached pages. The first column shows how much time is spent in the calls to <code>db\_query\(\)</code>. The second column shows how many times each function queried the database and the last column shows the functions' names and source files.*

## Without page caching

![Table showing function execution times when page caching is disabled, sorted by self-time and call frequency.](http://default/files/images/drupal/functions-nocache.jpg)
*This figure shows how much time is spent in each function when page caching is disabled. The functions are sorted by the 'Self' column, which shows the time spent in each function without the time spent in its children. The second column shows how often the function was called to serve 100 requests to the main page.*

When the page cache is disabled, we see that on average we need 144 SQL queries to generate the main page.  That is a lot.  We also observe that 25% of the total execution time is spent in database related functions: 13% of the total execution time is spent executing queries, and 12% of the total execution time is spent preparing the queries.  This is where the SQL queries come from:

![Table showing Drupal functions querying the database, with execution time, query count, and function names from source files.](http://default/files/images/drupal/queries-nocache.jpg)
*This figure shows the Drupal functions responsible for querying the database when serving 100 pages. The first column shows how much time is spent in the calls to <code>db\_query\(\)</code>. The second column shows how many times each function queried the database and the last column shows the functions' names and source files.*
