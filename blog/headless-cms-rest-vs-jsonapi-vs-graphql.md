---
title: 'Headless CMS: REST vs JSON:API vs GraphQL'
date: '2019-02-11T08:59:51-05:00'
author: Dries
summary: 'We compare REST, JSON:API and GraphQL — three different web services implementations — based on request efficiency, operational simplicity, API discoverability, and more.'
image: drupal/rest-vs-jsonapi-graphql-comparison
tags:
  - Drupal
  - 'Web services'
  - 'Headless Drupal'
featured: true
published: true
type: blog
url: /headless-cms-rest-vs-jsonapi-vs-graphql
id: 4751
---

[image drupal/rest-vs-jsonapi-graphql-comparison]

The web used to be server-centric in that web content management systems managed data and turned it into HTML responses. With the rise of *headless architectures* [a portion of the web is becoming server-centric for data but client-centric for its presentation](https://dri.es/a-history-of-javascript-across-the-stack); increasingly, data is rendered into HTML in the browser.

This shift of responsibility has given rise to JavaScript frameworks, while on the server side, it has resulted in the development of JSON:API and GraphQL to better serve these JavaScript applications with content and data.

In this blog post, we will compare REST, JSON:API and GraphQL. First, we'll look at an architectural, CMS-agnostic comparison, followed by evaluating some Drupal-specific implementation details.

It's worth noting that there are of course lots of intricacies and "it depends" when comparing these three approaches. When we discuss REST, we mean the "typical REST API" as opposed to one that is extremely well-designed or following a specification (not [REST as a concept](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm)). When we discuss JSON:API, we're referring to implementations of the [JSON:API specification](https://jsonapi.org). Finally, when we discuss GraphQL, we're referring to GraphQL as it used in practice. Formally, it is only [a query language](https://graphql.github.io/graphql-spec/), not a standard for building APIs.

The architectural comparison should be useful for anyone building decoupled applications regardless of the foundation they use because the qualities we will evaluate apply to most web projects.

To frame our comparisons, let's establish that most developers working with web services care about the following qualities:

1. **Request efficiency:** retrieving all necessary data in a single network round trip is essential for performance. The size of both requests and responses should make efficient use of the network.
2. **API exploration and schema documentation:** the API should be quickly understandable and easily discoverable.
3. **Operational simplicity:** the approach should be easy to install, configure, run, scale and secure.
4. **Writing data:** not every application needs to store data in the content repository, but when it does, it should not be significantly more complex than reading.

We summarized our conclusions in the table below, but we discuss each of these four categories (or rows in the table) in more depth below. If you aggregate the colors in the table, you see that **we rank JSON:API above GraphQL and GraphQL above REST**.

<div class="large">
  <table>
   <thead>
    <tr>
      <th style="width: 25%;">
     </th>
      <th style="width: 25%;">REST</th>
      <th style="width: 25%;">JSON:API</th>
      <th style="width: 25%;">GraphQL</th>
   </tr>
  </thead>
   <tbody>
    <tr>
      <td>
       <a href="https://dri.es/headless-cms-rest-vs-jsonapi-vs-graphql#request-efficiency">Request efficiency</a>
     </td>
      <td style="background-color: rgba(255, 0, 0, 0.2);">Poor; multiple requests are needed to satisfy common needs. Responses are bloated.</td>
      <td style="background-color: rgba(0, 255, 0, 0.2);">Excellent; a single request is usually sufficient for most needs. Responses can be tailored to return only what is required.</td>
      <td style="background-color: rgba(0, 255, 0, 0.2);">Excellent; a single request is usually sufficient for most needs. Responses only include exactly what was requested.</td>
   </tr>
    <tr>
      <td>
       <a href="https://dri.es/headless-cms-rest-vs-jsonapi-vs-graphql#api">Documentation, API explorability and schema</a>
     </td>
      <td style="background-color: rgba(255, 0, 0, 0.2);">Poor; no schema, not explorable.</td>
      <td style="background-color: rgba(255, 255, 0, 0.2);">Acceptable; generic schema only; links and error messages are self-documenting.</td>
      <td style="background-color: rgba(0, 255, 0, 0.2);">Excellent; precise schema; excellent tooling for exploration and documentation.</td>
   </tr>
    <tr>
      <td>
       <a href="https://dri.es/headless-cms-rest-vs-jsonapi-vs-graphql#operational-efficiency">Operational simplicity</a>
     </td>
      <td style="background-color: rgba(255, 255, 0, 0.2);">Acceptable; works out of the box with CDNs and reverse proxies; few to no client-side libraries required.</td>
      <td style="background-color: rgba(0, 255, 0, 0.2);">Excellent; works out of the box with CDNs and reverse proxies, no client-side libraries needed, but many are available and useful.</td>
      <td style="background-color: rgba(255, 0, 0, 0.2);">Poor; extra infrastructure is often necessary client side libraries are a practical necessity, specific patterns required to benefit from CDNs and browser caches.</td>
   </tr>
    <tr>
      <td>
       <a href="https://dri.es/headless-cms-rest-vs-jsonapi-vs-graphql#writing-data">Writing data</a>
     </td>
      <td style="background-color: rgba(255, 255, 0, 0.2);">Acceptable; HTTP semantics give some guidance but how specifics left to each implementation, one write per request.</td>
      <td style="background-color: rgba(0, 255, 0, 0.2);">Excellent; how writes are handled is clearly defined by the spec, one write per request, but multiple writes is being added to the specification.</td>
      <td style="background-color: rgba(255, 0, 0, 0.2);">Poor; how writes are handled is left to each implementation and there are competing best practices, it's possible to execute multiple writes in a single request.</td>
   </tr>
  </tbody>
 </table>
</div>

If you're not familiar with JSON:API or GraphQL, I recommend you watch the following two short videos. They will provide valuable context for the remainder of this blog post:

- A 3-minute [demo of Drupal's GraphQL implementation](https://youtu.be/Gm6fkwXrCP8).
- A 5-minute [demo of Drupal's JSON:API implementation](https://youtu.be/zEsNlAeYRn8).

### <a id="request-efficiency">Request efficiency</a>

Most REST APIs tend toward the simplest implementation possible: a resource can only be retrieved from one URI. If you want to retrieve article 42, you have to retrieve it from `https://example.com/article/42`. If you want to retrieve article 42 and article 72, you have to perform two requests; one to `https://example.com/article/42` and one to `https://example.com/article/72`. If the article's author information is stored in a different content type, you have to do two additional requests, say to `https://example.com/author/3` and `https://example.com/author/7`. Furthermore, you can't send these requests until you've requested, retrieved and parsed the article requests (you wouldn't know the author IDs otherwise).

Consequently, client-side applications built on top of basic REST APIs tend to need many successive requests to fetch their data. Often, these requests can't be sent until earlier requests have been fulfilled, resulting in a sluggish experience for the website visitor.

GraphQL and JSON:API were developed to address the typical inefficiency of REST APIs. Using JSON:API or GraphQL, you can use a single request to retrieve both article 42 and article 72, along with the author information for each. It simplifies the developer experience, but more importantly, it speeds up the application.

Finally, both JSON:API and GraphQL have a solution to limit response sizes. A common complaint against typical REST APIs is that their responses can be incredibly verbose; they often respond with far more data than the client needs. This is both annoying and inefficient.

GraphQL eliminates this by requiring the developer to explicitly add each desired resource field to every query. This makes it difficult to *over-fetch* data but easily leads to very large GraphQL queries, making (cacheable) GET requests impossible.

JSON:API solves this with the concept of *sparse fieldsets* or lists of desired resource fields. These behave in much the same fashion as GraphQL does, however, when they're omitted JSON:API will typically return *all* fields. An advantage, though, is that when a JSON:API query gets too large, sparse fieldsets can be omitted so that the request remains cacheable.

<table>
  <thead>
   <tr>
    <th style="width: 25%;">
   </th>
    <th style="width: 25%;">REST</th>
    <th style="width: 25%;">JSON:API</th>
    <th style="width: 25%;">GraphQL</th>
  </tr>
 </thead>
  <tbody>
   <tr>
    <td>Multiple data objects in a single response</td>
    <td style="background-color: rgba(255, 255, 0, 0.2);">Usually; but every implementation is different (for Drupal: custom "REST Export" view or custom REST plugin needed).</td>
    <td style="background-color: rgba(0, 255, 0, 0.2);">Yes</td>
    <td style="background-color: rgba(0, 255, 0, 0.2);">Yes</td>
  </tr>
   <tr>
    <td>Embed related data (e.g. the author of each article)</td>
    <td style="background-color: rgba(255, 0, 0, 0.2);">No</td>
    <td style="background-color: rgba(0, 255, 0, 0.2);">Yes</td>
    <td style="background-color: rgba(0, 255, 0, 0.2);">Yes</td>
  </tr>
   <tr>
    <td>Only needed fields of a data object</td>
    <td style="background-color: rgba(255, 0, 0, 0.2);">No</td>
    <td style="background-color: rgba(0, 255, 0, 0.2);">Yes; servers may choose sensible defaults, developers must be diligent to prevent over-fetching.</td>
    <td style="background-color: rgba(0, 255, 0, 0.2);">Yes; strict, but eliminates over-fetching, at the extreme, it can lead to poor cacheability.</td>
  </tr>
 </tbody>
</table>

### <a id="api">Documentation, API explorability and schema</a>

As a developer working with web services, you want to be able to discover and understand the API quickly and easily: what kinds of resources are available, what fields does each of them have, how are they related, etc. But also, if this field is a date or time, what machine-readable format is the date or time specified in? Good documentation and API exploration can make all the difference.

<table>
  <thead>
   <tr>
    <th style="width: 25%;">
   </th>
    <th style="width: 25%;">REST</th>
    <th style="width: 25%;">JSON:API</th>
    <th style="width: 25%;">GraphQL</th>
  </tr>
 </thead>
  <tbody>
   <tr>
    <td>Auto-generated documentation</td>
    <td style="background-color: rgba(255, 255, 0, 0.2);">Depends; if using the OpenAPI standard.</td>
    <td style="background-color: rgba(255, 255, 0, 0.2);">Depends; if using the OpenAPI standard.</td>
    <td style="background-color: rgba(0, 255, 0, 0.2);">Yes; various tools available.</td>
  </tr>
   <tr>
    <td>Interactivity</td>
    <td style="background-color: rgba(255, 0, 0, 0.2);">Poor; navigable links rarely available.</td>
    <td style="background-color: rgba(255, 255, 0, 0.2);">Acceptable; observing available fields and links in its responses enable exploration of the API.</td>
    <td style="background-color: rgba(0, 255, 0, 0.2);">Excellent; autocomplete feature, instant results or compilation errors, complete and contextual documentation.</td>
  </tr>
   <tr>
    <td>Validatable and programmable schema.</td>
    <td style="background-color: rgba(255, 255, 0, 0.2);">Depends; if using the OpenAPI standard.</td>
    <td style="background-color: rgba(255, 255, 0, 0.2);">Depends; the JSON:API specification defines a generic schema, but a reliable field-level schema is not yet available.</td>
    <td style="background-color: rgba(0, 255, 0, 0.2);">Yes; a complete and reliable schema is provided (with very few exceptions).</td>
  </tr>
 </tbody>
</table>

GraphQL has superior API exploration thanks to [GraphiQL](https://github.com/graphql/graphiql) (demonstrated in the video above), an in-browser IDE of sorts, which lets developers iteratively construct a query. As the developer types the query out, likely suggestions are offered and can be auto-completed. At any time, the query can be run and GraphiQL will display real results alongside the query. This provides immediate, actionable feedback to the query builder. Did they make a typo? Does the response look like what was desired? Additionally, documentation can be summoned into a flyout, when additional context is needed.

On the other hand, JSON:API is more self-explanatory: APIs can be explored with nothing more than a web browser. From within the browser, you can browse from one resource to another, discover its fields, and more. So, if you just want to debug or try something out, JSON:API is usable with nothing more than [cURL](https://en.wikipedia.org/wiki/CURL) or your browser. Or, you can use [Postman](https://www.getpostman.com/downloads/) (demonstrated in the video above) – a standalone environment for developing on top of an *any* HTTP-based API. Constructing complex queries requires some knowledge, however, and that is where GraphQL's GraphiQL shines compared to JSON:API.

### <a id="operational-efficiency">Operational simplicity</a>

We use the term *operational simplicity* to encompass how easy it is to install, configure, run, scale and secure each of the solutions.

The table should be self-explanatory, but we want to provide some more details about the "scalability" row. To scale a REST-based or JSON:API-based web service so that it can handle a large volume of traffic, you can use the same approach websites (and Drupal) already use, including reverse proxies like Varnish or a CDN. To scale GraphQL, you can't rely on HTTP caching as with REST or JSON:API without *persisted queries*. Persisted queries are not part of the official GraphQL specification but they are [a widely-adopted convention](https://blog.apollographql.com/persisted-graphql-queries-with-apollo-client-119fd7e6bba5) amongst GraphQL users. They essentially store a query on the server, assign it an ID and permit the client to get the result of the query using a `GET` request with only the ID. Persisted queries add more operational complexity, and it also means the architecture is no longer fully decoupled – if a client wants to retrieve different data, server-side changes are required.

<table>
  <thead>
   <tr>
    <th style="width: 25%;">
   </th>
    <th style="width: 25%;">REST</th>
    <th style="width: 25%;">JSON:API</th>
    <th style="width: 25%;">GraphQL</th>
  </tr>
 </thead>
  <tbody>
   <tr>
    <td>Scalability: additional infrastructure requirements</td>
    <td style="background-color: rgba(0, 255, 0, 0.2);">Excellent; same as a regular website (Varnish, CDN, etc).</td>
    <td style="background-color: rgba(0, 255, 0, 0.2);">Excellent; same as a regular website (Varnish, CDN, etc).</td>
    <td style="background-color: rgba(255, 0, 0, 0.2);">Usually poor; only the simplest queries can use GET requests; to reap the full benefit of GraphQL, servers needs their own tooling.</td>
  </tr>
   <tr>
    <td>Tooling ecosystem</td>
    <td style="background-color: rgba(255, 255, 0, 0.2);">Acceptable; lots of developer tools available, but for the best experience they need to be customized for the implementation.</td>
    <td style="background-color: rgba(0, 255, 0, 0.2);">Excellent; lots of developer tools available; tools don't need to be implementation-specific.</td>
    <td style="background-color: rgba(0, 255, 0, 0.2);">Excellent; lots of developer tools available; tools don't need to be implementation-specific.</td>
  </tr>
   <tr>
    <td>Typical points of failure</td>
    <td style="background-color: rgba(0, 255, 0, 0.2);">Fewer; server, client.</td>
    <td style="background-color: rgba(0, 255, 0, 0.2);">Fewer; server, client.</td>
    <td style="background-color: rgba(255, 0, 0, 0.2);">Many; server, client, client-side caching, client and build tooling.</td>
  </tr>
 </tbody>
</table>

### <a id="writing-data">Writing data</a>

For most REST APIs and JSON:API, writing data is as easy as fetching it: if you can read information, you also know how to write it. Instead of using the `GET` HTTP request type you use `POST` and `PATCH` requests. JSON:API improves on typical REST APIs by eliminating differences between implementations. There is just one way to do things and that enabled better, generic tooling and less time spent on server-side details.

The nature of GraphQL's write operations (called *mutations*) means that you must write custom code for each write operation; unlike JSON:API the specification, GraphQL doesn't prescribe a single way of handling write operations to resources, so there are many competing best practices. In essence, the GraphQL specification is optimized for reads, not writes.

On the other hand, the GraphQL specification supports bulk/batch operations automatically for the mutations you've already implemented, whereas the JSON:API specification does not. The ability to perform batch write operations can be important. For example, in our running example, adding a new tag to an article would require two requests; one to create the tag and one to update the article. That said, support for [bulk/batch writes in JSON:API](https://github.com/json-api/json-api/pull/1254) is on the specification's roadmap.

<table>
  <thead>
   <tr>
    <th style="width: 25%;">
   </th>
    <th style="width: 25%;">REST</th>
    <th style="width: 25%;">JSON:API</th>
    <th style="width: 25%;">GraphQL</th>
  </tr>
 </thead>
  <tbody>
   <tr>
    <td>Writing data</td>
    <td style="background-color: rgba(255, 255, 0, 0.2);">Acceptable; every implementation is different. No bulk support.</td>
    <td style="background-color: rgba(0, 255, 0, 0.2);">Excellent; JSON:API prescribes a complete solution for handling writes. Bulk operations are coming soon.</td>
    <td style="background-color: rgba(255, 0, 0, 0.2);">Poor; GraphQL supports bulk/batch operations, but writes can be tricky to design and implement. There are competing conventions.</td>
  </tr>
 </tbody>
</table>

### <a id="drupal-considerations">Drupal-specific considerations</a>

Up to this point we have provided an architectural and CMS-agnostic comparison; now we also want to highlight a few Drupal-specific implementation details. For this, we can look at the ease of installation, automatically generated documentation, integration with Drupal's entity and field-level access control systems and decoupled filtering.

Drupal 8's REST module is practically impossible to set up without the [contributed REST UI module](https://www.drupal.org/project/restui), and its configuration can be daunting. Drupal's JSON:API module is far superior to Drupal's REST module at this point. It is trivial to set up: install it and you're done; there's nothing to configure. The GraphQL module is also easy to install but does require some configuration.

Client-generated collection queries allow a consumer to filter an application's data down to just what they're interested in. This is a bit like a Drupal View except that the consumer can add, remove and control all the filters. This is almost always a requirement for public web services, but it can also make development more efficient because creating or changing a listing doesn't require server-side configuration changes.

Drupal's REST module does not support client-generated collection queries. It requires a "REST Views display" to be setup by a site administrator and since these need to be manually configured in Drupal; this means a client can't craft its own queries with the filters it needs.

JSON:API and GraphQL, clients are able to perform their own content queries without the need for server-side configuration. This means that they can be truly decoupled: changes to the front end don't always require a back-end configuration change.

These client-generated queries are a bit simpler to use with the JSON:API module than they are with the GraphQL module because of how each module handles Drupal's extensive access control mechanisms. By default JSON:API ensures that these are respected by altering the incoming query. GraphQL instead requires the consumer to have permission to simply bypass access restrictions.

Most projects using GraphQL that cannot grant this permission use persisted queries instead of client-generated queries. This means a return to a more traditional Views-like pattern because the consumer no longer has complete control of the query's filters. To regain some of the efficiencies of client-generated queries, the creation of these persisted queries can be automated using front-end build tooling.

<table>
  <thead>
   <tr>
    <th style="width: 25%;">
   </th>
    <th style="width: 25%;">REST</th>
    <th style="width: 25%;">JSON:API</th>
    <th style="width: 25%;">GraphQL</th>
  </tr>
 </thead>
  <tbody>
   <tr>
    <td>Ease of installation and configuration</td>
    <td style="background-color: rgba(255, 0, 0, 0.2);">Poor; requires contributed module <a href="https://www.drupal.org/project/restui">REST UI</a>, easy to break clients by changing configuration.</td>
    <td style="background-color: rgba(0, 255, 0, 0.2);">Excellent; zero configuration!</td>
    <td style="background-color: rgba(255, 0, 0, 0.2);">Poor; more complex to use, may require additional permissions, configuration or custom code.</td>
  </tr>
   <tr>
    <td>Automatically generated documentation</td>
    <td style="background-color: rgba(255, 255, 0, 0.2);">Acceptable; requires contributed module <a href="https://www.drupal.org/project/openapi">OpenAPI</a>.</td>
    <td style="background-color: rgba(255, 255, 0, 0.2);">Acceptable; requires contributed module <a href="https://www.drupal.org/project/openapi">OpenAPI</a>.</td>
    <td style="background-color: rgba(0, 255, 0, 0.2);">Excellent; GraphQL Voyager included.</td>
  </tr>
   <tr>
    <td>Security: content-level access control (entity and field access)</td>
    <td style="background-color: rgba(0, 255, 0, 0.2);">Excellent; content-level access control respected.</td>
    <td style="background-color: rgba(0, 255, 0, 0.2);">Excellent; content-level access control respected, even in queries.</td>
    <td style="background-color: rgba(255, 255, 0, 0.2);">Acceptable; some use cases require the consumer to have permission to bypass all entity and/or field access.</td>
  </tr>
   <tr>
    <td>Decoupled filtering (client can craft queries without server-side intervention)</td>
    <td style="background-color: rgba(255, 0, 0, 0.2);">No</td>
    <td style="background-color: rgba(0, 255, 0, 0.2);">Yes</td>
    <td style="background-color: rgba(255, 255, 0, 0.2);">Depends; only in some setups and with additional tooling/infrastructure.</td>
  </tr>
 </tbody>
</table>

### What does this mean for Drupal's roadmap?

Drupal grew up as a traditional web content management system but has since [evolved for this API-first world](https://dri.es/drupal-is-api-first-not-api-only) and industry analysts are [praising us for it](https://dri.es/acquia-a-leader-in-the-2018-forrester-wave-for-web-content-management-systems).

As Drupal's project lead, I've been talking about adding out-of-the-box support for both JSON:API and GraphQL for [a while now](https://dri.es/the-future-of-decoupled-drupal). In fact, I've been [very](https://dri.es/an-overview-of-web-service-solutions-in-drupal-8) [bullish](https://dri.es/state-of-drupal-presentation-september-2015) [about](https://www.youtube.com/watch?v=ZjDYg6NrAys) [GraphQL](https://www.drupal.org/project/graphql) since 2015. My optimism was warranted; GraphQL is undergoing a meteoric rise in interest across the web development industry.

<p class="pullquote">Based on this analysis, for Drupal core's needs, we rank JSON:API above GraphQL and GraphQL above REST.  As such, I want to change my recommendation for Drupal 8 core. Instead of adding both JSON:API and GraphQL to Drupal 8 core, I believe only JSON:API should be added. That said, Drupal's GraphQL implementation is fantastic, especially when you have the developer capacity to build a bespoke API for your project.</p>

On the four qualities by which we evaluated the REST, JSON:API and GraphQL modules, JSON:API has outperformed its contemporaries. Its web standards-based approach, its ability to handle reads and writes out of the box, its security model and its ease of operation make it the best choice for Drupal core. Additionally, where JSON:API underperformed, I believe that we have a real opportunity to contribute back to the specification. In fact, one of the JSON:API module's maintainers and co-authors of this blog post, [Gabe Sullice](http://www.sullice.com/) ([Acquia](https://www.acquia.com/)), recently became a [JSON:API specification](https://jsonapi.org/) editor himself.

This decision does not mean that you can't or *shouldn't* use GraphQL with Drupal. While I believe JSON:API covers the majority of use cases, there are valid use cases where GraphQL is a great fit. I'm happy that Drupal is endowed with such a vibrant contributed module ecosystem that provides so many options to Drupal's users.

I'm excited to see where both the JSON:API specification and Drupal's implementation of it goes in the coming months and years. As a first next step, we're preparing the JSON:API to be added to Drupal 8.7.

*Special thanks to [Wim Leers](https://www.drupal.org/u/wim-leers) ([Acquia](https://www.acquia.com/)) and [Gabe Sullice](https://www.drupal.org/u/gabesullice) ([Acquia](https://www.acquia.com/)) for co-authoring this blog post and to [Preston So](https://www.drupal.org/u/prestonso) ([Acquia](https://www.acquia.com/)) and [Alex Bronstein](https://www.drupal.org/u/effulgentsia) ([Acquia](https://www.acquia.com/)) for their feedback during the writing process.*
