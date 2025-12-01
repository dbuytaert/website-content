---
title: 'A history of JavaScript across the stack'
date: '2016-02-22T12:10:16-05:00'
author: Dries
summary: 'It took JavaScript 20 years, but now it is a well-established programming language for the web.'
image: blog/universal-javascript
tags:
  - Drupal
  - JavaScript
featured: true
published: true
type: blog
url: /a-history-of-javascript-across-the-stack
id: 3581
---

[image blog/javascript-powered-multichannel]

Did you know that JavaScript was created in 10 days? In May 1995, [Brendan Eich](https://en.wikipedia.org/wiki/Brendan_Eich) wrote the first version of JavaScript in 10 days while working at Netscape.

For the first 10 years of JavaScript's life, professional programmers denigrated JavaScript because its target audience consisted of "amateurs". That changed in 2004 with the launch of Gmail. Gmail was the first popular web application that really showed off what was possible with client-side JavaScript. Competing e-mail services such as Yahoo! Mail and Hotmail featured extremely slow interfaces that used server-side rendering almost exclusively, with almost every action by the user requiring the server to reload the entire web page. Gmail began to work around these limitations by using [XMLHttpRequest](https://en.wikipedia.org/wiki/XMLHttpRequest) for asynchronous data retrieval from the server. Gmail's use of JavaScript caught the attention of developers around the world. Today, Gmail is the classic example of a single-page JavaScript app; it can respond immediately to user interactions and no longer needs to make roundtrips to the server just to render a new page.

A year later in 2005, Google launched Google Maps, which used the same technology as Gmail to transform online maps into an interactive experience. With Google Maps, Google was also the first large company to offer a JavaScript API for one of their services allowing developers to integrate Google Maps into their websites.

Google's `XMLHttpRequest` approach in Gmail and Google Maps ultimately came to be called [Ajax](http://adaptivepath.org/ideas/ajax-new-approach-web-applications/) (originally "Asynchronous JavaScript and XML"). Ajax described a set of technologies, of which JavaScript was the backbone, used to create web applications where data can be loaded in the background, avoiding the need for full page refreshes. This resulted in a renaissance period of JavaScript usage spearheaded by open source libraries and the communities that formed around them, with libraries such as Prototype, jQuery, Dojo and Mootools. (We added jQuery to Drupal core as early as 2006.)

In 2008, Google launched Chrome with a faster JavaScript engine called V8. The [release announcement](https://googleblog.blogspot.com/2008/09/fresh-take-on-browser.html) read: *"We also built a more powerful JavaScript engine, V8, to power the next generation of web applications that aren't even possible in today's browsers."*. At the launch, V8 improved JavaScript performance by 10x over Internet Explorer by compiling JavaScript code to native machine code before executing it. This caught my attention because I had recently finished [my PhD thesis](https://dri.es/files/phd-thesis.pdf) on the topic of JIT compilation. More importantly, this marked the beginning of different browsers competing on JavaScript performance, which helped drive JavaScript's adoption.

In 2010, Twitter made a move unprecedented in JavaScript's history. For the [Twitter.com redesign in 2010](https://blog.twitter.com/engineering/en_us/a/2010/the-tech-behind-the-new-twittercom.html), they began implementing a new architecture where substantial amounts of server-side code and client-side code were built almost entirely in JavaScript. On the server side, they built an API server that offered a single set of endpoints for their desktop website, their mobile website, their native apps for iPhone, iPad, and Android, and every third-party application. As a result, they moved much of the UI rendering and corresponding logic to the user's browser. A JavaScript-based client fetches the data from the API server and renders the Twitter.com experience.

Unfortunately, the redesign caused severe performance problems, particularly on mobile devices. Lots of JavaScript had to be downloaded, parsed and executed by the user's browser before anything of substance was visible. The "time to first interaction" was poor. Twitter's new architecture broke new ground by offering a number of advantages over a more traditional approach, but it lacked support for various optimizations available only on the server.

Twitter suffered from these performance problems for almost two years. Finally in 2012, [Twitter reversed course](https://blog.twitter.com/engineering/en_us/a/2012/improving-performance-on-twittercom.html) by passing more of the rendering back to the server. The revised architecture renders the initial pages on the server, but asynchronously bootstraps a new modular JavaScript application to provide the fully-featured interactive experience their users expect. The user's browser runs no JavaScript at all until after the initial content, rendered on the server, is visible. By using server-side rendering, the client-side JavaScript could be minimized; fewer lines of code meant a smaller payload to send over the wire and less code to parse and execute. This new hybrid architecture reduced Twitter's page load time by 80%!

In 2013, [Airbnb was the first](http://nerds.airbnb.com/isomorphic-JavaScript-future-web-apps/) to use Node.js to provide *isomorphic* (also called *universal* or simply *shared*) JavaScript. In the Node.js approach, the same framework is identically executed on the server side and client side. On the server side, it provides an initial render of the page, and data could be provided through Node.js or through REST API calls. On the client side, the framework binds to DOM elements, "rehydrates" (updates the initial server-side render provided by Node.js) the HTML, and makes asynchronous REST API calls whenever updated data is needed.

The biggest advantage Airbnb's JavaScript isomorphism had over Twitter's approach is the notion of a *completely reusable rendering system*. Because the client-side framework is executed the same way on both server and client, rendering becomes much more manageable and debuggable in that the primary distinction between the server-side and client-side renders is not the language or templating system used, but rather what data is provisioned by the server and how.

[image blog/universal-javascript resize=false]

From a prototype written in 10 days to being used across the stack by some of the largest websites in the world, long gone are the days of clunky browser implementations whose APIs changed depending on whether you were using Netscape or Internet Explorer. It took JavaScript 20 years, but it is finally considered an equal partner to traditional, well-established server-side languages.
