---
url: 'https://dri.es/announcing-node-js-on-acquia-cloud'
title: 'Announcing Node.js on Acquia Cloud'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2017-09-20T10:48:22-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'Acquia Cloud now supports both managed Drupal and managed Node.js'
tags:
  - Drupal
  - Acquia
  - 'Headless Drupal'
  - JavaScript
image: drupal/node-js-on-acquia-cloud
published: true
id: 4026
---

# Announcing Node.js on Acquia Cloud

Today, [Acquia](https://www.acquia.com) announced that it expanded [Acquia Cloud to support Node.js](https://www.acquia.com/about-us/newsroom/press-releases/acquia-debuts-nodejs-and-headless-drupal-acquia-cloud-september-20), the popular open-source JavaScript runtime. This is a big milestone for Acquia as it is the first time we have extended our cloud beyond [Drupal](https://www.drupal.org). I wanted to take some time to explain the evolution of Acquia's open-source stack and why this shift is important for our customers' success.

### From client-side JavaScript to server-side JavaScript

JavaScript was created at Netscape in 1995, when Brendan Eich wrote the first version of JavaScript in just 10 days. It took around 10 years for [JavaScript to reach enterprise maturity](https://dri.es/a-history-of-javascript-across-the-stack), however. Adoption accelerated in 2004 when Google used JavaScript to build the first release of Gmail. In comparison to e-mail competitors like Yahoo! Mail and Hotmail, Gmail showed what was possible with client-side JavaScript, which enables developers to update pages dynamically and reduces full-page refreshes and round trips to the server. The benefit is [an improved user experience](https://dri.es/can-drupal-outdo-native-applications) that is usually faster, more dynamic in its behavior, and generally more application-like.

In 2009, Google invented the [V8 JavaScript engine](https://github.com/v8/v8/wiki), which was embedded into its Chrome browser to make both Gmail and Google Maps faster. Ryan Dahl used the V8 run-time as the foundation of [Node.js](https://nodejs.org), which enabled server-side JavaScript, breaking the language out of the boundaries of the browser. Node.js is [event-driven and provides asynchronous, non-blocking I/O](https://www.youtube.com/watch?v=L_JKb61EalQ) – things that help developers build modern web applications, especially those with real-time capabilities and streamed data. It ushered in the era of [isomorphic applications](https://dri.es/a-history-of-javascript-across-the-stack), which means that JavaScript applications can now share code between the client side and server side. The introduction of Node.js has spurred a JavaScript renaissance and contributed to the popularity of JavaScript frameworks such as [AngularJS](https://angularjs.org), [Ember](https://www.emberjs.com) and [React](https://reactjs.org/).

### Acquia's investment in Headless Drupal

In the web development world, few trends are spreading more rapidly than decoupled architectures using JavaScript frameworks and headless CMS. Decoupled architectures are gaining prominence because architects are looking to take advantage of other front-end technologies, most commonly JavaScript based front ends, in addition to those native to Drupal.

Acquia has been investing in the development of [headless Drupal](https://dri.es/tag/headless-drupal) for nearly five years, when we began contributing to the addition of [web service APIs to Drupal core](https://dri.es/the-future-is-a-restful-drupal). A year ago, we released [ Waterwheel](https://dev.acquia.com/blog/waterwheel-the-drupal-sdk-ecosystem/29/08/2016/16701), an ecosystem of software development kits (SDKs) that enables developers to build Drupal-backed applications in JavaScript and Swift, without needing extensive Drupal expertise. This summer, we released [Reservoir](https://dri.es/reservoir-a-simple-way-to-decouple-drupal), a Drupal distribution for decoupled Drupal. Over the past year, Acquia has helped to support [a variety of headless architectures](https://dri.es/how-should-you-decouple-drupal), with and without Node.js. While not always required, Node.js is often used alongside of a headless Drupal application to provide server-side rendering of JavaScript applications or real-time capabilities.

### Managed Node.js on Acquia Cloud

Previously, if an organization wanted to build a decoupled architecture with Node.js, it was not able to host the Node.js application on Acquia Cloud. This means that the organization would have to run Node.js with a separate vendor. In many instances, this requires organizations to monitor, troubleshoot and patch the infrastructure supporting the Node.js application of their own accord. Separating the management of the Node.js application and Drupal back end not only introduces a variety of complexities, including security risk and governance challenges, but it also creates operational strain. Organizations must rely on two vendors, two support teams, and multiple contacts to build decoupled applications using Drupal and Node.js.

To eliminate this inefficiency, Acquia Cloud can now support both Drupal and Node.js. Our goal is to offer the best platform for developing and running Drupal and Node.js applications. This means that organizations only need to rely on one vendor and one cloud infrastructure when using Drupal and Node.js. Customers can access Drupal and Node.js environments from a single user interface, in addition to tools that enable continuous delivery, continuous integration, monitoring, alerting and support across both Drupal and Node.js.

[image drupal/node-js-on-acquia-cloud resize=false]

### Delivering on Acquia's mission

When reflecting on [Acquia's first decade](https://dri.es/acquia-first-decade-the-founding-story) this past summer, I shared that one of the original corporate values our small team dreamed up was to "empower everyone to rapidly assemble killer websites". After ten years, we've evolved our mission to "build the universal platform for the world's greatest digital experiences". While our focus has expanded as we've grown, Acquia's enduring aim is to provide our customers with the best tools available. Adding Node.js to Acquia Cloud is a natural evolution of our mission.
