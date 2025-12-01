---
title: 'Acquia Hosting: an update after 8 months of Drupal hosting'
date: '2010-05-14T08:52:46-04:00'
author: Dries
tags:
  - Drupal
  - Statistics
  - Acquia
  - 'Acquia Cloud'
published: true
type: blog
url: /acquia-hosting-update-after-8-months-of-drupal-hosting
id: 1622
---

Roughly 8 months ago at DrupalCon Paris, [we launched Acquia Hosting](https://dri.es/acquia-hosting-now-available). In this blog post, I wanted to give a quick update on where we are after 8 months.

### Current status

For those who don't know, [Acquia Hosting](https://www.acquia.com/products-services/acquia-managed-cloud) is a highly-available cloud-based hosting platform tuned for Drupal performance and scalability. From a technology point of view, [we've built tools to automatically launch multi-server hosting environments](https://www.acquia.com/blog/acquia-hosting-automated-provisioning-system) optimized for [Drupal](https://www.drupal.org). It is built on [Amazon Web Services](http://aws.amazon.com) (i.e. [Amazon EC2](https://aws.amazon.com/ec2/), [Amazon S3](https://aws.amazon.com/s3/), etc) using Open Source components such as [Varnish](http://varnish-cache.org/), [Puppet](https://puppet.com/), [GlusterFS](https://www.gluster.org/), [NginX](http://nginx.org/) and more. If you are interested in the technical details, I highly recommend watching [Barry Jaspan's DrupalCon San Francisco presentation on the challenges of hosting Drupal on AWS](https://archive.org/details/ChallengesOfHostingDrupalOnAws) – I'm biased, but it is the best technical presentation that I've seen on hosting websites on Amazon Web Service (AWS). Highly recommended. The presentation is the result of 2.5 years of experience building products exclusively on [Amazon Web Services](http://aws.amazon.com) and having to maintain close to 200 EC2 instances.

At [Acquia](https://www.acquia.com), we're all very proud of what we've built. For example, we were recently able to have a new, enterprise-scale Acquia Hosting customer online only a few days after they first contacted us. It takes most hosting companies weeks or months to roll out, configure and tweak all the servers required to host a high-traffic traffic sites like this one. In just a few days, we scaled past the limits of their previous hosting provider and [flawlessly served 3 million page views per hour](https://www.acquia.com/blog/acquia-hosting-customer-hits-700-pagessecond-or-why-i-love-load-testing) (i.e. 830+ page views per second or 5000+ HTTP requests per second – yes, Drupal scales). I hope the customer will allow us to write-up a detailed case study at some point. It is a real success story for Drupal, Acquia Hosting, Amazon Web Services and cloud computing in general: incredible time to market, great performance and scalability. We've come a long way since we started working on a Drupal hosting product about a year ago.

The way we started work on Acquia Hosting is the way we have continued: with a very strong focus on engineering. Our first area of focus was on reliability. The results of this were: providing multiple, redundant web nodes; real-time database replication; backups; monitoring infrastructure (we track 25+ system parameters); customer isolation, and so on. Next, we focused our efforts on improving Acquia Hosting's performance by adding tools like Varnish for page caching; customer isolation; reorganizing parts of our underlying architecture; lots of tweaking to Apache, PHP and MySQL; and repeated rounds of realistic load testing. Along the way, we developed deployment tools to make it easy to roll-out and automatically configure our customers' EC2 instances – it takes just a matter of minutes to upgrade a site's capacity.

### Roadmap

Considering our costs and other metrics eight months into the hosting business adventure, the real value of our hosting offering comes not from the technology alone, but rather from our support team's work while getting customers' sites online and helping them day in, day out. Once servers are provisioned for a new site, getting customers up-and-running involves detailed site audits (making sure they don't have core hacks, analyzing their site architecture, etc.), teaching them how the Acquia Hosting environment works, helping them learn to best leverage clusters of servers, doing load testing, and helping them get over performance bottlenecks (slow or excessive SQL queries, expensive uncached Views or blocks, etc.). At the end of the day, our team's deep knowledge of Drupal and our technology stack are the essence and ultimate value-proposition of our Drupal hosting offering.

Going forward, a top priority is to make the process of getting new customers online easier for us and better for them. Among other things, that means developing more "self-service"-style systems, improved customer dashboards and documentation, and streamlined, focused support operations to make sure our customers are getting their questions answered and their problems fixed in the shortest time possible so they can worry about their business and not their websites.

### Free Acquia Hosting program

We also announced a [free Acquia Hosting program](https://www.acquia.com/products-services/acquia-managed-cloud/free-acquia-hosting). To help support the Drupal community, we give free Acquia Hosting to sites for non-profit groups that promote Drupal use and adoption. We're now hosting 25 community websites including [Drupal Edu](http://drupaledu.org/), [SpreadDrupal](http://spreaddrupal.org), [Drupal Dojo](http://drupaldojo.com), [Drupal Catalan](http://drupal.cat), [Design 4 Drupal Boston](https://boston2010.design4drupal.org/) and more. There are about 50 more Drupal community sites in the backlog waiting to get setup with an [Acquia Hosting](https://www.acquia.com/products-services/acquia-managed-cloud) account. Yet another reason to make it easier to get new users and customers up and running!
