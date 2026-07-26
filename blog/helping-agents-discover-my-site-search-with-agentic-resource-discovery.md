---
url: 'https://dri.es/helping-agents-discover-my-site-search-with-agentic-resource-discovery'
title: 'Helping agents discover my site search with Agentic Resource Discovery'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2026-07-23T15:25:24-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'My API catalog helps agents that already found my site. Agentic Resource Discovery, or ARD, tackles the harder problem: being found at all.'
tags:
  - 'My site'
  - 'Artificial Intelligence'
  - Drupal
discussions:
  - { platform: LinkedIn, url: 'https://www.linkedin.com/feed/update/urn:li:activity:7486197914839474176/' }
published: true
featured: false
id: 6281
---

# Helping agents discover my site search with Agentic Resource Discovery

Yesterday I blogged about the [API catalog](https://dri.es/helping-agents-discover-my-site-search-with-an-api-catalog) that announces my site's search API to agents. In response, someone pointed me to the [ARD specification](https://agenticresourcediscovery.org/), a draft announced last month by a working group that includes Google, Microsoft, GitHub, Hugging Face, Cisco, Nvidia, and Salesforce.

What ARD adds to yesterday's API catalog is *discovery*. If an agent has never heard of you, it does not know to look for your API catalog. Ask an agent what people have written about the future of Drupal, for example, and it will probably search Google. It may not think to check dri.es or drupal.org directly.

The web solved discovery decades ago. Search engines find the right site, so you do not have to know where the answer lives.

ARD brings search-engine-style discovery to AI agents. ARD registries crawl the web for catalogs published by sites and add their resources to a searchable index. An agent can then ask a registry a plain-language question, such as "Who can answer questions about the future of Drupal?". The registry returns a ranked list of relevant resources, perhaps pointing the agent to my site's search API.

You opt in by publishing a manifest at `/.well-known/ai-catalog.json`. Here is what my mine currently returns:

```json
{
  "specVersion": "1.0",
  "host": {
    "displayName": "Dries Buytaert"
  },
  "entries": [
    {
      "identifier": "urn:air:dri.es:search",
      "displayName": "Site search",
      "type": "application/openapi+json",
      "url": "https://dri.es/openapi.json",
      "description": "Full-text search across the site's content, ranked by relevance.",
      "representativeQueries": [
        "Find posts about the future of Drupal",
        "What has been written about open source sustainability?",
        "Find writing about digital sovereignty",
        "How is AI changing how we build websites?",
        "Search Dries Buytaert's blog and notes"
      ]
    }
  ]
}
```

Each entry describes a resource an agent can use. ARD deliberately defines "resource" broadly: it can be an API, an MCP server, another agent, a skill, or even a nested catalog containing more resources.

My site offers just one resource: a simple search API. The whole thing took less than an hour to implement because the ARD entry simply points to the existing OpenAPI document, [https://dri.es/openapi.json](https://dri.es/openapi.json), that I wrote about yesterday. In other words, it makes the same API description available through a second discovery mechanism.

The `representativeQueries` field is the interesting part. It lists example questions registries use to match an agent's intent. Mine are first guesses that I will revise once I can see how they get used.

Of the eleven companies listed as contributors, [Hugging Face](https://huggingface.co/) is the only one whose [AI catalog](https://huggingface.co/.well-known/ai-catalog.json) I could find on its primary domain. It also [runs an early registry](https://huggingface.co/blog/agentic-resource-discovery-launch). So I queried Hugging Face's registry. It responded correctly using the protocol defined by the specification, but for my queries, it returned only skills hosted by Hugging Face. 

Broad adoption will depend on whether major agents begin searching ARD registries. Microsoft, Google, and GitHub are members of the working group, but OpenAI and Anthropic are not. Google has said its [Agent Platform will connect to ARD registries](https://developers.googleblog.com/announcing-the-agentic-resource-discovery-specification/) in the coming months, but it remains to be seen how widely the specification will be adopted.

Does my blog need this? Probably not. Other sites have more to gain. An online store could announce its product search and checkout APIs, a restaurant its reservation system, and a city its appointment system for renewing a permit.

Many of these sites run on a content management system. A CMS that made its capabilities discoverable through ARD by default could therefore be interesting. Experiments like this help me understand whether [Drupal](https://www.drupal.org/) should be that CMS.

PS: Follow the discussion on [LinkedIn](https://www.linkedin.com/feed/update/urn:li:activity:7486197914839474176/).
