---
url: 'https://dri.es/the-orchestration-shift'
title: 'The Orchestration Shift'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2025-10-29T05:43:25-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'Your marketing stack is becoming a marketing network. Why the layer that connects your tools could be the next critical infrastructure.'
tags:
  - Drupal
  - Investing
  - 'Artificial Intelligence'
  - Activepieces
  - 'Workflow orchestration'
  - Trends
image: blog/orchestration-shift
discussions:
  - { platform: '', url: 'https://www.linkedin.com/posts/buytaert_the-orchestration-shift-activity-7389263259708694528-h5qe' }
published: true
featured: true
id: 5911
---

# The Orchestration Shift

[image blog/orchestration-shift lazy=false priority=true]

Last summer, I was building a small automation in [n8n](https://n8n.io/) when I came across [Activepieces](https://www.activepieces.com/). Both tools promise the same thing: connect your applications, automate your workflows, and host it yourself. But when I clicked through to [Activepieces' GitHub repo](https://github.com/activepieces/activepieces), I noticed it's released under the MIT license. Truly Open Source, not just [source-available](https://en.wikipedia.org/wiki/Source-available_software) like n8n.

As I dug deeper into these tools, something crystallized for me: _business logic is moving out of individual applications and into the orchestration layer_. 

Today, most organizations run on dozens of disconnected tools. A product launch means logging into Mailchimp for email campaigns, Salesforce for lead tracking, Google Analytics for performance monitoring, Drupal for content publishing, Slack for team coordination, and a spreadsheet to keep everything synchronized. We copy data between systems, paste it into different formats, and manually trigger each step. In other words, most organizations are still doing orchestration by hand. 

With orchestration tools maturing, this won't stay manual forever. That led me to an investment thesis that I call the Orchestration Shift: _the tools we use to connect systems are becoming as important as the systems themselves_.

This shift could change how we think about enterprise software architecture. For the last decade, we've talked about the "marketing technology stack" or "martech stack": collections of tools connected through rigid, point-to-point integrations. Orchestration changes this fundamentally. Instead of each tool integrating directly with others, an orchestration layer coordinates how they work together: the "martech stack" becomes a "martech network".

### Why I invested in Activepieces

I believe that in the next five to ten years, orchestration platforms like Activepieces are likely to become critical infrastructure in many organizations. If that happens, this shift needs Open Source infrastructure. Not only proprietary SaaS platforms or source-available licenses with commercial restrictions, but truly open infrastructure. 

The world benefits when critical infrastructure has strong Open Source alternatives. Linux gave us an alternative to proprietary operating systems. MySQL and PostgreSQL gave us alternatives to Oracle. And of course, Drupal and WordPress gave us alternatives to dozens of proprietary CMSes.

That is why Activepieces stood out: it is Open Source and positioned for an important market shift. 

So I reached out to [Ash Samhouri](https://www.linkedin.com/in/ashrafsam/), their co-founder and CEO, to learn more about their vision. After a Zoom call, I came away impressed by both the mission and the momentum. When I got the opportunity to invest, I took it. 

A couple months later, [n8n raised over $240 million at a $2.5 billion valuation](https://blog.n8n.io/series-c/), validation that the orchestration market was maturing rapidly.

I invested not just money, but also time and effort. Over the summer, I worked with [Jürgen Haas](https://www.drupal.org/u/jurgenhaas) to create [a Drupal integration for Activepieces](https://www.activepieces.com/pieces/drupal) and the [orchestration module for Drupal](https://www.drupal.org/project/orchestration). Both shipped the week before DrupalCon Vienna, where I demonstrated them in [my opening keynote](https://dri.es/state-of-drupal-presentation-october-2025). 

### How orchestration changes platforms

Consider what this means for platforms like [Drupal](https://www.drupal.org/), which I have led for more than two decades. Drupal has thousands of contributed modules that integrate with external services. But if orchestration tools begin offering those same integrations in a way that is easier and more powerful to use, we have to ask how Drupal's role should evolve.

Drupal could move from being the central hub that manages integrations to becoming a key node within this larger orchestration network.

In this model, Drupal continues managing and publishing content while also acting as a connected participant in such a network. Events in Drupal can trigger workflows across other systems, and orchestration tools can trigger actions back in Drupal. This bidirectional connection makes both more powerful. Drupal gains capabilities without adding complexity to its core, while orchestration platforms gain access to rich content, structured data, publishing workflows, and more. 

Drupal can also learn architecturally from these orchestration platforms. Tools like n8n and Activepieces use a simple but powerful pattern: every operation has defined inputs and outputs that can be chained together to build workflows. Drupal could adopt this same approach, making it easier to build internal automations and positioning Drupal as an even more natural participant in orchestration networks.

We have seen similar shifts before. TCP/IP did not make telephones irrelevant; it changed where the intelligence lived. Phones became endpoints in a network defined by the protocol connecting them. Orchestration may follow a similar path, becoming the layer that coordinates how business systems work together.

### Where orchestration is heading

Today, orchestration platforms handle workflow automation: when X happens, do Y. Form submissions create CRM entries, send email notifications, post Slack updates. I demonstrated this pattern in [my DrupalCon Vienna keynote](https://dri.es/state-of-drupal-presentation-october-2025), showing how predefined workflows eliminate manual work and custom integration code.

But orchestration is evolving toward something more powerful: _digital workers_. These AI-driven agents will understand context, make decisions, and execute complex tasks across platforms. A digital worker could interpret a goal like "Launch the European campaign for our product launch", analyze what needs to happen, build the workflows, coordinate across your martech network, execute them, and report results. 

Tools like Activepieces and protocols like the [Model Context Protocol](https://www.anthropic.com/news/model-context-protocol) are laying the groundwork for this future. We're moving from automation (executing predefined steps) to autonomy (understanding intent and figuring out how to achieve it). The future will likely require both: deterministic workflows for reliability and consistency, combined with AI-driven decision-making for flexibility and intelligence.

This shift makes the orchestration layer even more critical. It's not just connecting systems anymore; it's where business intelligence and decision-making will live.

### Conclusion

When I first clicked through to Activepieces' GitHub repo last summer, I was looking for a tool to automate a workflow. What I found was something bigger: a glimpse of how business software architecture is fundamentally changing. I've been thinking about it since.

To me, the question isn't whether orchestration will become critical infrastructure. It's whether that infrastructure will be open and built collaboratively. That is a future worth investing in, both with capital and with code.

PS: Follow the discussion on [](https://www.linkedin.com/posts/buytaert_the-orchestration-shift-activity-7389263259708694528-h5qe).
