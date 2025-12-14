---
title: 'Database replication lag'
date: '2007-08-24T03:02:27-04:00'
author: Dries
tags:
  - Drupal
  - 'Web performance'
  - MySQL
published: true
type: blog
url: /database-replication-lag
id: 317
---

As explained in [an earlier blog post](https://dri.es/scaling-with-mysql-replication), we recently started using MySQL master-slave replication on [drupal.org](https://www.drupal.org) in order to provide the scalability necessary to accommodate our growing demands. With one or more replicas of our database, we can instruct Drupal to distribute or load balance the SQL workload among different database servers.

MySQL's master-slave replication is an asynchronous replication model. Typically, all the mutator queries (like INSERT, UPDATE, DELETE) go to a single master, and the master propagates all updates to the slave servers without [synchronization or communication](https://en.wikipedia.org/wiki/Two-phase_commit). While the asynchronous nature has its advantages, it is also means that the slaves might be (slightly) out of sync.

Consider the following pseudo-code:

```php
$nid = node_save($data);
$node = node_load($nid);

```

Because `node_save()` executes a mutator query (an INSERT or UPDATE statement) is has to be executed on the master, so the master can propagate the changes to the slaves. Because `node_load()` uses a read-only query, it can go to the master or any of the available slaves. Because of the lack of synchronization between master and slaves, there is one obvious caveat: when we execute `node_load()` the slaves might not have been updated. In other words, unless we force `node_load()` to query the master, we risk not being able to present the visitor the data that he just saved. In other cases, we risk introducing data inconsistencies due to the race conditions.

So what is the best way to fix this?

1. Our current solution on drupal.org is to execute all queries on the master, except for those that we know can't introduce race conditions. In our running example, this means that we'd chose to execute all `node_load()`s on the master, even in absence of a `node_save()`. This limits our scalability so this is nothing but a temporary solution until we have a good solution in place.
2. One way to fix this is to switch to a synchronous replication model. In such a model, all database changes will be synchronized across all servers to ensure that all replicas are in a consistent state. MySQL provides a synchronous replication model through the [NDB cluster storage engine](https://dev.mysql.com/doc/refman/8.0/en/mysql-cluster-overview.html). Stability issues aside, MySQL's cluster technology works best when you avoid JOINs and sub-queries. Because Drupal is highly relational, we might have to rewrite large parts of our code base to get the most out of it.
3. Replication and load balancing can be left to some of the available proxy layers, most notably [Continuent's Sequoia](http://sequoia.continuent.org/) and [MySQL Proxy](https://www.mysql.com/wiki/MySQL_Proxy/). Drupal connects to the proxy as if it was the actual database, and the proxy talks to the underlying databases. The proxy parses all the queries and propagates mutator queries to all the underlying databases to make sure they remain in a consistent state. Reads are only distributed among the servers that are up-to-date. This solution is transparent to Drupal, and should work with older versions of Drupal. The only downside is that it not trivial to setup, and based on my testing, it requires quite a bit of memory.
4. We could use database partitioning, and assign data to different shards in one way or another. This would reduce the replica lag to zero but as we don't have that much data or database tables with millions of rows, I don't think partitioning will buy drupal.org much.
5. Another solution is to rewrite large parts of Drupal so it is "replication lag"-aware. In its most naive form, the `node_load()` function in our running example would get a second parameter that specifies whether the query should be executed on the master or not. The call should then be changed to `node_load($nid, TRUE)` when proceeded by a `node_save()`. I already [concluded through research](https://dri.es/scaling-with-mysql-replication) that this is not commonly done; probably because such a solution still doesn't provide any guarantees across page request.
6. A notable exception is [MediaWiki](https://www.mediawiki.org/), the software behind [Wikipedia](http://wikipedia.org) which has some documented best practices to deal with replication lag. Specifically, they recommend to query the master (using a very fast query) to see what version of the data they have to retrieve from the slave. If the specified version is not yet available on the slave due to replication lag, they simply wait for it to become available. In our running example, each node should get a version number and `node_load()` would first retrieve the latest version number from the master and then use that version number to make sure it gets an up-to-date copy from the slave. If the right version isn't yet available, `node_load()` will try loading the data again until it becomes available.
