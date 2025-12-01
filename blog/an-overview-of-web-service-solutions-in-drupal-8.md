---
title: 'An overview of web service solutions in Drupal 8'
date: '2016-05-04T05:48:47-04:00'
author: Dries
tags:
  - Drupal
  - 'Web services'
published: true
type: blog
url: /an-overview-of-web-service-solutions-in-drupal-8
id: 3666
---

Today's third-party applications increasingly depend on web services to retrieve and manipulate data, and Drupal offers a range of web services options for API-first content delivery. For example, a robust first-class web services layer is now available out-of-the-box with Drupal 8. But there are also new approaches to expose Drupal data, including Services and newer entrants like RELAXed Web Services and GraphQL.

The goal of this blog post is to enable Drupal developers in need of web services to make an educated decision about the right web services solution for their project. This blog post also sets the stage for a future blog post, where I plan to share my thoughts about [how I believe we should move Drupal core's web services API forward](https://dri.es/advancing-drupal-web-services). Getting aligned on our strengths and weaknesses is an essential first step before we can brainstorm about the future.

The Drupal community now has a range of web services modules available in core and as contributed modules sharing overlapping missions but leveraging disparate mechanisms and architectural styles to achieve them. Here is a comparison table of the most notable web services modules in Drupal 8:

<table>
  <tbody>
   <tr>
    <th style="width: 30%">Feature</th>
    <th style="width: 20%">Core REST</th>
    <th style="width: 20%">RELAXed</th>
    <th style="width: 20%">Services</th>
  </tr>
   <tr>
    <td>Content entity CRUD</td>
    <td>Yes</td>
    <td>Yes</td>
    <td>Yes</td>
  </tr>
   <tr>
    <td>Configuration entity CRUD</td>
    <td>Create resource plugin (<a href="https://www.drupal.org/node/2300677">issue</a>)</td>
    <td>Create resource plugin</td>
    <td>Yes</td>
  </tr>
   <tr>
    <td>Custom resources</td>
    <td>Create resource plugin</td>
    <td>Create resource plugin</td>
    <td>Create Services plugin</td>
  </tr>
   <tr>
    <td>Custom routes</td>
    <td>Create resource plugin or Views REST export (GET)</td>
    <td>Create resource plugin</td>
    <td>Configurable route prefixes</td>
  </tr>
   <tr>
    <td>Renderable objects</td>
    <td>Not applicable</td>
    <td>Not applicable</td>
    <td>Yes (no contextual blocks or views)</td>
  </tr>
   <tr>
    <td>Translations</td>
    <td>Not yet (<a href="https://www.drupal.org/node/2135829">issue</a>)</td>
    <td>Yes</td>
    <td>Create Services plugin</td>
  </tr>
   <tr>
    <td>Revisions</td>
    <td>Create resource plugin</td>
    <td>Yes</td>
    <td>Create Services plugin</td>
  </tr>
   <tr>
    <td>File attachments</td>
    <td>Create resource plugin</td>
    <td>Yes</td>
    <td>Create Services plugin</td>
  </tr>
   <tr>
    <td>Shareable UUIDs (GET)</td>
    <td>Yes</td>
    <td>Yes</td>
    <td>Yes</td>
  </tr>
   <tr>
    <td>Authenticated user resources (log in/out, password reset)</td>
    <td>Not yet (<a href="https://www.drupal.org/node/2403307">issue</a>)</td>
    <td>No</td>
    <td>User login and logout</td>
  </tr>
 </tbody>
</table>

### Core RESTful Web Services

Thanks to the [Web Services and Context Core Initiative](https://dri.es/the-future-is-a-restful-drupal) (WSCCI), Drupal 8 is now an out-of-the-box REST server with operations to create, read, update, and delete (CRUD) content entities such as nodes, users, taxonomy terms, and comments. The four primary REST modules in core are:

- *[Serialization](https://www.drupal.org/docs/8/core/modules/serialization/overview)* is able to perform serialization by providing normalizers and encoders. First, it normalizes Drupal data (entities and their fields) into arrays with a particular structure. Any normalization can then be sent to an encoder, which transforms those arrays into data formats such as JSON or XML.
- *[RESTful Web Services](https://www.drupal.org/docs/8/core/modules/rest/overview)* allows for HTTP methods to be performed on existing resources including but not limited to content entities and views (the latter facilitated through the "REST export" display in Views) and custom resources added through REST plugins.
- *[HAL](https://www.drupal.org/docs/8/core/modules/hal/overview)* builds on top of the Serialization module and adds the Hypertext Application Language normalization, a format that enables you to design an API geared toward clients moving between distinct resources through hyperlinks.
- *[Basic Auth](https://www.drupal.org/documentation/modules/basic_auth)* allows you to include a username and password with request headers for operations requiring permissions beyond that of an anonymous user. It should only be used with HTTPS.

Core REST adheres strictly to REST principles in that resources directly match their URIs (accessible via a query parameter, e.g. `?_format=json` for JSON) and in the ability to serialize non-content into JSON or XML representations. By default, core REST also includes two authentication mechanisms: basic authentication and cookie-based authentication.

While core REST provides a range of features with only a few steps of configuration there are several reasons why other options, available as contributed modules, may be a better choice. Limitations of core REST include the lack of [support for configuration entities](https://www.drupal.org/node/2300677) as well as the inability to include file attachments and revisions in response payloads. With your help, we can continue to improve and expand core's REST support.

### RELAXed Web Services

As I highlighted in my recent blog post about [improving Drupal's content workflow](https://dri.es/improving-drupal-content-workflow), [RELAXed Web Services](https://www.drupal.org/project/relaxed), is part of a larger [suite of modules](http://www.drupaldeploy.org/) handling content staging and deployment across environments. It is explicitly tied to the [CouchDB API specification](https://wiki.apache.org/couchdb/HTTP_Document_API), and when enabled, will yield a REST API that operates like the CouchDB REST API. This means that CouchDB integration with client-side libraries such as [PouchDB](https://pouchdb.com/) and [Hood.ie](http://hood.ie) makes possible offline-enabled Drupal, which synchronizes content once the client regains connectivity. Moreover, people new to Drupal with exposure to CouchDB will immediately understand the API, since there is robust documentation for the endpoints.

RELAXed Web Services depends on core's REST modules and extends its functionality by adding support for translations, parent revisions (through the [Multiversion](https://www.drupal.org/project/multiversion) module), file attachments, and especially cross-environment UUID references, which make it possible to replicate content to Drupal sites or other CouchDB compatible services. UUID references and revisions are essential to resolving merge conflicts during the content staging process. I believe it would be great to support translations, parent revisions, file attachments, and UUID references in core's RESTful web services – we simply didn't get around to them in time for Drupal 8.0.0.

### Services

Since RESTful Web Services are now incorporated into Drupal 8 core, relevant contributed modules have either been superseded or have gained new missions in the interest of extending existing core REST functionality. In the case of [Services](https://www.drupal.org/project/services), a popular Drupal 7 module for providing Drupal data to external applications, the module has evolved considerably for its upcoming Drupal 8 release.

With Services in Drupal 8 you can assign a custom name to your endpoint to distinguish your resources from those provisioned by core and also provision custom resources similar to core's RESTful Web Services. In addition to content entities, Services supports configuration entities such as blocks and menus – this can be important when you want to build a decoupled application that leverages Drupal's menu and blocks system. Moreover, Services is capable of returning renderable objects encoded in JSON, which allows you to use Drupal's server-side rendering of blocks and menus in an entirely distinct application.

At the time of this writing, the Drupal 8 version of Services module is not yet feature-complete: there is no test coverage, no content entity validation (when creating or modifying), no field access checking, and no CSRF protection, so caution is important when using Services in its current state, and contributions are greatly appreciated.

### GraphQL

GraphQL, originally created by Facebook to power its data fetching, is a query language that enables fewer queries and limits response bloat. Rather than tightly coupling responses with a predefined schema, [GraphQL](https://www.drupal.org/project/graphql) overturns this common practice by allowing for the client's request to explicitly tailor a response so that the client only receives what it needs: no more and no less. To accomplish this, client requests and server responses have a *shared shape*. It doesn't fall into the same category as the web services modules that expose a REST API and as such is absent from the table above.

GraphQL shifts responsibility from the server to the client: the server publishes its possibilities, and the client publishes its requirements instead of receiving a response dictated solely by the server. In addition, information from related entities (e.g. both a node's body and its author's e-mail address) can be retrieved in a single request rather than successive ones.

Typical REST APIs tend to be static (or versioned, in many cases, e.g. `/api/v1`) in order to facilitate backwards compatibility for applications. However, in Drupal's case, when the underlying content model is inevitably augmented or otherwise changed, schema compatibility is no longer guaranteed. For instance, when you remove a field from a content type or modify it, Drupal's core REST API is no longer compatible with those applications expecting that field to be present. With GraphQL's native schema introspection and client-specified queries, the API is much less opaque from the client's perspective in that the client is aware of what response will result according to its own requirements.

I'm very bullish on the potential for GraphQL, which I believe makes a lot of sense in core in the long term. I featured the project in [my Barcelona keynote](https://dri.es/state-of-drupal-presentation-september-2015) ([demo video](https://www.youtube.com/watch?v=ZjDYg6NrAys)), and [Acquia](https://www.acquia.com) also sponsored development of the [GraphQL module](https://www.drupal.org/project/graphql) (Drupal 8 only) following DrupalCon Barcelona. The GraphQL module, created by [Sebastian Siemssen](https://www.drupal.org/u/fubhy), now supports read queries, implements the GraphiQL query testing interface, and can be integrated with [Relay](https://facebook.github.io/relay/) (with some [limitations](https://www.drupal.org/node/2714803)).

### Conclusion

For most simple REST API use cases, core REST is adequate, but core REST can be insufficient for more complex use cases. Depending on your use case, you may need more off-the-shelf functionality without the need to write a resource plugin or custom code, such as support for configuration entity CRUD (Services); for revisions, file attachments, translations, and cross-environment UUIDs (RELAXed); or for client-driven queries (GraphQL).

*Special thanks to [Preston So](https://www.drupal.org/u/prestonso) for contributions to this blog post and to [Moshe Weitzman](https://www.drupal.org/u/moshe-weitzman), [Kyle Browning](https://www.drupal.org/u/kylebrowning), [Kris Vanderwater](https://www.drupal.org/u/eclipsegc), [Wim Leers](https://www.drupal.org/u/wim-leers), [Sebastian Siemssen](https://www.drupal.org/u/fubhy), [Tim Millwood](https://www.drupal.org/u/timmillwood) and [Ted Bowman](https://www.drupal.org/u/tedbow) for their feedback during its writing.*
