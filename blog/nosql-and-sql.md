---
title: 'NoSQL and SQL'
date: '2009-12-04T07:05:03-05:00'
author: Dries
tags:
  - MySQL
published: true
type: blog
url: /nosql-and-sql
id: 1241
---

Have a look at this video of [Brian Aker](https://en.wikipedia.org/wiki/Brian_Aker)'s great 10 minute lightning talk about [NoSQL](https://en.wikipedia.org/wiki/Nosql). NoSQL is a database movement which promotes non-relational data stores that do not need a fixed schema.

With the exception of [Memcached](http://memcached.org/), the [Drupal](https://www.drupal.org) world is very SQL driven – and for all the right reasons. However, both at [Mollom](https://mollom.com) and [Acquia](https://www.acquia.com) we have to deal with [some big data volumes](https://dri.es/hundred-million-spam-attempts-blocked) and have been using some of the NoSQL technologies like [Hadoop](http://hadoop.apache.org/), [Thrift](http://thrift.apache.org/), [Hbase](http://hbase.apache.org/), [Tokio Cabinet](http://1978th.net/tokyocabinet/), etc.

While these are great tools, at the end of the day, NoSQL is an "and" and not a "versus". Plus, I expect the gap to close as there are a couple of interesting projects under way that bring some of the NoSQL advantages to the SQL world. One of them is Brian Aker's own [Drizzle project](https://launchpad.net/drizzle), another project I can't talk about yet ... Sufficient to say, don't ditch your relation database just yet.

Either way, have a look [Brian's NoSQL presentation](https://www.youtube.com/watch?v=LhnGarRsKnA). *It's funny!*

[video LhnGarRsKnA]
