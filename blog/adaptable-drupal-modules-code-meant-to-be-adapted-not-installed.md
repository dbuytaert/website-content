---
url: 'https://dri.es/adaptable-drupal-modules-code-meant-to-be-adapted-not-installed'
title: 'Adaptable Drupal modules: code meant to be adapted, not installed'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2025-12-18T04:31:31-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
  - 'Artificial Intelligence'
published: true
featured: false
id: 6001
---

# Adaptable Drupal modules: code meant to be adapted, not installed

Over the years, I've built dozens of small, site-specific Drupal modules. None of them live on Drupal.org.

It makes me wonder: how many modules like that exist across the Drupal ecosystem? I'm guessing a lot.

For example, I recently [open-sourced the content of this blog](https://dri.es/i-open-sourced-my-blog-content) by exporting my posts as Markdown files and publishing them on GitHub. To do that, I built two custom Drupal modules with Claude Code: one that converts HTML to Markdown, and another that exports content as YAML with Markdown.

Both modules embed architectural choices and algorithms I explicitly described to Claude Code. Both have unit tests and have been used in production. But both _only_ work for my site.

They're built around my specific content model and field names. For example, my export module expects fields like `field_summary` and `field_image` to exist. I'd love to  contribute them to Drupal.org, but turning site-specific code into something reusable can be a lot of work.

On Drupal.org, contributed modules are expected to work for everyone. That means abstracting away my content model, adding configuration options I'll never use, handling edge cases I'll never hit, and documenting setups I haven't tested.

There is a "generalization tax": the cost of making code flexible enough for every possible site. Drupal has always had a strong culture of contribution, but this tax has kept a lot of useful code private. My blog alone has ten custom modules that will probably never make it to Drupal.org under the current model.

Generalization work is extremely valuable, and the maintainers who do it deserve a lot of credit. But it can be a high bar, and a lot of useful code never clears it.

That made me wonder: what if we had a different category of contributed code on Drupal.org?

Let's call them "adaptable modules", though the name matters less than the idea.

The concept is simple: tested, working code that solves a real problem for a real site, shared explicitly as a starting point. You don't install these modules. You certainly don't expect them to work out of the box. Instead, an AI adapts the code for you by reading it and understanding the design decisions embedded in it. Or a human can do the same.

In practice, that might mean pointing Claude Code at my Markdown export module and prompting: "I need something like this, but my site uses Paragraphs instead of a regular Body field". Or: "I store images in a media field instead of an image field". The AI reads the code, understands the approach, and generates a version tailored to your setup.

This workflow made less sense when humans had to do all the adaptation. But AI changes the economics. AI is good at reading code, understanding what it does, and reshaping it for a new context. The mechanical work of adaptation is becoming both cheap and reliable.

What matters are the design decisions embedded in the code: the architecture, the algorithms, the trade-offs. Those came from me, a human. They are worth sharing, even if AI handles the mechanical adaptation.

This aligns with where engineering is heading. As developers, we'll spend less time on syntax and boilerplate, and more time on understanding problems, making architectural choices, and weighing trade-offs. Our craft is shifting from writing code to shaping code. And orchestrating the AI agents that writes it. Adaptable modules fit that future.

Modules that work for everyone are still important. Drupal's success will always depend on them. But maybe they're not the only kind worth sharing. The traditional contribution model, generalizing everything for everyone, makes less sense for smaller utility modules when AI can generate context-specific code on demand.

Opinionated, site-specific modules have always lived in private repositories. What is new is that AI makes them worth sharing. Code that only works for my site becomes a useful starting point when AI can adapt it to yours. 

I created an [issue on Drupal.org to explore this further](https://www.drupal.org/project/drupalorg/issues/3563839). I'd love to hear what you think.

*(Thanks to [phenaproxima](https://www.drupal.org/u/phenaproxima), [Tim Lehnen](https://www.drupal.org/u/hestenet), [Gábor Hojtsy](https://www.drupal.org/u/g%C3%A1bor-hojtsy) and [Wim Leers](https://www.drupal.org/u/wim-leers) for reviewing my draft.)*
