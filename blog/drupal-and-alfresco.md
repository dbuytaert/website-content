---
url: 'https://dri.es/drupal-and-alfresco'
title: 'Drupal and Alfresco'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2009-02-23T09:23:01-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
  - Acquia
  - Alfresco
published: true
id: 605
---

# Drupal and Alfresco

[Alfresco](http://alfresco.com) and [Optaros](http://optaros.com), in conjunction with [Acquia](https://www.acquia.com), have made available a set of Drupal modules that integrate Drupal with Alfresco using the [CMIS APIs](http://wiki.alfresco.com/wiki/CMIS). See the [CMIS module](https://www.drupal.org/project/cmis) and the [CMIS Alfresco module](https://www.drupal.org/project/cmis_alfresco) on [drupal.org](https://www.drupal.org).

It all started with [my Amnesty blog post](https://dri.es/amnesty-using-drupal) a year or two ago. A lot of people mailed me asking me if I could find out more about Amnesty's Drupal Alfresco integration. I've had ongoing discussions with Alfresco ever since, and [Matt Asay](https://www.cnet.com/openroad/) (VP of Business Development at Alfresco) assigned Yong Qu to do the initial integration work. Optaros, who has extensive experience with both Drupal and Alfresco (they are partners with both [Alfresco](http://alfresco.com) and [Acquia](https://www.acquia.com)), [saw a similar demand in the market](http://www.optaros.com/blogs/drupal-alfresco-integration-and-alfrescos-move-front-end) and joined the integration effort. They have since built on top Alfresco's initial implementation and released the two Drupal modules on drupal.org.

Jeff Pots from [Optaros](http://optaros.com) provides a lot of details in [his blog post](https://mrm-mccann.com/optaros.html).

These modules mark a first step towards enterprise-grade document management support for Drupal – something enterprise users have asked for a lot. What is also cool about this approach is that different Drupal sites can share a single repository of assets. Images and other media assets from one site could be shared with different sub-sites, for example. Futhermore, the CMIS interface, which operates independently of the Alfresco integration, enables your Drupal site to connect with different content repositories. As indicated in a previous blog post, [this could be a big deal](https://dri.es/cmis) if enough vendors adopt [CMIS](http://wiki.alfresco.com/wiki/CMIS).

It is still very early and there is plenty of work left to be done. The high level roadmap for the modules is available in the module descriptions on drupal.org. Now that the foundation of the integration is in place, the goal is to improve the work based on customer demand, and if available, with help from the community.
