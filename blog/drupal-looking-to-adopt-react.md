---
title: 'Drupal looking to adopt React'
date: '2017-10-02T13:32:10-04:00'
author: Dries
summary: 'Drupal looking to adopt React for its administrative UIs'
image: blog/drupal-react
tags:
  - Drupal
  - 'Headless Drupal'
  - 'Web services'
  - JavaScript
published: true
type: blog
url: /drupal-looking-to-adopt-react
id: 4036
---

[image blog/drupal-react resize=false]

Last week at DrupalCon Vienna, I proposed adding a modern JavaScript framework to Drupal core. After the keynote, I met with core committers, framework managers, JavaScript subsystem maintainers, and JavaScript experts in the Drupal community to discuss next steps. In this blog post, I look back on how things have evolved, since the last time we explored adding a new JavaScript framework to Drupal core two years ago, and what we believe are the next steps after DrupalCon Vienna.

As a group, we agreed that we had learned a lot from watching the JavaScript community grow and change since our initial exploration. We agreed that today, React would be the most promising option given its expansive adoption by developers, its unopinionated and component-based nature, and its well-suitedness to building new Drupal interfaces in an incremental way. Today, I'm formally proposing that the Drupal community adopt React, after discussion and experimentation has taken place.

### Two years ago, it was premature to pick a JavaScript framework

Three years ago, I developed several convictions related to "headless Drupal" or "decoupled Drupal". I believed that:

1. More and more organizations wanted a headless Drupal so they can use a modern JavaScript framework to build application-like experiences.
2. Drupal's authoring and site building experience could be improved by using a more modern JavaScript framework.
3. JavaScript and Node.js were going to take the world by storm and that we would be smart to increase the amount of JavaScript expertise in our community.

(For the purposes of this blog post, I use the term "framework" to include both full MV\* frameworks such as Angular, and also view-only libraries such as React combined piecemeal with additional libraries for managing routing, states, etc.)

By September 2015, I had built up enough conviction to write several long blog posts about these views ([post 1](https://dri.es/the-future-of-decoupled-drupal), [post 2](https://dri.es/should-we-decouple-drupal-with-a-client-side-framework), [post 3](https://dri.es/selecting-a-client-side-framework-for-drupal)). I felt we could accomplish all three things by adding a JavaScript framework to Drupal core. After [careful analysis](https://dri.es/selecting-a-client-side-framework-for-drupal), I recommended that we consider [React](https://reactjs.org/), [Ember](https://www.emberjs.com/) and [Angular](https://angular.io/). My first choice was Ember, because I had concerns about a patent clause in Facebook's open-source license ([since removed](https://code.facebook.com/posts/300798627056246/relicensing-react-jest-flow-and-immutable-js/)) and because Angular 2 was not yet in a stable release.

At the time, the Drupal community didn't like the idea of picking a JavaScript framework. The overwhelming reactions were these: it's too early to tell which JavaScript framework is going to win, the risk of picking the wrong JavaScript framework is too big, picking a single framework would cause us to lose users that favor other frameworks, etc. In addition, there were a lot of different preferences for a wide variety of JavaScript frameworks. While I'd have preferred to make a bold move, the community's concerns were valid.

### Focusing on Drupal's web services instead

By May of 2016, after listening to the community, I changed my approach; instead of adding a specific JavaScript framework to Drupal, I decided we should double down on improving [Drupal's web service APIs](https://dri.es/tag/web-services). Instead of being opinionated about what JavaScript framework to use, we would allow people to use their JavaScript framework of choice.

I did a deep dive on [the state of Drupal's web services in early 2016](https://dri.es/an-overview-of-web-service-solutions-in-drupal-8) and helped define various next steps ([post 1](https://dri.es/advancing-drupal-web-services), [post 2](https://dri.es/a-roadmap-for-making-drupal-more-api-first), [post 3](https://dri.es/improving-drupal-8-api-first-json-api-oauth2)). I asked a few of the OCTO team members to focus on improving Drupal 8's web services APIs; funded improvements to Drupal core's REST API, as well as [JSON API](https://www.drupal.org/project/jsonapi), [GraphQL](https://www.drupal.org/project/graphql) and [OpenAPI](https://www.drupal.org/project/openapi); supported the creation of [Waterwheel projects](https://dev.acquia.com/blog/waterwheel-the-drupal-sdk-ecosystem/29/08/2016/16701) to help bootstrap an ecosystem of JavaScript front-end integrations; and most recently [supported the development of Reservoir](https://dri.es/reservoir-a-simple-way-to-decouple-drupal), a Drupal distribution for headless Drupal. There is also a lot of innovation coming from the community with lots of work on the [Contenta distribution](http://www.contentacms.org/), JSON API, GraphQL, and more.

The end result? Drupal's web service APIs have progressed significantly the past year. Ed Faulkner of Ember told us: <q>I'm impressed by how fast Drupal made lots of progress with its REST API and the JSON API contrib module!"</q>. It's a good sign when a core maintainer of one of the leading JavaScript frameworks acknowledges Drupal's progress.

### The current state of JavaScript in Drupal

Looking back, I'm glad we decided to focus first on improving Drupal's web services APIs; we discovered that there was a lot of work left to stabilize them. Cleanly integrating a JavaScript framework with Drupal would have been challenging 18 months ago. While there is still [more work to be done](https://www.drupal.org/node/2905563), Drupal 8's available web service APIs have matured significantly.

Furthermore, by not committing to a specific framework, we are seeing Drupal developers explore a range of JavaScript frameworks and members of multiple JavaScript framework communities consuming Drupal's web services. I've seen Drupal 8 used as a content repository behind Angular, Ember, React, Vue, and other JavaScript frameworks. Very cool!

There is a lot to like about how Drupal's web service APIs matured and how we've seen Drupal integrated with a variety of different frameworks. But there is also no denying that not having a JavaScript framework in core came with certain tradeoffs:

1. It created a barrier for significantly leveling up the Drupal community's JavaScript skills. In my opinion, we still lack sufficient JavaScript expertise among Drupal core contributors. While we do have JavaScript experts working hard to maintain and improve our existing JavaScript code, I would love to see more experts join that team.
2. It made it harder to accelerate certain improvements to Drupal's authoring and site building experience.
3. It made it harder to demonstrate how new best practices and certain JavaScript approaches could be leveraged and extended by core and contributed modules to create new Drupal features.

One trend we are now seeing is that traditional MV\* frameworks are giving way to component libraries; most people seem to want a way to compose interfaces and interactions with reusable components (e.g. libraries like React, Vue, Polymer, and Glimmer) rather than use a framework with a heavy focus on MV\* workflows (e.g. frameworks like Angular and Ember). This means that [my original recommendation of Ember](https://dri.es/selecting-a-client-side-framework-for-drupal) needs to be revisited.

Several years later, we still don't know what JavaScript framework will win, if any, and I'm willing to bet that waiting two more years won't give us any more clarity. JavaScript frameworks will continue to evolve and take new shapes. Picking a single one will always be difficult and to some degree "premature". That said, I see React having the most momentum today.

### My recommendations at DrupalCon Vienna

Given that it's been almost two years since I last suggested adding a JavaScript framework to core, I decided to bring the topic back in [my DrupalCon Vienna keynote presentation](https://dri.es/state-of-drupal-presentation-september-2017). Prior to my keynote, there had been some [renewed excitement and momentum](https://www.drupal.org/node/2645250) behind the idea. Two years later, here is what I recommended we should do next:

- **Invest more in Drupal's API-first initiative.** In 2017, there is no denying that decoupled architectures and headless Drupal will be a big part of our future. We need to keep investing in Drupal's web service APIs. At a minimum, we should expand Drupal's web service APIs and standardize on JSON API. Separately, we need to examine how to give API consumers more access to and control over Drupal's capabilities.
- **Embrace all JavaScript frameworks for building Drupal-powered applications.** We should give developers the flexibility to use their JavaScript framework of choice when building front-end applications on top of Drupal – so they can use the right tool for the job. The fact that you can front Drupal with Ember, Angular, Vue, React, and others is a great feature. We should also invest in expanding [the Waterwheel ecosystem](https://dev.acquia.com/blog/waterwheel-the-drupal-sdk-ecosystem/29/08/2016/16701) so we have SDKs and references for all these frameworks.
- **Pick a framework for Drupal's own administrative user interfaces.** Drupal should pick a JavaScript framework for its own administrative interface. I'm not suggesting we abandon our stable base of PHP code; I'm just suggesting that we leverage JavaScript for the things that JavaScript is great at by moving relevant parts of our code from PHP to JavaScript. Specifically, Drupal's authoring and site building experience could benefit from user experience improvements. A JavaScript framework could make our content modeling, content listing, and configuration tools faster and more application-like by using instantaneous feedback rather than submitting form after form. Furthermore, using a decoupled administrative interface would allow us to dogfood our own web service APIs.
- **Let's start small by redesigning and rebuilding one or two features.** Instead of rewriting the entirety of Drupal's administrative user interfaces, let's pick one or two features, and rewrite their UIs using a preselected JavaScript framework. This allows us to learn more about the pros and cons, allows us to dogfood some of our own APIs, and if we ultimately need to switch to another JavaScript framework or approach, it won't be very painful to rewrite or roll the changes back.

### Selecting a JavaScript framework for Drupal's administrative UIs

In my keynote, I proposed a new strategic initiative to test and research how Drupal's administrative UX could be improved by using a JavaScript framework. The feedback was very positive.

As a first step, we have to choose which JavaScript framework will be used as part of the research. Following the keynote, we had several meetings at DrupalCon Vienna to discuss the proposed initiative with core committers, all of the JavaScript subsystem maintainers, as well as developers with real-world experience building decoupled applications using Drupal's APIs.

There was unanimous agreement that:

1. Adding a JavaScript framework to Drupal core is a good idea.
2. We want to have sufficient real-use experience to make a final decision prior to 8.6.0's development period (Q1 2018). To start, the Watchdog page would be the least intrusive interface to rebuild and would give us important insights before kicking off work on more complex interfaces.
3. While a few people named alternative options, React was our preferred option, by far, due to its high degree of adoption, component-based and unopinionated nature, and its potential to make Drupal developers' skills more future-proof.
4. This adoption should be carried out in a limited and incremental way so that the decision is easily reversible if better approaches come later on.

We created [an issue on the Drupal core queue](https://www.drupal.org/node/2913321) to discuss this more.

### Conclusion

[image blog/drupal-supporting-different-javascript-front-ends resize=false]

In short, I continue to believe that adopting more JavaScript is important for the future of Drupal. My original recommendation to include a modern JavaScript framework (or JavaScript libraries) for Drupal's administrative user interfaces still stands. I believe we should allow developers to use their JavaScript framework of choice to build front-end applications on top of Drupal and that we can start small with one or two administrative user interfaces.

After meeting with core maintainers, JavaScript subsystem maintainers, and framework managers at DrupalCon Vienna, I believe that React is the right direction to move for Drupal's administrative interfaces, but we encourage everyone in the community to [discuss our recommendation](https://www.drupal.org/node/2913321). Doing so would allow us to make Drupal easier to use for site builders and content creators in an incremental and reversible way, keep Drupal developers' skills relevant in an increasingly JavaScript-driven world, move us ahead with modern tools for building user interfaces.

*Special thanks to [Preston So](https://www.drupal.org/u/prestonso) for contributions to this blog post and to [Matt Grill](https://www.drupal.org/u/drpal), [Wim Leers](https://www.drupal.org/u/wim-leers), [Jason Enter](https://www.drupal.org/u/jenter), [Gábor Hojtsy](https://www.drupal.org/u/g%C3%A1bor-hojtsy), and [Alex Bronstein](https://www.drupal.org/u/effulgentsia) for their feedback during the writing process.*
