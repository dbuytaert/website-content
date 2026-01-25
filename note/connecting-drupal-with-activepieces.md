---
url: 'https://dri.es/connecting-drupal-with-activepieces'
title: 'Connecting Drupal with Activepieces'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2025-11-07T04:44:00-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: note
tags:
  - Drupal
  - Activepieces
  - Automation
published: true
featured: false
id: 5931
---

# Connecting Drupal with Activepieces

[Activepieces](https://www.activepieces.com/) is an open source workflow automation platform, similar to [Zapier](https://zapier.com/) or [n8n](https://n8n.io/). It connects different systems so they can work together in automated workflows. For example, you might create a workflow where publishing a [Drupal](https://www.drupal.org/) article automatically creates a social media post, updates a Google Sheet, and notifies your team in Slack.

There are two main ways to run Activepieces:

- **Activepieces Cloud**: The easiest option for production use or for evaluating Activepieces.  The limitation is that it cannot reach Drupal sites running on your localhost.

- **Run Activepieces locally**: Useful when you are developing or testing Drupal integrations.  There are two ways to do this:
  
  1. **Docker environment**: If you are developing Drupal sites locally with tools like [DDEV](https://ddev.com/), the easiest option is to run Activepieces locally using Docker so both can communicate easily.  See [running Activepieces locally with Docker](https://dri.es/running-activepieces-locally-with-docker).
  
  2. **Development environment**: If you want to modify the Activepieces codebase or contribute to the [Drupal Piece](https://www.activepieces.com/pieces/drupal), you will need the full development toolchain.  See [setting up the Activepieces development environment](https://dri.es/setting-up-an-activepieces-development-environment).

Once you have Activepieces running, you'll want to connect it to your Drupal site. This note explains two ways to do that: a basic integration using Drupal's built-in APIs, and an advanced setup that unlocks deeper automation capabilities.

### Setting up basic integration

You can connect Drupal with Activepieces without installing any extra Drupal modules.

Drupal ships with [JSON:API](https://jsonapi.org/) support, a REST API that exposes your content and data through HTTP requests. This means Activepieces can query your content, fetch individual nodes, explore field definitions, and follow entity relationships without any custom code.

While JSON:API is part of Drupal Core, it may not be enabled yet. You can enable it with:

```bash
drush pm-enable jsonapi -y 
```

Next, set up a dedicated Drupal user account with only the permissions needed for what you want Activepieces to do. 

Activepieces can use [Basic Authentication](https://en.wikipedia.org/wiki/Basic_access_authentication) to connect to Drupal with the corresponding username and password. 

Basic Auth sends credentials with each request, which makes it simple to set up. For production environments, I recommend using a more secure authentication method like [OAuth](https://en.wikipedia.org/wiki/OAuth), though I have not tried that yet.

Drupal Core comes with a Basic Auth module, but you might also need to enable it:

```bash
drush pm-enable basic_auth -y
```

Once both modules are enabled, you can create a connection to Drupal from within Activepieces.  In the Activepieces interface, drag a Drupal trigger or action onto the canvas, and you'll be prompted to set up the connection.

### Setting up advanced integration

For more advanced scenarios, we created the [Orchestration module](https://www.drupal.org/project/orchestration). It's an optional module.  Installing this module unlocks deeper integrations that enable external systems to trigger [Drupal ECA workflows](https://www.drupal.org/project/eca), use [Drupal AI agents](https://www.drupal.org/project/ai), call [Drupal Tools](https://www.drupal.org/project/tool), and more.

The module is organized using specialized submodules, each connecting to a different part of Drupal's ecosystem. You can pick and choose the capabilities you want to use. 

For starters, here is how to install the Drupal AI and ECA integrations:

```bash
composer require drupal/orchestration drupal/ai drupal/ai_agents drupal/tool drupal/eca
drush pm-enable ai ai_agents tool eca orchestration_ai_agents orchestration_ai_function orchestration_tool orchestration_eca -y
```

Before you can use any of the AI agents, you also need to install and configure one or more AI providers:

```bash
composer require drupal/ai_provider_anthropic drupal/ai_provider_openai drupal/ai_provider_ollama
drush pm-enable ai_provider_anthropic ai_provider_openai ai_provider_ollama -y
```

Clear the cache: 

```bash
drush cache-rebuild
```

With these modules installed, you can build much more sophisticated workflows that leverage Drupal's internal automation and AI capabilities.
