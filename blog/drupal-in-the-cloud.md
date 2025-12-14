---
title: 'Drupal in the cloud'
date: '2008-04-16T04:53:09-04:00'
author: Dries
summary: 'Why the cloud looks promising for Drupal hosting and scaling'
tags:
  - Drupal
  - 'Web performance'
  - MySQL
published: true
type: blog
url: /drupal-in-the-cloud
id: 428
---

It is not always easy to scale [Drupal](https://www.drupal.org) – not because Drupal sucks, but simply because scaling the LAMP stack (including Drupal) takes no small amount of skill. You need to buy the right hardware, install [load balancers](http://www.linuxvirtualserver.org/), setup MySQL servers in [primary-secondary mode](https://dri.es/scaling-with-mysql-replication), setup static file servers, setup web servers, get PHP working with [an opcode cache](https://en.wikipedia.org/wiki/PHP_accelerator), tie in a distributed memory object caching system like [memcached](http://www.danga.com/memcached/), integrate with a [content delivery network](https://www.akamai.com/), watch security advisories for every component in your system and configure and tune the hell out of everything.

Either you can do all of the above yourself, or you outsource it to a company that knows how to do this for you. Both are non-trivial and I can count the number of truly qualified companies on one hand. [Tag1 Consulting](https://www.tag1consulting.com/) is one of the few Drupal companies that excel at this, in case you're wondering.

My experience is that [MySQL](http://mysql.com) takes the most skill and effort to scale. While proxy-based solutions like [MySQL Proxy](https://www.mysql.com/wiki/MySQL_Proxy/) look promising, I don't see strong signals about it becoming fundamentally easier for mere mortals to scale MySQL.

It is not unlikely that in the future, scaling a Drupal site is done using a radically different model. [Amazon EC2](https://aws.amazon.com/ec2/), [Google App Engine](https://cloud.google.com/appengine/) and even [Sun Caroline](https://www.projectcaroline.net) are examples of the hosting revolution that is ahead of us. What is interesting is how these systems already seem to evolve: Amazon EC2 allows you to launch any number of servers but you are pretty much on your own to take advantage of them. Like, you still have to pick the operating system, install and configure MySQL, Apache, PHP and Drupal. Not to mention the fact that you don't have access to a good persistent storage mechanism. No, [Amazon S3](https://aws.amazon.com/s3/) doesn't qualify, and yes, they are working to fix this by adding [Elastic IP addresses](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html) and [Availability Zones](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-regions-availability-zones.html). Either way, Amazon doesn't make it easier to scale Drupal. Frankly, all it does is making capacity planning a bit easier ...

Then comes along [Amazon SimpleDB](http://aws.amazon.com/simpledb/), [Google App Engine](https://cloud.google.com/appengine/) and [Sun Caroline](https://www.projectcaroline.net). Just like Amazon EC2/S3 they provide instant scalability, only they moved things up the stack a level. They provide a *managed application environment* on top of a *managed hosting environment*. Google App Engine provides APIs that allow you to do user management, e-mail communication, persistent storage, etc. You no longer have to worry about server management or all of the scale-out configuration. Sun Caroline seems to be positioned somewhere in the middle – they provide APIs to provision lower level concepts such as processes, disk, network, etc.

Unfortunately for Drupal, Google App Engine is Python-only, but more importantly, a lot of the concepts and APIs don't map onto Drupal. Also, the more I dabble with tools like [Hadoop](http://hadoop.apache.org/) ([MapReduce](https://research.google.com/archive/mapreduce.html)) and [CouchDB](http://couchdb.org), the more excited I get, but the more it feels like everything that we do to scale the LAMP stack is suddenly wrong. I'm trying hard to think beyond the relational database model, but I can't figure out how to map Drupal onto this completely different paradigm.

So while the center of gravity may be shifting, I've decided to keep an eye on Amazon's EC2/S3 and Sun's Caroline as they are "relational database friendly". Tools like [Elastra](http://www.elastra.com) are showing a lot of promise. Elastra claims to be the world's first infinitely scalable solution for running standard relational databases in an on-demand computing cloud. If they deliver what they promise, we can instantly scale Drupal without having to embrace a different computing model and without having to do all of the heavy lifting. Specifically exciting is the fact that Elastra teamed up with [EnterpriseDB](https://www.enterprisedb.com/) to make their version of PostgreSQL virtually expand across multiple Amazon EC2 nodes. I've already reached out to Elastra, EnterpriseDB and Sun to keep tabs on what is happening.

Hopefully, companies like Elastra, EnterpriseDB, Amazon and Sun will move fast because I can't wait to see relational databases live in the cloud ...
