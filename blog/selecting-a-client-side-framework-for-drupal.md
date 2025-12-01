---
title: 'Selecting a client-side framework for Drupal'
date: '2016-01-06T10:00:18-05:00'
author: Dries
summary: 'Selecting a client-side framework for Drupal'
tags:
  - Drupal
  - JavaScript
  - 'Headless Drupal'
published: true
type: blog
url: /selecting-a-client-side-framework-for-drupal
id: 3541
---

Last month, my blog post about [whether a client-side framework is right for Drupal](https://dri.es/should-we-decouple-drupal-with-a-client-side-framework) stimulated some excellent insights into how the future of the Drupal front end might look. There was broad agreement that incorporating more JavaScript into Drupal's administrative interface is important for a future-ready user experience.

I am confident that adopting a client-side framework through [progressive decoupling](https://dri.es/the-future-of-decoupled-drupal) will give us the best of both worlds. Of course, this does not mean I oppose fully decoupling through any other framework; in fact, I believe we should redouble our efforts toward a first-class API-first Drupal. But progressive decoupling means that we will be able to work toward a next-generation user experience without abandoning much of the work we've done so far.

With that in mind, I tasked a small team made up of various experts from the Drupal and various JavaScript communities with putting together a list of criteria and a comparison matrix to help us decide on the most appropriate client-side framework for progressive decoupling in Drupal.

### JavaScript framework comparison matrix

After a hundred hours of work, we came up with a [criteria document and comparison matrix](https://docs.google.com/document/d/1eDnJ-NpJBjicxVkrZgCwMHewSZUUePVY6LCVPS_swAw/pub) ([PDF version](https://dri.es/files/javascript-framework-comparison-january-2016.pdf)).

Special thanks to all of the following experts who provided review and input: [Miško Hevery](https://github.com/mhevery) (creator of Angular; Google) and [Igor Minar](https://github.com/igorminar) (technical lead for Angular; Google); [Ed Faulkner](https://github.com/ef4) (core maintainer for Ember); [Amitai Burstein](https://www.drupal.org/u/amitaibu) (Drupal and Elm contributor; Gizra); [Sebastian Siemssen](https://www.drupal.org/u/fubhy) (Drupal contributor, Elm and React developer; Zensations); and [John Albin Wilkins](https://www.drupal.org/u/johnalbin) (Drupal 8 mobile initiative lead), [Alex Bronstein](https://www.drupal.org/u/effulgentsia) (Drupal core maintainer; Acquia), [Wim Leers](https://www.drupal.org/u/wim-leers) (Drupal core contributor; Acquia), and [Preston So](https://www.drupal.org/u/prestonso) (Drupal contributor, Acquia).

Though this is a good starting point that lays the groundwork for a formal adoption process in Drupal core, it is time to open [our comparison](https://docs.google.com/document/d/1eDnJ-NpJBjicxVkrZgCwMHewSZUUePVY6LCVPS_swAw/pub) for review by members of both the Drupal and JavaScript communities. We should also more rigorously evaluate these frameworks' appropriateness through actual development.

First, have we decided on the right criteria regardless of the frameworks themselves? This is probably the most important at this stage. While many organizations choose to adopt client-side frameworks for fully decoupled implementations, Drupal is the first to consider layering a framework on top to allow both richly dynamic and more traditional modules to coexist gracefully through progressive decoupling. What issues around templates, rendering, and client-side caching should we incorporate into these criteria? Is there anything missing or overemphasized?

Second, have we selected the right frameworks to focus on? Are there other frameworks, libraries, or even compile-to-JavaScript projects (such as Elm) that should be included in the matrix? In my view, it is best for Drupal to adopt a framework with an already large community and ecosystem that would allow us to more quickly bridge the gap and resolve any friction during adoption. To provide a good frame of reference, we've also included Backbone, Angular, and Knockout, all three slightly older among client-side frameworks. Others on our shortlist that we didn't consider due to low levels of adoption and small communities are Mithril, Riot, and Vue. Still other ambitious projects such as the Elm and ClojureScript languages are also candidates, but their adoption will mean more up-front work to support typical features of client-side frameworks, as well as buy-in into an approach where JavaScript is compiled from a different language.

Finally, have we drawn the right conclusions against these criteria? In other words, did we fill out the cells correctly? While they have been reviewed by some of the frameworks' experts, there might be unexpected gotchas or caveats.

I'm sharing the initial comparison matrix on my blog for maximum reach; I want both the Drupal community and the JavaScript framework communities, as well as the broader front-end community, to take note. After three installments on my blog (["The future of decoupled Drupal"](https://dri.es/the-future-of-decoupled-drupal), ["Should we decouple Drupal with a client-side framework?"](https://dri.es/should-we-decouple-drupal-with-a-client-side-framework)), it's time to move the technical conversation to drupal.org. There is now [an issue in the core issue queue on drupal.org](https://www.drupal.org/node/2645250) to iterate on the matrix.

### Preliminary conclusions

At the moment, the most promising candidates in the comparison matrix appear to be Angular 2, Ember, and React, given their technical robustness, relative suitability for progressively decoupled Drupal, and their strong levels of community support and broader adoption. Given that Backbone is already in core and several modules already rely on it, we have included it too.

What we've learned from talking to the different projects is that they are often converging on similar techniques and best practices; they are by and large adding support for Virtual DOM implementations or rehydration (seamless state transfer), and they are all obsessing over small payload size and performance, better testability, etc. Therefore it is important to focus on the fundamental, often philosophical, differences between the projects that will likely be unchanged in time; key architectural differences, their release cadence and stance on backward compatibility, their license, their governance model, their flexibility and learning curve, etc.

From a quick glance at the criteria and our needs, it seems that Ember is currently our best candidate, as it appears to have a slight technical edge overall. Ember 2.0 has an all-new rendering engine named Glimmer, and it has server-side rendering through FastBoot. On the other hand, however, Ember is quite bulky and opinionated (enforcing patterns for code structure) compared to other candidate frameworks. A more fundamental difference is that unlike Angular and React, which have corporate governance and funding, Ember is a community-driven project like Drupal.

While React is lightweight, it needs integration with a variety of other libraries in the React ecosystem to work as a full-fledged implementation, which gives it a steep learning curve from an implementation standpoint. Because React is a relatively young project, best practices are shifting quickly and making it less attractive. The Virtual DOM, among React's most compelling features, has also seen its core ideas filter into other framework projects. But more importantly, React is licensed with what I believe to be a potentially unacceptable [patent clause](https://github.com/facebook/react/blob/master/PATENTS), which states that an organization can no longer use React once it sues Facebook for any (unrelated) patent infringement. This has already generated some concerted pushback from both [WordPress's Calypso](https://github.com/automattic/wp-calypso/issues/650) and [React](https://github.com/facebook/react/pull/3554) contributors.

Angular 2 is a complete rewrite of Angular 1 to address issues with that version of the framework, including performance problems stemming from a large file size. The new version also introduces a new template engine that incorporates both directives familiar to Angular 1 developers and nestable component-based templates. But Angular 2's Apache 2.0 licensing is [incompatible with Drupal's own GPLv2 license](http://www.gnu.org/licenses/license-list.html#apache2). While Drupal's PHP code and JavaScript code run in isolated processes, it appears that an Apache 2.0-licensed project [can't be jointly distributed](http://www.gnu.org/licenses/gpl-faq.html#WhatDoesCompatMean) within an umbrella project that uses a GPLv2 license.

In addition to being at a slight technical disadvantage to Ember, the legal concerns with React and Angular make me believe Ember might be our best bet. But I'm not a lawyer nor a JavaScript expert, so I can't make this decision alone; I'm looking for lots of feedback, particularly from JavaScript experts, to determine the best option for Drupal.

### Conclusion

Whatever the result of the debate around which client-side framework to adopt, I believe that Drupal needs to move quickly to embrace a framework that will aid development of a progressively decoupled architecture and corresponding user experience improvements. By providing some baseline criteria and including our accomplished community, I have no doubt we can reach this decision quickly but also intelligently.

*Special thanks to [Preston So](https://www.drupal.org/u/prestonso) for contributions to this blog post.*
