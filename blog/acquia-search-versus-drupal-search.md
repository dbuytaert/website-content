---
title: 'Acquia Search versus Drupal search'
date: '2009-07-06T14:07:52-04:00'
author: Dries
tags:
  - Drupal
  - Acquia
  - 'Acquia Search'
published: true
type: blog
url: /acquia-search-versus-drupal-search
id: 781
---

It's been several days since [we launched Acquia Search commercially](https://dri.es/acquia-search-available-commercially). After reviewing the press, articles, comments, and tweets, I wanted to address the question of why we seem to care so much about search and why we can't simply improve Drupal's built-in search module. These questions came up during the beta test period as well, and have even [resonated with the WordPress community on Matt Mullenweg's blog](https://ma.tt/2009/07/acquia-searc/#comments). I feel they are important questions to address.

I've already partially answered these questions in two recent blog posts – [why Acquia Search matters for site administrators](https://dri.es/acquia-search-benefits-for-site-administrators) and [why Acquia Search matters for site visitors](https://dri.es/acquia-search-benefits-for-visitors) – but there is more to it.

First, at the end of the day, search is a hard but important problem. This is reflected by the size of the search market. Some have estimated the search market to be at least as big as the web content management market. The leading providers of site search technology such as [Autonomy](http://www.autonomy.com/), [FAST](https://www.microsoft.com/enterprisesearch) and [Endeca](http://endeca.com) have built large, successful businesses supplying search technology to the enterprise. Last year, FAST was acquired by Microsoft for $1.2 billion. Gartner forecasts that the enterprise search market will grow to more than $1.1 billion in total software revenue by 2011 (excluding professional service revenues). For many people in the Drupal community, these data points will probably come as a surprise.

Reality is that for a certain class of websites – like intranets or e-commerce websites – search can be the most important feature of the entire site. Faceted search can really increase your conversions if you have an e-commerce website, or can really boost the productivity of your employees if you have a large intranet. For those organizations, Drupal's built in search is simply not adequate. We invested in search because we believe that for many of these sites, enterprise-grade search is a requirement.

Secondly, why don't we just implement improvements in Drupal's core search module? As I've noted, search is a difficult problem – it is hard for Drupal to compete with enterprise-grade search engines, to keep up with advances in search technology, and to do both while continuing to run in shared hosting environments. Instead, Acquia Search leverages the Open Source [Lucene](http://lucene.apache.org/) and [Solr](http://lucene.apache.org/solr/) distributions from the Apache project.

The search module shipped with Drupal core has its purpose and target audience. It isn't right for everyone, just as [Acquia Search](https://www.acquia.com/products-services/acquia-search) is not for everyone. Both are important, not just for the Drupal community at large, but also for many of Acquia's own customers. Regardless, there is no question that we need to keep investing and improving Drupal's built-in search. The search module that is built into Drupal 7 already has improvements over the one in Drupal 6, in part because of Acquia's support of the [Search sprint in Minnesota](https://groups.drupal.org/node/4102/minnesota-search-sprint).

I'm hopeful that we can scale up our investments in Acquia Search as we grow the search component of our business. There is a lot more we can do, so I'd like to see us become active contributors to Apache Lucene and Solr, as well as continue to ramp our contributions to the [different Apache Solr projects on drupal.org](https://www.drupal.org/project/apachesolr), as well as Drupal core's built-in search.
