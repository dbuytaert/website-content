---
title: 'State of Drupal presentation (October 2025)'
date: '2025-10-23T03:20:34-04:00'
author: Dries
summary: 'In my DrupalCon Vienna keynote, I talk about how Drupal is adapting to an AI-driven web through AI-enabled visual editing, site templates, autonomous agents, and workflow orchestration.'
image: drupalcon-vienna-2025/driesnote
tags:
  - 'State of Drupal'
  - Drupal
  - 'Artificial Intelligence'
  - 'Drupal Starshot'
  - DrupalCon
  - 'Workflow orchestration'
  - Vienna
featured: true
published: true
type: blog
url: /state-of-drupal-presentation-october-2025
id: 5906
---

The web is changing fast. AI now writes content, builds web pages, and answers questions directly, often bypassing websites entirely. 

People often wonder what this means for Drupal, so at DrupalCon Vienna, I tackled this head-on. My message was simple: AI is the storm, but it's also the way through it. Instead of fighting AI, we're leaning into it.

My keynote focused on how Drupal is evolving across four product areas. We're making it easier to get started with Site Templates, enabling visual site building through Drupal Canvas, accelerating development with AI assistance, and exploring complex workflows with new orchestration tools.

If you missed the keynote, you can [watch the video below](https://youtu.be/lTBim0nMD5s), or [download my slides](https://dri.es/files/state-of-drupal-october-2025.pdf) (62 MB).

[video lTBim0nMD5s]

Vienna felt like a turning point. People could see the pieces coming together. Drupal is finding its footing in the AI era, leading in AI innovation, and ready to help shape what comes next for the web.

### Growing Drupal with Site Templates

One of the most important ways to grow Drupal is to make it easier and faster to build new sites. We began that work with *Recipes*, a way to quickly add common features to a site. Recipes help people go from idea to a website in hours instead of days.

At DrupalCon Vienna, I talked about the next step in that journey: our first *Site Template*. Site Templates build on Recipes and also include a complete design with layouts, visual style, and sample content. The result is that you can go from a new Drupal install to a fully working website in minutes. It will be the easiest way yet to get started with Drupal.

Next, we plan to introduce more Site Templates and launch a *Site Template Marketplace* where anyone can [discover, share, and build on templates](https://dri.es/exploring-a-marketplace-for-drupal-site-templates) for different use cases. 

### A new visual editing experience 

At DrupalCon Vienna, the energy around [Drupal Canvas](https://www.drupal.org/project/canvas) was infectious. Some even called it "CanvasCon". Drupal Canvas sessions were often standing room only, just like the Drupal AI sessions.

I first showed an early version of Drupal Canvas at [DrupalCon Barcelona in September 2024](https://dri.es/state-of-drupal-presentation-september-2024), when we launched [Drupal's Starshot initiative](https://dri.es/introducing-drupal-starshot-product-strategy). The progress we've made in just one year is remarkable. My keynote showed parts of Drupal Canvas in action, but for a deeper dive, I recommend watching [this breakout session](https://youtu.be/f47lMXlf4B8?si=R22rMcLTvuk31C3u&t=644).

Version 1.0 of Drupal Canvas is scheduled for November 2025. Starting in January 2026, it will become the default page builder in Drupal CMS 2.0. After more than 15 months of development and countless contributors working to make Drupal easier for everyone, it's hard to believe we're almost there. This marks the beginning of a new chapter for how people create with Drupal.

What excites me most is what this solves. For years, building pages in Drupal required technical expertise. Drupal Canvas gives end-users a visual page builder that is both more powerful and easy to use. Plus, it supports React, which means front-end developers can contribute using skills they already have.

### Drupal's accidental AI advantage

Every content management system faces defining moments. For Drupal, one came with the release of Drupal 8. We [rebuilt Drupal from the ground up](https://dri.es/why-the-big-architectural-changes-in-drupal-8), adopting modern design patterns and improving configuration management, versioning, workflows, and more.

The transition was hard, but here is the surprising part: ten years later those decisions gave Drupal [an unexpected advantage](https://dri.es/why-drupal-is-built-for-the-ai-era) in today's AI-driven web. The architecture we created is exactly what AI systems need today. When AI modifies content, you need version control to roll back mistakes. When it builds pages, you need structured data, permissions, and workflows. Drupal already has those capabilities.

For years, Drupal prioritized flexibility and robustness while other platforms focused on ease of use. What once felt like extra complexity now makes perfect sense. Drupal has quietly become one of the most AI-ready platforms available. 

### AI is the storm, and the way through the storm

[image drupalcon-vienna-2025/ai-is-the-storm]

As I said in my keynote: "Some days AI terrifies me. An hour later it excites me. By the evening, I'm tired of hearing about it.". Still, we can't ignore AI.

I first introduced AI as part of Starshot. Five months ago, it became its own dedicated track with [the launch of the Drupal AI initiative](https://dri.es.ddev.site/accelerating-ai-innovation-in-drupal). Since then, twenty two agencies have backed it with funding and contributors, together [contributing over one million dollars](https://www.drupal.org/about/starshot/initiatives/ai/blog/1-million-dollars-raised-to-accelerate-innovation-in-drupal-ai). This is the largest fundraising effort in Drupal's history. 

The initiative is already producing impressive results. At DrupalCon Vienna, we [released Drupal AI version 1.2](https://www.drupal.org/about/starshot/initiatives/ai/blog/drupal-ai-and-ai-agents-120-stable-release-is-out), a major step forward for the initiative.

In my keynote, I also demonstrated three new AI capabilities:

1. **AI-powered page building:** Drupal AI can now generate complete, designed pages in minutes using a component-based design system in Drupal Canvas. What site builders used to build in hours now happens in minutes while maintaining your site's structure and style.
2. **Context Control Center:** Teams can define brand voice, target audiences, and key messages from a single UI. All AI agents draw from this source of truth.
3. **Autonomous agents:** When you update information in the Context Control Center, such as a product price or company statistic, agents automatically find every instance throughout your site and propose updates. You review and approve changes before they go live.

### Orchestration as a path to explore

Earlier this year, I wrote about [the great digital agency unbundling](https://dri.es/ai-and-the-great-digital-agency-unbundling). As AI automates more technical work, agencies need to evolve their business models and find new ways to create value.

One promising direction is orchestration: building systems and workflows that connect AI agents, content platforms, CRMs, and marketing tools into intelligent, automated workflows. I think of it as DXP 2.0.

Most organizations have complex marketing technology stacks. Connecting all the systems in their stack often requires custom code or repetitive manual tasks. This integration work can be time-consuming and hard to maintain.

Modern orchestration tools solve this by automating how information flows between systems. Instead of writing custom code, you can use no-code tools to define workflows that trigger automatically. When someone fills out a form, the system creates a CRM contact, sends a welcome email, and notifies your team without any manual work.

In my keynote, I showed how [ECA](https://www.drupal.org/project/eca) and [ActivePieces](https://www.activepieces.com/) can work together. [Jürgen Haas](https://www.drupal.org/u/jurgenhaas), who created ECA, and I collaborated on this integration.  ECA lets you define automations inside Drupal using events, conditions, and actions. ActivePieces is an open source automation platform similar to [Zapier](https://zapier.com/) or [n8n](https://n8n.io/).

This approach allows us to build user experiences that are not only better and smarter, but also positions Drupal to benefit from AI innovation happening across the broader ecosystem. The idea resonated in Vienna. People approached me enthusiastically with related projects and demos, including tools like [Flowdrop](https://www.drupal.org/project/flowdrop) or [Drupal's MCP module](https://www.drupal.org/project/mcp). 

Between now and DrupalCon Chicago, we're inviting the community to explore and expand on this work. Join us in `#orchestration` on [Drupal Slack](https://www.drupal.org/join-slack), test the new [Orchestration module](https://www.drupal.org/project/orchestration), connect more automation platforms, or help improve ECA. If this direction proves valuable, we'll share what we learned at DrupalCon Chicago.

### Building the future together

At DrupalCon Vienna, I felt something shift. Sessions were packed. People were excited about Site Templates and the Marketplace. Drupal Canvas drew huge crowds, and even more agencies signed up to join the Drupal AI initiative. During the contribution day, more people than usual showed up looking for ways to help.

AI is changing how people use the web and how we build for it. It can feel threatening, and it can feel full of possibility, but what became clear in Vienna is that Drupal is well positioned at this inflection point, with both momentum and direction.

What makes this moment special is how the community is responding with focus and collaboration. We are approaching it as a much more coordinated effort, while still leaving room for experimentation.

Vienna showed me that the Drupal community is ready to take this on together. We have navigated uncharted territory before, but this time there is a boldness and unity I have not seen in years. That is the way through the storm. I am proud to be part of it.

*I want to extend my gratitude to everyone who contributed to making my presentation and demos a success. A special thank you to [Adam G-H](https://www.drupal.org/u/phenaproxima), [Aidan Foster](https://www.drupal.org/u/afoster), [ASH Sullivan](https://www.drupal.org/u/burnashburn), [Bálint Kléri](https://www.drupal.org/u/balintbrews), [Cristina Chumillas](https://www.drupal.org/u/ckrina), [Elliott Mower](https://www.drupal.org/u/elliottmower), [Emma Horrell](https://www.drupal.org/u/emma-horrell), [Gábor Hojtsy](https://www.drupal.org/u/gábor-hojtsy), [Gurwinder Antal](https://www.drupal.org/u/gantal), [James Abrahams](https://www.drupal.org/u/yautja_cetanu), [Jurgen Haas](https://www.drupal.org/u/jurgenhaas), [Kristen Pol](https://www.drupal.org/u/kristen-pol), [Lauri Timmanee](https://www.drupal.org/u/lauriii), [Marcus Johansson](https://www.drupal.org/u/marcus_johansson), [Martin Anderson-Clutz](https://www.drupal.org/u/mandclu), [Pamela Barone](https://www.drupal.org/u/pameeela), [Tiffany Farriss](https://www.drupal.org/u/farriss), [Tim Lehnen](https://www.drupal.org/u/hestenet), and [Witze Van der Straeten](https://www.drupal.org/u/witzevds). Many others contributed indirectly to make this possible. If I've inadvertently omitted anyone, please reach out.*
