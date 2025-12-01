---
title: 'Industry Standard using Drupal'
date: '2008-09-09T10:00:28-04:00'
author: Dries
tags:
  - Drupal
  - 'Drupal sites'
  - 'Mollom sites'
  - Publishing
published: true
type: blog
url: /industry-standard-using-drupal
id: 503
---

The Industry Standard, aka [thestandard.com](http://thestandard.com), is using [Drupal](https://www.drupal.org). The Industry Standard features news and analysis that covers emerging technologies and companies, venture funding, acquisitions, site launches, and other developments in the internet space. This system is built as a prediction market, intersected with a reputation-based social network. The site is part of the [IDG network](http://idg.com), which includes sites like Computerworld, Infoworld, JavaWorld.com, Macworld, PC World, and more.

Like most big Drupal sites, they use CCK, Views, memcache, and a master-slave database configuration. Two noteworthy items are the fact that they use Apache Solr for search, and [Mollom](https://mollom.com) as their spam deterrent.

[image drupal/industry-standard]
