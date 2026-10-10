---
url: 'https://dri.es/state-of-drupal-presentation-september-2026'
title: 'State of Drupal presentation (September 2026)'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2026-10-07T03:50:03-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'DrupalCon Rotterdam 2026 DriesNote presentation.'
tags:
  - Drupal
  - 'State of Drupal'
  - DrupalCon
  - 'Drupal Canvas'
  - 'Artificial Intelligence'
image: drupalcon-rotterdam-2026/driesnote
discussions:
  - { platform: LinkedIn, url: 'https://www.linkedin.com/feed/update/urn:li:activity:7513516254889058304/' }
published: true
featured: false
id: 6336
---

# State of Drupal presentation (September 2026)

![Opening slide of my keynote, reading "Driesnote, DrupalCon Rotterdam".](http://default/files/cache/drupalcon-rotterdam-2026/driesnote-640w.png)

Drupal is now light-years ahead of its reputation. Closing that gap is our #1 challenge, and it was the main message of my DrupalCon Rotterdam keynote.

Just over two years ago, I launched [Drupal Starshot](https://dri.es/introducing-drupal-starshot-product-strategy). I did it because I wasn't sure we could still innovate like we used to. It turns out we can.

Starshot became [Drupal CMS](https://dri.es/drupal-cms-1-released), which brings together Site Templates, Recipes, Drupal AI, Drupal Canvas and more to make building websites easier. 

Alongside that work, Drupal Core has become a faster and better framework for developers. A stronger Drupal Core helps us build a better Drupal CMS, while building Drupal CMS has driven further improvements in Drupal Core.

Unfortunately, many people outside the Drupal community haven't seen what Drupal can do today. In Rotterdam, I showed how far we have come and where we're going next, and we launched an advocacy program to help more people see how great Drupal has become.

If you missed the keynote, you can [watch the video below](https://youtu.be/jrXnvVD8ryo) or [download my slides](https://dri.es/files/state-of-drupal-september-2026.pdf) (86 MB).

https://www.youtube.com/watch?v=jrXnvVD8ryo

## More ways to reach more people

The first part of my keynote showed improvements for multilingual sites, JavaScript front-ends, headless Canvas, and Drupal AI.

Drupal has long had strong multilingual capabilities, but [Drupal Canvas](https://www.drupal.org/project/canvas), our powerful new page builder, didn't yet support multilingual sites. Not only did we add multilingual support to Canvas, but we made all multilingual sites easier to set up.

https://www.youtube.com/watch?v=xoPDb4UhHyg 

React has one of the world's largest developer communities. Drupal Canvas code components are written in React, and we designed the developer experience around the tools, patterns, and workflows front-end JavaScript developers already know. They can use their preferred development tools, including modern AI-assisted workflows, without having to learn Drupal-specific concepts or conventions. We've continued to make that experience better, lowering the barrier for a much larger community of developers to build with Drupal.

https://www.youtube.com/watch?v=zim-Wr-HJNk

At DrupalCon, we extended that same model with [Drupal Canvas Headless](https://project.pages.drupalcode.org/canvas/headless/). Developers can now use Drupal to manage content while building the front-end separately with frameworks like Next.js, Astro, TanStack, Angular, or Nuxt. Editors still get the visual experience of Drupal Canvas: they can build pages in Drupal and preview exactly how those pages will appear on the front-end.

This changes an important trade-off. Teams no longer have to choose between a modern JavaScript front-end and Drupal Canvas' visual authoring experience. They can have both. That opens Drupal to more developers, more front-end architectures, and more types of projects.

https://www.youtube.com/watch?v=IPaNNc0MBnE

Drupal AI is moving so fast that I could have filled a whole keynote with it. Instead, we launched a [new Drupal AI demo](https://drupal.org/ai/demo) where people can experience Drupal AI for themselves. It comes preconfigured, making it easy to explore what Drupal AI can do or even show it to customers.

With the latest Drupal AI, you can ask questions and get answers grounded in your site's content. You can audit your content against brand guidelines, translate content, classify content,  build pages and React components with AI, and more. Through MCP, AI assistants can work with Drupal content from outside Drupal.

What excites me most is the foundation underneath all of this. Drupal AI turns Drupal into an AI harness: organizations can connect AI models to structured content, tools, and workflows, while keeping control through permissions, guardrails, observability, metering, and a choice of AI models.

https://www.youtube.com/watch?v=Ka1cLG5nvkw

## Opening Drupal's capabilities to other software

The second part of my keynote looked at another important shift: AI assistants can give people a new way to work with Drupal.

In one demo, an editor simply asked an AI assistant to unpublish a page. They didn't need to know where to click or understand Drupal's revisions, moderation workflows, or permissions. The assistant translated their intent into action, but Drupal remained in control: it checked whether the editor was allowed to unpublish the page and applied the site's publishing rules, just as it would if they had done it by hand.

If you want to see the demo in more detail, Scott Falconer, who worked on it, recorded a [behind-the-scenes walkthrough](https://www.youtube.com/watch?v=Gpq0ZnMg4mg) showing how to set it up yourself, what happens under the hood, and how to get involved.

That demo was built on the [Tool module](https://www.drupal.org/project/tool), which I believe is one of the most important modules for Drupal developers to watch. Drupal modules already contain thousands of useful capabilities: publishing content, managing users, processing media, changing configuration, and much more. The Tool module gives developers a standard way to expose those capabilities so AI assistants and other software can discover and use them.

Today, exposing existing capabilities as tools can still require too much code. My own album module didn't expose tools, and making its existing capabilities available to an AI assistant took about 1,000 additional lines of code.

But once those tools were available, the value became obvious. Adding MCP support has already changed how I manage the more than 10,000 photos on my site. Tasks that used to take a lot of time can now be done much faster and more accurately with an AI assistant, while Drupal still manages the content, permissions, and workflows underneath.

That experience reinforced something I wrote about in [AI and the great CMS unbundling](https://dri.es/ai-and-the-great-cms-unbundling): AI can take on more of the execution work while Drupal remains the control layer. I expect more organizations will want to manage parts of their sites through AI assistants. AI can make complex tasks much faster and easier without giving up the structure, governance, and safeguards that Drupal provides.

I believe thousands of module developers will eventually want to expose their capabilities in the same way, so I've been working with Matt Glaman to make it much easier. Matt has been developing [a change to the Tool API](https://git.drupalcode.org/project/tool/-/work_items/3518120) that lets developers expose existing PHP methods as tools using attributes.

The idea is simple: add PHP attributes to an existing method to describe its name, purpose, inputs and outputs. In my album module, roughly 1,000 lines of integration code became about 20 attributes. My site already uses the experimental branch, and we're working to get it merged into the [Tool module](https://www.drupal.org/project/tool) proper.

And this isn't only about AI. The same tools can be called by AI assistants over MCP, by other applications over HTTP, or used to generate schemas for JavaScript components and connect Drupal modules to workflow systems like [ECA](https://www.drupal.org/project/eca), [FlowDrop](https://www.drupal.org/project/flowdrop), and [Maestro](https://www.drupal.org/project/maestro). The video below shows FlowDrop using capabilities exposed by my album module:

https://www.youtube.com/watch?v=7CnZd63-JWg

## Talk louder about Drupal

In the last part of my keynote, I came back to Drupal's reputation gap. We can make enormous progress with Drupal, but that doesn't automatically change what people or AI agents think of it. For example, an [AI coding agent I tested in June](https://dri.es/do-ai-coding-agents-recommend-drupal-2026) didn't even mention Drupal CMS or Site Templates when it evaluated Drupal.

Over the past few years, much of my personal focus has been on accelerating innovation in Drupal. That work is paying off, and we have real product momentum. I'm now shifting more of my attention to the other side of the equation: making sure people see what we've built, understand what has changed, and know why it matters.

![Slide reading "Drupal is now light-years ahead of its reputation" over translucent red and yellow shapes, with a pink glass rocket on the left.](http://default/files/cache/drupalcon-rotterdam-2026/reputation-640w.png)

So I announced the [Drupal Advocacy Program](https://www.drupal.org/advocacy), led by the Drupal Association.

Drupal already has a contribution credit system. It recognizes the people who contribute to Drupal and the organizations that support their work. For businesses, those credits also help determine visibility in the Drupal marketplace. Until now, we've been much better at recognizing technical contributions and financial support than advocacy work.

The new Drupal Advocacy Program will change that. Advocacy work can now earn contribution credit, and work that reaches people outside the existing Drupal community can earn more weight.

If we want to close Drupal's reputation gap, we can't only talk to people who already know Drupal well. We need more talks at external events, articles in broader publications, customer stories, demos, tutorials, and other work that helps people see what Drupal can do today.

Blue Drop Labs is a good example of what I mean. The day after the DriesNote, they published a post on [building a website with Drupal CMS and Canvas Headless](https://www.bluedroplabs.com/resources/articles/drupal-canvas-headless-astro). The project itself was already live, but they quickly turned that work into a story others could learn from, with demos showing how editors and developers work with Drupal today.

That is exactly what I mean by "talking louder". There is already a lot of impressive Drupal work happening. We need to do a better job of showing it to the world.

I was a little nervous about announcing the Advocacy Program. We've wrestled with Drupal's reputation gap for a long time, and I felt we needed to do more than acknowledge it. Using contribution credit to reward advocacy was a concrete way to change the incentives, but I wasn't sure how the community would react.

It turned out to be one of the best-received announcements of the keynote. That response gave me confidence that people were ready to act on the reputation gap, not just recognize it.

You can [learn how to earn Drupal advocacy credit](https://www.drupal.org/association/blog/drupal-advocacy-program) and [submit your advocacy work](https://www.drupal.org/advocacy).

![Slide reading "Talk louder" over translucent circuit boards and electronic parts glowing red, orange and yellow.](http://default/files/cache/drupalcon-rotterdam-2026/talk-louder-640w.png)

My ask is simple: talk louder about Drupal, especially to people outside our community. Drupal doesn't need hype, but we do need a better public record. We need more people showing, with real examples, what Drupal can do today.

*I want to extend my gratitude to everyone who contributed to making my presentation and demos a success. A special thank you to [Bálint Kléri](https://www.drupal.org/u/balintbrews), [Christoph Breidert](https://www.drupal.org/u/breidert), [Gábor Hojtsy](https://www.drupal.org/u/gábor-hojtsy), [Lauri Timmanee](https://www.drupal.org/u/lauriii), [Matt Glaman](https://www.drupal.org/u/mglaman), [Michael Lander](https://www.drupal.org/u/michaellander), [Pamela Barone](https://www.drupal.org/u/pameeela), [Shibin Das](https://www.drupal.org/u/d34dman), and the [Drupal AI partners](https://www.drupal.org/ai/partners). Many others contributed indirectly to make this possible. If I've inadvertently omitted anyone, please reach out.*

PS: Follow the discussion on [LinkedIn](https://www.linkedin.com/feed/update/urn:li:activity:7513516254889058304/).
