---
url: 'https://dri.es/drupal-role-in-agentic-workflows'
title: "Drupal's role in agentic workflows"
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2026-06-23T09:47:53-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: "Drupal's future in AI workflows has two parts: helping people with AI inside Drupal, and helping agents and workflow tools use Drupal from the outside."
tags:
  - Drupal
  - 'Workflow orchestration'
  - 'Artificial Intelligence'
image: blog/orchestrating-nodes
discussions:
  - { platform: LinkedIn, url: 'https://www.linkedin.com/feed/update/urn:li:activity:7475188947816636417/' }
published: true
featured: true
id: 6241
---

# Drupal's role in agentic workflows

![A person stands before a large, glowing dark sphere filled with stars and surrounded by smaller orbiting nodes.](http://default/files/cache/blog/orchestrating-nodes-640w.jpg)

When we started working on the [Drupal AI initiative](https://dri.es/accelerating-ai-innovation-in-drupal) in June 2025, I assumed most AI features would live inside [Drupal](https://www.drupal.org). 

By my [DrupalCon Chicago keynote](https://dri.es/state-of-drupal-presentation-march-2026) in March 2026, my thinking had changed. I framed the shift as "inside-out" versus "outside-in" and concluded that not every AI capability belongs inside Drupal. Some work is better done outside the CMS, where AI tools can move faster and connect back to Drupal when needed.

Last week, I explored these ideas in more detail in "[AI and the great CMS unbundling](https://dri.es/ai-and-the-great-cms-unbundling)". That post argued AI is making the CMS less central as a creation tool, but more important as a control layer: the place where content is structured, governed, reused, and published with trust.

This post picks up from there. If Drupal's role as the control layer is becoming more important, it needs to support AI-driven workflows that run inside Drupal, start outside Drupal, and move across both: external workflows that call into Drupal, and Drupal-native workflows that outside systems can safely rely on.

## Drupal joins workflows beyond the CMS

First, Drupal needs to work well with tools outside the CMS: coding agents like [Claude Code](https://www.anthropic.com/claude-code) and [Cursor](https://cursor.com), and orchestration platforms like [Salesforce Agentforce](https://www.salesforce.com/agentforce/), [n8n](https://n8n.io), and [Activepieces](https://www.activepieces.com).

I actually showed what this could look like in my [DrupalCon Vienna keynote](https://dri.es/state-of-drupal-presentation-october-2025) in October 2025. Here is a [short clip](https://www.youtube.com/watch?v=UZDMIGJ8O9A) of that:

https://www.youtube.com/watch?v=UZDMIGJ8O9A

It was a proof of concept demo, and we had some fun with it. But the pattern behind the demo mattered more than the demo itself: an external tool drove the work and handed tasks to Drupal, while Drupal returned structured content and state.

Watch the demo, and it will be easy to imagine the same pattern in a real marketing use case. Campaigns usually begin with a marketing brief and span many tools and channels: email, website landing pages, social media, paid media, and more.

An external agentic platform could generate campaign copy and ask Drupal to build a landing page. Drupal could map the copy to the right structured content type, place it into approved components with Drupal Canvas, save a draft, and flag any fields, metadata, or translations still missing before it can publish.

If Drupal reports a missing hero image, the agentic platform could search the digital asset management system (DAM), find an approved campaign image, and hand it back. Drupal could then attach it through its media model, supply or verify the required `alt`-text, confirm the page meets its requirements, and advance the draft through the editorial workflow.

This is a pattern that Drupal will need to support well. External platforms can coordinate work across the broader digital stack, but Drupal should remain the system that assembles, validates, governs, and publishes the content.

## External workflows call Drupal-native workflows

While the larger campaign workflow may live outside Drupal, there is an equally important case for Drupal-native workflows. 

External agents are good at coordinating work across systems. But once a workflow needs to act on Drupal content or data, it should use Drupal's native content model, permissions, validation rules, moderation states, revisions, and publishing workflows rather than recreate them outside of Drupal.

That is where projects like [ECA](https://www.drupal.org/project/eca), [FlowDrop](https://www.drupal.org/project/flowdrop), and [Maestro](https://www.drupal.org/project/maestro) become more important. They let Drupal turn site-specific processes into repeatable, multi-step workflows that outside systems can call. 

For example, any of these three systems could power a single Drupal workflow that validates a draft, coordinates translations in five languages, assigns reviewers, and publishes the content only after all required approvals are complete. 

Depending on the task, these internal Drupal workflows can be deterministic, AI-assisted, or fully agentic. Drupal can support that today.

An external agent should not have to manipulate Drupal from the outside, field by field or function by function. It should be able to ask Drupal to execute a Drupal-native workflow through a single external API call.

That is the other half of what I showed in the [demo video](https://www.youtube.com/watch?v=UZDMIGJ8O9A) above. Drupal was not just exposing content to an external agent. It was exposing custom Drupal-native ECA workflows that an external automation tool called.

That was powerful last fall at DrupalCon Vienna, but as agentic workflows become more common, this pattern will only grow in importance.

## The best end-to-end experience will win

There is a natural tendency to debate what should live where. Should AI happen inside Drupal, or outside of it? Should workflows be Drupal-native, or managed by external platforms?

Those are useful questions, but the answer is not universal. AI and workflows should live where they create the best end-to-end experience. Sometimes that will be inside Drupal, sometimes outside Drupal, and often across both.

What "best" means depends on the use case, the user, and the requirements for speed, reliability, security, governance, cost, and human review. There will be best practices, but no single approach fits every case.

Who is doing the work shapes what "best" looks like: 
* A developer may prefer an external coding agent like Claude Code. 
* A marketer may prefer a Drupal-native experience that keeps them close to previews, translations, moderation, and publishing. 
* A campaign manager may need an external workflow that coordinates email, social media, analytics, DAM, and CMS.

Work will move across systems and people. The best end-to-end experience will come from doing each step where it can be done best, while making the handoffs feel invisible.

## A head start is not a plan to win

Understanding Drupal's role in these future workflows gives us clarity about where Drupal needs to go. Drupal needs to get better at supporting external orchestration, Drupal-native workflows, and the real-world hybrids that combine both.

What makes Drupal interesting is that it already has so much of the hard, unglamorous infrastructure these workflows need: structured content, granular permissions, revisions, rollback, JSON:API, and plenty more. These are exactly the capabilities agents need, and they're genuinely difficult to build well from scratch or retrofit.

Conceptual clarity and a strong foundation are wonderful things, but they are not enough to win.

When I asked [whether AI coding agents would recommend Drupal](https://dri.es/do-ai-coding-agents-recommend-drupal-2026), the issue was not Drupal's capability. It was whether agents could get from prompt to a working Drupal site quickly and easily enough. As I wrote in "[Friction, abstraction and verification](https://dri.es/friction-abstraction-and-verification)", agents tend to choose the path that gets them to a real, verified result with the least friction. 

For experienced Drupal teams, the challenge is different. They have already chosen Drupal. They do not need an agent to recommend it. They need agents that help them build, validate, and ship quality work faster.

To turn Drupal's advantage into adoption, we need to improve both paths: helping agents choose Drupal for new builds, and helping existing Drupal teams ship better work faster. Both depend on making it easier for agents to work with Drupal from start to finish.

That means Drupal needs to expose the best practices, site context, tool definitions, constraints, and precise validation agents need to take the right actions and verify the result.

A lot of this is already underway across Recipes, Site Templates, Drupal AI, Drupal Canvas, ECA, FlowDrop, Maestro, MCP, and CLI improvements, to name a few.

But the goal is bigger than any one project. Drupal needs these efforts to add up to a clear, coordinated path for agents: from setup to connection, context, governed action, validation, recovery, and launch. 

*Special thanks to [James Abrahams](https://www.drupal.org/u/yautja_cetanu), [Jürgen Haas](https://www.drupal.org/u/jurgenhaas), [Randy Kolenko](https://www.drupal.org/u/_randy), [Scott Falconer](https://www.drupal.org/u/scott-falconer), and [Shibin Das](https://www.drupal.org/u/d34dman) for their review and contributions to this blog post.*

PS: Follow the discussion on [LinkedIn](https://www.linkedin.com/feed/update/urn:li:activity:7475188947816636417/).
