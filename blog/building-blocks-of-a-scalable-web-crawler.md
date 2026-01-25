---
url: 'https://dri.es/building-blocks-of-a-scalable-web-crawler'
title: 'Building blocks of a scalable web crawler'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2010-12-24T05:09:14-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
  - Acquia
published: true
id: 2066
---

# Building blocks of a scalable web crawler

I recently had the pleasure of serving as a thesis advisor on a work by [Marc Seeger](http://marc-seeger.de), who was completing a portion of his requirements for a Master of Science in Computer Science and Media at Stuttgart Media University. Marc's thesis was titled "Building blocks of a scalable web crawler".

Marc undertook a project for [Acquia](https://www.acquia.com) that I had originally started in 2006; a [Drupal site crawler](https://dri.es/drupal-site-crawler-project) to catalog, as best as possible, the current distribution of Drupal sites across the web. That is a task for which there is no easy answer as [Drupal](https://www.drupal.org) can be downloaded and used free (in all senses of the word). The best way to find out how many Drupal sites exist, is to develop a crawler that crawls the entire web and that counts all the Drupal sites one by one.

With Marc's help, I was able to resurrect my crawler project. Marc spent 6 months working with me; 3 months were spent in Germany where Marc lives, and 3 months were spent in Boston where Acquia is based.

During that time, Marc explored suitable architectures for building out, collecting and managing website data on the order of many millions of domains. He examined different backend storage systems (Riak, Cassandra, MongoDB, Redis, CouchDB, Tokyo Cabinet, MySQL, Postgres, ...), contemplated the methods of collecting the data while simultaneously allowing search and access. As part of his work, Marc explored a variety of different database technologies, database schemas and configurations, and experimented with various configurations of Amazon's Elastic Cloud hardware (EC2). Issues common to any large deployment were investigated and analyzed in detail, including HTTP persistent connections, data locking and concurrency control, caching, and performant solutions for large-scale searches. HTTP redirects, DNS issues – his thesis covers it all, at least in terms of how each of these items impacted the search for an acceptable algorithm.

The crawler has been up and running for a number of months now, and investigated about 100 million domain names. Now we crawled about 100 million domain names, I plan to start publishing the results.

Marc's work is available in PDF from [his blog post](http://blog.marc-seeger.de/2010/12/09/my-thesis-building-blocks-of-a-scalable-webcrawler/), and it's a good read, even if I'm slightly biased. Thanks for the great work, Marc! Time to look for a couple new thesis projects, and thesis students that want to work with me for a few months. Ideas welcome!
