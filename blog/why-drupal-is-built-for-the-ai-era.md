---
title: 'Why Drupal is built for the AI era'
date: '2025-07-30T10:21:11-04:00'
author: Dries
summary: 'Drupal accidentally prepared for AI. The architectural decisions that made Drupal 8 painful to adopt now make it uniquely capable of deep AI integration.'
image: blog/drupal-ai-advantage
tags:
  - Drupal
  - 'Artificial Intelligence'
featured: false
published: true
type: blog
url: /why-drupal-is-built-for-the-ai-era
id: 5851
---

[image blog/drupal-ai-advantage lazy=false priority=true]

In my previous post, [The great digital agency unbundling](https://dri.es/ai-and-the-great-digital-agency-unbundling), I explored how AI is transforming the work of digital agencies. As AI automates more technical tasks, agencies will be shifting their focus toward orchestration, strategic thinking, and accountability. This shift also changes what they need from their tools.

Content management systems like [Drupal](https://new.drupal.org/home) must evolve with them. This is not just about adding AI features. It is about becoming a platform that strengthens the new agency model. Because as agencies take on new roles, they will adopt the tools that help them succeed.

As I wrote then:
> "As the Project Lead of Drupal, I think about how Drupal, the product, and its ecosystem of digital agencies can evolve _together_. They need to move in step to navigate change and help shape what comes next"

The good news is that the Drupal community is embracing AI in a coordinated and purposeful way. Today, Drupal CMS already ships with 22 AI agents, and through the [Drupal AI Initiative](https://dri.es/accelerating-ai-innovation-in-drupal), we are building additional infrastructure and tooling to bring more AI capabilities to Drupal.

In this post, I want to share why I believe Drupal is not just ready to evolve, but uniquely positioned to thrive in the AI era.

### Drupal is built for AI

Imagine an AI agent that plans, executes, and measures complex marketing campaigns across your CMS, CRM, email platform, and analytics tools without requiring manual handoff at every step.

To support that level of orchestration, a platform must expose its content models, configuration data, state, user roles and permissions, and business logic in a structured, machine-readable way. That means making things like entity types, field definitions, relationships, and workflows available through APIs that AI systems can discover, inspect, and act on safely.

Most platforms were not designed with this kind of structured access in mind. Drupal has been moving in that direction for more than a decade.

Since Drupal 7, the community has invested deeply in modernizing the platform. We introduced a unified Entity API, adopted a service container with dependency injection, and expanded support for REST, JSON:API, and GraphQL. We also built a robust configuration management system, improved testability, and added more powerful workflows with granular revisioning and strong rollback support.  Drupal also has excellent API documentation.

These changes made Drupal not only more programmable but also more introspectable. AI agents can query Drupal's structure, understand relationships between entities, and make informed decisions based on both content and configuration. This enables AI to take meaningful action inside the system rather than just operating at the surface. And because Drupal's APIs are open and well-documented, these capabilities are easier for developers and AI systems to discover and build on.

Making these architectural improvements was not easy. Upgrading from Drupal 7 was painful for many, and at the time, the benefits of Drupal 8's redesign were not obvious. We were not thinking about AI at the time, but in hindsight, we built exactly the kind of modern, flexible foundation that makes deep AI integration possible today. As is often the case, there is [pain before the payoff](https://dri.es/the-pain-before-the-payoff).

### AI makes Drupal's power more accessible

I think this is exciting because AI can help make Drupal's flexibility more accessible. Drupal is one of the most flexible content management systems available. It powers everything from small websites to large, complex digital platforms. That flexibility is a strength, but it also introduces complexity.

For newcomers, Drupal's flexibility can be overwhelming.  Building a Drupal site requires understanding how to select and configure contributed modules, creating content types and relationships, defining roles and permissions, building Views, developing a custom theme, and more.  The learning curve is steep and often prevents people from experiencing Drupal's power and flexibility.

AI has the potential to change that. In the future, you might describe your needs by saying something like, "I need a multi-language news site with editorial workflows and social media integration". An AI assistant could ask a few follow-up questions, then generate a working starting point.

I've demonstrated early prototypes of this vision in recent [DriesNotes](https://dri.es/tag/state-of-drupal), including [DrupalCon Barcelona 2024](https://dri.es/state-of-drupal-presentation-september-2024) and [DrupalCon Atlanta 2025](https://dri.es/state-of-drupal-presentation-march-2025). Much of that code has been productized in the [Drupal AI modules](https://www.drupal.org/project/ai).

In my Barcelona keynote, I said that "AI is the new UI". AI helps lower the barrier to entry by turning complex setup tasks into simple prompts and conversations. With the right design, it can guide new users while still giving experts full control.

In my last post, [The great digital agency unbundling](https://dri.es/ai-and-the-great-digital-agency-unbundling), I shared a similar perspective:
> "Some of the hardest challenges the Drupal community has faced, such as improving usability or maintaining documentation, may finally become more manageable. I see ways AI can support Drupal's mission, lower barriers to online publishing, make Drupal more accessible, and help build a stronger, more inclusive Open Web. The future is both exciting and uncertain."

Of course, AI comes with both promise and risk. It raises ethical questions and often fails to meet expectations. But ignoring AI is _not_ a strategy. AI is already changing how digital work gets done. If we want Drupal to stay relevant, we need to explore its potential. That means experimenting thoughtfully, sharing what we learn, and helping shape how these tools are built and used.

### Drupal's AI roadmap helps agencies

AI is changing how digital work gets done. Some platforms can now generate full websites, marketing campaigns, or content strategies in minutes. For simple use cases, that may be enough.

But many client needs are more complex. As requirements grow and automations become more sophisticated, agencies continue to play a critical role. They bring context, strategy, and accountability to challenges that off-the-shelf tools cannot solve.

That is the future we want Drupal to support. We are _not_ building AI to replace digital agencies, but to strengthen them. Through the [Drupal AI Initiative](https://dri.es/accelerating-ai-innovation-in-drupal), Drupal agencies are actively helping shape the tools they want to use in an AI-driven world.

As agencies evolve in response to AI, they will need tools that evolve with them. Drupal is not only keeping pace but helping lead the way. By investing in AI in collaboration with the agencies who rely on it, we are making Drupal stronger, more capable, and more relevant.

### Now is the moment to move

The shift toward AI-powered digital work is inevitable. Platforms will succeed or fail based on how well they adapt to this reality.

Drupal's investments in modern architecture, open development, and community collaboration has created something unique: a platform that doesn't just add AI features but fundamentally supports AI-driven workflows. While other systems scramble to retrofit AI capabilities, Drupal's foundation makes deep integration possible.

The question isn't whether AI will change digital agencies and content management. It already has. The question is which platforms will help agencies and developers thrive in that new reality. Drupal is positioning itself to be one of them.
