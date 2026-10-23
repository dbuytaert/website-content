---
url: 'https://dri.es/one-description-inside-and-outside-drupal'
title: 'One description, inside and outside Drupal'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2026-10-15T08:26:16-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'Every Drupal module should describe its data once, so AI assistants, front ends, workflow tools and other systems can use it. It could be a CCK and Views moment.'
tags:
  - Drupal
  - 'Workflow orchestration'
  - 'Artificial Intelligence'
  - 'My site'
image: blog/drupal-ai-advantage
discussions:
  - { platform: LinkedIn, url: 'https://www.linkedin.com/feed/update/urn:li:activity:7516521150189916161/' }
published: true
featured: true
id: 6341
---

# One description, inside and outside Drupal

![An astronaut explores a surreal landscape beneath rainbow-colored planetary rings, symbolizing the journey into AI's transformative potential for Drupal.](http://default/files/cache/blog/drupal-ai-advantage-640w.jpg)
*© Tithi Luadthong.*

My website has a custom photo album module that I've maintained for about twenty years. It helps me manage more than ten thousand photos. In [my DrupalCon Rotterdam keynote](https://dri.es/state-of-drupal-presentation-september-2026), I talked about making that module work with AI assistants. You can [watch that part of the keynote](https://www.youtube.com/watch?v=jrXnvVD8ryo&t=2361s). I didn't have time on stage to go into the details, so I'm doing that in this post.

To let assistants find and edit my photos, I used the contributed [Tool module](https://www.drupal.org/project/tool), which provides Tool API, to expose my module's operations as tools. These include finding photos and updating a photo's caption or alt text. 

Most of these tools are public methods on [Drupal services](https://www.drupal.org/docs/drupal-apis/services-and-dependency-injection/services-and-dependency-injection-in-drupal) I already had, like the one that searches my photos. A few PHP attributes are usually enough for Tool API to expose an existing method, so AI assistants can call it over MCP, the [Model Context Protocol](https://modelcontextprotocol.io/).

To describe a tool to other software, Tool API needs to know what data it accepts and returns: what each value is called, what type it is and what it means. 

My album module doesn't store photos as Drupal entities (I know, I know), so Drupal has no field definitions for them. Instead, it keeps them in its own database table and loads each photo into an instance of `Image`, a plain PHP class. I added PHP attributes to the getters for the properties I wanted to expose, like this one for the alt text:

```php
#[ToolProperty(description: 'Plain text describing the image for screen readers.', media_type: 'text/plain')]
public function getAlt(): string { 
  ... 
}
```

From attributes like this one, Tool API generates JSON Schema, a format for describing JSON data. MCP and [OpenAPI](https://www.openapis.org/what-is-openapi), a standard for describing HTTP APIs, both use this format. So do Drupal's [Single Directory Components](https://www.drupal.org/docs/develop/theming-drupal/using-single-directory-components), which use it to describe the data passed to reusable interface components. 

In my album module, I use the same descriptions of my photo data to tell AI assistants what my tools return, generate TypeScript types for a React app that searches my photos, and define the inputs for my Drupal components. 

The same tools also connect my site to various workflow systems. A workflow built with [ECA](https://www.drupal.org/project/eca), [FlowDrop](https://www.drupal.org/project/flowdrop), [Maestro](https://www.drupal.org/project/maestro), [n8n](https://n8n.io) or [Activepieces](https://www.activepieces.com) can call the same photo-search tool an AI assistant calls, without requiring a separate integration with my album module.

A module maintainer exposes an operation once, and several kinds of software can use it.

<svg class="diagram" viewBox="0 0 640 344" font-size="13" text-anchor="middle" role="img" aria-label="Image.php describes a photo once in PHP attributes. Tool API generates JSON Schema from them, which AI assistants, front ends, workflow systems and Drupal components all use.">
  <style>
  .diagram rect { fill: var(--background); stroke: var(--hair-strong); }
  .diagram .source rect { fill: var(--tint); }
  .diagram path { fill: none; stroke: var(--meta); }
  .diagram marker path { fill: var(--meta); stroke: none; }
  .diagram text { fill: var(--ink); }
  .diagram .title { font-size: 16px; }
  .diagram .examples { fill: var(--meta); font-size: 12px; }
</style>
  <marker id="arrow" viewBox="0 0 10 10" refX="10" refY="5" markerWidth="7" markerHeight="7" orient="auto">
  <path d="M0 0 10 5 0 10z"/>
</marker>

  <g class="source">
  <rect x=".5" y="21.5" width="180" height="74" rx="6"/>
  <text x="90.5" y="46" class="title">Image.php</text>
  <text x="90.5" y="66">Describes a photo once,<tspan x="90.5" dy="16">in PHP attributes</tspan></text>
  <rect x=".5" y="135.5" width="180" height="74" rx="6"/>
  <text x="90.5" y="160" class="title">Tool API</text>
  <text x="90.5" y="180">Generates JSON Schema<tspan x="90.5" dy="16">from those attributes</tspan></text>
</g>

  <g marker-end="url(#arrow)">
  <path d="M90.5 95.5V135"/>
  <path d="M180.5 172.5 250 37.5"/>
  <path d="M180.5 172.5 250 127.5"/>
  <path d="M180.5 172.5 250 217.5"/>
  <path d="M180.5 172.5 250 307.5"/>
</g>

  <rect x="250.5" y=".5" width="389" height="74" rx="6"/>
  <text x="445" y="25" class="title">AI assistants</text>
  <text x="445" y="45">Find, read and edit my photos over MCP</text>
  <text x="445" y="63" class="examples">Claude, or any other MCP client</text>

  <rect x="250.5" y="90.5" width="389" height="74" rx="6"/>
  <text x="445" y="115" class="title">Front ends</text>
  <text x="445" y="135">Search my photos with TypeScript types from OpenAPI</text>
  <text x="445" y="153" class="examples">React, Next.js, mobile apps</text>

  <rect x="250.5" y="180.5" width="389" height="74" rx="6"/>
  <text x="445" y="205" class="title">Workflow systems</text>
  <text x="445" y="225">Search my photos in workflows built without code</text>
  <text x="445" y="243" class="examples">ECA, FlowDrop, Maestro, Activepieces</text>

  <rect x="250.5" y="270.5" width="389" height="74" rx="6"/>
  <text x="445" y="295" class="title">Drupal components</text>
  <text x="445" y="315">Render my photos with props from a generated schema.json</text>
  <text x="445" y="333" class="examples">Single Directory Components, Drupal Canvas</text>
</svg><p />

This is why I said in my keynote that I believe the [Tool module](https://www.drupal.org/project/tool), built by [Michael Lander](https://www.drupal.org/u/michaellander) and team, is one of the most important modules in Drupal right now. A module's capabilities can become available to assistants, front ends and workflows without its maintainer having to build for each one separately. 

I think every Drupal module should work this way, which is why I featured it in my keynote and why I launched a broader effort around this called Rosetta.

The goal is for Drupal's own systems and software outside Drupal to work from shared descriptions of data and operations. Below, I'll walk through what I built and tested with my album module.

## Drupal needs shared descriptions of data and operations

More of the work on a site happens outside Drupal every year: in AI assistants, in front ends built with JavaScript frameworks, and in [orchestration platforms that connect Drupal to other systems](https://dri.es/drupal-role-in-agentic-workflows). As I explained in [AI and the great CMS unbundling](https://dri.es/ai-and-the-great-cms-unbundling), those systems still need the content management, governance and observability that Drupal already provides.

Drupal has entities, fields, permissions, revisions, workflows, content moderation and tens of thousands of contributed modules. But making a module's capabilities available to an assistant, a workflow or a front end still too often requires some integration work.

![Keynote slide titled "The capabilities are here, but access is still too hard".](http://default/files/cache/drupalcon-rotterdam-2026/drupal-capabilities-access-still-too-hard-640w.png)
*A slide from [my DrupalCon Rotterdam 2026 keynote](https://dri.es/state-of-drupal-presentation-september-2026): Drupal has the capabilities, but making them available to other software is still too hard.*

Installing a Drupal module should make its capabilities available to software already connected to a site: new tools for assistants, new operations for workflows, and new capabilities for front-end developers.

In my album module, I should only have to describe a photo once and implement photo search once, not write a separate integration for every assistant, front end or workflow system.

In Drupal, we already know why shared descriptions matter. When a site builder adds a field to a content type, Drupal stores a definition for it: its type, its label and whether it's required. Content editing forms, Views and JSON:API all reuse that definition. 

CCK, Drupal's Content Construction Kit, let site builders define a field once, and Drupal used that definition for the edit form, the display and the database. Views let them list, filter and sort data from any module that described its data. Rosetta is about extending that kind of reuse to more of a module's data and operations.

<p class="pullquote">Shared descriptions of data and operations could be Drupal's next CCK and Views moment.</p>

User interfaces also keep changing: web pages, then native mobile apps, then headless front ends, then chat, and now AI assistants and agents. I don't know what comes after agents. But if modules describe their data and operations, new interfaces can build on the capabilities we already have. The next interface reads the description and gets to work. That won't make Drupal immune to change, but it makes us fast to adapt, and fast to adapt helps us win.

The question then becomes how to make that practical for thousands of module maintainers. Tool API gives us a starting point, alongside years of work on Typed Data, Single Directory Components, JSON:API, Drupal Canvas Code Components, [Modeler API](https://www.drupal.org/project/modeler_api), and more. We need the people behind that work to help shape the approach, including whether Tool API, or parts of it, belongs in Drupal Core.

That's why I'm organizing the Rosetta Sprint: a few days for the people behind these projects to get together in person to compare the existing approaches, identify what is missing and agree on next steps with the relevant maintainers and Core committers.

## Describe existing data and expose functions as tools

Tool API supports two ways to define a tool: (1) you can write a dedicated plugin class that Drupal discovers as a tool, or (2) add PHP attributes to an existing public method on a class registered as a [Drupal service](https://www.drupal.org/docs/drupal-apis/services-and-dependency-injection/structure-of-a-service-file).

I started with a dedicated plugin class but ultimately switched to PHP attributes. Attribute support was still experimental when I started, and I helped improve Tool API as I used it ([#3583030](https://git.drupalcode.org/project/tool/-/work_items/3583030), [#3583031](https://git.drupalcode.org/project/tool/-/work_items/3583031), [#3583032](https://git.drupalcode.org/project/tool/-/work_items/3583032), [#3583041](https://git.drupalcode.org/project/tool/-/work_items/3583041), [#3583085](https://git.drupalcode.org/project/tool/-/work_items/3583085)). The [attribute support is now merged and available in Tool API's development version](https://git.drupalcode.org/project/tool/-/work_items/3518120). Dedicated plugin classes remain fully supported.

I'll show the basic pieces here rather than walk through a full tutorial. Here is how the method that searches my photos becomes the `find_images` tool, simplified a little:

```php
/**
 * Searches the images.
 *
 * @param string $query
 *   Words to look for in the title, caption or alt text.
 *
 * @return \Drupal\album\Image[]
 *   The matching images.
 */
#[ToolMethod(
  id: 'find_images',
  label: 'Find images',
  description: "Searches the site's images. …",
  operation: ToolOperation::Read,
  permission: 'access content',
)]
public function search(string $query): array {
  // The search code is unchanged.
}
```

The method body stays the same: it takes a search query and returns the matching images. The `#[ToolMethod]` attribute gives the tool its ID, label and description. It also declares that the operation reads data and that the caller needs the `access content` permission. The search code must still enforce any restrictions on which photos the caller can see.

Tool API reads the input's name and type, `query` and `string`, from the method signature. When type information is missing, Tool API tries to infer it from the method signature and docblock. Here, the `Image[]` return annotation tells Tool API that the array contains `Image` objects.

Knowing that the result is a list of `Image` objects doesn't tell other software which properties a photo has. I describe those with `#[ToolProperty]` attributes on the `Image` class's getters, like `getAlt()` above.

The attributes also explain what each property means. In PHP, a title, a caption and a URL can all be strings, but other software needs to know which is plain text, which contains HTML and which is a URL. I illustrated that distinction in the keynote:

<div class="large">
![Keynote slide titled "Three strings can mean three different things".](http://default/files/cache/drupalcon-rotterdam-2026/image-class-tool-attributes-640w.png)
*A slide from [my DrupalCon Rotterdam 2026 keynote](https://dri.es/state-of-drupal-presentation-september-2026): all three values have PHP's `string` type, but `#[ToolProperty]` attributes describe the title as plain text, the caption as HTML and the URL as a URI.*
</div>

Tool API only includes the photo properties I explicitly describe with `#[ToolProperty]`. The attribute can go on a public class property or a getter method. On `getUrl()`, it exposes the returned value as a photo property named `url`; it doesn't make the getter a callable tool.

Under the hood, Tool API uses [Drupal's Typed Data API](https://www.drupal.org/docs/develop/drupal-apis/typed-data-api/typed-data-api-overview) to represent these descriptions and can generate JSON Schema from them.

Drush, MCP, ECA, FlowDrop, Maestro and my album module's custom HTTP route can all call the same runner, `ToolRunner::run()`. That means the same permission checks and input validation apply whichever way a tool is called. The runner also distinguishes invalid input from denied access or an execution failure, so each integration doesn't have to work that out for itself.

As mentioned, PHP attributes aren't the only way to define a tool. A dedicated plugin class is a bit more verbose, but it has some advantages. For example, it doesn't have to live in the module it exposes. A separate module can define the tools and call the original module's services and APIs, with no changes to its code. [Tool Belt](https://www.drupal.org/project/tool_belt) currently takes that separate-module approach for Drupal Core operations, like creating content and updating fields. That means we can add tool support for existing modules without waiting for their maintainers to adopt Tool API.

If you maintain a module, try exposing one useful operation as a tool. If you get stuck, or Tool API can't describe the data you need, [open an issue](https://www.drupal.org/project/issues/tool). Your feedback can help us improve Tool API before its first stable 1.x release. Tool API is still young, so you can help shape it. 

## AI assistants can handle complex tasks without developers

I actually started with search. A while ago, I exposed my blog's search to AI agents and wrote about it several times: as an [MCP tool](https://dri.es/helping-agents-discover-my-site-search-with-mcp), through an [API catalog](https://dri.es/helping-agents-discover-my-site-search-with-an-api-catalog) and with [Agentic Resource Discovery](https://dri.es/helping-agents-discover-my-site-search-with-agentic-resource-discovery). That code started out custom, but I've since updated it to use Tool API as well.

Later, I added the album tools. My album module provides seven. The ones I use most are `find_images` and `get_image`, which find and read photos, and `update_image`, which changes a photo's title, caption or alt text. 

I've used these tools to write titles and alt text for whole albums. Here are a few other things I ask an assistant to do:

- Find every photo that still has no alt text, across all albums, and suggest alt text for me to review.
- Find typos or grammar issues in my captions.
- List the photos in an album that have no title, and suggest titles for me to review.

The album tools and `find_posts` often work together. If I have an album from a trip and a blog post about the same trip, an AI assistant can call `find_posts` while it writes alt text for the album's photos, and use the post as context. It picks up details such as where we went, who was there and what the trip was for. The alt text gets better, without me having to point the assistant at the post.

My album module's admin screens can't do any of these tasks quickly, and some tasks have no screen at all. Before these tools, I either had to run SQL queries on the database or didn't do the task at all. To fix missing alt text, I'd query for the photos without it, then open each photo's edit screen in a browser. Updating dozens of images that way gets tedious.

Now an assistant finds the photos and drafts the alt text, and I review and approve its suggestions in Claude. It's at least 10 times faster than my old workflow.

I've been writing SQL for nearly 30 years, so I could always do these jobs myself. Many site owners can't. They ask a developer for help, or the job never gets done. Tools can remove that dependency. Photos are just my example. Any operation a module exposes as a tool becomes something a site owner can ask for directly, without waiting for a developer.

## AI assistants can handle complex tasks without dedicated UIs

When an assistant calls `get_image`, it gets the photo's properties and the photo itself, so it can see what it's describing. In Claude, an interface I built also displays the photo in the chat. It uses [MCP Apps](https://modelcontextprotocol.io/extensions/apps/overview), an MCP extension that lets a server provide an HTML interface the client renders in the conversation.

https://www.youtube.com/watch?v=z_l4ZYLCCOw

Every module has tasks that are too rare or too specific to justify a screen of their own. A maintainer can build screens for everyday work and make rare or specialized tasks available through tools. I've already removed parts of my album module's interface, like the button that generated alt text with a language model, because an assistant now does that job. I expect to remove more.

Shared descriptions can also make it easier to tailor interfaces to the people using them. Tool API can already generate a form from a tool's inputs and apply the same validation constraints when the tool is called without a form. Michael Lander is exploring this further in his [Data Surface prototype](https://github.com/mlander/data_surface), where forms and tools use the same definitions of accepted values and validation rules.

An organization could build admin screens around its own workflow while reusing those definitions and validation rules. With the right prompting, assistants can already build interfaces around these tools. For a batch of photo updates, that could be a table of images and proposed alt text where I can review and approve the changes. Over time, I expect assistants to recognize when an interface would help with a task and build one without being asked.

Michael's work builds on Drupal's configuration validation, and it is a good example of what I mean when I say [Drupal has an accidental AI advantage](https://dri.es/why-drupal-is-built-for-the-ai-era). Wim Leers began [advocating for configuration validation](https://wimleers.com/talk/config-validation) in 2022. AI wasn't part of his case. Years later, Michael can reuse those validation constraints to power forms and tools from one definition, and in [Validation-first](https://wimleers.com/validation-first), Wim describes how the same precision helps AI tools generate valid Drupal Canvas code components. 

## JavaScript front ends can use the same tools as AI assistants

But that is not all. With my album data and operations described, I decided to make the same data and tools available to front-end developers. I wrote two pieces of connecting code: a shared HTTP route that calls read-only tools, and a generator that produces an OpenAPI document from their definitions. Together, they take under 150 lines of PHP.

The route uses the URL to identify the tool and the query string to supply its arguments. For example, a request to [`/api/find-images?query=ski`](https://dri.es/api/find-images?query=ski) calls `find_images` with `ski` as its query and returns the result as JSON. I didn't write another photo search or a separate route for each tool.

The auto-generated OpenAPI document, available at [https://dri.es/openapi.json](https://dri.es/openapi.json), describes those endpoints, their parameters and their responses. It uses the same `#[ToolMethod]` and `#[ToolProperty]` attributes the MCP tools use.

OpenAPI is a 15-year-old standard for describing HTTP APIs, so it's supported by many developer tools. [Swagger UI](https://swagger.io/tools/swagger-ui/), for example, lists my endpoints and lets you try them. This video shows the document, then Swagger UI reading it and calling the API for "driesnote":

https://www.youtube.com/watch?v=lFNiD6nlgp0

Many front-end developers use TypeScript, which adds static types to JavaScript. A type can describe an image as an object with a string `alt` and a string `title`. The TypeScript compiler checks the code against those types before it runs, and editors like [VS Code](https://en.wikipedia.org/wiki/Visual_Studio_Code) show type errors as you write. 

To see what this gives a front-end developer, I asked Claude Code to build a small React app that searches my photos from the browser. The app knows nothing about Drupal, and building it didn't require any Drupal knowledge either. All Claude Code had was my site's URL and its generated OpenAPI document.

I'm not a front-end developer, so it was interesting to watch. Claude used a code generator called [openapi-typescript](https://openapi-ts.dev/introduction) to turn my OpenAPI document into TypeScript types in under a second. A small library called [openapi-fetch](https://openapi-ts.dev/openapi-fetch/) then uses those types, so the compiler can check the request paths and parameters in the app's code.

The whole app is a single React component of 45 lines, and I wrote no additional Drupal code for it. In this video, it searches for "driesnote":

https://www.youtube.com/watch?v=dPzySZ6AONc

The HTTP route and OpenAPI generator are prototype code on my site. Nothing in them is specific to photos, so they shouldn't be something each site or module has to write. They belong in shared infrastructure that works for any module's tools. JSON-RPC is one place that could happen: if [JSON-RPC](https://www.drupal.org/project/jsonrpc) supported Tool API, it could expose tools from other modules without each module writing its own JSON-RPC integration.

## Workflows can call module operations as tools

Inside Drupal, [ECA](https://www.drupal.org/project/eca), [FlowDrop](https://www.drupal.org/project/flowdrop) and [Maestro](https://www.drupal.org/project/maestro) can call tools as steps in a workflow. The [ECA Tool](https://www.drupal.org/project/eca_tool) module, for example, makes tools available as ECA actions.

In the keynote, Shibin Das showed a FlowDrop workflow he built with my album module's tools. It searches my photos and lists my albums, first without any AI, then with an agent that decides which tools to use:

https://www.youtube.com/watch?v=7CnZd63-JWg

Workflow systems can also expose tools of their own. ECA calls its workflows "models", and the ECA Tool module exposes each Tool event in a model as a separate tool. One model can therefore offer several tools. Maestro can expose public workflow templates as tools, using their variables as inputs.

A workflow that is also a tool can be used like any other tool. A Maestro workflow can call a tool exposed by ECA, through the same Tool API integration it uses to call my photo search. Neither system needed a direct integration with the other. I still find that a little hard to get my head around, but I love it and see the potential.

Automation platforms outside Drupal need a way to call those tools too. Last year, Jürgen Haas and I built the [Orchestration module](https://www.drupal.org/project/orchestration) to connect Drupal with Activepieces. It lets Activepieces call tools defined through Tool API, run AI agents and trigger ECA models, while events in Drupal can trigger workflows in Activepieces. I described that setup in [Connecting Drupal with Activepieces](https://dri.es/connecting-drupal-with-activepieces). Other platforms can call Drupal's tools over MCP, for example through [n8n's MCP Client node](https://docs.n8n.io/integrations/builtin/core-nodes/n8n-nodes-langchain.mcpClient).

Tools compose. An assistant can combine them in a single task, a workflow can chain them, and a workflow can be one of the tools in another workflow. Once a system can call Drupal's tools, it can reuse that connection for operations from different modules.

That is the [orchestration shift](https://dri.es/the-orchestration-shift): a stack becomes a network, and workflows coordinate work across applications. Drupal can be a node in that network, with its modules offering operations that other systems can call. For [agencies building those workflows](https://dri.es/ai-and-the-great-digital-agency-unbundling), Tool API makes Drupal's capabilities available as reusable steps.

## Drupal components can share data descriptions

So shared descriptions help JavaScript front ends and other applications use Drupal's data, but they can also help Drupal's own rendering system, even when no AI assistant or external application is involved.

My photos are rendered using [Single Directory Components](https://www.drupal.org/docs/develop/theming-drupal/using-single-directory-components), or SDCs. Each component keeps its [Twig template](https://twig.symfony.com/), CSS and metadata in one folder. Its `.component.yml` file declares the component's inputs, called props, and describes the data they accept.

My album module already describes a photo's properties with `#[ToolProperty]` attributes. I was also maintaining descriptions of those same properties in each photo component's `.component.yml` file. When I changed what a photo property contained, I had to remember to update both descriptions.

So I wrote a [Drush](https://www.drush.org) command that reads the PHP attributes and generates a shared `schema.json` file. My album module's [generated photo schema](https://dri.es/modules/custom/album/schema.json) describes properties such as `alt` and `caption`: their types and what they contain. Each photo component's `.component.yml` file now references that shared description instead of describing those properties again. When I change what a photo property contains, I update its PHP attribute and run the command.

Moving the descriptions into a shared file creates a new problem. Anything that reads a component's `.component.yml` now finds a reference to `schema.json`, not the property definitions. A tool that builds a component catalog, showing what data each component expects, has to find and resolve that reference itself. Core's component API doesn't do it for them: it returns the reference without the photo's property definitions.

Pierre Dureau's merge request in [Core issue 3352063](https://www.drupal.org/project/drupal/issues/3352063) addresses that gap, though it isn't merged yet. With it applied on my site, Core's component API followed the reference and loaded the photo property definitions, without any changes to the schema file.

That matters for generative UI. Frameworks like [OpenUI](https://www.openui.com) and [A2UI](https://a2ui.org) let an AI agent assemble an interface from a catalog of components, so they need to know which components exist and what props each one accepts. With this change, an integration could build that catalog from Drupal's API instead of writing its own reference resolver. Tools that read the component files directly still need to learn to follow these references. The SDC add-on for [Storybook](https://storybook.js.org/docs), a tool for developing and previewing components, doesn't yet follow the Drupal-specific references I use.

The same goes for the generator. Other module maintainers shouldn't each have to write one like mine. My experiment uses Tool API's property descriptions, but describing data and generating schemas are useful beyond tools. Some of that support could belong in Drupal Core, benefiting both SDC and the [Icon API](https://www.drupal.org/docs/develop/drupal-apis/icon-api), which uses JSON Schema to describe icon settings such as size and color.

My approach only covers components built to render my module's photos. General-purpose components define their own inputs and still need a way to get Drupal's data. Drupal describes entity fields with [Typed Data](https://www.drupal.org/node/1794140), while SDC describes props with JSON Schema. [UI Patterns](https://www.drupal.org/project/ui_patterns) already handles much of the work between them, including which data sources can supply a prop. Rosetta should build on that work too.

## Make shared descriptions standard practice

The same photo descriptions and operations now support AI assistants, a React app, workflows inside and outside Drupal, and Drupal components.

I want more module maintainers to adopt Tool API: describe their modules' data once and expose useful operations as tools. That should become a normal part of developing and maintaining a Drupal module.

We should also provide the HTTP integration, OpenAPI generator and component schema generator as shared Drupal infrastructure. Module maintainers shouldn't each have to write that connecting code.

My prototypes show this working for one module. Rosetta is about making that reuse work across Drupal. We need to work with the relevant maintainers and Core committers to decide what belongs in Tool API, its integrations and Drupal Core.

If you maintain a module, try exposing one useful operation as a tool and using it with another system. Share what worked, and [open an issue](https://www.drupal.org/project/issues/tool) when you find something Tool API can't describe or do. 

*Thanks to [Jamie Abrahams](https://www.drupal.org/u/yautja_cetanu), [Mateu Aguiló Bosch](https://www.drupal.org/u/e0ipso), [Ronald te Brake](https://www.drupal.org/u/ronaldtebrake), [Shibin Das](https://www.drupal.org/u/d34dman), [Pierre Dureau](https://www.drupal.org/u/pdureau), [Matt Glaman](https://www.drupal.org/u/mglaman), [Jürgen Haas](https://www.drupal.org/u/jurgenhaas), [Marcus Johansson](https://www.drupal.org/u/marcus_johansson), [Randy Kolenko](https://www.drupal.org/u/_randy), [Michael Lander](https://www.drupal.org/u/michaellander), and [Fons Vandamme](https://www.drupal.org/u/f0ns) for reviewing this post.*

PS: Follow the discussion on [LinkedIn](https://www.linkedin.com/feed/update/urn:li:activity:7516521150189916161/).
