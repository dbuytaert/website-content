---
url: 'https://dri.es/how-should-you-decouple-drupal'
title: 'How should you decouple Drupal?'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2016-03-22T06:03:37-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: "Do I build my website with Drupal's built-in templating layer or do I use Drupal's decoupled or headless capabilities in combination with a JavaScript framework?"
tags:
  - Drupal
  - JavaScript
  - 'Headless Drupal'
image: drupal/how-to-decouple-drupal-in-2017-flowchart-full
published: true
id: 3616
---

# How should you decouple Drupal?

**Update:** A more up-to-date version of this blog post is available at [How to decouple Drupal in 2019](https://dri.es/how-to-decouple-drupal-in-2019).

With [RESTful web services in Drupal 8 core](https://www.drupal.org/docs/8/core/modules/rest/overview), Drupal can function as an API-first back end serving browser applications, native applications on mobile devices, in-store displays, even in-flight entertainment systems (Lufthansa is doing so in Drupal 8!), and much more. When building a new website or web application in 2016, you may ask yourself: how should I decouple Drupal? Do I build my website with Drupal's built-in templating layer or do I use a JavaScript framework? Do I need Node.js?

There is a lot of hype around decoupled architectures, so before embarking on a project, it is important to make a balanced analysis. Your choice of architecture has implications on your budget, your team, time to launch, the flexibility for content creators, the ongoing maintenance of your website, and more. In this blog post, I'd like to share a flowchart that can help you decide when to use what technology.

[image drupal/how-to-decouple-drupal-in-2017-flowchart-full resize=false]

This flowchart shows three things:

First, using **coupled Drupal** is a perfectly valid option for those who don't need extensive client-side rendering and state management. In this case, you would use Drupal's built-in Twig templating system rather than heavily relying on a JavaScript framework. You would use jQuery to take advantage of limited JavaScript where necessary. Also, with [BigPipe in Drupal 8.1](https://dri.es/bigpipe-no-longer-just-for-the-top-50-websites), certain use cases that typically needed asynchronous JavaScript can now be done in PHP without slowing down the page (i.e. communication with an external web service delaying the display of user-specific real-time data). The advantage of this approach is that content marketers are not blocked by front-end developers as they assemble their user experiences, thus shortening time to market and reducing investment in ongoing developer support.

Second, if you want all of the benefits of a JavaScript framework without completely bypassing Drupal's HTML generation and all that you get with it, I recommend using **progressively decoupled Drupal**. With [progressive decoupling](https://dri.es/the-future-of-decoupled-drupal), you start with Drupal's HTML output, and then use a JavaScript framework to add client-side interactivity on the client side. One of the most visited sites in the world, [The Weather Channel](https://weather.com) (100 million unique visitors per month), does precisely this with Angular 1 layered on top of Drupal 7. In this case, you can enjoy the benefits of having a "decoupled" team made up of both Drupal and JavaScript developers progressing at their own velocities. JavaScript developers can build richly interactive experiences while leaving content marketers free to assemble those experiences without needing a developer's involvement.

Third, whereas **fully decoupled Drupal** makes a lot of sense when building native applications, for most websites, the leap to fully decoupling is not strictly necessary, though a growing number of people prefer using JavaScript these days. Advantages include some level of independence on the underlying CMS, the ability to tap into a rich toolset around JavaScript (e.g. Babel, Webpack, etc.) and a community of JavaScript front-end professionals. But if you are using a universal JavaScript approach with Drupal, it's also important to consider the drawbacks: you need to ask yourself if you're ready to add more complexity to your technology stack and possibly forgo functionality provided by a more integrated content delivery system, such as layout and display management, user interface localization, [and more](https://dri.es/the-future-of-decoupled-drupal). Losing that functionality can be costly, increase your dependence on a developer team, and hinder the end-to-end content assembly experience your marketing team expects, among other things.

It's worth noting that over time we are likely to see better integrations between Drupal and the different JavaScript frameworks (e.g. Drupal modules that export their configuration, and SDKs for different JavaScript frameworks that use that configuration on the client-side). When those integrations mature, I expect more people will move towards fully decoupled Drupal.

To be performant, fully decoupled websites using JavaScript [employ Node.js on the server to improve initial performance](https://dri.es/a-history-of-javascript-across-the-stack), but in the case of Drupal this is not necessary, as Drupal can do the server-side pre-rendering for you. Many JavaScript developers opt to use Node.js for the convenience of shared rendering across server and client rather than for the specific things that Node.js excels in, like real-time push, concurrent connections, and bidirectional client-server communication. In other words, most Drupal websites don't need Node.js.

[image drupal/decoupled-delivery-architectures resize=false]

In practice, I believe many organizations want to use all of these content delivery options. In certain cases, you want to let your content management system render the experience so you can take full advantage of its features with minimal or no development effort (coupled architecture). But when you need to build a website that needs a much more interactive experience or that integrates with unique devices (i.e. on in-store touch screens), you should be able to use that same content management system's content API (decoupled architecture). Fortunately, Drupal allows you to use either. The beauty of choosing from the spectrum of fully decoupled Drupal, progressively decoupled Drupal, and coupled Drupal is that you can do what makes the most sense in each situation.

*Special thanks to [Preston So](https://www.drupal.org/u/prestonso), [Alex Bronstein](https://www.drupal.org/u/effulgentsia) and [Wim Leers](https://www.drupal.org/u/wim-leers) for their contributions to this blog post. We created at least 10 versions of this flowchart before settling on this one.*
