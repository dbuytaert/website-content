---
url: 'https://dri.es/mollom-protecting-drupal-gardens-against-spam'
title: 'Mollom protecting Drupal Gardens against spam'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2010-06-17T09:05:01-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
  - Mollom
  - 'Drupal Gardens'
published: true
id: 1711
---

# Mollom protecting Drupal Gardens against spam

[Acquia](https://www.acquia.com) recently wrapped up [its latest internal development sprint](http://www.drupalgardens.com/content/removing-mittens-drupal-gardens-june-10-update). One new development that was announced is the fact that [Drupal Gardens](http://drupalgardens.com) is now protected by [Mollom's spam protection services](https://mollom.com).

What does this mean for Drupal Gardens users? Just what you'd think. You receive the best spam protection available on the web from [Mollom](https://mollom.com). There is no setup, no hassle, and no cost.

What does this mean for developers? A great example of how to provide Mollom to your customers, in the form of the [Mollom API module](https://www.drupal.org/project/mollomapi) for [Drupal](https://www.drupal.org). The Mollom API module was [developed by Jacob Singh and Gábor Hojtsy](https://www.acquia.com/blog/mollom-provisioning-api) from [Acquia](https://www.acquia.com). The [Mollom API module](https://www.drupal.org/project/mollomapi) uses [Mollom's Reseller API](https://www.mollom.com/api/mollom-reseller-api) to automatically provision the service and to programmatically obtain public and private keys for each Drupal Gardens site.
