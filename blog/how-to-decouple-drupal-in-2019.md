---
title: 'How to decouple Drupal in 2019'
date: '2019-01-24T11:18:25-05:00'
author: Dries
summary: "Do I build my website with Drupal's built-in templating layer or do I use Drupal's decoupled or headless capabilities in combination with a JavaScript framework?"
image: drupal/how-to-decouple-drupal-in-2019-flowchart-full
tags:
  - Drupal
  - JavaScript
  - 'Headless Drupal'
featured: true
published: true
type: blog
url: /how-to-decouple-drupal-in-2019
id: 4721
---

The pace of innovation in content management has been accelerating – driven by both the number of channels that content management systems need to support (web, mobile, social, chat) as well as the need to support JavaScript frameworks in the traditional web channel. As a result, we've seen headless or decoupled architectures emerge.

Decoupled Drupal has seen adoption from all corners of the Drupal community. In response to the trend towards decoupled architectures, I wrote blog posts in [2016](https://dri.es/how-should-you-decouple-drupal) and [2018](https://dri.es/how-to-decouple-drupal-in-2018) for architects and developers about how and when to decouple Drupal. In the time since my last post, the surrounding landscape has evolved, Drupal's web services have only gotten better, and new paradigms such as static site generators and the [JAMstack](https://jamstack.org/) are emerging.

Time to update my recommendations for 2019! As we did a year ago, let's start with the 2019 version of the flowchart in full. (At the end of this post, there is also [an accessible version of this flowchart described in words](https://dri.es/how-to-decouple-drupal-in-2019#accessible-flowchart).)

<div class="large">
  [image drupal/how-to-decouple-drupal-in-2019-flowchart-full resize=false]
</div>

### Different ways to decouple Drupal

I want to revisit some of the established ways to decouple Drupal as well as discuss new paradigms that are seeing growing adoption. As I've written previously, the three most common approaches to Drupal architecture from a decoupled standpoint are *traditional* (or *coupled*), *progressively decoupled*, and *fully decoupled*. The different flavors of decoupling Drupal exist due to varying preferences and requirements.

In **traditional Drupal**, all of Drupal's usual responsibilities stay intact, as Drupal is a monolithic system and therefore maintains complete control over the presentation and data layers. Traditional Drupal remains an excellent choice for editors who need full control over the visual elements on the page, with access to features such as in-place editing and layout management. This is Drupal as we have known it all along. Because the benefits are real, this is still how most new content management projects are built.

Sometimes, JavaScript is required to deliver a highly interactive end-user experience. In this case, a decoupled approach becomes required. In **progressively decoupled Drupal**, a JavaScript framework is layered on top of the existing Drupal front end. This JavaScript might be responsible for nothing more than rendering a single block or component on a page, or it may render everything within the page body. The progressive decoupling paradigm [lies on a spectrum](https://dev.acquia.com/blog/progressively-decoupled-drupal-approaches/22/08/2016/16296); the less of the page dedicated to JavaScript, the more editors can control the page through Drupal's administrative capabilities.

Up until this year, **fully decoupled Drupal** was a single category of decoupled Drupal architecture that reflects a full separation of concerns between the presentation layer and all other aspects of the CMS. In this scenario, the CMS becomes a data provider, and a JavaScript application with server-side rendering becomes responsible for all rendering and markup, communicating with Drupal via web service APIs. Though key functionality like in-place editing and layout management are unavailable, fully decoupled Drupal is appealing for developers who want greater control over the front end and who are already experienced with building applications in frameworks like Angular, React, Vue.js, etc.

Over the last year, fully decoupled Drupal has branched into two separate paradigms due to the increasing complexity of JavaScript development. The so-called *JAMstack* (JavaScript, APIs, Markup) introduces a new approach: **fully decoupled static sites**. The primary reason for static sites is improved performance, security, and reduced complexity for developers. A static site generator like [Gatsby](https://www.gatsbyjs.org/) will retrieve content from Drupal, generate a static website, and deploy that static site to a CDN, usually through a specialized cloud provider such as [Netlify](https://www.netlify.com/).

### What do you intend to build?

<div class="large">
  [image drupal/how-to-decouple-drupal-in-2019-flowchart-top-section resize=false]
</div>

The essential question, as always, is what you're trying to build. Here is updated advice for architects exploring decoupled Drupal in 2019:

1. If your intention is to build a single standalone website or web application, choosing decoupled Drupal may or may not be the right choice, depending on the features your developers and editors see as must-haves.
2. If your intention is to build multiple *web* experiences (websites or web applications), you can use a decoupled Drupal instance either as a) a content repository without its own public-facing front end or b) a traditional website that acts simultaneously as a content repository. Depending on how dynamic your application needs to be, you can choose a JavaScript framework for highly interactive applications or a static site generator for mostly static websites.
3. If your intention is to build multiple *non-web* experiences (native mobile or IoT applications), you can leverage decoupled Drupal to expose web service APIs and consume that Drupal site as a content repository without its own public-facing front end.

What makes Drupal so powerful is that it supports all of these use cases. Drupal makes it simple to build decoupled Drupal thanks to widely recognized standards such as [JSON:API](https://www.drupal.org/project/jsonapi), [GraphQL](https://www.drupal.org/project/graphql), [OpenAPI](https://www.drupal.org/project/openapi), and [CouchDB](https://www.drupal.org/project/relaxed). In the end, it is your **technical requirements** that will decide whether decoupled Drupal should be your next architecture.

In addition to technical requirements, **organizational factors** often come into play as well. For instance, if it is proving difficult to find talented front-end Drupal developers with Twig knowledge, it may make more sense to hire more affordable JavaScript developers instead and build a fully decoupled implementation.

### Are there things you can't live without?

<div class="large">
  [image drupal/how-to-decouple-drupal-in-2019-flowchart-middle-section resize=false]
</div>

As I wrote last year, the most important aspect of any decision when it comes to decoupling Drupal is the list of features your project requires; the needs of editors and developers have to be carefully considered. It is a critical step in your evaluation process to weigh the different advantages and disadvantages. Every project should embark on a clear-eyed assessment of its organization-wide needs.

Many editorial and marketing teams select a particular CMS because of its layout capabilities and rich editing functionality. Drupal, for example, gives editors [the ability to build layouts in the browser and drop-and-drag components into it](https://dri.es/why-drupal-layout-builder-is-so-unique-and-powerful), all without needing a developer to do it for them. Although it is possible to rebuild many of the features available in a CMS on a consumer application, this can be a time-consuming and expensive process.

In recent years, the developer experience has also become an important consideration, but not in the ways that we might expect. While the many changes in the JavaScript landscape are one of the motivations for developers to prefer decoupled Drupal, the fact that there are now multiple ways to write front ends for Drupal makes it easier to find people to work on decoupled Drupal projects. As an example, many organizations are finding it difficult to find affordable front-end Drupal developers experienced in Twig. Moving to a JavaScript-driven front end can resolve some of these resourcing challenges.

This balancing act between the requirements that developers prioritize and those that editors prioritize will guide you to the correct approach for your needs. If you are part of an organization that is mostly editorial, decoupled Drupal could be problematic, because it reduces the amount of control editors have over the presentation of their content. By the same token, if you are part of an organization with more developer resources, fully decoupled Drupal could potentially accelerate progress, with the warning that many mission-critical editorial features disappear.

### Current and future trends to consider

<div class="large">
  [image drupal/how-to-decouple-drupal-in-2019-spectrum-diagram resize=false]
</div>

One of the common complaints I have heard about the JavaScript landscape is that it shows fragmentation and a lack of cohesion due to increasing complexity. This has been a driving force for static site generators. Whereas two years ago, most JavaScript developers would have chosen a fully functional framework like Angular or Ember to create even simple websites, today they might choose a static site generator instead. A static site generator still allows them to use JavaScript, but it is simpler because performance considerations and build processes are offloaded to hosted services rather than the responsibility of developers.

I predict that static site generators will gain momentum in the coming year due to the positive developer experience they provide. Static site generators are also attracting a middle ground of both more experienced and less experienced developers.

### Conclusion

Drupal continues to be an ideal choice for decoupled CMS architectures, and it is only getting better. The API-first initiative is making good progress on preparing the [JSON:API module](https://www.drupal.org/project/jsonapi) for inclusion in Drupal core, and the Admin UI and JavaScript Modernization initiative is working to dogfood Drupal's web services with [a reinvented administrative interface](https://dri.es/working-toward-a-javascript-driven-drupal-administration-interface). Drupal's support for GraphQL continues to improve, and now there is even [a book on the subject of decoupled Drupal](https://dri.es/a-book-for-decoupled-drupal-practitioners). It's clear that developers today have a wide range of ways to work with the rich features Drupal has to offer for decoupled architectures.

With the introduction of fully decoupled static sites as an another architectural paradigm that developers can select, there is an even wider variety of architectural possibilities than before. It means that the spectrum of decoupled Drupal approaches I [defined last year](https://dri.es/how-to-decouple-drupal-in-2018) has become even more extensive. This flexibility continues to define Drupal as an excellent CMS for both traditional and decoupled approaches, with features that go well beyond Drupal's competitors, including WordPress, Sitecore and Adobe. Regardless of the makeup of your team or the needs of your organization, Drupal has a solution for you.

*Special thanks to [Preston So](https://www.drupal.org/u/prestonso) for co-authoring this blog post and to [Angie Byron](https://www.drupal.org/u/webchick), [Chris Hamper](https://www.drupal.org/u/hampercm), [Gabe Sullice](https://www.drupal.org/u/gabesullice), [Lauri Eskola](https://www.drupal.org/u/lauriii), [Ted Bowman](https://www.drupal.org/u/tedbow), and [Wim Leers](https://www.drupal.org/u/wim-leers) for their feedback during the writing process.*

<h3 id="accessible-flowchart">Accessible version of flowchart</h3>

This is an accessible and described version of the flowchart images earlier in this blog post. First, let us list the available architectural choices:

- **Coupled.** Use Drupal as is without additional JavaScript (and as a content repository for other consumers).
- **Progressively decoupled.** Use Drupal for initial rendering with JavaScript on top (and as a content repository for other consumers).
- **Fully decoupled static site.** Use Drupal as a data source for a static site generator and, if needed, deploy to a JAMstack hosting platform.
- **Fully decoupled app.** Use Drupal as a content repository accessed by other consumers (if JavaScript, use Node.js for server-side rendering).

Second, ask the question "What do you intend to build?" and choose among the answers "One experience" or "Multiple experiences".

If you are building one experience, ask the question "Is it a website or web application?" and choose among the answers "Yes, a single website or web application" or "No, Drupal as a repository for non-web applications only".

If you are building multiple experiences instead, ask the question "Is it a website or web application?" with the answers "Yes, Drupal as website and repository" or "No, Drupal as a repository for non-web applications only".

If your answer to the previous question was "No", then you should build a *fully decoupled application*, and your decision is complete. If your answer to the previous question was "Yes", then ask the question "Are there things the project cannot live without?"

Both editorial and developer needs are things that projects cannot live without, and here are the questions you need to ask about your project:

#### Editorial needs

- Do editors need to manipulate page content and layout without a developer?
- Do editors need in-context tools like in-place editing, contextual links, and toolbar?
- Do editors need to preview unpublished content without custom development?
- Do editors need content to be accessible by default like in Drupal's HTML?

#### Developer needs

- Do developers need to have control over visual presentation instead of editors?
- Do developers need server-side rendering or Node.js build features?
- Do developers need JSON from APIs and to write JavaScript for the front end?
- Do developers need data security driven by a publicly inaccessible CMS?

If, after asking all of these questions about things your project cannot live without, your answers show that your requirements reflect a mix of both editorial and developer needs, you should consider a *progressively decoupled* implementation, and your decision is complete.

If your answers to the questions about things your project cannot live without show that your requirements reflect purely developer needs, then ask the question "Is it a static website or a dynamic web application?" and choose among the answers "Static" or "Dynamic." If your answer to the previous question was "Static", you should build a *fully decoupled static site*, and your decision is complete. If your answer to the previous question was "Dynamic", you should build a *fully decoupled app*, and your decision is complete.

If your answers to the questions about things your project cannot live without show that your requirements reflect purely editorial needs, then ask two questions. Ask the first question, "Are there parts of the page that need JavaScript-driven interactions?" and choose among the answers "Yes" or "No." If your answer to the first question was "Yes", then you should consider a *progressively decoupled* implementation, and your decision is complete. If your answer to the first question was "No", then you should build a *coupled* Drupal site, and your decision is complete.

Then, ask the second question, "Do you need to access multiple data sources via API?" and choose among the answers "Yes" or "No." If your answer to the second question was "Yes", then you should consider a *progressively decoupled* implementation, and your decision is complete. If your answer to the second question was "No", then you should build a *coupled* Drupal site, and your decision is complete.
