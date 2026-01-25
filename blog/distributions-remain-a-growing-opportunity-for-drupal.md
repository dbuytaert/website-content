---
url: 'https://dri.es/distributions-remain-a-growing-opportunity-for-drupal'
title: 'Distributions remain a growing opportunity for Drupal'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2017-02-14T14:40:01-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
  - Acquia
  - 'Drupal distributions'
published: true
id: 3881
---

# Distributions remain a growing opportunity for Drupal

Yesterday, after publishing a blog post about [Nasdaq's Drupal 8 distribution for investor relations websites](https://dri.es/how-nasdaq-offers-a-drupal-distribution-as-a-service), I realized I don't talk enough about "Drupal distributions" on my blog. The ability for anyone to take Drupal and build their own distribution is not only a powerful model, but something that is relatively unique to Drupal. To the best of my knowledge, Drupal is still the only content management system that actively encourages its community to build and share distributions.

A Drupal distribution packages a set of contributed and custom modules together with Drupal core to optimize Drupal for a specific use case or industry. For example, [Open Social](https://www.drupal.org/project/social) is a free Drupal distribution for creating private social networks. Open Social was developed by [GoalGorilla](https://www.goalgorilla.com), a digital agency from the Netherlands. The United Nations is currently migrating many of their own social platforms to Open Social.

Another example is [Lightning](https://www.drupal.org/project/lightning), a distribution developed and maintained by [Acquia](https://www.acquia.com). While Open Social targets a specific use case, Lightning provides a framework or starting point for any Drupal 8 project that requires more advanced layout, media, workflow and preview capabilities.

For more than 10 years, I've believed that [Drupal distributions are one of Drupal's biggest opportunities](https://dri.es/drupal-distributions). As I wrote back in 2006: <q>Distributions allow us to create ready-made downloadable packages with their own focus and vision. This will enable Drupal to reach out to both new and different markets.</q>.

To capture this opportunity we needed to (1) make distributions less costly to build and maintain and (2) make distributions more commercially interesting.

### Making distributions easier to build

Over the last 12 years we have evolved the underlying technology of Drupal distributions, making them even easier to build and maintain. We began working on distribution capabilities in 2004, when the CivicSpace Drupal 4.6 distribution was created to support Howard Dean's presidential campaign. Since then, every major Drupal release has advanced Drupal's distribution building capabilities.

The release of Drupal 5 marked a big milestone for distributions as we introduced a web-based installer and support for "installation profiles", which was the foundational technology used to create Drupal distributions. We continued to make improvements to installation profiles during the Drupal 6 release. It was these improvements that resulted in an explosion of great Drupal distributions such as [OpenAtrium](https://www.drupal.org/project/openatrium) (an intranet distribution), [OpenPublish](https://www.drupal.org/project/openpublish) (a distribution for online publishers), [Ubercart](https://www.drupal.org/project/ubercart) (a commerce distribution) and [Pressflow](http://pressflow.org) (a distribution with performance and scalability improvements).

Around the release of Drupal 7, we added distribution support to Drupal.org. This made it possible to build, host and collaborate on distributions directly on Drupal.org. Drupal 7 inspired another wave of great distributions: [Commerce Kickstart](https://www.drupal.org/project/commerce_kickstart) (a commerce distribution), [Panopoly](https://www.drupal.org/project/panopoly) (a generic site building distribution), [Opigno LMS](https://www.drupal.org/project/opigno_lms) (a distribution for learning management services), and more! Today, Drupal.org lists over 1,000 distributions.

Most recently we've made another giant leap forward with Drupal 8. There are at least 3 important changes in Drupal 8 that make building and maintaining distributions much easier:

1. Drupal 8 has vastly improved dependency management for modules, themes and libraries thanks to support for [Composer](https://getcomposer.org).
2. Drupal 8 ships with a new configuration management system that makes it much easier to share configurations.
3. We moved a dozen of the most commonly used modules into Drupal 8 core (e.g. Views, WYSIWYG, etc), which means that maintaining a distribution requires less compatibility and testing work. It also enables an easier upgrade path.

[Open Restaurant](http://www.open.restaurant) is a great example of a Drupal 8 distribution that has taken advantage of these new improvements. The Open Restaurant distribution has everything you need to build a restaurant website and uses Composer when installing the distribution.

More improvements are already in the works for future versions of Drupal. One particularly exciting development is the [concept of "inheriting" distributions](https://www.drupal.org/node/1356276), which allows Drupal distributions to build upon each other. For example, Acquia Lightning could "inherit" the standard core profile – adding layout, media and workflow capabilities to Drupal core, and Open Social could inherit Lightning - adding social capabilities on top of Lightning. In this model, Open Social delegates the work of maintaining Layout, Media, and Workflow to the maintainers of Lightning. It's not too hard to see how this could radically simplify the maintenance of distributions.

The less effort it takes to build and maintain a distribution, the more distributions will emerge. The more distributions that emerge, the better Drupal can compete with a wide range of turnkey solutions in addition to new markets. Over the course of twelve years we have improved the underlying technology for building distributions, and we will continue to do so for years to come.

### Making distributions commercially interesting

In 2010, after having built a couple of distributions at Acquia, I used to joke that distributions are the "most expensive lead generation tool for professional services work". This is because monetizing a distribution is hard. Fortunately, we have made progress on making distributions more commercially viable.

At Acquia, [our Drupal Gardens product](https://dri.es/drupal-gardens) taught us a lot about how to monetize a single Drupal distribution through a SaaS model. We discontinued Drupal Gardens but turned what we learned from operating Drupal Gardens into Acquia Cloud Site Factory. Instead of hosting a single Drupal distribution (i.e. Drupal Gardens), we can now host any number of Drupal distributions on Acquia Cloud Site Factory.

This is why [Nasdaq's offering](https://dri.es/how-nasdaq-offers-a-drupal-distribution-as-a-service) is so interesting; it offers a powerful example of how organizations can leverage the distribution "as-a-service" model. Nasdaq has built a custom Drupal 8 distribution and offers it as-a-service to their customers. When Nasdaq makes money from their Drupal distribution they can continue to invest in both their distribution and Drupal for many years to come.

In other words, distributions have evolved from an expensive lead generation tool to something you can offer as a service at a large scale. Since 2006 we have known that [hosted service models are more compelling](https://dri.es/long-live-the-web-services-loophole) but unfortunately at the time the technology wasn't there. Today, we have the tools that make it easier to deploy and manage large constellations of websites. This also includes providing a 24x7 help desk, SLA-based support, hosting, upgrades, theming services and go-to-market strategies. All of these improvements are making distributions more commercially viable.
