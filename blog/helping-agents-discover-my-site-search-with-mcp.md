---
url: 'https://dri.es/helping-agents-discover-my-site-search-with-mcp'
title: 'Helping agents discover my site search with MCP'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2026-08-04T11:01:09-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: "MCP's new stateless protocol let me expose my site's search as an agent tool in fewer than 150 lines of custom PHP."
tags:
  - 'Artificial Intelligence'
  - 'My site'
discussions:
  - { platform: LinkedIn, url: 'https://www.linkedin.com/feed/update/urn:li:share:7490426794232348672' }
published: true
featured: false
id: 6296
---

# Helping agents discover my site search with MCP

This is the third post in a series about making my site's search available to AI agents. First, I published an [API Catalog](https://dri.es/helping-agents-discover-my-site-search-with-an-api-catalog), which helps agents that already know to check my site find its search API. Second, I added an [Agentic Resource Discovery](https://dri.es/helping-agents-discover-my-site-search-with-agentic-resource-discovery) (ARD) entry so my search can be indexed by "AI registries" (think search engines for AI agents).

So far, no agent has found my search on its own. The API Catalog has been a [published IETF standard](https://datatracker.ietf.org/doc/html/rfc9727) for over a year but I found no evidence that either OpenAI or Anthropic checks for it. ARD is newer, still a [v0.9 draft](https://agenticresourcediscovery.org/spec/), and I found no evidence that OpenAI or Anthropic supports it either.

In the meantime, what does work is a custom Agent Skill that points my AI assistants to the API Catalog, which leads them to [my OpenAPI description](https://dri.es/openapi.json) and from there to the search itself. If and when agents adopt one or more of these discovery standards, I might be able to drop the skill and have it all work automagically.

Until last week, I had decided [Model Context Protocol](https://modelcontextprotocol.io/) (MCP) was not worth implementing for my search API endpoint. It required an initialization handshake and could involve protocol-level sessions. My search doesn't need either: every query is stateless and anonymous. MCP felt like overkill for my simple use case.

The [2026-07-28 revision](https://modelcontextprotocol.io/specification/2026-07-28/changelog) changed my mind because both the protocol-level session and the initialization handshake are gone. Every request can now be self-contained, which means that, for a service like mine, an MCP server is basically a POST route that returns JSON.

So I went ahead and implemented MCP support for my search endpoint. The whole thing came to one route and three small RPC methods: fewer than 150 lines of code, excluding tests.

## You can call it from any terminal

In my testing, adding my site as a custom MCP connector to Claude Desktop, Claude Code, or ChatGPT still fails. These clients don't support the new protocol yet, which is understandable because it is only a week old. Once they catch up, anyone will be able to add dri.es as a connector, not just me.

Until then, an easy way to talk to my site with an MCP client is Simon Willison's [mcp-explorer](https://github.com/simonw/mcp-explorer). You can run it with `uvx`, which comes with [`uv`](https://docs.astral.sh/uv/):

```bash
uvx mcp-explorer list https://dri.es/mcp
uvx mcp-explorer call https://dri.es/mcp search -a q "open source"
```

The first command prints the tool's name, description, and arguments. The second runs a search across my posts and returns up to twenty results.

Alternatively, you can use the raw protocol by running this `curl` command from a terminal:

```bash
curl -s https://dri.es/mcp \
  -H "Content-Type: application/json" \
  -H "MCP-Protocol-Version: 2026-07-28" \
  -H "Mcp-Method: tools/call" \
  -H "Mcp-Name: search" \
  -d '{"jsonrpc":"2.0","id":1,"method":"tools/call","params":{"name":"search","arguments":{"q":"open source"},"_meta":{"io.modelcontextprotocol/protocolVersion":"2026-07-28"}}}' \
  | jq .result.structuredContent
```

## Discovery and invocation are separate layers

Having implemented support for three new standards, the useful thing I learned is that they are not alternatives.

ARD handles discovery: it gives registries a standard way to index and search for services like mine. OpenAPI and MCP handle invocation by defining how agents can call and use those services.

So the choice is not ARD or MCP. It is ARD plus OpenAPI, or ARD plus MCP.

For an anonymous, read-only API like mine, I prefer OpenAPI. It was easier to implement and anything that can make an HTTP request can use it.

MCP becomes more attractive when you have services that involve multi-step interactions, authentication, or explicit application state.

Ultimately, agent and crawler adoption will decide. Time will tell, but my money is on ARD and MCP right now.

PS: Follow the discussion on [LinkedIn](https://www.linkedin.com/feed/update/urn:li:share:7490426794232348672).
