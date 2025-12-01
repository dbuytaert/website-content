---
title: 'JSON:API lands in Drupal core'
date: '2019-03-21T09:25:35-04:00'
author: Dries
summary: 'Drupal core now provides an out-of-the-box JSON:API implementation, marking another major milestone towards making Drupal API-first.'
image: drupal/json-api-crane
tags:
  - Drupal
  - 'Web services'
  - 'Headless Drupal'
published: true
type: blog
url: /jsonapi-lands-in-drupal-core
id: 4796
---

[image drupal/json-api-crane]

Breaking news: we just committed the JSON:API module to the development branch of Drupal 8.

In other words, JSON:API support is coming to *all* Drupal 8 sites in just a few short months! ?

This marks another important milestone in Drupal's evolution to be an API-first platform optimized for building [both coupled and decoupled applications](https://dri.es/drupal-is-api-first-not-api-only).

With JSON:API, developers or content creators can create their content models in Drupal's UI without having to write a single line of code, and automatically get not only a great authoring experience, but also a powerful, standards-compliant, web service API to pull that content into JavaScript applications, digital kiosks, chatbots, voice assistants and more.

[video zEsNlAeYRn8]

When you enable the JSON:API module, all *Drupal entities* such as blog posts, users, tags, comments and more become accessible via the JSON:API web service API. JSON:API provides a standardized API for reading and modifying resources (entities), interacting with relationships between resources (entity references), [fetching of only the selected fields](https://dri.es/headless-cms-rest-vs-jsonapi-vs-graphql#request-efficiency) (e.g. only the "title" and "author" fields), including related resources to avoid additional requests (e.g. details about the content's author) and filtering, sorting and paginating collections of resources.

In addition to being incredibly powerful, JSON:API is [easy to learn and use](https://dri.es/headless-cms-rest-vs-jsonapi-vs-graphql#api) and [uses all the tooling we already have available to test, debug and scale Drupal sites](https://dri.es/headless-cms-rest-vs-jsonapi-vs-graphql#operational-efficiency).

### Drupal's JSON:API implementation was years in the making

Development of the JSON:API module started in May 2016 and reached a stable 1.0 release in May 2017. Most of the work was driven by a single developer partially in his free time: [Mateu Aguiló Bosch (e0ipso)](https://www.drupal.org/u/e0ipso).

After soliciting input and consulting others, I felt JSON:API belonged in Drupal core. I first floated this idea in [July 2016](https://dri.es/a-roadmap-for-making-drupal-more-api-first), became more convinced in [December 2016](https://dri.es/improving-drupal-8-api-first-json-api-oauth2) and recommended that we standardize on it in [October 2017](https://dri.es/drupal-looking-to-adopt-react).

This is why at the end of 2017, I asked [Wim Leers](https://www.drupal.org/u/wim-leers) and [Gabe Sullice](https://www.drupal.org/u/gabesullice) – as part of their roles at [Acquia](https://www.acquia.com/) – to start devoting the majority of their time to getting JSON:API to a high level of stability.

Wim and Gabe quickly became key contributors alongside Mateu. They wrote hundreds of tests and added missing features to make sure we guarantee strict compliance with the [JSON:API specification](https://jsonapi.org/).

A year later, their work culminated in a [JSON:API 2.0 stable release on January 7th, 2019](https://www.drupal.org/project/jsonapi/releases/8.x-2.0). The 2.0 release marked the start of the module's move to Drupal core. After rigorous reviews and more improvements, the module was finally committed to core earlier today.

From [beginning](https://www.drupal.org/project/jsonapi/issues/2829327) to [end](https://cgit.drupalcode.org/drupal/commit/?id=b2f88e3), it took 28 months, 450 commits, 32 releases and more than 5,500 test runs.

### The best JSON:API implementation in existence

The JSON:API module for Drupal is almost certainly the most feature-complete and easiest-to-use JSON:API implementation in existence.

The Drupal JSON:API implementation supports *every* feature of the JSON:API 1.0 specification out-of-the-box. Every Drupal entity (a *resource object* in JSON:API terminology) is automatically made available through JSON:API. Existing access controls for both reading and writing are respected. Both [translations](https://www.drupal.org/docs/8/modules/jsonapi/translations) and [revisions](https://www.drupal.org/docs/8/modules/jsonapi/revisions) of entities are also made available. Furthermore, [querying](https://www.drupal.org/docs/8/modules/jsonapi/filtering) entities (*filtering resource collections* in JSON:API terminology) is possible without any configuration (e.g. setting up a "Drupal View"), which means front-end developers can get started on their work right away.

What is particularly rewarding is that all of this was made possible thanks to Drupal's data model and introspection capabilities. Drupal's decade-old Entity API, Field API, Access APIs and more recent Configuration and Typed Data APIs exist as an incredibly robust foundation for making Drupal's data available via web service APIs. This is not to be understated, as it makes the JSON:API implementation robust, deeply integrated and elegant.

I want to extend a special thank you to the many contributors that contributed to the JSON:API module and that helped make it possible for JSON:API to be added to Drupal 8.7.

*Special thanks to [Wim Leers](https://www.drupal.org/u/wim-leers) ([Acquia](https://www.acquia.com/)) and [Gabe Sullice](https://www.drupal.org/u/gabesullice) ([Acquia](https://www.acquia.com/)) for co-authoring this blog post and to [Mateu Aguiló Bosch (e0ipso)](https://www.drupal.org/u/e0ipso) ([Lullabot](https://www.lullabot.com/)), [Preston So](https://www.drupal.org/u/prestonso) ([Acquia](https://www.acquia.com/)), [Alex Bronstein](https://www.drupal.org/u/effulgentsia) ([Acquia](https://www.acquia.com/)) for their feedback during the writing process.*
