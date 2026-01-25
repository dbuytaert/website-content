---
url: 'https://dri.es/reservoir-a-simple-way-to-decouple-drupal'
title: 'Reservoir, a simple way to decouple Drupal'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2017-08-22T16:52:54-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'Reservoir is a Drupal-based content repository with all the necessary web service APIs needed to build decoupled front-end applications.'
tags:
  - Drupal
  - 'Headless Drupal'
  - JavaScript
  - 'Web services'
  - 'Drupal distributions'
image: drupal/reservoir-api-documentation
published: true
id: 4006
---

# Reservoir, a simple way to decouple Drupal

Headless Drupal seems to be taking the world by storm. I'm currently in Sydney, and everyone I talked to so far, including the attendees at the Sydney Drupal User Group, is looking into [headless Drupal](https://dri.es/tag/headless-drupal). Digital agencies are experimenting with it on more projects, and there is even [a new Decoupled Dev Days conference](https://decoupleddevdays.com/) dedicated to the topic.

Roughly eight months ago, we asked ourselves in [Acquia's Office of the CTO](https://dri.es/announcing-the-office-of-the-cto-at-acquia) whether we could create a "headless" version of Drupal, optimized for integration with a variety of applications, channels and touchpoints. Such a version could help us build bridges with other developer communities working with different frameworks and programming languages, and the JavaScript community in particular.

I've been too busy with [the transition at Acquia](https://dri.es/acquia-next-phase) to blog about it in real time, but a few months ago, [we released Reservoir](https://dev.acquia.com/blog/introducing-reservoir-a-distribution-for-decoupling-drupal/19/06/2017/18296). It's a Drupal-based content repository with all the necessary web service APIs needed to build decoupled front-end applications, be it a React application, an Ember front end, a native application, an [augmented reality application](https://dri.es/from-imagination-to-augmented-reality-in-48-hours), a Java or .NET application, or something completely different. You can even front-end it with a PHP application, something I hope to experiment with on my blog.

API-first distributions for Drupal like [Reservoir](https://github.com/acquia/reservoir) and [Contenta](http://contentacms.org) are a relatively new phenomenon but seem to be taking off rapidly. It's no surprise because an API-first approach is critical in a world where you have to [operate agnostically across any channel and any form factor](https://dri.es/cross-channel-user-experiences-with-drupal). I'm convinced that an API-first approach will be a critical addition to Drupal's future and could see a distribution like Reservoir or Contenta evolve to become a third installation profile for Drupal core (not formally decided).

### Headless Drupal for both editors and developers

[image drupal/reservoir-welcome-screen]

The reason headless Drupal is taking off is that organizations are now grappling with a multitude of channels, including mobile applications, single-page JavaScript applications, IoT applications, digital signage, and content driven by augmented and virtual reality. Increasingly, organizations need a single place to house content.

What you want is an easy but powerful way for **your editorial team** to create and manage content, including administering advanced content models, content versioning, integrating media assets, translations, and more. All of that should be made easy through a great UI without having to involve a developer. This, incidentally, is aligned with Drupal 8's roadmap, in which we are focused on [media management](https://dri.es/a-plan-for-media-management-in-drupal-8), [workflows](https://dri.es/tag/workflow-initiative), layouts, and usability improvements through [our outside-in work](https://dri.es/tag/outside-in).

At the same time, you want to enable **your developers** to easily deliver that content to different devices, channels, and platforms. This means that the content needs to be available through APIs. This, too, is aligned with Drupal 8's roadmap, where we are focused on [web services capabilities](https://dri.es/tag/web-services). Through Drupal's web service APIs, developers can build freely in [different front-end technologies](https://dri.es/selecting-a-client-side-framework-for-drupal), such as Angular, React, Ember, and Swift, as well as Java and .NET. For developers, accomplishing this without the maintenance burden of a full Drupal site or the complexity of configuring standard Drupal to be decoupled is key.

API-first distributions like Reservoir keep Drupal's workflows and editorial UI intact but emphasize Drupal's web service APIs to return control to your developers. But with flexible content modeling and custom fields added to the equation, they also give more control over how editors can curate, combine, and remix content for different channels.

### Success is getting to developer productivity faster

[image drupal/reservoir-side-by-side-previews]

The goal of a content repository should be to make it simple for developers to consume your content, including digital assets and translations, through a set of web service APIs. Success means that a developer can programmatically access your content within minutes.

Reservoir tries to achieve this in four ways:

1. **Easy on-boarding.** Reservoir provides a welcome tour with helpful guidance to create and edit content, map out new content models, manage access control, and most importantly, introspect the web service APIs you'll need to consume to serve your applications.
2. **JSON API standard.** Reservoir makes use of [JSON API](http://jsonapi.org), which is the specification used for many APIs in JSON and adopted by the Ember and Ruby on Rails communities. Using a common standard means you can on-board your developers faster.
3. **Great API documentation.** Reservoir ships with great API documentation thanks to [OpenAPI](https://swagger.io/specification/), formerly known as Swagger, which is a specification for describing an API. If you're not happy with the default documentation, you can bring your own approach by using Reservoir's OpenAPI export.
4. **Libraries, references, and SDKs.** With the [Waterwheel ecosystem](https://dev.acquia.com/blog/waterwheel-the-drupal-sdk-ecosystem/29/08/2016/16701), a series of libraries, references, and SDKs for popular languages like JavaScript and Swift, developers can skip learning the APIs and go straight to integrating Drupal content in their applications.

### Next steps for Reservoir

[image drupal/reservoir-api-documentation]

We have a lot of great plans for Reservoir moving forward. Reservoir has several items on its short-term roadmap, including GraphQL support. As an emerging industry standard for data queries, GraphQL is a query language I first highlighted in [my 2015 Barcelona keynote](https://dri.es/state-of-drupal-presentation-september-2015); see my blog post on [the future of decoupled Drupal](https://dri.es/the-future-of-decoupled-drupal) for a quick demo video.

We also plan to expand API coverage by adding the ability to programmatically manipulate users, tags, and other crucial content elements. This means that developers will be able to build richer integrations.

While content such as articles, pages, and other custom content types can be consumed and manipulated via web services today, upstream in Drupal core, API support for things like Drupal's blocks, menus, and layouts is in the works. The ability to influence more of Drupal's internals from external applications will open the door to better custom editorial interfaces.

### Conclusion

I'm excited about Reservoir, not just because of the promise API-first distributions hold for the Drupal community, but because it helps us reach developers of different stripes who just need a simple content back end, all the while keeping all of the content editing functionality that editorial teams take for granted.

We've put the [Reservoir codebase on GitHub](https://github.com/acquia/reservoir), where you can open an issue, create a pull request, or contribute to documentation. Reservoir only advances when you give us feedback, so please let us know what you think!

*Special thanks to [Preston So](https://www.drupal.org/u/prestonso) for contributions to this blog post and to [Ted Bowman](https://www.drupal.org/u/tedbow), [Wim Leers](https://www.drupal.org/u/wim-leers), and [Matt Grill](https://www.drupal.org/u/drpal) for feedback during the writing process.*
