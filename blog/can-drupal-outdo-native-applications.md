---
url: 'https://dri.es/can-drupal-outdo-native-applications'
title: 'Can Drupal outdo native applications?'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2016-09-14T14:54:21-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: '"Inversion of control" is a powerful design principle that we could use to improve the user experience of Drupal, and rival that of native applications.'
tags:
  - JavaScript
  - Drupal
  - Outside-in
  - 'Headless Drupal'
published: true
id: 3766
---

# Can Drupal outdo native applications?

I've made no secret of my interest in [the open web](https://dri.es/tag/open-web), so it won't come as a surprise that I'd love to see more web applications and fewer native applications. Nonetheless, many argue that "[the future of the internet isn't the web](https://contently.com/strategist/2016/08/09/future-internet-isnt-web/)" and that it's only a matter of time before walled gardens like Facebook and Google – and the native applications which serve as their gatekeepers – overwhelm the web as we know it today: a public, inclusive, and decentralized common good.

I'm not convinced. Native applications seem to be winning because they offer [a better user experience](https://dri.es/winning-back-the-open-web). So the question is: can open web applications, like those powered by [Drupal](https://www.drupal.org), ever match up to the user experience exemplified by native applications? In this blog post, I want to describe inversion of control, a technique now common in web applications and that could benefit Drupal's own user experience.

### Native applications versus web applications

Using a native application – for the first time – is usually a high-friction, low-performance experience because you need to download, install, and open the application (Android's streamed apps notwithstanding). Once installed, native applications offer unique access to smartphone capabilities such as hardware APIs (e.g. microphone, GPS, fingerprint sensors, camera), events such as push notifications, and gestures such as swipes and pinch-and-zoom. Unfortunately, most of these don't have corresponding APIs for web applications.

A web application, on the other hand, is a low-friction experience upon opening it for the first time. While native applications can require a large amount of time to download initially, web applications usually don't have to be installed and launched. Nevertheless, web applications do incur the constraint of low performance when there is significant code weight or dozens of assets that have to be downloaded from the server. As such, one of the unique challenges facing web applications today is how to emulate a native user experience without the drawbacks that come with a closed, opaque, and proprietary ecosystem.

### Inversion of control

In the spirit of open source, the Drupal Association invited experts from the wider front-end community to speak at DrupalCon New Orleans, including from Ember and Angular. [Ed Faulkner](https://www.drupal.org/u/ef4), a member of the [Ember](https://emberjs.com) core team and contributor to the [API-first initiative](https://dri.es/a-roadmap-for-making-drupal-more-api-first), delivered a [fascinating presentation](https://www.youtube.com/watch?v=O12qBp1lWUc) about how Drupal and Ember working in tandem can enrich the user experience.

One of Ember's primary objectives is to demonstrate how web applications can be indistinguishable from native applications. And one of the key ideas of JavaScript frameworks like Ember is *inversion of control*, in which the client side essentially "takes over" from the server side by driving requirements and initiating actions. In the traditional page delivery model, the server is in charge, and the end user has to wait for the next page to be delivered and rendered through a page refresh. With inversion of control, the client is in charge, which enables fluid transitions from one place in the web application to another, just like native applications.

Before the advent of JavaScript and AJAX, distinct states in web applications could be defined only on the server side as individual pages and requested and transmitted via a round trip to the server, i.e. a full page refresh. Today, the client can retrieve application states asynchronously rather than depending on the server for a completely new page load. This improves perceived performance. I discuss the history of this trend in more detail in [this blog post](https://dri.es/a-history-of-javascript-across-the-stack).

Through inversion of control, JavaScript frameworks like Ember provide much more than seamless interactions and perceived performance enhancements; they also offer client-side storage and offline functionality when the client has no access to the server. As a result, inversion of control opens a door to other features requiring the empowerment of the client beyond just client-driven interactions. In fact, because the JavaScript code is run on a client such as a smartphone rather than on the server, it would be well-positioned to access other hardware APIs, like [near-field communication](https://w3c.github.io/web-nfc/), as web APIs become available.

### Inversion of control in end user experiences

[image blog/inversion-of-control-animation resize=false]

In response to our [recent evaluation](https://dri.es/selecting-a-client-side-framework-for-drupal) of JavaScript frameworks and their compatibility with Drupal, Ed applied the inversion of control principle to [Drupal.com](https://www.drupal.com) using Ember. Ed's goal was to enhance Drupal.com's end user experience with Ember to make it more application-like, while also preserving Drupal's editorial and rendering capabilities as much as possible.

Ed's changes are not in production on Drupal.com, but in his demo, clicking a teaser image causes it to "explode" to become the hero image of the destination page. Pairing Ember with Drupal in this way allows a user to visually and mentally transition from a piece of teaser content to its corresponding page via an animated transition between pages – all without a page refresh. The animation is very impressive and the animated GIF above doesn't do it full justice. While this transition across pages is similar to behavior found in native mobile applications, it's not currently possible out of the box in Drupal without extensive client-side control.

Rather than the progressively decoupled approach, which embeds JavaScript-driven components into a Drupal-rendered page, Ed's implementation inverts control by allowing Ember to render what is emitted by Drupal. Ember maintains control over how URLs are loaded in the browser by controlling URLs under its responsibility; take a look at [Ed's DrupalCon presentation](https://www.youtube.com/watch?v=O12qBp1lWUc) to better understand how Drupal and Ember interact in this model.

These impressive interactions are possible using the Ember plugin [Liquid Fire](https://github.com/ember-animation/liquid-fire). Fewer than 20 lines of code were needed to build the animations in Ed's demo, much like how SDKs for native mobile applications provide easy-to-implement animations out of the box. Of course, Ember isn't the only tool capable of this kind of functionality. The [RefreshLess module](https://www.drupal.org/project/refreshless) for Drupal by [Wim Leers](https://www.drupal.org/u/wim-leers) (Acquia) also uses client-side control to enable navigating across pages with minimal server requests. Unfortunately, RefreshLess can't tap into Liquid Fire or other Ember plugins.

### Inversion of control in editorial experiences

[image blog/inversion-of-control-editor resize=false]

We can apply this principle of inversion of control not only to the end user experience but also to editorial experiences. The last demos in Ed's presentation depict [CardStack Editor](https://github.com/ef4/cardstack-editor), a fully decoupled Ember application that uses inversion of control to overlay an administrative interface to edit Drupal content, much like in-place editing.

CardStack Editor communicates with Drupal's web services in order to retrieve and manipulate content to be edited, and in this example Drupal serves solely as a central content repository. This is why the [API-first initiative](https://dri.es/a-roadmap-for-making-drupal-more-api-first) is so important; it enables developers to use JavaScript frameworks to build application-like experiences on top of and backed by Drupal. And with the help of SDKs like [Waterwheel.js](https://github.com/acquia/waterwheel.js) (a native JavaScript library for interacting with Drupal's REST API), Drupal can become a preferred choice for JavaScript developers.

### Inversion of control as the rule or exception?

Those of you following the [outside-in work](https://dri.es/drupal-8-2-now-with-more-outside-in) might have noticed some striking similarities between outside-in and the work Ed has been doing: both use inversion of control. The primary purpose of our outside-in interfaces is to provide for an in-context editing experience in which state changes take effect live before your eyes; hence the need for inversion of control.

Thinking about the future, we have to answer the following question: does Drupal want inversion of control to be the rule or the exception? We don't have to answer that question today or tomorrow, but at some point we should.

If the answer to that question is "the rule", we should consider [embracing a JavaScript framework like Ember](https://dri.es/selecting-a-client-side-framework-for-drupal). The constellation of tools we have in jQuery, Backbone, and the Drupal AJAX framework makes using inversion of control much harder to implement than it could be. With a JavaScript framework like Ember as a standard, implementation could accelerate by becoming considerably easier. That said, there are [many other factors to consider](https://dri.es/how-to-decouple-drupal-in-2019), including the costs of developing and hosting two codebases in different languages.

In the longer term, client-side frameworks like Ember will allow us to build web applications which compete with and even exceed native applications with regard to perceived performance, built-in interactions, and a better developer experience. But these frameworks will also enrich interactions between web applications and device hardware, potentially allowing them to react to pinch-and-zoom, issue native push notifications, and even interact with lower-level devices.

In the meantime, I maintain my recommendation of (1) [progressive decoupling](https://dri.es/the-future-of-decoupled-drupal) as a means to begin exploring inversion of control and (2) a continued focus on the [API-first initiative](https://dri.es/a-roadmap-for-making-drupal-more-api-first) to enable application-like experiences to be developed on Drupal.

### Conclusion

I'm hopeful Drupal can exemplify how the [open web will ultimately succeed](https://dri.es/winning-back-the-open-web) over native applications and walled gardens. Through the API-first initiative, Drupal will provide the underpinnings for web and native applications. But is it enough?

Inversion of control is an important principle that we can apply to Drupal to improve how we power our user interactions and build robust experiences for end users and editors that rival native applications. Doing so will enable us to enhance our user experience long into the future in ways that we may not even be able to think of now. I encourage the community to experiment with these ideas around inversion of control and consider how we can apply them to Drupal.

*Special thanks to [Preston So](https://www.drupal.org/u/prestonso) for contributions to this blog post and to [Angie Byron](https://www.drupal.org/u/webchick), [Wim Leers](https://www.drupal.org/u/wim-leers), [Kevin O'Leary](https://www.drupal.org/u/tkoleary), [Matt Grill](https://www.drupal.org/u/drpal), and [Ted Bowman](https://www.drupal.org/u/tedbow) for their feedback during its writing.*
