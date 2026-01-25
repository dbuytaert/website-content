---
url: 'https://dri.es/an-update-on-the-workflow-initiative-for-drupal-8-4-8-5'
title: 'An update on the Workflow Initiative for Drupal 8.4/8.5'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2017-11-22T09:57:47-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'Want to know what has been happening with the Workflow Initiative in Drupal? Read my update.'
tags:
  - Drupal
  - 'Workflow initiative'
image: drupal/drupal-8-workspaces-prototype-november-2017
published: true
id: 4081
---

# An update on the Workflow Initiative for Drupal 8.4/8.5

Over the past weeks I have shared [an update on the Media Initiative](https://dri.es/an-update-on-the-media-initiative-for-drupal-8-4-8-5) and [an update on the Layout Initiative](https://dri.es/an-update-on-the-layout-initiative-for-drupal-8-4-8-5). Today I wanted to give an update on the Workflow Initiative.

Creating great software doesn't happen overnight; it requires a desire for excellence and a disciplined approach. Like the Media and Layout Initiatives, the Workflow Initiative has taken such an approach. The disciplined and steady progress these initiative are making is something to be excited about.

### 8.4: The march towards stability

As you might recall from [my last Workflow Initiative update](https://dri.es/moving-the-drupal-8-workflow-initiative-along), we added the Content Moderation module to Drupal 8.2 as an experimental module, and we added the Workflows module in Drupal 8.3 as well. The Workflows module allows for the creation of different publishing workflows with various states (e.g. draft, needs legal review, needs copy-editing, etc) and the Content Moderation module exposes these workflows to content authors.

As of Drupal 8.4, [the Workflows module has been marked stable](https://www.drupal.org/node/2897130). Additionally, the Content Moderation module is marked beta in Drupal 8.4, and is down to [two final blockers](https://www.drupal.org/node/2897132) before marking stable. If you want to help with that, [check out the Content Moderation module roadmap](https://www.drupal.org/node/2755073).

### 8.4: Making more entity types revisionable

To advance Drupal's workflow capabilities, more of Drupal's entity types needed to be made "revisionable". When content is revisionable, it becomes easier to move it through different workflow states or to stage content. Making more entity types revisionable is a necessary foundation for better content moderation, workflow and staging capabilities. But it was also hard work and took various people over a year of iterations – we worked on this throughout the Drupal 8.3 and Drupal 8.4 development cycle.

When working through this, we discovered various adjacent bugs (e.g. bugs related to content revisions and translations) that had to be worked through as well. As a plus, this has led to a more stable and reliable Drupal, even for those who don't use any of the workflow modules. This is a testament to our desire for excellence and disciplined approach.

### 8.5+: Looking forward to workspaces

While these foundational improvements in Drupal 8.3 and Drupal 8.4 are absolutely necessary to enable better content moderation and content staging functionality, they don't have much to show for in terms of user experience changes. Now a lot of this work is behind us, the Workflow Initiative changed its focus to stabilizing the Content Moderation module, but is also aiming to bring the [Workspace module](https://www.drupal.org/project/workspace) into [Drupal core as an experimental module](https://www.drupal.org/node/2784921).

The Workspace module allows the creation of multiple environments, such as "Staging" or "Production", and allows moving collections of content between them. For example, the "Production" workspace is what visitors see when they visit your site. Then you might have a protected "Staging" workspace where content editors prepare new content before it's pushed to the Production workspace.

While workflows for individual content items are powerful, many sites want to publish multiple content items at once as a group. This includes new pages, updated pages, but also changes to blocks and menu items – hence our focus on making things like block content and menu items revisionable. 'Workspaces' group all these individual elements (pages, blocks and menus) into a logical package, so they can be prepared, previewed and published as a group. This is one of the most requested features and will be a valuable differentiator for Drupal. It looks pretty slick too:

[image drupal/drupal-8-workspaces-prototype-november-2017 resize=false]

I'm impressed with the work the Workflow team has accomplished during the Drupal 8.4 cycle: the Workflow module became stable, the Content Moderation module improved by leaps and bounds, and the under-the-hood work has prepared us for content staging via Workspaces. In the process, we've also fixed some long-standing technical debt in the revisions and translations systems, laying the foundation for future improvements.

*Special thanks to [Angie Byron](https://www.drupal.org/u/webchick) for contributions to this blog post and to [Dick Olsson](https://www.drupal.org/u/dixon_), [Tim Millwood](https://www.drupal.org/u/timmillwood) and [Jozef Toth](https://www.drupal.org/u/jojototh) for their feedback during the writing process.*
