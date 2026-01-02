---
title: 'The Control Layers of AI'
date: '2025-12-30T17:05:37-05:00'
author: Dries
image: blog/orchestration-shift
tags:
  - 'Artificial Intelligence'
  - Drupal
  - Activepieces
  - 'Workflow orchestration'
featured: false
published: true
type: blog
url: /the-control-layers-of-ai
id: 6021
---

[image blog/orchestration-shift lazy=false priority=true]

Salesforce had an embarrassing moment last week.

Vivint uses Salesforce's Agentforce to send satisfaction surveys after customer service calls. Recently they discovered surveys were randomly not being sent and no one noticed for weeks.

When Salesforce investigated this problem, they found the root cause: their AI agents were skipping steps. They didn't need AI for that task. They needed the workflow to complete every time. So they added more structure and guardrails around the agents. More workflow, not more magic.

And that is the right answer. I actually wrote about this months ago in [The Orchestration Shift](https://dri.es/the-orchestration-shift):

> The future will likely require both: deterministic workflows for reliability and consistency, combined with AI-driven decision-making for flexibility and intelligence.

Salesforce learned it the hard way.

This is exactly why I've been paying attention to external workflow automation platforms like [n8n](https://n8n.io/) and [Activepieces](https://www.activepieces.com/). They let you control which steps are deterministic and which steps use AI. Internal automation solutions like [Drupal's Event-Condition-Action module](https://www.drupal.org/project/eca) follow the same idea.

Using Activepieces or n8n, Vivint's workflow would look like this: the customer service call ends, AI analyzes the transcript and personalizes the survey message, then the automation platform sends the email. The AI does what it is good at and the automation platform ensures the send happens every time.

LLMs are probabilistic by design. Steps that require determinism should not use AI. 

Two architectural approaches are emerging for solving this problem.

The first is "outside in". Workflow platforms like n8n or Activepieces put a deterministic process in control and use AI for specific steps within it. The workflow specifies when to invoke the AI, what to do with its output, and what happens if it fails. Outside in is more reliable and auditable. If the AI fails or returns something unexpected, the workflow catches it. You can see exactly what happened and why. But it is less flexible because you are limited to what the workflow designer anticipated.

The second approach is "inside out". AI agents can invoke deterministic tools as part of their operation. The AI is in control, but when it needs to do something that requires precision, it hands that task to a tool that executes reliably. This is what Anthropic's Claude Code does, for example. When Claude Code needs to verify that code compiles, it does not guess. It calls an actual compiler. Inside out is more adaptive. You describe what you want and the AI figures out how. But it is harder to audit and debug, harder to explain to regulators, and more expensive at scale since the AI is invoked at every step.

It feels intuitive that both approaches will coexist. They can be nested. Picture three layers. The outer layer is workflow automation. It is fully deterministic and guarantees the process. The middle layer is AI. It is non-deterministic and makes the judgment calls. The inner layer of the AI step are deterministic tools. They execute the precise actions for the AI.

Not everyone needs all three layers. For certain tasks, like writing software, inside out is enough. But for complex enterprise workflows with many steps, multiple integrations, complex business rules, and strict audit requirements, you need the outer layer.

That is where workflow automation platforms come in. They do not need to power every AI use case. They need to win the complex workflows where enterprises need visibility and control. That is also where a lot of commercial value will accrue. Enterprises pay for reliability and accountability. 

We are still early in the age of AI agents. The temptation is to believe that intelligence alone will replace structure. But enterprises cannot gamble processes that touch customers, revenue, or compliance. They need systems where every step is accountable. That is why deterministic workflows matter. They are where reliability and intelligence meet and where the next generation of enterprise platforms will be built.

And when infrastructure becomes essential, organizations want to own it, not rent it. That is why Linux won servers and PostgreSQL won databases. If the orchestration layer becomes essential to enterprise AI, open source will be an important choice. Activepieces is open source and n8n is "source available" (the code can be inspected but has commercial restrictions). Either way, I would love to see them succeed.
