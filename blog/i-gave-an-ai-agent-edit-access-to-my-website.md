---
url: 'https://dri.es/i-gave-an-ai-agent-edit-access-to-my-website'
title: 'I gave an AI agent edit access to my website'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2025-01-21T17:31:49-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - 'Artificial Intelligence'
  - Drupal
image: blog/collaborating-with-an-ai-agent
published: true
id: 5746
---

# I gave an AI agent edit access to my website

[image blog/collaborating-with-an-ai-agent schema=false]

I'm often asked, <q>Will AI agents replace digital marketers and site builders?</q>. The answer is <q>yes</q>, at least for certain kinds of tasks.

To explore this idea, I prototyped two AI agents to automate marketing tasks on my personal website. They update meta descriptions to improve SEO and optimize tags to improve content discovery.

Watching the AI agents in action is incredible. In the video below, you'll see them effortlessly navigate my Drupal site: logging in, finding posts, and editing content. It's a glimpse into how AI could transform the role of digital marketers.

<div class="large">
  [video sRlVFCILV3Q]
</div>

### The experiment

I built two AI agents to help optimize my blog posts. Here is how they work together:

- **Agent 1: Content analysis:** This agent finds a blog post, reviews its content, and suggests improved summaries and tags to enhance SEO and increase discoverability.
- **Agent 2: Applying updates:** After manual approval, this agent logs into the site and updates the summary and tags suggested by the first agent.

All of this could be done in one step, or with a single agent, but keeping a 'human-in-the-loop' is good for quality assurance.

This was achieved with just 120 lines of Python code and a few hours of trial and error. As the video demonstrates, the code is approachable for developers with basic programming skills.

The secret ingredient is the [`browser_use` framework](https://github.com/browser-use/browser-use), which acts as a bridge between various LLMs and [Playwright](https://playwright.dev/), a framework for browser automation and testing.

### The magic and the reality check

What makes this exciting is the agent's ability to problem-solve. It's almost human-like.

Watching the AI agents operate my site, I noticed they often face the same UX challenges as humans. It likely means that the more we simplify a CMS like Drupal for human users, the more accessible it becomes for AI agents. I find this link between human and AI usability both striking and thought-provoking.

In the first part of the video, the agent was tasked with finding my [DrupalCon Lille 2023 keynote](https://dri.es/state-of-drupal-presentation-october-2023). When scrolling through the [blog section](/blog) failed, it adapted by using Google search instead.

In the second part of the video, it navigated Drupal's more complex UI elements, like auto-complete taxonomy fields, though it required one trial-and-error attempt.

The results are incredible, but not flawless. I ran the agents multiple times, and while they performed well most of the time, they aren't reliable enough for production use. However, this field is evolving quickly, and agents like this could become highly reliable within a year or two.

### Native agents versus explorer agents

In my mind, agents can be categorized as "explorer agents" or "native agents". I haven't seen these terms used before, so here is how I define them:

- **Explorer agents:** These agents operate across multiple websites. For example, an agent might use Google to search for a product, compare prices on different sites, and order the cheapest option.
- **Native agents:** These agents work within a specific site, directly integrating with the CMS to leverage its APIs and built-in features.

The `browser_use` framework, in my view, is best suited for explorer agents. While it can be applied to a single website, as [shown in my demo](https://youtu.be/sRlVFCILV3Q), it's not the most efficient approach.

Native agents that directly interact with the CMS's APIs should be more effective. Rather than imitating human behavior to "search" for content, the agent could retrieve it directly through a single API call. It could then programmatically propose changes within a CMS-supported content editing workflow, complete with role-based permissions and moderation states

I can also imagine a future where native agents and explorer agents work together (hybrid agents), combining the strengths of both approaches to unlock even greater opportunities.

### Next steps

A next step for me is to build a similar solution using [Drupal's AI agent capabilities](https://dri.es/drupal-cms-1-released). Drupal's native AI agents should make finding and updating content more efficiently.

Of course, other digital marketing use cases might benefit from explorer agents. I'd be happy to explore these possibilities as well. Let me know if you have ideas.

### Conclusions

Building an AI assistant to handle digital marketing tasks is no longer science fiction. It's clear that, soon, AI agents will be working alongside digital marketers and site builders.

These tools are advancing rapidly and are surprisingly easy to create, even though they're not yet perfect. Their potential disruption is both exciting and hard to fully understand.

As Drupal, we need to stay ahead by asking questions like: are we fully imagining the disruption AI could bring? The future is ours to shape, but we need to rise to the challenge.
