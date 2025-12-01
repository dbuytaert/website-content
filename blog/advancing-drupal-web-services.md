---
title: "Advancing Drupal's web services"
date: '2016-06-06T03:24:14-04:00'
author: Dries
summary: "How to advance Drupal's web services beyond for the benefit of Drupal core contributors, module creators and technical decision-makers"
tags:
  - Drupal
  - 'Web services'
published: true
type: blog
url: /advancing-drupal-web-services
id: 3706
---

In [an earlier blog post](https://dri.es/an-overview-of-web-service-solutions-in-drupal-8), I looked at the web services solutions available in Drupal 8 and compared their strengths and weaknesses. That blog post was intended to help developers choose between different solutions when building Drupal 8 sites. In this blog post, I want to talk about how to advance Drupal's web services beyond Drupal 8.1 for the benefit of Drupal core contributors, module creators and technical decision-makers.

I believe it is really important to continue advancing Drupal's web services support. There are powerful market trends that oblige us to keep focused on this: integration with [diverse systems having their own APIs](https://dri.es/cross-channel-user-experiences-with-drupal), the proliferation of new devices, the expanding Internet of Things (IoT), and [the widening adoption of JavaScript frameworks](https://dri.es/a-history-of-javascript-across-the-stack). All of these depend to some degree on robust web services.

Moreover, newer headless content-as-a-service solutions (e.g. Contentful, Prismic.io, Backand and CloudCMS) have entered the market and represent a widening interest in content repositories enabling more flexible content delivery. They provide content modeling tools, easy-to-use tools to construct REST APIs, and SDKs for different programming languages and client-side frameworks.

In my view, we need to do the following, which I summarize in each of the following sections: (1) facilitate a single robust REST module in core; (2) add functionality to help web services modules more easily query and manipulate Drupal's entity graph; (3) incorporate GraphQL and JSON API out of the box; and (4) add SDKs enabling easy integration with Drupal. Though I shared some of this in [my DrupalCon New Orleans keynote](https://dri.es/state-of-drupal-presentation-may-2016), I wanted to provide more details in this blog post. I'm hoping to discuss this and revise it based on feedback from you.

### One great REST module in core

While core REST can be enabled with only a few configuration changes, the full extent of possibilities in Drupal is only unlocked either when leveraging modules which add to or work alongside core REST's functionality, such as [Services](https://www.drupal.org/project/services) or [RELAXed](https://www.drupal.org/project/relaxed), or when augmenting core REST's capabilities with additional resources to interact with (by [providing corresponding plugins](https://www.drupal.org/docs/8/api/restful-web-services-api/restful-web-services-api-overview)) or using other custom code.

Having such disparate REST modules complicates the experience. These REST modules have overlapping or conflicting feature sets, which are shown in the following table.

<table>
  <tbody>
   <tr>
    <th>Feature</th>
    <th style="width: 16%">Core REST</th>
    <th style="width: 16%">RELAXed</th>
    <th style="width: 16%">Services</th>
    <th style="width: 16%">Ideal core REST</th>
  </tr>
   <tr>
    <td>Content entity CRUD</td>
    <td>Yes</td>
    <td>Yes</td>
    <td>Yes</td>
    <td>
      <strong>Yes</strong>
   </td>
  </tr>
   <tr>
    <td>Configuration entity CRUD</td>
    <td>Create resource plugin (<a href="https://www.drupal.org/node/2300677">issue</a>)</td>
    <td>Create resource plugin</td>
    <td>Yes</td>
    <td>
      <strong>Yes</strong>
   </td>
  </tr>
   <tr>
    <td>Custom resources</td>
    <td>Create resource plugin</td>
    <td>Create resource plugin</td>
    <td>Create Services plugin</td>
    <td>
      <strong>Possible without code</strong>
   </td>
  </tr>
   <tr>
    <td>Custom routes</td>
    <td>Create resource plugin or Views REST export (GET)</td>
    <td>Create resource plugin</td>
    <td>Configurable route prefixes</td>
    <td>
      <strong>Possible without code</strong>
   </td>
  </tr>
   <tr>
    <td>Translations</td>
    <td>Not yet (<a href="https://www.drupal.org/node/2135829">issue</a>)</td>
    <td>Yes</td>
    <td>Create Services plugin</td>
    <td>
      <strong>Yes</strong>
   </td>
  </tr>
   <tr>
    <td>Revisions</td>
    <td>Create resource plugin</td>
    <td>Yes</td>
    <td>Create Services plugin</td>
    <td>
      <strong>Yes</strong>
   </td>
  </tr>
   <tr>
    <td>File attachments</td>
    <td>Create resource plugin</td>
    <td>Yes</td>
    <td>Create Services plugin</td>
    <td>
      <strong>Yes</strong>
   </td>
  </tr>
   <tr>
    <td>Authenticated user resources (log in/out, password reset)</td>
    <td>Not yet (<a href="https://www.drupal.org/node/2403307">issue</a>)</td>
    <td>No</td>
    <td>User login and logout</td>
    <td>
      <strong>Yes</strong>
   </td>
  </tr>
 </tbody>
</table>

I would like to see a convergence where all of these can be achieved in Drupal core with minimal configuration and minimal code.

### Working with Drupal's entity graph

Recently, a discussion at DrupalCon New Orleans with key contributors to the core REST modules, maintainers of important contributed web services modules, and external observers led to a proposed path forward for all of Drupal's web services.

[image blog/web-services-entity-graph resize=false]

Buried inside Drupal is an "entity graph" over which different API approaches like traditional REST, JSON API, and GraphQL can be layered. These varied approaches all traverse and manipulate Drupal's entity graph, with differences solely in the syntax and features made possible by that syntax. Unlike core's REST API which only returns a single level (single entity or lists of entities), GraphQL and JSON API can return multiple levels of nested entities as the result of a single query. To better understand what this means, have a look at the [GraphQL demo video](https://www.youtube.com/watch?v=ZjDYg6NrAys) I shared in [my DrupalCon Barcelona keynote](https://dri.es/state-of-drupal-presentation-september-2015).

What we concluded at DrupalCon New Orleans is that Drupal's GraphQL and JSON API implementations require a substantial amount of custom code to traverse and manipulate Drupal's entity graph, that there was a lot of duplication in that code, and that there is an opportunity to provide more flexibility and simplicity. Therefore, it was agreed that we should first focus on building an "entity graph iterator" that can be reused by JSON API, GraphQL, and other modules.

This entity graph iterator would also enable manipulation of the graph, e.g. for aliasing fields in the graph or simplifying the structure. For example, the difference between Drupal's "base fields" and "configured fields" is irrelevant to an application developer using Drupal's web services API, but Drupal's responses leak this internal distinction by prefixing configured fields with `field_` (see the left column in the table below). By the same token, all fields, even if they carry single values, expose the verbosity of Drupal's typed data system by being presented as arrays (see the left column in the table below). While there are both advantages and disadvantages to exposing single-value fields as arrays, many developers prefer more control over the output or the ability to opt into simpler outputs.

A good Drupal entity graph iterator would simplify the development of Drupal web service APIs, provide more flexibility over naming and structure, and eliminate duplicate code.

<table>
  <tbody>
   <tr>
    <th>Current core REST (shortened response)</th>
    <th>Ideal core REST (shortened response)</th>
  </tr>
   <tr>
    <td>
      <pre>{
      "nid": [
      {
      "value": "2"
      }
      ],
      "title": [
      {
      "value": "Lorem ipsum"
      }
      ],
      "field_product_number": [
      {
      "value": "35"
      }
      ],
      "field_image": [
      {
      "target_id": "2",
      "alt": "Image",
      "title": "Hover text",
      "width": "210",
      "height": "281",
      "url": "http://site.com/x.jpg"
      }
      ]
      }</pre>
   </td>
    <td>
      <pre>{
      "nid": "2"
      "title": "Lorem ipsum",
      "product_number": {
      "value": 35
      },
      "image": {
      "target_id": 2,
      "alt": "Image",
      "title": "Hover text",
      "width": 210,
      "height": 281,
      "url": "http://site.com/x.jpg"
      }
      }</pre>
   </td>
  </tr>
 </tbody>
</table>

### GraphQL and JSON API in core

We should acknowledge simultaneously that the wider JavaScript community is beginning to embrace different approaches, like [JSON API](http://jsonapi.org) and [GraphQL](https://www.drupal.org/project/graphql), which both enable complex relational queries that require fewer requests between Drupal and the client (thanks to the ability to follow relationships, as mentioned in the section concerning the entity graph).

While both JSON API and GraphQL are preferred over traditional REST due to their ability to provide nested entity relationships, GraphQL goes a step further than JSON API by facilitating explicitly client-driven queries, in which the client dictates its data requirements.

I believe that GraphQL and JSON API in core would be a big win for those building decoupled applications with Drupal, and these modules can use existing foundations in Drupal 8 such as the Serialization module. Furthermore, Drupal's own built-in JavaScript-driven UIs could benefit tremendously from GraphQL and JSON API. I'd love to see them in core rather than as contributed modules, as we could leverage them when building decoupled applications backed by Drupal or exchanging data with other server-side implementations. We could also "eat our own dog food" by using them to power JavaScript-driven UIs for block placement, media management, and other administrative interfaces. I can even see a future where Views and GraphQL are closely integrated.

[image blog/web-services-rest-json-grapql resize=false]

### SDKs to consume web services

While a unified REST API and support for GraphQL and JSON API would dramatically improve Drupal as a web services back end, we need to be attentive to the needs of consumers of those web services as well by providing SDKs and helper libraries for developers new to Drupal.

An SDK could make it easy to retrieve an article node, modify a field, and send it back without having to learn the details of Drupal's particular REST API implementation or the structure of Drupal's underlying data storage. For example, this would allow front-end developers to not have to deal with the details of single- versus multi-value fields, optional vs required fields, validation errors, and so on. As an additional example, incorporating user account creation and password change requests into decoupled applications would empower front-end developers building these forms on a decoupled front end such that they would not need to know anything about how Drupal performs user authentication.

As starting points for JavaScript applications, native mobile applications, and even other back-end applications, these SDKs could handle authenticating against the API and juggling of the correct routes to resources without the front-end developer needing an understanding of those nuances.

In fact, at Acquia we're now in the early stages of building the first of several SDKs for consuming and manipulating data via Drupal 8's REST API. [Waterwheel](https://github.com/acquia/waterwheel.js) (previously Hydrant), a new generic helper library intended for JavaScript developers building applications backed by Drupal, is the work of Acquia's [Matt Grill](https://www.drupal.org/u/drpal) and [Preston So](https://www.drupal.org/u/prestonso), and it is already seeing community contributions. We're eager to share our work more widely and welcome new contributors.

### Conclusion

I believe that it is important to have first-class web services in Drupal out of the box in order to enable top-notch APIs and continue our evolution to become API-first.

In parallel with our ongoing work on shoring up our REST module in core, we should provide the underpinnings for even richer web services solutions in the future. With reusable helper functionality that operates on Drupal's entity graph available in core, we open the door to GraphQL, JSON API, and even our current core REST implementation eventually relying on the same robust foundation. Both GraphQL and JSON API could also be promising modules in core. Last but not least, SDKs like Hydrant that empower developers to work with Drupal without learning its complexities will further advance our web services.

Collectively, these tracks of work will make Drupal uniquely compelling for application developers within our own community and well beyond.

*Special thanks to [Preston So](https://www.drupal.org/u/prestonso) for contributions to this blog post and to [Moshe Weitzman](https://www.drupal.org/u/moshe-weitzman), [Kyle Browning](https://www.drupal.org/u/kylebrowning), [Kris Vanderwater](https://www.drupal.org/u/eclipsegc), [Wim Leers](https://www.drupal.org/u/wim-leers), [Sebastian Siemssen](https://www.drupal.org/u/fubhy), [Tim Millwood](https://www.drupal.org/u/timmillwood), [Ted Bowman](https://www.drupal.org/u/tedbow), and [Mateu Aguiló Bosch](https://www.drupal.org/u/e0ipso) for their feedback during its writing.*
