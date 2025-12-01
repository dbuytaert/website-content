---
title: 'Effortless inspecting of Drupal database queries'
date: '2023-12-28T09:45:51-05:00'
author: Dries
tags:
  - Drupal
  - MySQL
published: true
type: note
url: /effortless-inspecting-of-drupal-database-queries
id: 5536
---

Drupal's database abstraction layer is great for at least two reasons. First, it ensures compatibility with various database systems like MySQL, MariaDB, PostgreSQL and SQLite. Second, it improves security by preventing SQL injection attacks.

My main concern with using any database abstraction layer is the seemingly reduced control over the final SQL query. I like to see and understand the final query.

To inspect and debug database queries, I like to use **MariaDB's General Query Log**. When enabled, this feature captures every query directly in a text file.

I like this approach for a few reasons:

- It directly captures the query in MariaDB instead of Drupal. This provides the most accurate view of the final SQL queries.
- It enables real-time monitoring of all queries in a separate terminal window, removing the need to insert debug statements into code.
- It records both successful and unsuccessful queries, making it a handy tool for debugging purposes.

If you're interested in trying it out, here is how I set up and use MariaDB's General Query Log.

First, log in as the MySQL super user. Since I'm using [DDEV](https://ddev.com/) for my development, the command to do that looks like this:

```shell
$ ddev mysql -u root -proot
```

After logging in as the MySQL super user, you need to set a few global variables:

```shell
SET global general_log = 1;

SET global log_output = 'file';

SET global general_log_file = '/home/dries/queries.txt';
```

This will start logging all queries to a file named 'queries.txt' in my home directory.

DDEV employs containers, isolated environments designed for operating specific software such as databases. To view the queries, you must log into the database container.

```shell
$ ddev ssh -s db
```

Now, you can easily monitor the queries in real-time from a separate terminal window:

```shell
$ tail -f /home/dries/queries.txt
```

This is a simple yet effective way to monitor all database queries that Drupal generates.
