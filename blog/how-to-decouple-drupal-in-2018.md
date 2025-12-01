---
title: 'How to decouple Drupal in 2018'
date: '2018-01-10T14:16:07-05:00'
author: Dries
summary: "Do I build my website with Drupal's built-in templating layer or do I use Drupal's decoupled or headless capabilities in combination with a JavaScript framework?"
image: drupal/how-to-decouple-drupal-in-2018-flowchart-full
tags:
  - Drupal
  - JavaScript
  - 'Headless Drupal'
published: true
type: blog
url: /how-to-decouple-drupal-in-2018
id: 4126
---

**Update:** A more up-to-date version of this blog post is available at [How to decouple Drupal in 2019](https://dri.es/how-to-decouple-drupal-in-2019).

Almost two years ago, I had written a blog post called ["How should you decouple Drupal?"](https://dri.es/how-should-you-decouple-drupal). Many people have found the flowchart in that post to be useful in their decision-making on how to approach their Drupal architectures. Since that point, Drupal, its community, and the surrounding market have evolved, and [the original flowchart](https://dri.es/files/images/drupal/how-to-decouple-drupal-in-2017-flowchart-full.jpg) needs a big update.

Drupal's [API-first initiative](https://dri.es/improving-drupal-8-api-first-json-api-oauth2) has introduced new capabilities, and we've seen the advent of the [Waterwheel ecosystem](https://dev.acquia.com/blog/waterwheel-the-drupal-sdk-ecosystem/29/08/2016/16701) and API-first distributions like [Reservoir](https://dri.es/reservoir-a-simple-way-to-decouple-drupal), [Headless Lightning](https://github.com/acquia/headless-lightning), and [Contenta](http://www.contentacms.org/). More developers both inside and outside the Drupal community are experimenting with Node.js and adopting fully decoupled architectures. As a result, [Acquia now offers Node.js hosting](https://dri.es/announcing-node-js-on-acquia-cloud), which means it's never been easier to implement decoupled Drupal on the Acquia platform.

Let's start with the new flowchart in full:

[image drupal/how-to-decouple-drupal-in-2018-flowchart-full resize=false]

### All the ways to decouple Drupal

The **traditional approach** to Drupal architecture, also referred to as *coupled Drupal*, is a monolithic implementation where Drupal maintains control over all front-end and back-end concerns. This is Drupal as we've known it – ideal for traditional websites. If you're a content creator, keeping Drupal in its coupled form is the optimal approach, especially if you want to achieve a fast time to market without as much reliance on front-end developers. But traditional Drupal 8 also remains a great approach for developers who love Drupal 8 and want it to own the entire stack.

A second approach, [**progressively decoupled Drupal**](https://dri.es/the-future-of-decoupled-drupal), offers an approach that strikes a balance between editorial needs like layout management and developer desires to use more JavaScript, by interpolating a JavaScript framework into the Drupal front end. [Progressive decoupling is in fact a spectrum](https://dev.acquia.com/blog/progressively-decoupled-drupal-approaches/22/08/2016/16296), whether it is Drupal only rendering the page's shell and populating initial data – or JavaScript only controlling explicitly delineated sections of the page. Progressively decoupled Drupal hasn't taken the world by storm, likely because it's a mixture of both JavaScript and PHP and doesn't take advantage of server-side rendering via Node.js. Nonetheless, it's an attractive approach because it makes more compromises and offers features important to both editors and developers.

Last but not least, **fully decoupled Drupal** has gained more attention in recent years as the growth of JavaScript continues with no signs of slowing down. This involves a complete separation of concerns between the structure of your content and its presentation. In short, it's like treating your web experience as just another application that needs to be served content. Even though it results in a loss of some out-of-the-box CMS functionality such as in-place editing or content preview, it's been popular because of the freedom and control it offers front-end developers.

### What do you intend to build?

[image drupal/how-to-decouple-drupal-in-2018-flowchart-top-section resize=false]

The most important question to ask is what you are trying to build.

1. If your plan is to create a single standalone website or web application, decoupling Drupal may or may not be the right choice based on the must-have features your developers and editors are asking for.
2. If your plan is to create multiple experiences (including web, native mobile, IoT, etc.), you can use Drupal to provide web service APIs that serve content to other experiences, either as (a) a content repository with no public-facing component or (b) a traditional website that is also a content repository at the same time.

Ultimately, your needs will determine the usefulness of decoupled Drupal for your use case. There is no technical reason to decouple if you're building a standalone website that needs editorial capabilities, but that doesn't mean people don't prefer to decouple because of their preference for JavaScript over PHP. Nonetheless, you need to pay close attention to the needs of your editors and ensure you aren't removing crucial features by using a decoupled approach. By the same token, you can't avoid decoupling Drupal if you're using it as a content repository for IoT or native applications. The next part of the flowchart will help you weigh those trade-offs.

Today, Drupal makes it much easier to build applications consuming decoupled Drupal. Even if you're using Drupal as a content repository to serve content to other applications, well-understood specifications like [JSON API](https://www.drupal.org/project/jsonapi), [GraphQL](https://www.drupal.org/project/graphql), [OpenAPI](https://www.drupal.org/project/openapi), and [CouchDB](https://www.drupal.org/project/relaxed) significantly lower its learning curve and open the door to tooling ecosystems provided by the communities who wrote those standards. In addition, there are now API-first distributions optimized to serve as content repositories and SDKs like [Waterwheel.js](https://dev.acquia.com/blog/getting-started-with-waterwheeljs-and-resource-discovery/30/09/2016/16911) that help developers "speak" Drupal.

### Are there things you can't live without?

[image drupal/how-to-decouple-drupal-in-2018-flowchart-middle-section resize=false]

Perhaps most critical to any decision to decouple Drupal is the must-have feature set desired for both editors and developers. In order to determine whether you should use a decoupled Drupal, it's important to isolate which features are most valuable for your editors and developers. Unfortunately, there is are no black-and-white answers here; every project will have to weigh the different pros and cons.

For example, many marketing teams choose a CMS because they want to create landing pages, and a CMS gives them the ability to lay out content on a page, quickly reorganize a page and more. The ability to do all this without the aid of a developer can make or break a CMS in marketers' eyes. Similarly, many digital marketers value the option to edit content in the context of its preview and to do so across various workflow states. These kind of features typically get lost in a fully decoupled setting where Drupal does not exert control over the front end.

On the other hand, the need for control over the visual presentation of content can hinder developers who want to craft nuanced interactions or build user experiences in a particular way. Moreover, developer teams often want to use the latest and greatest technologies, and JavaScript is no exception. Nowadays, more JavaScript developers are including modern techniques, like server-side rendering and ES6 transpilation, in their toolboxes, and this is something decision-makers should take into account as well.

How you reconcile this tension between developers' needs and editors' requirements will dictate which approach you choose. For teams that have an entirely editorial focus and lack developer resources – or whose needs are focused on the ability to edit, place, and preview content in context – decoupling Drupal will remove all of the critical linkages within Drupal that allow editors to make such visual changes. But for teams with developers itching to have more flexibility and who don't need to cater to editors or marketers, fully decoupled Drupal can be freeing and allow developers to explore new paradigms in the industry – with the caveat that many of those features that editors value are now unavailable.

### What will the future hold?

In the future, and in light of the rapid evolution of decoupled Drupal, my hope is that Drupal keeps shrinking the gap between developers and editors. After all, this was the original goal of the CMS in the first place: to help content authors write and assemble their own websites. Drupal's history has always been a balancing act between editorial needs and developers' needs, even as the number of experiences driven by Drupal grows.

I believe the next big hurdle is how to begin enabling marketers to administer all of the other channels appearing now and in the future with as much ease as they manage websites in Drupal today. In an ideal future, a content creator can build a content model once, preview content on every channel, and use familiar tools to edit and place content, regardless of whether the channel in question is mobile, chatbots, digital signs, or even [augmented reality](https://dri.es/shopping-with-augmented-reality).

Today, developers are beginning to use Drupal not just as a content repository for their various applications but also as a means to create custom editorial interfaces. It's my hope that we'll see more experimentation around conceiving new editorial interfaces that help give content creators the control they need over a growing number of channels. At that point, I'm sure we'll need another new flowchart.

### Conclusion

Thankfully, Drupal is in the right place at the right time. We've anticipated the new world of decoupled CMS architectures with web services in Drupal 8 and older contributed modules. More recently, API-first distributions, SDKs, and even [reference applications in Ember and React](https://dev.acquia.com/blog/decoupling-drupal-with-waterwheel-for-ember-and-react/26/06/2017/18381) are giving developers who have never heard of Drupal the tools to interact with it in unprecedented ways. Moreover, for Acquia customers, [Acquia's recent launch of Node.js hosting on Acquia Cloud](https://dri.es/announcing-node-js-on-acquia-cloud) means that developers can leverage the most modern approaches in JavaScript while benefiting from Drupal's capabilities as a content repository.

Unlike many other content management systems, old and new, Drupal provides a spectrum of architectural possibilities tuned to the diverse needs of different organizations. This flexibility between fully decoupling Drupal, progressively decoupling it, and traditional Drupal – in addition to each solution's proven robustness in the wild – gives teams the ability to make an educated decision about the best approach for them. This optionality sets Drupal apart from new headless content management systems and most SaaS platforms, and it also shows Drupal's maturity as a decoupled CMS over WordPress. In other words, it doesn't matter what the team looks like or what the project's requirements are; Drupal has the answer.

*Special thanks to [Preston So](https://www.drupal.org/u/prestonso) for contributions to this blog post and to [Alex Bronstein](https://www.drupal.org/u/effulgentsia), [Angie Byron](https://www.drupal.org/u/webchick), [Gabe Sullice](https://www.drupal.org/u/gabesullice), [Samuel Mortenson](https://www.drupal.org/u/samuelmortenson), [Ted Bowman](https://www.drupal.org/u/tedbow) and [Wim Leers](https://www.drupal.org/u/wim-leers) for their feedback during the writing process.*
