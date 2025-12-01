---
title: 'Acquia Search: benefits for site administrators'
date: '2009-07-01T06:33:13-04:00'
author: Dries
tags:
  - Drupal
  - Acquia
  - 'Acquia Search'
published: true
type: blog
url: /acquia-search-benefits-for-site-administrators
id: 731
---

Yesterday [we took the beta-wraps off of Acquia Search](https://dri.es/acquia-search-available-commercially), and I followed up with a post about [why Acquia Search matters for site visitors](https://dri.es/acquia-search-benefits-for-visitors). We're still having some good discussions in the comments and the Twitter-sphere, but today I want to talk a bit more about the technical details. How does Acquia Search work, what does our infrastructure look like, and why is it a great deal for site owners?

Acquia Search is a hosted search service based on the *Software as a Service* (SaaS) model. The way it works is that Drupal sites push their content to the search servers hosted by Acquia. We index the content, build an index, and handle search queries. We provide the search results, facets, and content recommendations to your Drupal site over the network.

Your site's data is protected in transit by SSL and by HMAC authentication in the Acquia Network. Plain english? The data is encrypted so anyone snooping in the middle can't read it and the request is authenticated which means that the Acquia Network knows you sent the request you claimed to, and you know that messages received from the network are legitimate.

Acquia Search is built using the Open Source [Lucene](http://lucene.apache.org/) and [Solr](http://lucene.apache.org/solr/) distributions from the Apache project. If you want to install, run and maintain Lucene and Solr yourself, and you have the resources to do so, you can. All the code, including our contributions to the [Apache Solr integration modules for Drupal](https://www.drupal.org/project/apachesolr), are available as Open Source.

However, many organizations simply lack the Java expertise to deploy, manage and scale Java applications – or their hosting environment may not accommodate it. Because Acquia Search is a hosted service, it takes away the burden of installation, configuration, and operational duties to keep the software fast, secure and up-to-date. That's our job.

As a reference, we've spent the last 9 months developing [Acquia Search](https://www.acquia.com/products-services/acquia-search) with the equivalent of three full-time employees. This also included setting up a billing system, integrating our support system, connecting it to the Acquia Network, performance testing and tuning, and more. Other Acquians helped out with the infrastructure, quality assurance, product management, design, and documentation. It was a non-trivial amount of work.

The result of these efforts is that we can launch any number of Solr farms on [Amazon EC2](https://aws.amazon.com/ec2/). For high-performance and high-availability, each farm has a master Solr server and one or more slave Solr servers. A load balancer pushes content changes to the master Solr server, which are replicated by the slave servers. The load balancer makes sure that most regular search queries are done against the slave servers. Because multiple servers can handle your site's search requests, Acquia Search is fast and can scale, but it also means that Acquia Search is very robust because it can survive a server failure. As I wrote yesterday, [Acquia Search is faster that Drupal's built-in search](https://dri.es/acquia-search-benefits-for-visitors) – especially for large sites.

In most scenarios, several Drupal sites share a single Solr farm – by sharing resources, we can offer a high-performance and high-availability search solution to small sites at relative cheap price point. For really big sites, we can provision a dedicated farm and scale out Solr so that it can handle millions of search queries.

Once you begin to use our search service you'll be able to disable Drupal's built-in core search. When you do this you reduce the amount of memory and processing power needed by your own infrastructure. As we've learned with big sites like [drupal.org](https://www.drupal.org), Drupal's built-in search can bring a large site to its knees. With Acquia Search, you can avoid the drain.

On the front-end, we made significant contributions to the [Apache Solr Search Integration modules on drupal.org](https://www.drupal.org/project/apachesolr). We helped add new features, improve the usability, and iron out a legion of bugs that cropped up during the beta period. The top-3 most active maintainers of the Apache Solr module are all Acquia employees, respectively Peter Wolanin, Robert Douglass, and Jacob Singh. As a result, Peter, Robert and Jacob are sometimes referred to as [Acquia's three Apache Solr Musketeers](http://coderamblings.com/story/hotties-drupal-planet).

[image acquia/drupal-apache-solr-committers resize=false]

All things combined, Acquia Search makes it staggeringly simple and low-cost to get better search on your site. You can get started in minutes and you don't have to worry about installing, upgrading, monitoring, or scaling the software. In short, we built an enterprise-quality, highly-available, secure, scalable, and fast indexing search solution that we believe Drupal was missing – especially for the enterprise.
