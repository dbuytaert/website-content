---
url: 'https://dri.es/friction-abstraction-and-verification'
title: 'Friction, abstraction and verification'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2026-06-08T03:13:27-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'AI agents favor software they can easily install, run, change, and verify. Open Source software has a structural advantage over proprietary software, but only token-efficient Open Source projects may get chosen.'
tags:
  - 'Artificial Intelligence'
  - 'Open Source'
  - 'Software development'
  - Usability
discussions:
  - { platform: LinkedIn, url: 'https://www.linkedin.com/feed/update/urn:li:share:7469674277081067520/' }
published: true
featured: false
id: 6216
---

# Friction, abstraction and verification

AI coding agents like Claude Code and OpenAI Codex tend to choose the path that is cheapest to complete. They work within a budget of tokens, context, time, tools, and permissions. Every step spends from that budget: reading documentation, installing software, running it, configuring it, changing it, and fixing errors.

For Open Source, this is a rare opportunity. AI agents could become its biggest adoption engine yet. While that should energize Open Source communities, it should also make proprietary vendors deeply uncomfortable. 

Many proprietary software vendors have spent years optimizing for a human buyer journey: capture a lead, qualify the buyer, force a signup, offer a demo or trial experience, ask for a credit card, schedule a sales call.

Humans may grumble but keep going. To an AI coding agent, these are blockers, not buying steps.

Open Source starts from a different place. AI agents can read the source code, run it locally, and change it without asking anyone for permission. That does not guarantee adoption, but it removes the proprietary gates that slow agents down.

But being Open Source is not enough. Open Source removes the "permission barriers", but it can still have "execution barriers". If an Open Source project is hard to install, configure, extend, debug, or verify, an agent may choose an easier Open Source project instead.

In that sense, AI agents amplify an old truth about software adoption: the best software does not always win. The software with the easiest path to a working result often does. 

But AI agents amplify that truth through "silent rejection". A human evaluator might complain, ask for help, file an issue, or write an angry Reddit post. An AI agent just tries another path. You may never know your software was considered and rejected.

### Easy is more than low friction

If you want your project to be adopted, you have to make the best path the easiest one to complete.

And "easy" means more than low friction. For an AI agent, there are at least three costs: friction, abstraction, and verification.

<figure>
  <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 685 155" role="img" aria-label="Three adoption costs: friction, abstraction, and verification" focusable="false" color="var(--primary-font-color, #222)" style="max-width:100%;height:auto;font-size:1rem">
  <desc>A compact diagram showing three adoption costs: friction, abstraction, and verification.</desc>
  <g font-family="inherit" text-anchor="middle" fill="currentColor">
  <g transform="translate(0 14)">
  <rect width="215" height="96" rx="14" fill="var(--hover-color, #f4f4f4)" />
  <text x="107.5" y="35" font-size="1.2em" font-weight="650">Friction</text>
  <path d="M77.5 50h60" stroke="var(--table-zebra-color, #ddd)" stroke-width="1" />
  <text x="107.5" y="75" font-size="0.88em">Can I get it running?</text>
  <text x="107.5" y="126" font-size="0.76em" fill="var(--secondary-font-color, #666)">Install • Setup • Access</text>
</g>
  <g transform="translate(235 14)">
  <rect width="215" height="96" rx="14" fill="var(--hover-color, #f4f4f4)" />
  <text x="107.5" y="35" font-size="1.2em" font-weight="650">Abstraction</text>
  <path d="M77.5 50h60" stroke="var(--table-zebra-color, #ddd)" stroke-width="1" />
  <text x="107.5" y="70" font-size="0.88em">Do I know what</text>
  <text x="107.5" y="88" font-size="0.88em">to do next?</text>
  <text x="107.5" y="126" font-size="0.76em" fill="var(--secondary-font-color, #666)">Recipes • Scaffolds • Defaults</text>
</g>
  <g transform="translate(470 14)">
  <rect width="215" height="96" rx="14" fill="var(--hover-color, #f4f4f4)" />
  <text x="107.5" y="35" font-size="1.2em" font-weight="650">Verification</text>
  <path d="M77.5 50h60" stroke="var(--table-zebra-color, #ddd)" stroke-width="1" />
  <text x="107.5" y="70" font-size="0.88em">Can I tell whether</text>
  <text x="107.5" y="88" font-size="0.88em">it worked?</text>
  <text x="107.5" y="126" font-size="0.76em" fill="var(--secondary-font-color, #666)">Tests • Errors • Visible state</text>
</g>
</g>
</svg>
</figure>

_Friction_ is the cost of getting to a system the agent can run and change. Some friction comes from the environment: runtimes, containers, databases, package managers, local services, and setup choices that must be installed or configured before useful work can begin. Some comes from access and authorization: private repositories, account creation, credentials, and API keys.

_Abstraction_ is the cost of figuring out what to do next. Once the software is running, the agent still has to know which modules to use, how to structure the data, which settings to apply, which conventions to follow, and how the pieces should fit together. A good site template, recipe, or scaffold packages that expertise so the agent can take several correct steps at once instead of reconstructing the path from scratch.

_Verification_ is the cost of knowing whether the work succeeded. Tests, clear errors, inspectable state, and fast debugging cycles help the agent compare what happened with what should have happened. As I wrote in [AI rewards strict APIs](https://dri.es/ai-rewards-strict-apis), agents do not struggle with complexity; they struggle with ambiguity.

Each cost burns tokens, meaning the AI agent has to spend more of its limited context and reasoning budget reading documentation, comparing different options, or recovering from failed attempts.

### What helps agents helps people

This is not just an AI problem. People have always preferred software that is easy to get running, gives them a clear path forward, and tells them when something worked. AI agents make the same preference more obvious because they have even less room for trial and error.

Developer Experience (DX) makes software easier for developers to evaluate, build with, and maintain. Agent Experience (AX) makes software easier for agents to install, modify, and verify.

In practice, the overlap is large. Better scaffolding, clearer errors, faster setup, opinionated best practices, and reliable tests help agents, but they also help developers, evaluators, and contributors.

### Open Source still has to compete

The cheap-to-run advantage will not belong to Open Source forever. Proprietary vendors and SaaS companies are adding free tiers, programmatic access, and Model Context Protocol servers that give agents tools and context with less friction.

Open Source's structural advantage is about to expand, but it will concentrate in the projects that are easiest for agents to understand, run, and improve.

Every software project will have to earn its place in the agent flow. Being open will get you considered, but being easy to discover, install, inspect, modify, and verify will get you chosen.

PS: Follow the discussion on [LinkedIn](https://www.linkedin.com/feed/update/urn:li:share:7469674277081067520/).
