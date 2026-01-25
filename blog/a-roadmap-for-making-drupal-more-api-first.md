---
url: 'https://dri.es/a-roadmap-for-making-drupal-more-api-first'
title: 'A roadmap for making Drupal more API-first'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2016-07-07T10:06:50-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
  - 'Web services'
published: true
id: 3736
---

# A roadmap for making Drupal more API-first

In one of my recent blog posts, I articulated [a vision for the future of Drupal's web services](https://dri.es/advancing-drupal-web-services), and at DrupalCon New Orleans, I announced the [API-first initiative for Drupal 8](https://dri.es/state-of-drupal-presentation-may-2016). I believe that there is considerable momentum behind driving the web services initiative. As such, I want to provide a progress report, highlight some of the key people driving the work, and map the proposed vision from the previous blog post onto a rough timeline.

Here is a bird's-eye view of the plan for the next twelve months:

<table>
  <tbody>
   <tr>
    <th>8.2 (Q4 2016)</th>
    <th>8.3 (Q2 2017)</th>
    <th>Beyond 8.3 (2017+)</th>
  </tr>
   <tr>
    <td>New REST API capabilitiesWaterwheel initial release</td>
    <td>New REST API capabilitiesJSON API module</td>
    <td>GraphQL module?Entity graph iterator?</td>
  </tr>
 </tbody>
</table>

### New REST API capabilities

[Wim Leers](https://www.drupal.org/u/wim-leers) (Acquia) and [Daniel Wehner](https://www.drupal.org/u/dawehner) (Chapter Three) have produced a comprehensive list of the [top priorities for the REST module](https://www.drupal.org/node/2721489). We're introducing [significant REST API advancements](https://www.drupal.org/list-changes/drupal/drupal/published?keywords_description=REST&to_branch=8.2.x&version=&created_op=%3E%3D&created%5Bvalue%5D=&created%5Bmin%5D=&created%5Bmax%5D=) in Drupal 8.2 and 8.3 in order to improve the developer experience and extend the capabilities of the REST API. We've been focused on configuration entity support, simplified REST configuration, translation and file upload support, pagination, and last but not least, support for user login, logout and registration. All this work starts to address differences between core's REST module and various contributed modules like [Services](https://www.drupal.org/project/services) and [RELAXed Web Services](https://www.drupal.org/project/relaxed). More details are available in [my previous blog post](https://dri.es/advancing-drupal-web-services).

Many thanks to [Wim Leers](https://www.drupal.org/u/wim-leers) (Acquia), [Daniel Wehner](https://www.drupal.org/u/dawehner) (Chapter Three), [Ted Bowman](https://www.drupal.org/u/tedbow) (Acquia), [Alex Pott](https://www.drupal.org/u/alexpott) (Chapter Three), and others for their work on Drupal core's REST modules. Though there is considerable momentum behind efforts in core, we could always benefit from new contributors. Please consider taking a look at the [REST module issue queue](https://www.drupal.org/project/issues/drupal?component=rest.module) to help!

### Waterwheel initial release

As I mentioned in my previous post, there has been exciting work surrounding [Waterwheel](https://github.com/acquia/waterwheel.js), an SDK for JavaScript developers building Drupal-backed applications. If you want to build decoupled applications using a JavaScript framework (e.g. Angular, Ember, React, etc.) that use Drupal as a content repository, stay tuned for Waterwheel's initial release later this year.

Waterwheel aims to facilitate the construction of JavaScript applications that communicate with Drupal. Waterwheel's JavaScript library allows JavaScript developers to work with Drupal without needing deep knowledge of how requests should be authenticated against Drupal, what request headers should be included, and how responses are molded into particular data structures.

The [Waterwheel Drupal module](https://www.drupal.org/project/waterwheel) adds a new endpoint to Drupal's REST API allowing Waterwheel to discover entity resources and their fields. In other words, Waterwheel intelligently discovers and seamlessly integrates with the content model defined on any particular Drupal 8 site.

A wider ecosystem around Waterwheel is starting to grow as well. [Gabe Sullice](https://www.drupal.org/u/gabesullice) (Aten Design Group), creator of the [Entity Query API module](https://www.drupal.org/project/entityqueryapi), has contributed an integration of Waterwheel which opens the door to features such as sorts, conditions and ranges. The Waterwheel team welcomes early adopters as well as those working on other REST modules such as JSON API and RELAXed or using native HTTP clients in JavaScript frameworks to add their own integrations to the mix.

Waterwheel is the currently the work of [Matt Grill](https://www.drupal.org/u/drpal) (Acquia) and [Preston So](https://www.drupal.org/u/prestonso) (Acquia), who are developing the JavaScript library, and [Ted Bowman](https://www.drupal.org/u/tedbow) (Acquia), who is working on the Drupal module.

### JSON API module

In conjunction with the ongoing efforts in core REST, parallel work is underway to build a [JSON API module](https://www.drupal.org/project/jsonapi) which embraces the JSON API specification. [JSON API](http://jsonapi.org) is a particular implementation of REST that provides conventions for resource relationships, collections, filters, pagination, and sorting, in addition to error handling and full test coverage. These conventions help developers build clients faster and encourages reuse of code.

Thanks to [Mateu Aguiló Bosch](https://www.drupal.org/u/e0ipso), [Ed Faulkner](https://www.drupal.org/u/ef4) and [Gabe Sullice](https://www.drupal.org/u/gabesullice) (Aten Design Group), who are spearheading the JSON API module work. The module could be ready for production use by the end of this year and included as an experimental module in core by 8.3. Contributors to JSON API are meeting weekly to discuss progress moving forward.

### Beyond 8.3: GraphQL and entity graph iterator

While these other milestones are either certain or in the works, there are other projects gathering steam. Chief among these is GraphQL, which is a query language I highlighted in [my Barcelona keynote](https://dri.es/state-of-drupal-presentation-september-2015) and allows for clients to tailor the responses they receive based on the structure of the requests they issue.

One of the primary outcomes of the New Orleans web services discussion was the importance of a unified approach to iterating Drupal's entity graph; both GraphQL and JSON API require such an "entity graph iterator". Though much of this is still speculative and needs greater refinement, eventually, such an "entity graph iterator" could enable other functionality such as editable API responses (e.g. aliases for custom field names and timestamp formatters) and a unified versioning strategy for web services. However, more help is needed to keep making progress, and in absence of additional contributors, we do not believe this will land in Drupal until after 8.3.

Thanks to [Sebastian Siemssen](https://www.drupal.org/u/fubhy), who has been leading the effort around this work, which is currently [available on GitHub](https://github.com/contentacms/type-graph).

### Validating our work and getting involved

In order to validate all of the progress we've made, we need developers everywhere to test and experiment with what we're producing. This means stretching the limits of our core REST offerings, trying out JSON API for your own Drupal-backed applications, reporting issues and bugs as you encounter them, and participating in the discussions surrounding this exciting vision. Together, we can build towards a first-class API-first Drupal.

*Special thanks to [Preston So](https://www.drupal.org/u/prestonso) for contributions to this blog post and to [Wim Leers](https://www.drupal.org/u/wim-leers) for feedback during its writing.*
