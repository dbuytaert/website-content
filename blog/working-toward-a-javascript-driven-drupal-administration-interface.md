---
title: 'Working toward a JavaScript-driven Drupal administration interface'
date: '2018-05-17T13:42:52-04:00'
author: Dries
summary: "The key next steps required to decouple Drupal's administration UI and modernize it using a JavaScript framework"
tags:
  - Drupal
  - JavaScript
  - 'Web services'
published: true
type: blog
url: /working-toward-a-javascript-driven-drupal-administration-interface
id: 4356
---

As web applications have evolved from static pages to application-like experiences, end-users' expectations of websites have become increasingly demanding. JavaScript, partnered with effective user-experience design, enable the [seamless, instantaneous interactions that users now expect](https://dri.es/can-drupal-outdo-native-applications).

The Drupal project anticipated this trend years ago and we have been investing heavily in [making Drupal API-first](https://dri.es/tag/web-services) ever since. As a result, more organizations are building decoupled applications served by Drupal. This approach allows organizations to use modern JavaScript frameworks, while still benefiting from Drupal's powerful content management capabilities, such as content modeling, content editing, content workflows, access rights and more.

While organizations use JavaScript frameworks to create visitor-facing experiences with Drupal as a backend, Drupal's own administration interface has not yet embraced a modern JavaScript framework. There is high demand for Drupal to provide a cutting-edge experience for its own users: the site's content creators and administrators.

At [DrupalCon Vienna](https://dri.es/state-of-drupal-presentation-september-2017), we decided to start working on [an alternative Drupal administrative UI using React](https://dri.es/drupal-looking-to-adopt-react). Sally Young, one of the initiative coordinators, recently posted [a fantastic update on our progress](https://www.lullabot.com/articles/drupal-javascript-initiative-the-road-to-a-modern-administration-ui) since DrupalCon Vienna.

### Next steps for Drupal's API-first and JavaScript work

While we made [great progress improving Drupal's web services support](https://wimleers.com/blog/api-first-drupal-two-big-maintainability-milestones) and improving our JavaScript support, I wanted to use this blog post to compile an overview of some of our most important next steps:

#### 1. Stabilize the JSON API module

[JSON API](http://jsonapi.org) is a widely-used specification for building web service APIs in JSON. We are working towards [adding JSON API to Drupal core](https://www.drupal.org/project/drupal/issues/2843147) as it makes it easier for JavaScript developers to access the content and configuration managed in Drupal. There is a central plan issue that lists [all of the blockers for getting JSON API into core](https://www.drupal.org/project/jsonapi/issues/2931785) (comprehensive test coverage, specification compliance, and more). We're working hard to get all of them out of the way!

#### 2. Improve our JavaScript testing infrastructure

Drupal's testing infrastructure is excellent for testing PHP code, but until now, it was not optimized for testing JavaScript code. As we expect the amount of JavaScript code in Drupal's administrative interface to dramatically increase in the years to come, we have been working on improving our JavaScript testing infrastructure using [Headless Chrome](https://chromium.googlesource.com/chromium/src/+/lkgr/headless/README.md) and [Nightwatch.js](http://nightwatchjs.org/). [Nightwatch.js has already been committed for inclusion in Drupal 8.6](https://www.drupal.org/project/drupal/issues/2869825), however some additional work remains to create a robust JavaScript-to-Drupal bridge. Completing this work is essential to ensure we do not introduce regressions, as we proceed with the other items in our roadmap.

#### 3. Create designs for a React-based administration UI

Having a JavaScript-based UI also allows us to rethink how we can improve Drupal's administration experience. For example, Drupal's current content modeling UI requires a lot of clicking, saving and reloading. By using React, we can reimagine our user experience to be more application-like, intuitive and faster to use. We still need a lot of help to [design and test different parts of the Drupal administration UI](https://www.drupal.org/project/ideas/issues/2902399).

#### 4. Allow contributed modules to use React or Twig

We want to enable modules to provide either a React-powered administration UI or a traditional Twig-based administration UI. We are working on an architecture that can support both at the same time. This will allow us to introduce JavaScript-based UIs incrementally instead of enforcing a massive paradigm shift all at once. It will also provide some level of optionality for modules that want to opt-out from supporting the new administration UI.

#### 5. Implement missing web service APIs

While we have been working for years to add web service APIs to many parts of Drupal, [not all of Drupal has web services support yet](https://www.drupal.org/project/drupal/issues/2913790). For our [React-based administration UI prototype](https://github.com/jsdrupal/drupal-admin-ui) we decided to implement a new permission screen (i.e. `https://example.com/admin/people/permissions`). We learned that Drupal lacked the necessary web service APIs to retrieve a list of all available permissions in the system. This led us to create a support module that provides such an API. This support module is a temporary solution that helped us make progress on our prototype; the goal is to integrate these APIs into core itself. If you want to contribute to Drupal, [creating web service APIs for various Drupal subsystems](https://www.drupal.org/project/drupal/issues/2913790) might be a great way to get involved.

#### 6. Make the React UI extensible and configurable

One of the benefits of Drupal's current administration UI is that it can be configured (e.g. you can modify the content listing because it has been built using the Views module) and extended by contributed modules (e.g. the Address module adds a UI that is optimized for editing address information). We want to make sure that in the new React UI [we keep enough flexibility for site builders](https://github.com/jsdrupal/drupal-admin-ui/issues/14) to customize the administrative UI.

### All decoupled builds benefit

All decoupled applications will benefit from the six steps above; they're important for building a fully-decoupled administration UI, and for building visitor-facing decoupled applications.

<table>
  <thead>
   <tr>
    <td>
   </td>
    <td align="center" width="20%">Useful for decoupling of visitor-facing front-ends</td>
    <td align="center" width="20%">Useful for decoupling of the administration backend</td>
  </tr>
 </thead>
  <tr>
   <td>1. Stabilize the JSON API module</td>
   <td align="center">✔</td>
   <td align="center">✔</td>
 </tr>
  <tr>
   <td>2. Improve our JavaScript testing infrastructure</td>
   <td align="center">✔</td>
   <td align="center">✔</td>
 </tr>
  <tr>
   <td>3. Create designs for a React-based administration UI</td>
   <td>
  </td>
   <td align="center">✔</td>
 </tr>
  <tr>
   <td>4. Allow contributed modules to use React or Twig</td>
   <td align="center">✔</td>
   <td align="center">✔</td>
 </tr>
  <tr>
   <td>5. Implement missing web service APIs</td>
   <td align="center">✔</td>
   <td align="center">✔</td>
 </tr>
  <tr>
   <td>6. Make the React UI extensible and configurable</td>
   <td>
  </td>
   <td align="center">✔</td>
 </tr>
</table>

### Conclusion

Over the past three years we've been making steady progress to move Drupal to a more API-first and JavaScript centric world. It's important work given a variety of market trends in our industry. While we have made excellent progress, there are more challenges to be solved. We hope you like our next steps, and we welcome you to get involved with them. Thank you to everyone who has contributed so far!

*Special thanks to [Matt Grill](https://www.drupal.org/u/drpal) and [Lauri Eskola](https://www.drupal.org/u/lauriii) for co-authoring this blog post and to [Wim Leers](https://www.drupal.org/u/wim-leers), [Gabe Sullice](https://www.drupal.org/u/gabesullice), [Angela Byron](https://www.drupal.org/u/webchick), and [Preston So](https://www.drupal.org/u/prestonso) for their feedback during the writing process.*
