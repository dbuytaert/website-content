---
url: 'https://dri.es/improving-drupal-content-workflow'
title: "Improving Drupal's content workflow"
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2016-04-04T14:38:37-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: "Why we should start a Drupal 8 initiative to improve Drupal's content workflow capabilities"
tags:
  - Drupal
  - 'Workflow initiative'
published: true
id: 3631
---

# Improving Drupal's content workflow

At [DrupalCon Mumbai](https://dri.es/state-of-drupal-presentation-february-2016) I sat down for several hours with the Drupal team at Pfizer to understand the work they have been doing on improving Drupal content management features. They built a set of foundational modules that help advance Drupal's content workflow capabilities; from content staging, to multi-site content staging, to better auditability, offline support, and several key user experience improvements like full-site preview, and more. In this post, I want to point a spotlight on some of Pfizer's modules, and kick-off an initial discussion around the usefulness of including some of these features in core.

### Use cases

Before jumping to the technical details, let's talk a bit more about the problems these modules are solving.

1. **Cross-site content staging** – In this case you want to synchronize content from one site to another. The first site may be a staging site where content editors make changes. The second site may be the live production site. Changes are previewed on the stage site and then pushed to the production site. More complex workflows could involve multiple staging environments like multiple sites publishing into a single master site.
2. **Content branching** – For a new product launch you might want to prepare a version of your site with a new section on the site featuring the new product. The new section would introduce several new pages, updates to existing pages, and new menu items. You want to be able to build out the updated version in a self-contained 'branch' and merge all the changes as a whole when the product is ready to launch. In an election case scenario, you might want to prepare multiple sections; one for each candidate that could win.
3. **Preview your site** – When you're building out a new section on your site for launch, you want to preview your entire site, as it will look on the day it goes live. This is effectively content staging on a single site.
4. **Offline browse and publish** – Here is a use-case that Pfizer is trying to solve. A sales rep goes to a hospital and needs access to information when there is no wi-fi or a slow connection. The site should be fully functional in offline mode and any changes or forms submitted, should automatically sync and resolve conflicts when the connection is restored.
5. **Content recovery** – Even with confirmation dialogs, people delete things they didn't want to delete. This case is about giving users the ability to "undelete" or recover content that has been deleted from their database.
6. **Audit logs** – For compliance reasons, some organizations need all content revisions to be logged, with the ability to review content that has been deleted and connect each action to a specific user so that employees are accountable for their actions in the CMS.

### Technical details

All these use cases share a few key traits:

1. Content needs to be synchronized from one place to another, e.g. from workspace to workspace, from site to site or from frontend to backend
2. Full revision history needs to be kept
3. Content revision conflicts needs to be tracked

Much of this started as a single module: [Deploy](https://www.drupal.org/project/deploy). The Deploy module was first created by [Greg Dunlap](https://www.drupal.org/u/gdd) for Drupal 6 in 2008 for a customer of [Palantir](https://www.palantir.net). In 2012, Greg handed over maintainership to [Dick Olsson](https://www.drupal.org/u/dixon_). Dick continued to improve Deploy module for Al Jazeera while working at [Node One](http://www.wunderkraut.com). Later, [Dave Hall](https://www.drupal.org/u/skwashd) created a second Drupal 7 version which more significant improvements based on feedback from different users. Today, both Dick and Dave work for Pfizer and have continued to include lessons learned in the Drupal 8 version of the module. After years of experience working on Deploy module and various redesigns, the team has extracted the functionality in a set of modules:

- [Deploy](https://www.drupal.org/project/deploy)
- [Multiversion](https://www.drupal.org/project/multiversion)
- [Replication](https://www.drupal.org/project/replication)
- [Workspace](https://www.drupal.org/project/workspace)
- [RELAXed Web Services](https://www.drupal.org/project/relaxed)
- [Trash](https://www.drupal.org/project/trash)

[image blog/pfizer-content-workflow-improvements-modules]

#### Multiversion

This module does three things: (1) it adds revision support for all content entities in Drupal, not just nodes and block content as provided by core, and (2) it introduces the concept of parent revisions so you can create different branches of your content or site, and (3) it keeps track of conflicts in the revision tree (e.g. when two revisions share the same parent). Many of these features complement the [ongoing improvements to Drupal's Entity API](https://www.drupal.org/node/2635070).

#### Replication

Built on top of Multiversion module, this lightweight module reads revision information stored by Multiversion, and uses that to determine what revisions are missing from a given location and lets you replicate content between a source and a target location. The next two modules, Workspace and RELAXed Web Services depend on replication module.

#### Workspace

This module enables single site content staging and full-site previews. The UI lets you create workspaces and switch between them. With Replication module different workspaces on the same site can behave like different editorial environments.

#### RELAXed Web Services

This module facilitates cross-site content staging. It provides a more extensive REST API for Drupal with support for UUIDs, translations, file attachments and parent revisions – all important to solve unique challenges with content staging (e.g. UUID and revision information is needed to resolve merge conflicts). The RELAXed Web Services module extends the Replication module and makes it possible to replicate content from local workspaces to workspaces on remote sites using this API.

In short, Multiversion provides the "storage plumbing", whereas Replication, Workspace, and RELAXed Web Services, provide the "transport plumbing".

#### Deploy

Historically Deploy module has taken care of everything from bottom to top related to content staging. But for Drupal 8 Deploy has been rewritten to just provide a UI on-top of the Workspace and Replication modules. This UI lets you manage content deployments between workspaces on a single site, or between workspaces across sites (if used together with RELAXed Web Services module). The maintainers of the Deploy module have put together a marketing site with more details on what it does: <http://www.drupaldeploy.org>.

#### Trash

To handle use case #5 (content recovery) the Trash module was implemented to restore entities marked as deleted. Much like a desktop trash or recycle bin, the module displays all entities from all supported content types where the default revision is flagged as deleted. Restoring creates a newer revision, which is not flagged as deleted.

#### Synchronizing sites with a battle-tested API

When a Drupal site installs and enables RELAXed Web Services it will look and behave like the REST API from [CouchDB](http://couchdb.apache.org). This is a pretty clever trick because it enables us to leverage the CouchDB ecosystem of tools. For example, you can use [PouchDB](https://pouchdb.com/), a JavaScript implementation of CouchDB, to provide a fully-decoupled offline database in the web browser or on a mobile device. Using the same API design as CouchDB also gives you "streaming replication" with instant updates between the backend and frontend. This is how Pfizer implements off-line browse and publish.

[image blog/pfizer-content-workflow-improvements-workspaces resize=false]

[image blog/pfizer-content-workflow-improvements-deploy resize=false]

### Conclusion

Drupal 8.0 core packed many great improvements, but we didn't focus much on advancing Drupal's content workflow capabilities. As we think about Drupal 8.x and beyond, it might be good to move some of our focus to features like content staging, better audit-ability, off-line support, full-site preview, and more. If you are a content manager, I'd love to hear what you think about better supporting some or all of these use cases. And if you are a developer, I encourage you to take a look at these modules, try them out and let us know what you think.

*Thanks to [Tim Millwood](https://www.drupal.org/u/timmillwood), [Dick Olsson](https://www.drupal.org/u/dixon_) and [Nathaniel Catchpole](https://www.drupal.org/u/catch) for their feedback on the blog post. Special thanks to Pfizer for contributing to Drupal.*
