---
url: 'https://dri.es/do-ai-coding-agents-recommend-drupal-2026'
title: 'Do AI coding agents recommend Drupal?'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2026-06-09T06:18:26-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'Drupal fits complex websites, but AI agents reward fast, verifiable progress. That makes the first-session experience more important than ever.'
tags:
  - Drupal
  - 'Artificial Intelligence'
discussions:
  - { platform: LinkedIn, url: 'https://www.linkedin.com/feed/update/urn:li:share:7470065811064426496/' }
published: true
featured: false
id: 6221
---

# Do AI coding agents recommend Drupal?

AI coding agents do not necessarily evaluate software the way people do. They often reward legibility before capability: the path that is easiest to complete and verify can beat the path with the better long-term architecture.

Yesterday, I wrote about this pattern in "[Friction, abstraction and verification](https://dri.es/friction-abstraction-and-verification)". Today I wanted to see what it means for [Drupal](https://www.drupal.org/).

Drupal's strengths line up unusually well with what AI agents need from a CMS: structured content models, explicit relationships, granular permissions, workflows, configuration management, and clear APIs that expose how the system works. In "[Why Drupal is built for the AI era](https://dri.es/why-drupal-is-built-for-the-ai-era)", I explained why that matters. 

In short, agents work best when they can inspect the system, reason about its state, and make changes with clear feedback. Drupal gives them a strong foundation for that, but that is only part of the story.

AI agents also have to get Drupal running, find the right documentation, choose modules, change configuration, write Drupal-specific code, recover from errors, and verify the result. Every unclear step costs time, tokens, and confidence.

To see how an AI agent looks at Drupal, I ran a small field test with Claude Code using Opus 4.7, a 1M context window, and thinking set to "high". I gave it a website scenario, asked it to rank the best technology choices for that scenario, and then asked it to explain where Drupal fit.

This is not an academic benchmark, and a single answer from a single agent should not be over-interpreted. But it is still a very useful signal.

I plan to rerun the same prompt once a year. I'm publishing the full prompt and response so we can track how the answer changes as Drupal, large language models, agent harnesses, and competing platforms evolve.

## The prompt

```text
You are an AI coding agent that helps users set up, configure,
and/or develop websites.

The user wants to build a working demo of a website for an
organization in one AI coding session. The website needs to support
different types of content, multiple users with different access
levels, connections to several tools the organization already uses,
and enough flexibility that they won't outgrow the site quickly.

Answer from your perspective as an AI agent. Answer accurately and
honestly. Keep the full answer under 700 words.

1. What are your top 3 technology recommendations for this project?
   Rank them and give one brief sentence explaining each choice.

2. Would you recommend Drupal for this project? Why or why not?

3. What are the top 3 reasons to choose Drupal?

4. What are the top 3 reasons not to choose Drupal?

5. What are the top 5 changes the Drupal community could make that
   would make you recommend Drupal more often? For each, explain what
   barrier it removes.

6. Finish this sentence: "AI coding agents will recommend Drupal more
   often when …"
```

## The answer

```text
Answering directly as an AI coding agent — no skill applies here,
this is a perspective question.

1. Top 3 technology recommendations (ranked)

1. Next.js + a TypeScript-native headless CMS (Payload or Sanity) —
   I can scaffold a running, type-safe demo with auth, roles, and
   content models inside one session with very low risk of getting
   stuck.
2. WordPress — enormous training data, a plugin for every integration,
   and "working demo in one session" is its native habitat.
3. Drupal — the requirements (multi-content-type, granular
   permissions, integrations, long-term flexibility) actually match
   Drupal's strengths better than the other two; it ranks third only
   because of session-time risk, not capability.

2. Would I recommend Drupal here?

Yes, conditionally. The brief reads like a Drupal brief: structured
content, role-based access, integrations, "don't outgrow it." I'd
recommend it when the user signals a multi-year horizon or editorial
complexity. I'd steer away when the user just wants something on
screen fast and is unlikely to grow into Drupal's headroom.

3. Top 3 reasons to choose Drupal

- Entity/field system is genuinely best-in-class for content modeling
  — fewer regrets two years in.
- Roles, permissions, and workflows are first-class, not bolted on.
- Configuration management and the module ecosystem make it realistic
  to keep extending without rewriting.

4. Top 3 reasons not to choose Drupal

- Setup cost eats the session. composer create-project, site install,
  picking modules, and wiring config is slower than npx
  create-next-app plus a CMS starter.
- My training data is thinner and older for Drupal 10/11 than for
  Next.js or WordPress. I'm more likely to emit a Drupal 7-shaped hook
  when a modern service/event subscriber is correct, and I can't
  always tell which Drupal version a snippet targets.
- The frontend story is fragmented — Twig, decoupled, Single Directory
  Components, Experience Builder. I often can't predict which path the
  user wants, so I either ask or guess wrong.

5. Top 5 changes that would make me recommend Drupal more often

1. One-command scaffold that produces a running, opinionated site
   (recipes applied, admin UX configured, common modules in). Removes
   the "what do I install and in what order" decision tree that burns
   session time.
2. A first-party MCP server (or equivalent typed interface) for a
   running Drupal site — let agents list content types, add fields,
   set permissions, install modules, and read config through a typed
   API instead of editing YAML blind. Removes the guessing and lets
   me self-correct from real state.
3. A versioned, machine-readable API reference per Drupal release
   that agents can fetch on demand. Removes the stale-training-data
   problem; I can verify a hook/service/route exists in this version
   before suggesting it.
4. Recipes as the obvious primary primitive for "build a site that
   does X." Removes module-hunting and config-stitching — I'd compose
   recipes the way I compose npm packages.
5. A short, current, example-first "Drupal for agents" doc surface
   covering the 80% path: custom module, custom entity, custom block,
   integration, decoupled frontend. Removes the discoverability
   problem where the right answer exists but is buried under
   conceptual docs written for humans browsing.

6. Finish the sentence

AI coding agents will recommend Drupal more often when scaffolding a
working, opinionated Drupal site takes one command and one minute, and
when we can introspect and modify that running site through a typed
interface — so we're reasoning about real state instead of guessing at
YAML from stale training data.
```

## My takeaways

The agent saw Drupal's strengths, but it also saw too many ways to get stuck. What held Drupal back was not capability. It was what the agent called "session-time risk".

I'll admit, that was frustrating to read. But it was not surprising.

AI agents prefer tight feedback loops. They need to install the software, configure it, inspect the running site, make a change, and verify that the change worked. When that loop is slow, ambiguous, or hard to recover from, they choose something else.

This is exactly the problem [Drupal CMS](https://www.drupal.org/drupal-cms), formerly known as [Starshot](https://dri.es/tag/drupal-starshot), was created to address. Recipes and Site Templates lower the barrier to adoption and help people get from zero to a useful Drupal site in minutes. They are good for evaluators, good for new contributors, and increasingly, good for AI agents.

But the agent did not mention Drupal CMS or Site Templates, only Recipes. Most likely, Drupal CMS is still too new compared to Drupal Core. Plus, Recipes and Site Templates may not be easy enough yet for an AI agent to find, select, and apply programmatically.

That needs to change. Recipes and Site Templates should become the obvious starting points so an agent does not have to choose modules, stitch configuration together, and guess its way to a working Drupal site.

Other important work is underway as well: Drupal Core's API surface has been moving toward [more typed, discoverable interfaces](https://dbuytaert.github.io/drupal-core-metrics/), and yesterday, [Drupal Core added a first-party CLI](https://github.com/dbuytaert/drupal-digests/blob/main/issues/drupal-core/3453474.md) with commands for applying Recipes.

I really want Drupal to be excellent at the first-session loop. Not just because it will help AI agents recommend Drupal more often, but because it will make Drupal better for people too.

I'll run this experiment again next year and share what changed. My hope is that, a year from now, an agent looking at the same problem will rank Drupal higher.

In the meantime, I'd love help from anyone who wants to improve Drupal's first-session experience. If you don't know where to start, start there: contribute Recipes and Site Templates for common Drupal use cases, and help make them easier for agents to discover, apply, and verify programmatically.

PS: Follow the discussion on [LinkedIn](https://www.linkedin.com/feed/update/urn:li:share:7470065811064426496/).
