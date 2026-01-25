---
url: 'https://dri.es/scaling-with-mysql-replication'
title: 'Scaling with MySQL replication'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2007-07-13T11:05:40-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
  - 'Web performance'
  - MySQL
published: true
id: 297
---

# Scaling with MySQL replication

To deal with Drupal's growth, we're adding a second database server to [drupal.org](https://www.drupal.org) which is useful for at least two reasons. First, we'll be able to handle more SQL queries as we can distribute them between multiple database servers *(load balancing)*. Secondly, this new server can act as a "hot spare" that can immediately take over if the other database server fails *(high availability / fail-over)*.

The current plan is to configure both database servers in [master-slave configuration](https://dev.mysql.com/doc/refman/8.0/en/replication.html), which is the most common replication model for websites. This model provides scalability, but not necessarily fail-over. With a master-slave configuration, all data modification queries (like `INSERT`, `UPDATE` and `DELETE` queries) are sent to the master. The master writes updates to a binary log file, and serves this log file to the slaves. The slaves read the queries from the binary log, and execute them against their local copy of the data. While all data modification queries go to the master, all the read-only queries (most notably the `SELECT` queries) can be distributed among the slaves. By following this model, we can spread the workload amongst multiple database servers. And as Drupal.org's traffic continues to grow, we can scale horizontally by adding more slaves.

While MySQL does the database replication work, it doesn't do the actual load balancing work. That is up to the application or the database abstraction layer to implement. To be able to distribute queries among multiple database servers, the application needs to distinguish between data modification queries and read-only queries.

Care needs to be taken, as the data on the slaves might be slightly out of sync. It may or may not be practical to guarantee a low-latency environment. In those cases, the application might want to require that certain read-only queries go to the master.

There are different ways to accomplish this:

- [Drupal](https://www.drupal.org) executes all SQL queries through `db_query()`. Traditionally, big Drupal sites manually patched `db_query()` to use query parsing (regular expression foo) to separate read queries from write queries. This is not convenient and it doesn't provide a good solution to deal with lag. Fortunately, work is being done to provide [better support for database replication](https://www.drupal.org/node/147160) in Drupal 6. It's our intend to backport this to Drupal 5 so we can use it on drupal.org until Drupal 6 has been released and drupal.org has been upgraded to use Drupal 6.
- [MediaWiki](https://www.mediawiki.org/), the software behind [Wikipedia](http://wikipedia.org) uses [$db-&gt;select() and $db-&gt;insert()](https://www.mediawiki.org/wiki/Manual:Database_access). They have some documented best practices to deal with lag.
- Neither the [Pear DB database abstraction layer](https://pear.php.net/package/DB) or its successor [Pear MDB2](https://pear.php.net/package/DB) seem to support database replication.
- [Wordpress](http://wordpress.org) uses [HyperDB](http://svn.wp-plugins.org/hyperdb/trunk/), a drop-in replacement for Wordpress' default database abstraction layer that provides support for replication. It was developed for use on [Wordpress.com](https://wordpress.com), a mass hosting provider for WordPress blogs. Because HyperDB is a drop-in replacement, they don't have a clean API and just like Drupal 5, they have to use query parsing to separate read queries from write queries. It's not clear how they deal with lag.
- [Joomla! 1.0](https://joomla.org) does not separate read queries from write queries, but Joomla! 1.5 will use functions like `$db->insertObject()` and `$db->updateObject()`. Joomla! 1.5 won't support replication out of the box, but their API allows a clean drop-in replacement to be developed. It's not clear how they would deal with lag.
- [PostNuke](http://postnuke.org) uses the [ADOdb database abstraction library](http://adodb.sourceforge.net/), which at first glance does not support database replication either.
- Java applications use the [statement.executeQuery() and statement.executeUpdate()](http://download.oracle.com/javase/1.5.0/docs/api/java/sql/Statement.html) that are part of the standard class libraries. It's not clear how they deal with lag.

What other popular applications support database replication, and what do their APIs look like? I'd like to find out what the ideal API looks like so we can still push that for inclusion in Drupal 6.

Based on the research above, I think we should get the best of all worlds by introducing these three functions (and deprecating `db_query()`):

1. `db_select_slave(); // results might be slightly out of date`
2. `db_select_master(); // results always up to date`
3. `db_update(); // for UPDATE, INSERT, DELETE, etc`

Even if they don't actually do anything useful in Drupal 6, and just map onto the deprecated `db_query()`, they set a better standard, and they allow for a drop-in replacement to be developed during Drupal 6's lifetime. Ideally, however, Drupal 6 would ship with a working implementation.
