---
url: 'https://dri.es/using-the-akiban-database-with-drupal'
title: 'Using the Akiban database with Drupal'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2012-12-06T09:32:04-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
  - Acquia
  - 'Acquia Cloud'
published: true
id: 2836
---

# Using the Akiban database with Drupal

For four years now I've been an advisor for Akiban, a Boston start-up building a new class of NewSQL/NoSQL database. I'm excited that after 4 years of hard work, [Akiban](http://akiban.com) launched their first Drupal customer solution in the [Acquia Cloud](https://www.acquia.com/products-services/acquia-cloud). A great opportunity to talk a bit more about what Akiban is doing, and why I'm excited to help their team.

The early phase strategy for Akiban is to augment existing deployments (for example MySQL) to enhance query performance among other capabilities. Our mutual customer was facing performance, concurrency and availability challenges with some custom Drupal report code. The report was built in Drupal as a module, and involved a series of complex joins making performance unpredictable, frequently resulting in slow query performance and periodically crashing the whole site. Using Akiban's database, the customer is realizing 66x performance improvement over their existing implementation, without any significant change to the Drupal application.

One of the core benefits of Akiban is query acceleration. The Akiban database can run along side of MySQL server in "augmentation mode" comparable to master-slave configuration. Akiban implemented a simple Drupal patch which allows the reporting queries to be redirected to the Akiban server. While Akiban's solution requires data duplication, it also means that there is virtually no intrusion on the day-to-day running of the site.

The report module remains as originally designed but now the problem queries are redirected to the Akiban server. Akiban's core technology is called Table Grouping. Table Grouping enables for the physical grouping of tables while preserving a logical layer allowing developers to continue to use SQL. This grouping eliminates complex traditional joins while preserving the use of ANSI SQL. In addition, Akiban can create cross-table indexes thus accelerating formerly slow queries. As a result, with the reporting queries now directed to Akiban server, the report performs 66x faster.

The Akiban team refers to Akiban server as a new class of database that accelerates SQL and NoSQL data by 10-100x, while allowing developers to access data in both traditional SQL and RESTful environments (SOAs). Compared to other database technologies, Table Grouping provides an innovative way to store and query structured and semi-structured data.

Akiban's Padraig O'Sullivan is working on a module for Drupal 7, and while there is still some work to be done to test and optimize it, he has already enabled [Akiban](http://akiban.com) to run as the source database for Drupal 8 in development. Something to keep an eye on. If you want to test out Akiban yourself, head over to [akiban.com](http://akiban.com) and download it.
