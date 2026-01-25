---
url: 'https://dri.es/a-composable-digital-experience-manifesto'
title: 'A Composable Digital Experience Manifesto'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2022-10-06T09:14:45-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: "An update on the evolution of Acquia's product strategy through the lens of a Composable Digital Experience Platform (DXP)."
tags:
  - Drupal
  - Acquia
  - Trends
image: acquia/composable-dxp-principle-6
published: true
featured: true
id: 5366
---

# A Composable Digital Experience Manifesto

It's been a while since I wrote about my views on the Content Management System (CMS) and Digital Experience Platform (DXP) markets.

It's also been a while since I gave an update on [Acquia](https://www.acquia.com/)'s product vision and strategy, like I did in [2009](https://dri.es/acquia-2009-roadmap), [2011](https://dri.es/acquia-product-strategy-and-vision) or [2017](https://dri.es/the-evolution-of-acquia-product-strategy).

In this post, I want to give you an update on both. I will share my views on the Digital Experience Platform market and talk more about Acquia's vision and strategy.

Throughout the article, I will also give practical examples of how [Drupal](https://www.drupal.org/) (the Open Source project I started) and [Acquia](https://www.acquia.com/) (the company I started) fit into a 'Composable Enterprise'.

### The Composable Enterprise

The Composable Enterprise has been one of the most important trends in the software industry. Analyst firm [Gartner](https://www.gartner.com/en/doc/465932-future-of-applications-delivering-the-composable-enterprise) popularized the term, and defines the Composable Enterprise as follows:

> A <dfn>Composable Enterprise</dfn> is an organization that can innovate and adapt to changing business needs through the assembly and combination of packaged business capabilities. To enable the Composable Enterprise, organizations will need to adapt the way they source and deliver applications as vendors deliver more modular capabilities.

The main idea behind the Composable Enterprise is that when organizations compose or assemble solutions from existing building blocks, they are able to move faster. It also provides them the flexibility to adjust to changing business needs.

Per Gartner's thought-leadership, architectural modularity is key to composability. But composability is also much more than modularity. Composability defines an end-to-end approach, and not only a software architecture. Composability is a philosophy of business agility, architecture and governance.

### A Composable Digital Experience Platform

In this article, I will apply the ideas of the Composable Enterprise to the DXP market.

Specifically, I will expand upon six core tenets that I believe are key to Composable DXPs:

1. [Principle 1: Software architecture needs to be modular](#principle-1)
2. [Principle 2: Components need to be discoverable and orchestrated](#principle-2)
3. [Principle 3: All business stakeholders need to be empowered with low-code / no-code](#principle-3)
4. [Principle 4: Data makes the difference, but it needs to be unified and automated](#principle-4)
5. [Principle 5: Multi-experience content demands strong content management](#principle-5)
6. [Principle 6: A platform approach requires diverse experience composition and delivery methods](#principle-6)

### MACH and Jamstack

Before jumping into the six key principles, I wanted to acknowledge that composability in the DXP market has given rise to trends like [MACH](https://machalliance.org/) and [Jamstack](https://jamstack.org/).

- <dfn>MACH</dfn> stands for <u>M</u>icroservices, <u>A</u>PI-first, <u>C</u>loud-native SaaS, <u>H</u>eadless. In a MACH architecture, each piece of business functionally is a cloud service. The cloud services are built and managed by independent vendors and integrated by the customer. The typical MACH service is a backend service with either no frontend (headless service) or a decoupled frontend. As a result, MACH services offer web service APIs for integration and frontend development.
- <dfn>Jamstack</dfn> stands for <u>J</u>avaScript, <u>A</u>PIs and <u>M</u>arkup. Jamstack is an architectural approach that decouples the web experience layer from data and business logic. The web experience layer is often pre-rendered as static pages (markup), served via a CDN.

In short, MACH and Jamstack primarily describe architectural approaches. MACH is mostly about the backend architecture of web applications, and Jamstack is mostly about the frontend architecture of web applications.

Both MACH and Jamstack represent developer-centric approaches to the challenge of composability. Neither are prescriptive about the capabilities of a DXP. Both MACH and Jamstack can be part of a Composable DXP.

### <a id="principle-1">Principle 1: Software architecture needs to be modular</a>

[image acquia/composable-dxp-principle-1]

At the core of a Composable DXP are modular software design principles. Organizations should reject software monoliths and focus on software that is modular.

Software monoliths are inflexible. Monoliths prevent teams from moving fast, hinder innovation and make it harder to deliver digital products and services.

Modular software is decomposed into smaller pieces with standardized interfaces. Modular software allows solutions to be created by combining reusable chunks of code.

This idea is not new – modular software has been around since the 1960s – but a lot of software still doesn't live up to these basic design principles.

<section class="note">
  <h4>Drupal proof points</h4>
  <p>Open Source software is almost always better than proprietary software with regards to APIs and modularity.</p>
  <p>For over 10 years, Drupal has been pushing the concept of the <a href="https://dri.es/the-assembled-web">Assembled Web</a>.</p>
  <p>Today, Drupal's open and modular architecture allows over 10,000 active contributors to build and maintain 46,000 modules for the more than 1 million websites running Drupal.</p>
  <p>Integrations include third-party commerce platforms, digital asset management platforms, analytics platforms, CRM systems, marketing automation software, frontend frameworks, and many more.</p>
</section>

### <a id="principle-2">Principle 2: Components need to be discoverable and orchestrated</a>

[image acquia/composable-dxp-principle-2]

A <dfn>**Composable Architecture**</dfn> is an architecture in which the individual components of the stack can be replaced without affecting other parts of the system.

The idea is to enable organizations to select and assemble a customized solution that best fits their needs.

Combining components from different providers gives organizations a lot of flexibility, but it also comes with added cost and complexity:

- **Components can be hard to discover**; e.g. what are all the available components for my DXP, what do they do and how do I use them?
- **Components can be hard to orchestrate**; e.g. some components might not work together, components might have dependencies, etc.

A software stack that consists of many components can be hard to build and maintain. In fact, Composable Architectures shift much of the discovery, orchestration, integration and testing burden from vendors to the end user.

Composability necessitates an approach that simplifies the discovery, installation, assembly, and maintenance of components. A good Composable DXP offers the following solutions to manage diverse components:

- **Packaged Business Capabilities (PBCs)** combine components and their configuration into higher-level building blocks. This is helpful to make solution delivery more repeatable.
- A **Marketplace** where both components and PBCs can be searched for and discovered.
- A **Component Manager** to provide a unified mechanism to install and update components from different providers. The Component Manager resolves component dependencies (*i.e. component A requires component B to be installed as well*) and manages component compatibility (*i.e. component A only works with v2 of component B but not yet with v3*). A Component Manager also knows when there is a new version of a component (e.g. component B has a security release and needs to be updated) and orchestrates its update (*e.g. updating component B for security reasons, requires updating component C as well*).
- A **Component Catalog** is a registry or database of components and the metadata required to manage components. This includes the component's location, version information, dependency chain, compatibility restrictions, release details, etc. Marketplaces and Component Managers operate on top of one or more Component Catalogs.
- A **CI/CD Pipeline** for continuous integration, management and updating of components. New versions of components are released every day by independent providers. Automated integration and automated testing is required to deliver composable software reliably and quickly.

<section class="note">
  <h4>Drupal and Acquia proof points</h4>

Drupal has 46,000 components, called *modules*. Drupal also offers more than 1,000 PBCs, which Drupal calls *distributions* and *recipes*. Distributions and recipes not only combine modules, but also ship with data schemas, configuration, content and data to make everything work well together. Example distributions include:

- [Open Social](https://www.getopensocial.com/) for knowledge sharing and community websites
- [Commerce Kickstart](https://www.drupal.org/project/commerce_kickstart) for commerce solutions
- [Thunder](https://www.thunder.org/) for building magazine websites
- [Opigno LMS](https://www.opigno.org/) for learning management solutions
- ... and hundreds more.

Modules (components) and distributions (PBCs) can be searched, browsed and filtered in at least three ways:

- [Drupal.org's module repository](https://www.drupal.org/project/project_module), a component marketplace.
- [Drupal.org's distribution repository](https://www.drupal.org/project/project_distribution), a PBC marketplace.
- Drupal has a [Project Browser](https://www.drupal.org/about/core/strategic-initiatives/project-browser) ([demo video](https://youtu.be/RnSgNo_tYxI)) that enables developers and business users to discover and install modules from within Drupal's administrative UI.

Since the release of Drupal 8 in 2015, Drupal sites are managed with [Composer](https://getcomposer.org/) (a Component Manager) and [Packagist](https://packagist.org/) (a Component Catalog). Composer downloads and installs modules, along with any third-party dependencies. Composer also takes care of updates, version management, compatibility management and dependency management.

Last but not least, [Acquia Code Studio offers a CI/CD pipeline](https://dri.es/my-drupal-deployment-workflow). It continuously checks for new releases of components. When there is an update, it will install the new version and test it in a staging environment. The automated tests include integration testing, security testing, unit testing, performance testing and more.

</section>

### <a id="principle-3">Principle 3: All business stakeholders need to be empowered with low-code / no-code</a>

[image acquia/composable-dxp-principle-3]

To deliver the best customer experiences, all departments (engineering, marketing, sales, customer success and HR) must participate in the creation of these experiences.

Being modular and component-driven is great for developers, but it doesn't necessarily enable other business stakeholders to take part in the experience creation.

This is where **low-code and no-code solutions** come in. Low-code and no-code technologies use a graphical user interface (GUI) to speed up experience building. They empower every business stakeholder to create customer experiences without the help of software developers.

A Composable DXP with low-code / no-code helps organizations in at least three ways:

1. When separate business functions own their technology, rather than relying on inside or outside engineering teams, they can move faster.
2. Low-code / no-code solutions free up internal development teams to focus on unique, differentiated innovation. The low-code / no-code value proposition isn't exclusive to business users; it also speeds up development teams.
3. Low-code / no-code solutions reduce an organization's reliance on software engineering capacity and skills that can be harder to find.

In short, low-code / no-code solutions **enable cross-functional teams** to deliver great customer experiences faster.

<section class="note">
  <h4>Drupal and Acquia proof points</h4>

For low-code / no-code to be effective across all of an experience's creation, it needs to be available throughout the Composable DXP; from the content layer, to the data layer, to the orchestration layer.

  <h5>Content layer</h5>

- Drupal's UI enables developers and non-developers to compose or assemble websites without having to write code. Over the past 20+ years, Drupal has helped democratize website design using its low-code / no-code approach.
- Acquia Site Studio makes Drupal even more accessible to business users and cross-functional teams. For example, Acquia Site Studio enables organizations to set up a **composable design system**. Organizations can design visual components (e.g. header, footer, gallery, buttons, etc.) using no-code tools, organize them in a catalog, and use them across multiple websites.

<h5>Data layer</h5>

- Acquia's Customer Data Platform (CDP) provides 300 out-of-the-box connectors along with low-code tooling to quickly create custom integrations. Using a drag-and-drop UI, organizations can build simple to sophisticated data integrations. Despite being low-code, these integrations can handle complex data transformations, data deduplication, conditional triggers, and much more.

  <h5>Orchestration layer</h5>

- Acquia Campaign Studio allows organizations to create customer journeys. Engaging workflows, beautiful emails and landing pages can be built in minutes with an easy-to-use, drag-and-drop interface.

</section>

### <a id="principle-4">Principle 4: Data makes the difference, but it needs to be unified and automated</a>

[image acquia/composable-dxp-principle-4]

Organizations are increasingly using data to create superior, personalized customer experiences. The goal is simple: improve customer satisfaction, loyalty and advocacy via tailored experiences.

Tomorrow's applications will consume data from multiple sources to develop a fine-grained user profile for each user. In turn, these user profiles are used for **personalization**.

The first problem is that customer data is everywhere: in CRM systems, accounting systems, websites, marketing tools, commerce systems, point of sale systems, analytics platforms, customer support software, mobile applications, chatbots, call center software, and more.

Despite the clear need to tap all data sources, data is locked up in different databases and in disparate formats. Data silos are one of the biggest barriers to delivering personalized experiences.

To use data to its fullest potential, **data needs to be unified**. It needs to break free from these silos.

The second problem is scalability. Humans can't manually compose an experience for every single single customer and every single customer interaction.

When you have millions of user profiles and millions of interactions, **automation is key**. Organizations must rely on machine learning algorithms to tailor experiences to people's preferences.

Last but not least, it goes without saying that organizations also need and want to respect their customers' data privacy, and remain in compliance with regulations like GDPR and other local data privacy laws. This adds a third layer of complexity to managing and using user data.

<section class="note">
  <h4>Drupal and Acquia proof points</h4>

Acquia's Customer Data Platform (CDP) helps companies manage both consumer privacy and deliver personalized experiences at scale.

First, by integrating different data sources, Acquia CDP provides all teams with direct access to unified customer data. Data is integrated, cleaned up, and de-duped.

Second, Acquia's machine learning platform helps teams use that data to deliver personalized experiences or drive targeted campaigns. Acquia delivers over 1 trillion machine learning recommendations a year, or 3 billion personalization recommendations a day.

With Acquia CDP, users can easily leverage pre-built families of predictions, personas or next-best experience models such as 'Likelihood to pay full price', 'Product affinity segments' or 'Next-best channel' models. Users can also implement, manage and publish their own custom ML models.

</section>

### <a id="principle-5">Principle 5: Multi-experience content demands strong content management</a>

[image acquia/composable-dxp-principle-5]

<dfn>Multi-experience</dfn> refers to a user's end-to-end experience with one organization across a variety of digital touchpoints – websites, mobile applications, chatbots, voice assistants, wearables, augmented reality, metaverses, and more.

Great content is at the core of any great (multi-)experience. Quality content helps organizations stand out from the competition. This raises expectations for organizations to create content that customers care about, and to deliver that content on the channels they prefer to use. Composable content is key.

A Composable DXP should provide a **Content Platform** designed to address the challenges of managing content across all channels. These challenges include:

- Streamlining content management and content operations by eliminating content silos.
- Leveraging content models and headless delivery capabilities to provide content across channels and customer touchpoints.
- Improving content governance and brand consistency across all customer touchpoints.

To address these challenges, a Content Platform needs the following core capabilities:

- **Content modeling** – Breaks content up into common elements so they can be shared and remixed for different channels. It also enables content to be assembled and reassembled quickly, based on data-driven insights into each customer's particular interests. This includes models for articles, blogs, pages, etc., along with atomized digital assets and product information.
- **Content operations** – Organizes all people and processes responsible for strategizing, creating, distributing and analyzing content.
- **Content delivery** – Delivers content to different channels. A Content Platform acts as a content repository that makes content available to different channels using web services (headless) and/or a traditional presentation layer (coupled).
- **Content governance** – Ensures that content is consistent across all engagement channels. Engagement channels can't be disjointed or siloed.
- **Content personalization** – Personalizes content in real time. Personalization can be based on anonymous behavioral actions and/or explicit preferences in the customer profile.
- **Journey orchestration** – Seamlessly coordinates customer journeys from inbound to outbound touchpoints, and from native to federated channels. Journey orchestration acts on real-time events, inferred insights, decisioning through machine learning and business rules to deliver next-best actions in-moment for every individual at scale.

Composable content does not necessarily mean headless CMSes are de facto the best Content Platform. Headless solutions have pros and cons relative to alternative approaches:

- A <dfn>**Traditional CMS**</dfn> provides both a content repository and no-code tools to build experiences with. Traditional CMSes empower marketers and developers to build web experiences using a UI. Because traditional CMSes do not have strong web service APIs, they have limited ability to push content to multiple channels.
- A <dfn>**Headless CMS**</dfn> is primarily a content repository, and generally lacks no-code tools for building digital experiences. Headless CMSes excel at pushing content to multiple channels. They are frontend agnostic and require developers to build custom frontends. A headless CMS often leaves marketers at a disadvantage, but is more flexible for developers.
- A <dfn>**Hybrid CMS**</dfn> offers headless capabilities, but also comes with an optional out-of-the-box frontend. It provides developers with the web service APIs required to deliver content across channels, while at the same time ensuring marketers have no-code tools to build digital experiences.

<p class="pullquote">Nearly all Traditional CMSes have evolved to be Hybrid CMSes. It's no longer relevant to talk about Traditional CMSes. Today, the choice is really between Headless and Hybrid.</p>

<section class="note">
  <h4>Drupal and Acquia proof points</h4>

- Drupal is decidedly a *Hybrid CMS*. Drupal evolved [from a Traditional CMS to a Hybrid CMS](https://dri.es/the-future-is-a-restful-drupal) in 2012, more than 10 years ago, well before the term 'headless' became popular. Today, you can use Drupal as a Traditional CMS, a Headless CMS or a combination of both. Drupal is [API-first, but not API-only](https://dri.es/drupal-is-api-first-not-api-only).

  When Drupal is used in *headless mode*, organizations can use their preferred JavaScript framework to build a frontend. This includes React, Next.js, Vue, Svelte, Angular and more.

  - Example 1: Drupal integrates with [Gatsby](https://www.gatsbyjs.com/). Gatsby enables developers to build static websites using React. The content for the React website is provided by Drupal.
  - Example 2: Drupal has excellent [Next.js integration](https://next-drupal.org/) that includes support for JSON:API, GraphQL, authentication, seamless editing, live previews, form building, search, internationalization, and much more.

  To streamline the building of headless applications with Drupal, Acquia provides headless SDKs, Node.js hosting, and more.

- Acquia DAM offers deep governance across distributed marketing teams for properly managing digital assets and storing rich product information. It provides brand automation that ensures brand consistency across different channels.

</section>

### <a id="principle-6">Principle 6: A platform approach requires diverse experience composition and delivery methods</a>

[image acquia/composable-dxp-principle-6]

If you're like most organizations, the number of digital experience applications you have continues to grow, not shrink.

Different sites also have different scale, functionality, complexity and longevity. Some experiences are continuously developed, while others are only around for a few months. Some are built by IT, others by marketing. Some sites get a thousand visitors a month, others get 100 million visitors a month.

When managing a portfolio of digital experiences, a one-size-fits-all approach simply doesn't work. Organizations need to balance development approaches and operational costs.

For one website, an organization might want to use a marketer-friendly page builder and static site hosting. For another website, the same organization might require a headless CMS and PaaS delivery platform.

Furthermore, CIOs and CMOs often face cost-cutting and acceleration pressures at the same time. They are constantly having to figure out how to do more with less.

So how do you manage a diverse portfolio of digital experience applications, maximize velocity, minimize cost and meet growing security demands – all without sacrificing quality?

This is done by standardizing on a platform or ecosystem that scales from small to large, from simple to complex, and from IT to marketing. Specifically, this type of platform lets you choose between different experience composition and delivery options:

- **Experience composition options** – A platform that offers both APIs and no-code tooling; from web service APIs, to templates, to page builders, to different frontend JavaScript frameworks.
- **Experience delivery options** – A platform that can deploy static sites or dynamic sites on either SaaS or PaaS.

These different composition and delivery models also need to be underpinned by a standard set of **shared services**:

- Services that enable the sharing of content.
- Services that enable the sharing of data.
- Services that streamline cloud-native delivery.
- Services that encourage consistent operational workflows, including release management, deployment, security and compliance best-practices.
- Services to manage a global catalog of components, PBC, and design systems.
- Services to manage a global portfolio of sites and digital experiences.

In short, managing a portfolio of digital experiences requires a standard technology footprint, build around certain core services, but with the option to vary approaches to experience building and experience delivery.

<section class="note">
  <h4>Drupal and Acquia proof points</h4>

More and more, we see organizations standardize on Drupal. Why? Because Drupal is one of the few solutions that can scale from very small to extremely large.

Drupal also has the depth and breadth of functionality to support thousands of different use cases; including blogs, marketing sites, employee experience sites, corporate intranets, commerce sites and extremely high-traffic event websites.

Because Drupal is a hybrid CMS, you can use no-code tools to build experiences, or JavaScript frameworks to build experiences.

For websites that require custom code, Acquia Cloud is the leading Drupal Platform-as-a-Service (Drupal PaaS). It offers high security, high-availability, on-demand elasticity, staging environments and many developer tools.

For templated sites, Acquia Site Factory allows you to assemble tens, hundreds or thousands of unique digital experiences.

Regardless of the delivery model used, services like Acquia Content Hub and Acquia CDP help you share content and data across your portfolio of sites. In addition, Acquia provides global visibility over all your Drupal applications and experiences.

</section>

### Conclusion

After decades of contending with rigid, inflexible systems, enterprises crave the agility and speed that comes with composability.

This is particularly important in today's economy, where organizations gain competitive advantages based on having a tailored digital customer experience.

I predict that the majority of enterprises will have migrated to a composable model within the next 10 years.
