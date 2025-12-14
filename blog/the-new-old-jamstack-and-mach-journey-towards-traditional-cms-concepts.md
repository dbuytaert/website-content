---
title: "The new old: Jamstack and MACH's journey towards traditional CMS concepts"
date: '2023-12-27T10:20:29-05:00'
author: Dries
summary: 'How Jamstack, MACH, and traditional CMSes like Drupal are evolving by learning from one another. Also, debunking some myths in Jamstack and MACH marketing.'
image: drupal/jamstack-mach-traditional-cms
tags:
  - Drupal
  - 'Headless Drupal'
  - Trends
featured: true
published: true
type: blog
url: /the-new-old-jamstack-and-mach-journey-towards-traditional-cms-concepts
id: 5531
---

[image drupal/jamstack-mach-traditional-cms schema=false]

In recent years, new architectures like [MACH](https://machalliance.org/) and [Jamstack](https://jamstack.org/) have emerged in the world of Content Management Systems (CMS) and Digital Experience Platforms (DXP).

In some way, they have challenged traditional models. As a result, people sometimes ask for my take on MACH and Jamstack. I've mostly refrained from sharing my perspective to avoid controversy.

However, recognizing the value of diverse viewpoints, I've decided to share some of my thoughts. I hope it contributes positively to the ongoing evolution of these technologies.

### The Jamstack is embracing its inner CMS

[Jamstack](https://jamstack.org/), born in 2015, began as an approach for building static sites. The term <dfn>Jamstack</dfn> stands for <u>J</u>avaScript, <u>A</u>PIs and <u>M</u>arkup. Jamstack is an architectural approach that decouples the web experience layer from content and business logic. The web experience layer is often pre-rendered as static pages (markup), served via a Content Delivery Network (CDN).

By 2023, the [Jamstack community](https://jamstack.org/) underwent a considerable transformation. It evolved significantly from its roots, increasingly integrating traditional CMS features, such as "content previews". This shift is driven by the need to handle more complex websites and to make the Jamstack more user-friendly for marketers, moving beyond its developer-centric origins.

Netlify, a leader in the Jamstack community, has acknowledged this shift. As part of that, they are publicly moving away from the term "Jamstack" towards being a "[composable web platform](https://www.netlify.com/blog/introducing-the-netlify-composable-web-platform/)".

Many traditional CMSes, including [Drupal](https://www.drupal.org/), have long embraced the concept of "composability". For example, [Drupal has been recognized as a composable CMS](https://dri.es/the-assembled-web) for two decades and offers [advanced composable capabilities](https://dri.es/the-evolution-of-drupal-composability-from-the-command-line-to-the-browser).

This expansion reflects a natural progression in technology, where software tends to grow more complex and multifaceted over time, often referred to as the [law of increasing complexity](https://en.wikipedia.org/wiki/Lehman%27s_laws_of_software_evolution). What starts simple becomes more complex over time.

I believe the Jamstack will continue adding traditional CMS features such as menu management, translation workflows, and marketing technology integrations until they more closely resemble traditional CMSes.

### Wake-up call: CMSes are hybrid now

The Jamstack is starting to look more like traditional CMSes, not only in features, but also in architecture. Traditional CMSes can work in two main ways: "coupled" or "integrated", where they separate the presentation layer from the business logic using an approach called [Model-View-Controller](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller) (MVC), or "decoupled", where the front-end and back-end are split using web service APIs, like the Jamstack does.

Modern CMSes integrate well with various JavaScript frameworks, have GraphQL backends, can render static pages, and much more.

This combination of both methods is known as "hybrid". Most traditional CMSes have adopted this hybrid approach. For example, [Drupal has championed a headless approach for over a decade](https://dri.es/the-future-is-a-restful-drupal), predating both the terms "Jamstack" and "Headless".

Asserting that traditional CMSes are "monolithic" and "outdated" is a narrow-minded view held by people who have overlooked their evolution. In reality, today's choice is between a purely Headless or a Hybrid CMS.

### Redefining "Jamstack" beyond overstated claims

As the Jamstack becomes more versatile, the original "Jamstack" name and definition feel restrictive. The essence of Jamstack, once centered on creating faster, secure websites with a straightforward deployment process, is changing.

It's time to move beyond some of the original value proposition, not just because of its evolution, but also because many of the Jamstack's advantages have been overstated for years:

- The notion that Jamstack deployments are easy is debatable. In reality, it can be a frustrating task, both for developers and marketers, but especially for marketers.
- I'm also [critical of Jamstack's purported performance benefits](https://dri.es/why-content-management-systems-can-outperform-static-site-generators).

In short, Jamstack, initially known for its static site generation and simplicity, is growing into something more dynamic and complex. This is a positive evolution driven by the market's need. This evolution narrows the gap between Jamstack and traditional CMSes, though they still differ somewhat – Jamstack offers a pure headless approach, while traditional CMSes offer both headless and integrated options.

Last but not least, this shift is making Jamstack more similar to MACH, leading to my opinion on the latter.

### The key difference between MACH and traditional CMSes

Many readers, especially people in the Drupal community, might be unaware of [MACH](https://machalliance.org/). <dfn>MACH</dfn> is an acronym for <u>M</u>icroservices, <u>A</u>PI-first, <u>C</u>loud-native SaaS, <u>H</u>eadless. It specifies an architectural approach where each business function is a distinct cloud service, often created and maintained by separate vendors and integrated by the end user.

Imagine creating an online store with MACH certified solutions: you'd use different cloud services for each aspect – one for handling payments, another for your product catalog, and so on. A key architectural concept of MACH is that each of these services can be developed, deployed, and managed independently.

At first glance, that doesn't look too different from Drupal or WordPress. Platforms like WordPress and Drupal are already integration-rich, with Drupal surpassing 50,000 different modules in 2023. In fact, some of these modules integrate Drupal with MACH services. For example, when building an online store in Drupal or WordPress, you'd install modules that connect with a payment service, SaaS-based product catalog, and so on.

At a glance, this modular approach seems similar to MACH. Yet, there is a distinct contrast: Drupal and WordPress extend their capabilities by adding modules to a "core platform", while MACH is a collection of independent services, operating without relying on an underlying core platform.

### MACH could benefit from "monolithic" features

Many in the MACH community applaud the lack of a core platform, often criticizing it as "monolithic". Calling a CMS like Drupal "monolithic" is, in my opinion, a misleading and simplistic marketing strategy. From a technical perspective, Drupal's core platform is exceptionally modular, allowing all components to be swapped.

<p class="pullquote">Rather than (mis)labeling traditional CMSes as "monolithic", a more accurate way to explain the difference between MACH and traditional CMSes is to focus on the presence or absence of a "core platform".</p>

More importantly, what is often overlooked is the vital role a core platform plays in maintaining a consistent user experience, centralized account management, handling integration compatibility and upgrades, streamlining translation and content workflows across integrations, and more. The core platform essentially offers "shared services" aimed to help improve the end user and developer experience. Without a core platform, there can be increased development and maintenance costs, a fragmented user experience, and significant challenges in composability.

This aligns with a phenomenon that I call "MACH fatigue". Increasingly, organizations come to terms with the expenses of developing and maintaining a MACH-based system. Moreover, end-users often face a fragmented user experience. Instead of a seamlessly integrated interface, they often have to navigate multiple disconnected systems to complete their tasks.

To me, it seems that an ideal solution might be described as "loosely-coupled architectures with a highly integrated user experience". Such architectures allow the flexibility to mix and match the best systems (like your preferred CMS, CRM, and commerce platform). Meanwhile, a highly integrated user experience ensures that these combinations are seamless, not just for the end users but also for content creators and experience builders.

At present, traditional platforms like Drupal are closer to this ideal compared to MACH solutions. I anticipate that in the coming years, the MACH community will focus on improving the cost-effectiveness of MACH platforms. This will involve creating tools for managing dependencies and ensuring version compatibility, [similar to the practices embraced by Drupal with Composer](https://dri.es/the-evolution-of-drupal-composability-from-the-command-line-to-the-browser).

Efforts are already underway to streamline the MACH user experience with "Digital Experience Composition (DXC) tools". DXC acts as a layer over a MACH architecture, offering a user interface that breaks down various MACH elements into modular "Lego blocks". This allows both developers and marketers to [assemble these blocks into a digital experience](https://dri.es/the-assembled-web). Users familiar with traditional CMSes might find this a familiar concept, as many CMS platforms include DXC elements as integral features within their core platform.

Traditional CMSes like Drupal can also take cues from Jamstack and MACH, particularly in their approaches to web services. For instance, while Drupal effectively separates business logic from the presentation layer using the MVC pattern, it primarily relies on internal APIs. A shift towards more public web service APIs could enhance Drupal's flexibility and innovation potential.

### Conclusions

In recent years, we've witnessed a variety of technical approaches in the CMS/DXP landscape, with MACH, Jamstack, decoupled, and headless architectures each carving out their paths.

Initially, these paths appeared to diverge. However, we're now seeing a trend of convergence, where different systems are learning from each other and integrating their unique strengths.

The Jamstack is evolving beyond its original focus on static site generation into a more dynamic and complex approach, narrowing the gap with traditional CMSes.

Similarly, to bridge the divide with traditional CMSes, MACH may need to broaden its scope to encompass shared services commonly found in the core platform of traditional CMSes. That would help with developer cost, composability and user-friendliness.

In the end, the success of any platform is judged by how effectively it delivers a good user experience and cost efficiency, regardless of its architecture. The focus needs to move away from architectural considerations to how these technologies can create more intuitive, powerful platforms for end users.
