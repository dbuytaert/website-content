---
url: 'https://dri.es/playing-with-new-relic-on-acquia-hosting'
title: 'Playing with New Relic on Acquia Hosting'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2010-12-16T17:17:25-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
  - Acquia
  - 'Acquia Cloud'
  - 'My site'
published: true
id: 2041
---

# Playing with New Relic on Acquia Hosting

During the past month, I've been trying [New Relic](http://newrelic.com) on my personal blog. New Relic is a performance management tool. It can help to monitor, debug and optimize a site. It includes features like slow page request analysis, slow database query analysis, error tracking, scalability analysis, performance alerts, weekly e-mail reports, up-time monitoring and even very specialized features like Apache Solr profiling. It's a bundle of developer goodies that can be used on live production websites.

I'm a bit of a profiling geek. In my previous life, I spent a lot of time working on production profiling and performance optimization of Java applications. So when New Relic recently announced that they're working on support for PHP applications, I wanted to give it a try.

We began testing [New Relic](http://newrelic.com) when the PHP version was still in beta. We believe it can make for a great service to add to [Acquia Hosting](https://www.acquia.com/products-services/acquia-managed-cloud) and the [Acquia Network](https://www.acquia.com/products-services/acquia-network). My site is hosted on Acquia Hosting which is why I have been testing it on my site. So far the testing has been good. We've helped New Relic fix a number of bugs during the beta test period, and in return New Relic has helped us to discover a performance problem in one of our deployment scripts on Acquia Hosting. Proof that New Relic is useful!

Now that we are past internal testing, I am excited to say that we will soon be bundling New Relic into the Acquia Network. Every Acquia customer will soon get access to a premium version of New Relic's monitoring tools at no additional charge – whether you are hosting with us or not. Expect more detail from us soon on how to access New Relic as a subscriber.

New Relic requires a small 'agent' to be installed on your web server. The agent hooks into the PHP interpreter and sends the relevant information to a back-end for analysis and visualization. Because it hooks into the PHP interpreter, it can provide that deep, code-level visibility that is useful when debugging a performance problem. The New Relic agent also adds extra Drupal specific instrumentation – and will probably add more over time.

I've only used it on my personal site, which currently runs on a regular Drupal 6. However, I'm quite keen to unleash it on a Drupal 7 installation to see what we can learn. In the mean time, I'm including some screenshots of what my personal blog looks like according to New Relic. If you're interested in improving the performance of your site and are a profiling geek like me, you should give New Relic a try.

![](http://default/files/images/new-relic/announcement-1.jpg)
*New Relic uses <a href="http://en.wikipedia.org/wiki/Apdex">Apdex</a>, an industry standard for measuring the satisfaction of a user of an application or service.*
![](http://default/files/images/new-relic/announcement-2.jpg)
*New Relic conveniently separates database performance from PHP performance. On a busy system, that makes it easy to pinpoint bottlenecks.*
![](http://default/files/images/new-relic/announcement-3.jpg)
*New Relic tries to annotate performance problems to 'controllers' rather than to specific URLs. Thus, it automatically extracts 'Drupal page callbacks'. This is nice because when an application has thousands of unique URLs \(<code>/article/11/19/why-mysql-is-cool</code> and <code>/article/11/19/postgres-is-cool</code> and so on\) that are all handled by the same controller \(e.g. <code>node\_page\_view\(\)</code>\).*
![](http://default/files/images/new-relic/announcement-4.jpg)
*This graph shows that most of my database time is spent reading and writing to the <code>accesslog</code> MySQL table. By disabling the access log feature in Drupal, I could reduce my database load roughly in half.*
