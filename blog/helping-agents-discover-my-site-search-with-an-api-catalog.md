---
url: 'https://dri.es/helping-agents-discover-my-site-search-with-an-api-catalog'
title: 'Helping agents discover my site search with an API Catalog'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2026-07-22T10:22:42-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'I added /.well-known/api-catalog support to dri.es so AI agents can discover my search API and search my site efficiently.'
tags:
  - 'Artificial Intelligence'
  - 'My site'
discussions:
  - { platform: LinkedIn, url: 'https://www.linkedin.com/feed/update/urn:li:activity:7485718495020818432/' }
published: true
featured: false
id: 6276
---

# Helping agents discover my site search with an API Catalog

I kept running into the same small frustration. My site has its own search, but when I ask an AI agent whether I have written about a topic before, it searches Google instead of using my site's search directly. As a result, it often misses relevant posts that Google has not indexed.

At the same time, the web is gaining a new audience. In addition to people visiting pages, AI agents increasingly access a site's knowledge and tools directly.

That combination led me to add support for `/.well-known/api-catalog` to my site. A request to [https://dri.es/.well-known/api-catalog](https://dri.es/.well-known/api-catalog) currently returns:

```json
{
  "linkset": [
    {
      "anchor": "https://dri.es/search/json",
      "service-desc": [
        {
          "href": "https://dri.es/openapi.json",
          "type": "application/openapi+json"
        }
      ]
    }
  ]
}
```

[RFC 9727](https://www.rfc-editor.org/rfc/rfc9727), an IETF Proposed Standard, defines `/.well-known/api-catalog` as a predictable location for discovering a site's public APIs.

The catalog is a small JSON document written in the [Linkset](https://www.rfc-editor.org/rfc/rfc9264) format. It advertises my search endpoint and, in turn, links to an [OpenAPI](https://www.openapis.org/) document that tells software how to use it.

The JSON endpoint at `/search/json` predates the catalog and powers my site's search. However, it was not documented or easy for software to discover. The catalog now makes it explicit.

The OpenAPI document at [https://dri.es/openapi.json](https://dri.es/openapi.json) tells AI agents exactly how to call the endpoint and interpret the results. It removes the guesswork, reducing the time and tokens agents would otherwise spend [figuring out how the API works](https://dri.es/friction-abstraction-and-verification).

In short, the API catalog announces that my search API exists, while the OpenAPI document explains how to use it. An agent can start with just my domain, check `/.well-known/api-catalog`, follow the link to the OpenAPI document, and learn how to search dri.es directly.

The feature has been live for a few months, but I am only now writing about it. In the meantime, I have logged every request to `/.well-known/api-catalog` and `/openapi.json`. The result so far: zero AI agents have used it.

I found the same problem when I [analyzed `llms.txt` usage](https://dri.es/markdown-llms-txt-and-ai-crawlers): the AI crawlers it was meant for never use it, so I never bothered implementing it.

Unlike `llms.txt`, the API catalog solves a problem I have, and I do not need to wait for industry adoption. I recently created an [Agent Skill](https://agentskills.io/specification), a `SKILL.md` file that directs my agents to check the catalog and use my site's search API whenever they need information from dri.es.

My agents now search dri.es directly and find posts that Google misses. And if any AI agent adopts API catalog discovery, my site is ready.

PS: Follow the discussion on [LinkedIn](https://www.linkedin.com/feed/update/urn:li:activity:7485718495020818432/).
