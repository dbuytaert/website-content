---
url: 'https://dri.es/should-we-decouple-drupal-with-a-client-side-framework'
title: 'Should we decouple Drupal with a client-side framework?'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2015-12-07T08:19:22-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'Should we decouple Drupal with a client-side framework?'
tags:
  - Drupal
  - JavaScript
  - 'Headless Drupal'
published: true
id: 3521
---

# Should we decouple Drupal with a client-side framework?

As user experiences evolve from static pages to application-like experiences, end users' expectations of websites have become increasingly demanding. The Facebook newsfeed, the Gmail inbox, and the Twitter live stream are all compelling examples that form a baseline for the application-like experiences users now take for granted.

Many of Drupal's administrative interfaces and Drupal sites could benefit from a similarly seamless, instantaneous user experience. Drupal's user interfaces for content modeling (Field UI), layout management (Panels), and block management would benefit from no page refreshes, instant previews, and [interface previews](http://www.callumhart.com/blog/non-blocking-uis-with-interface-previews). These traits could also enrich the experience of site visitors; Drupal's commenting functionality could similarly gain from these characteristics and resemble an experience more like the commenting experience found in Facebook.

As Drupal's project lead, I ask myself: how can our community feel enabled and encouraged to start building rich user experiences?

In recent years, the emergence of decoupled architectures with client-side frameworks and libraries have helped our industry build these experiences. Does that mean we have to decouple Drupal's front-facing site experience (for site visitors or end users) and/or the administration experience (for content editors and site builders)? If so, should Drupal decouple the administration layer differently from the front-facing site experience? By extension, should a client-side framework guide this change?

Here is my current thinking: in the short term, Drupal should work toward a next-generation user experience under [progressive decoupling](https://dri.es/the-future-of-decoupled-drupal) for both the administration layer and the end user experience. At the same time, we should enable fully decoupled end-user and administrative experiences to be built on Drupal too. In my view, the best way to achieve this is to formally standardize on a full-featured MV\* *framework* (e.g. [Angular](https://angularjs.org/), [Ember](https://emberjs.com/), [Backbone](https://backbonejs.org/), and [Knockout](http://knockoutjs.com/)) or a component-based view *library* (e.g. [React](https://reactjs.org/), [Vue](http://vuejs.org), and [Riot](http://riotjs.com/)). In this blog post, I want to kick off the discussion and walk you through my current position in some more detail.

### Should we decouple Drupal itself?

[image drupal/should-we-decouple-drupal-framework-responsibility resize=false]

The question we have to answer is: do we stand to benefit from decoupling Drupal? In this context, *decoupled Drupal* refers to a separation between the Drupal back end and one or more front ends. In a decoupled architecture, the back end is built in a server-side language like PHP, the front end is built using a client-side framework written in JavaScript, and data is transferred between the two. Decoupling your content management system gives front-end developers greater control over an application or site's rendered markup and user experience, and using a client-side framework gives them better tools to build application-like experiences.

There is no doubt that Drupal's administration layer is very application-like and would benefit from an experience that is more interactive. For the end-user experience, a decoupled implementation is not always the best option. Some sites may not need or want the application-like interactivity that a client-side framework would provide, since not every site needs interaction. For instance, news sites or blogs do not need much interactivity, custom applications need a great deal, while e-commerce sites lie somewhere in the middle. It's not clear-cut, so let's look at our options in more detail.

The first option is to *preserve traditional Drupal*, the status quo where there is no decoupling. This would leave the Drupal theme layer intact apart from additional JavaScript embedded freely by the developer, but as a result, the onus is on the developer to introduce client-side user experience improvements. The likely outcome is that different modules will start using different client-side frameworks. Such a scenario would steepen Drupal's learning curve, impede collaboration, make Drupal more brittle, and damage performance on pages whose display is influenced by front-end components of multiple modules.

The second option is to work toward *full decoupling*, in which Drupal is solely a themeless content repository for client-side applications. But fully decoupling both the Drupal administrative interface and the front end would require us to [rebuild much of our page building functionality](https://dri.es/the-future-of-decoupled-drupal) (e.g. site preview, layouts, and block placement) and to abandon [many performance benefits of Drupal 8](https://dri.es/making-drupal-8-fly). Moreover, more JavaScript, especially on the server side, means complicating infrastructure requirements and a large-scale overhaul of server-side code.

The third option is what I call *progressive decoupling*, where Drupal renders templates on the server to provide an initial application state, and JavaScript then manipulates that state. This means we can have the best of both worlds: unobtrusive JavaScript and all the out-of-the-box performance advantages of Drupal 8 – a short time to first paint (when the user sees the page materialize) via BigPipe as well as interface previews and static fallbacks during the time to first interaction (when the user can perform an action). Plus, while some additional JavaScript would enter the picture, progressive decoupling mitigates the amount of change needed across the stack by using a baseline of existing theme functionality.

<small>
  <table>
   <tr>
    <th>Approach</th>
    <th>User experience</th>
    <th>Developer experience</th>
    <th>Ease of implementation</th>
  </tr>
   <tr>
    <td>
      <strong>Traditional coupling</strong>
   </td>
    <td>
      <em>Page refreshes</em>
      <em>No immediate feedback</em>
      <em>Interrupted workflow</em>
   </td>
    <td>
      Theme layer preserved
      Modules in mostly PHP
      <em>Ad-hoc client-side code</em>
   </td>
    <td>
      PHP and minimal JavaScript
      No server-side change
      No client-side change
   </td>
  </tr>
   <tr>
    <td>
      <strong>Progressive decoupling</strong>
   </td>
    <td>
      No page refreshes
      Immediate feedback
      Uninterrupted workflow
   </td>
    <td>
      Theme layer preserved
      Modules in PHP and JavaScript
      Unified client-side code
   </td>
    <td>
      <em>Both PHP and JavaScript</em>
      Some server-side change
      Some client-side change
   </td>
  </tr>
   <tr>
    <td>
      <strong>Full decoupling</strong>
   </td>
    <td>
      No page refreshes
      Immediate feedback
      Uninterrupted workflow
   </td>
    <td>
      <em>Theme layer replaced</em>
      <em>Module rewrites in JavaScript</em>
      Unified client-side code
   </td>
    <td>
      <em>Primarily JavaScript</em>
      <em>Much server-side change</em>
      <em>Much client-side change</em>
   </td>
  </tr>
 </table>
</small>

### How should Drupal decouple its user experience?

[image drupal/should-we-decouple-drupal-front-end-experiences resize=false]

Drupal's *administration layer* (content editor and site builder experience) is effectively an application. Fully decoupling may be the appropriate call to achieve the best possible user experience for creating, managing and presenting content. However, rewriting the administration layer from the ground up is a monumental task, especially since its modules provide powerful interfaces that allow site builders to build robust, complex sites without a line of code.

The same expectations for application-like interactivity often hold for the *end-user experience*: users expect shopping carts, comments, notifications, and searches to be updated instantaneously, without having to wait for a page to load.

For both the administration layer and the end-user experience, I believe the Drupal front end should not be fully decoupled out of the box. We should advance from our traditional paradigm and default to [progressive decoupling](https://dri.es/the-future-of-decoupled-drupal). It allows us to achieve the user experience we want without significant downsides, since not every use case would benefit from fully decoupling. Through progressive decoupling, Drupal could potentially reach the ideals of [the assembled web](https://dri.es/the-assembled-web) more quickly by preserving a tight link between Drupal modules and their front-end components.

Nonetheless, we should empower people building fully decoupled sites and applications. Depending on the use case, Drupal 8 is a good match for decoupled applications but we should improve and extend Drupal's REST API, enhance contributed modules such as [Services](https://www.drupal.org/project/services), and shore up new features such as [GraphQL](https://www.drupal.org/project/graphql) ([demo video](https://www.youtube.com/watch?v=ZjDYg6NrAys)) so more functionality can be decoupled. Front-end developers can then use any framework of their choice – whether it is Angular, Ember, React, or something else – to build a fully decoupled administrative application.

### Should Drupal standardize on a single framework?

All things considered, I do believe Drupal should standardize on a single client-side framework, but it should only make such an explicit recommendation for progressively decoupled Drupal, not fully decoupled architectures. It would result in a more seamless user experience, better compatibility across interactive components in modules, maximum code reuse, a more consistent front-end developer experience, more maintainable code, and better performance as we don't have to load multiple frameworks.

Despite the potential benefits, there are also good reasons not to embrace a single client-side framework. New front-end frameworks are being created at what feels like an unsustainable pace; every nine months there is a new kid on the block. It's hard for a project as large as Drupal to embrace a single technology when there is no guarantee of its longevity.

For instance, [Backbone](https://backbonejs.org/), with its underlying library [Underscore](https://underscorejs.org/), currently powers interactions in [the toolbar and in-place editing in Drupal 8](https://dri.es/spark-update-in-line-editing-in-drupal). Though Drupal could expand the scope of Backbone in core and encourage front-end developers to build with it, it means buying even further into a framework that is quite old among its peers.

To deal with the fast-evolving nature of the front-end landscape, we need to be thoughtful about which framework we choose, to reassess our choice from time to time, and to make sure we can migrate fairly easily if we so decide.

### What client-side framework should Drupal standardize on?

Assuming we agree that embracing a single client-side framework makes sense for Drupal, there are actually three additional questions: what framework to standardize on, how to do it, and when to decide.

I'm the first to admit I'm not the best person to answer the first question. As I'm not a front-end developer, I'm looking at you, the Drupal community, to help answer this question. I'd hope that the chosen framework aligns well with both our architecture (modular, flexible) and community (collaborative, community-driven).

The second question – how to standardize on a framework – I can help answer. On the one extreme, Drupal could be opinionated and ship a client-side framework with Drupal core, meaning that every installation of Drupal ships with the chosen framework. This would be much like the adoptions of jQuery and Backbone.js. On the other end of the spectrum, Drupal could recommend a specific framework but not ship with it. Finally, somewhere in between, Drupal could provide a default standard framework in core but make it easy to replace with it a framework of a developer's choice, though the likelihood of this is quite small. This is akin to Drupal core shipping with a template engine (i.e. PHPTemplate) that could be (but was rarely) replaced with another. Ultimately, I think we get the best result if Drupal ships with a specific framework–much like the adoption of jQuery in Drupal 5.

The last question, when to standardize on a framework, is important too. I would recommend we experiment with possible directions as soon as possible in order to decide on a final vision sooner rather than later.

### Conclusion

I believe that, for now, it makes more sense to progressively decouple Drupal sites and their administration layer by first building our pages with Drupal. Once the page is loaded, we can let a unified client-side framework take over as much of the page as needed to foster a next-generation user experience without reinventing the wheel or alienating developers.

Whatever the result of this debate, Drupal needs your help. We will need initiatives to build a foundation for better decoupled experiences. For all decoupled implementations - whether full or progressive - we will want to redouble our efforts on existing web services to create the best APIs for client-side applications. As for progressively decoupled experiences, we will need a process for selecting a client-side framework and defining how the existing Drupal JavaScript behaviors system would need to evolve. Finally, we will need to coordinate all of these efforts to focus on offering a better administrative experience.

That is not all! We will need module developers to bring rich interactions to their user interfaces with the help of the framework we choose. We will need designers to guide module developers in building a graceful user interface. We will need front-end developers to demonstrate how they want to develop the user experiences that will define Drupal for years to come. We will need users to test and validate all of our work. It will be tough going, but together, we can ensure Drupal stays ahead of the curve well into the future.

*Special thanks to [Preston So](https://www.drupal.org/u/prestonso) and [Wim Leers](https://www.drupal.org/u/wim-leers) for contributions to this blog post and to [Moshe Weitzman](https://www.drupal.org/u/moshe-weitzman) and [Gábor Hojtsy](https://www.drupal.org/u/gabor-hojtsy) for feedback during its writing.*
