---
url: 'https://dri.es/acquia-hosting-now-available'
title: 'Acquia Hosting now available '
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2009-09-03T04:44:07-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
  - Acquia
  - 'Acquia Cloud'
published: true
id: 976
---

# Acquia Hosting now available 

For a number of months now, [my personal website](https://dri.es) ran on a development version of [Acquia Hosting](https://www.acquia.com/products-services/acquia-managed-cloud) (previously referred to with the code name [Acquia Fields](https://dri.es/acquia-2009-roadmap)). There is nothing better than eating your own dog food. You have to eat a lot of it, and you have to start eating it early on. Either way, today at DrupalCon, we announced that Acquia Hosting is commercially available. In this post, I want to talk a little bit about what we have built and why we believe it matters.

The $4 billion web hosting industry is fiercely competitive with thousands of hosting companies. Nonetheless, we believe that there is a market need for specialized Drupal hosting – every day I see people struggle with hosting their Drupal sites. Our goal is to offer the best hosting for medium to large Drupal sites. Acquia's hosting offering will differ from generic hosting in at least two ways. First, our infrastructure will be carefully tuned and optimized for Drupal and our deployment tools will be streamlined for Drupal development. Second, we provide technical support for your Drupal site, the Drupal application, and all of the underlying infrastructure. Because we have some of the best Drupal people, we can help you scale your site to millions of page views, and more if necessary.

At the moment, my personal website is running on a 6 server cluster with redundant web nodes and database servers optimized for Drupal. Currently, the infrastructure is provided by Amazon AWS. The web nodes are load-balanced with Nginx and all content is replicated to two database servers that are configured in master-master configuration. Files are stored in a highly-available network filesystem on top of EBS volumes with frequent off-site backups. For deployment purposes, we provide each site owner a SVN repository which we use to keep all web nodes synchronized and to orchestrate the roll-out of multi-server updates. A staging server is also available. Everything is monitored with multiple triggers and notification methods in place to our operations team to assure high availability.

The creation and configuration of these server clusters is fully automated – we can get large sites up and running with their own dedicated cluster in 10 minutes. While a dedicated server cluster is great for high-end Drupal users with huge or mission-critical Drupal sites, we acknowledge that most people have more modest requirements. While we can easily provision a dedicated cluster, we expect the majority of people using Acquia Hosting to benefit from resource sharing. Customers who are on a shared cluster will benefit from high availability, high performance, and virtually unlimited scalability at an affordable price. Unlike other providers' shared hosting offerings, our shared cluster hosting is optimized for Drupal sites and backed by support from Acquia.

To date, we spent most of our effort building out a scalable infrastructure that is highly-available. The next couple of months we intend to shift our focus to performance. We'll offer memcached servers, reverse proxies and integration with one or more content delivery networks.

We have a great team of people building and supporting Acquia Hosting. Barry Jaspan is the product manager and technical lead. Kevin Rego was previously part of a team that supported 3000+ servers for hosting customers like the Chicago Tribune. Jacob Singh built, profiled and optimized sites like Amnesty International. Paul Lovvik wrote rich JavaScript applications that handled over 25 million e-mail inboxes. Kurt Gray has over a decade of experience in LAMP stack scaling and was responsible for scaling Slashdot.org, SourceForge.net, ThinkGeek.com, and Linux.com. Robert Douglas is the original author of the memcached module for Drupal, and helped build and scale sites for MTV UK, Sony Music, Lifetime TV and more. Kevin Hankens helped scale Velonews to up to 23 million page views a month. Peter Wolanin is the author of many Drupal 5 and Drupal 6 performance improvements, and together with Jacob Singh, built our scalable and high availability Acquia Search product. We also contracted with Narayan Newton who helps to keep drupal.org running. And this is just a sampling of the team's experience.

At [Acquia](https://www.acquia.com), we like building products and services that push Drupal forward. Specialized cloud hosting for Drupal can provide a healthy revenue stream for Acquia, but high-end Drupal hosting is just as important for Drupal's continued adoption in the enterprise.
