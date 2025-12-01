---
title: 'Moving the Drupal 8 workflow initiative along'
date: '2017-01-06T03:24:26-05:00'
author: Dries
summary: "An update on the workflow initiative's progress the past 9 months and an update on future plans"
tags:
  - Drupal
  - 'Workflow initiative'
published: true
type: blog
url: /moving-the-drupal-8-workflow-initiative-along
id: 3856
---

Nine months ago I wrote about the [importance of improving Drupal's content workflow capabilities](https://dri.es/improving-drupal-content-workflow) and how we set out to include a common base layer of workflow-related functionality in Drupal 8 core. That base layer would act as the foundation on which we can build a list of great features like cross-site content staging, content branching, site previews, offline browsing and publishing, content recovery and audit logs. Some of these features are really impactful; 5 out of the top 10 most requested features for content authors are related to workflows (features 3-7 on the image below). We will deliver feature requests 3 and 4 as part of the "content workflow initiative" for Drupal 8. Feature requests 5, 6 and 7 are not in scope of the current content workflow initiative but still stand to benefit significantly from it. Today, I'd like to provide an update on the workflow initiative's progress the past 9 months.

[image drupal/top-requests-for-content-authors-2016 resize=false]

### Configurable content workflow states in Drupal 8.2

While Drupal 8.0 and 8.1 shipped with just two workflow states (Published and Unpublished), Drupal 8.2 (with the the experimental *Content moderation* module) ships with three: Published, Draft, and Archived. Rather than a single 'Unpublished' workflow state, content creators will be able to distinguish between posts to be published later (drafts) and posts that were published before (archived posts).

The 'Draft' workflow state is a long-requested usability improvement, but may seem like a small change. What is more exciting is that the list of workflow states is fully configurable: you can add additional workflow states, or replace them with completely different ones. The three workflow states in Drupal 8.2 are just what we decided to be good defaults.

Let's say you manage a website with content that requires legal sign-off before it can be published. You can now create a new workflow state 'Needs legal sign-off' that is only accessible to people in your organization's legal department. In other words, you can set up content workflows that are simple (like the default one with just three states) or that are very complex (for a large organization with complex content workflows and permissions).

This functionality was already available in Drupal 7 thanks to the contributed modules like the [Workbench suite](https://www.drupal.org/project/workbench). Moving this functionality into core is useful for two reasons. First, it provides a much-requested feature out of the box – this capability meets the third most important feature request for content authors. Second, it encourages contributed modules to be built with configurable workflows in mind. Both should improve the end-user experience.

### Support for different workflows in Drupal 8.3

Drupal 8.3 (still in development, planned to be released in April of 2017) goes one step further and introduces the concept of multiple types of workflows in the experimental *Workflows* module. This provides a more intuitive way to set up different workflows for different content types. For example, blog posts might not need legal sign-off but legal contracts do. To support this use case, you need to be able to setup different workflows assigned to their appropriate content types.

What is also interesting is that the workflow system in Drupal 8.3 can be applied to things other than traditional content. Let's say that our example site happens to be a website for a membership organization. The new workflow system could be the technical foundation to move members through different workflows (e.g. new member, paying member, honorary member). The reusability of Drupal's components has always been a unique strength and is what differentiates an application from a platform. By enabling people to reuse components in interesting ways, we turn Drupal into a powerful platform for building many different applications.

[image drupal/drupal-8-workflow-configuration resize=false]

### Workspace interactions under design

While workflows for individual content items is very powerful, many sites want to publish multiple content items at once as a group. This is reflected in the fourth-most requested feature for content authors, 'Staging of multiple content changes'. For example, a newspaper website might cover the passing of George Michael in a dedicated section on their site. Such a section could include multiple pages covering his professional career and personal life. These pages would have menus and blocks with links to other resources. 'Workspaces' group all these individual elements (pages, blocks and menus) into a logical package, so they can be prepared, previewed and published as a group. And what is great about the support for multiple different workflows is that content workflows can be applied to workspaces as well as to individual pieces of content.

We are still in the early stages of building out the workspace functionality. Work is being done to [introduce the concept of workspaces in the developer API](https://www.drupal.org/node/2784921) and on [designing the user interface](https://www.drupal.org/node/2732081#comment-11836237). A lot remains to be figured out and implemented, but we hope to introduce this feature in Drupal 8.5 (planned to be released in Q2 of 2018). In the mean time, other Drupal 8 solutions are available as contributed modules.

[image drupal/drupal-8-workspaces-prototype-january-2017 resize=false]

### Closing thoughts

We discussed work on content workflows and workspaces. The changes being made will also help with other problems like content recovery, cross-site content staging, content branching, site previews, offline browsing and publishing, and audit logs. Check out [the larger roadmap of the workflow initiative](https://www.drupal.org/node/2721129) and [the current priorities](https://contribkanban.com/sprint/WorkflowInitiative). We have an exciting roadmap and are always looking for more individuals and organizations to get involved and accelerate our work. If you want to get involved, don't be afraid to raise your hand in the comments of this post.

### Thank you

*I tried to make a list of all people and organizations to thank for their work on the workflow initiative but couldn't. The Drupal 8 workflow initiative borrows heavily from years of hard work and learnings from many people and organizations. In addition, there are many people actively working on various aspects of the Drupal 8 workflow initiative. Special thanks to [Dick Olsson](https://www.drupal.org/u/dixon_) (Pfizer), [Jozef Toth](https://www.drupal.org/u/jojototh) (Pfizer), [Tim Millwood](https://www.drupal.org/u/timmillwood) (Appnovation), [Andrei Jechiu](https://www.drupal.org/u/jeqq) (Pfizer), [Andrei Mateescu](https://www.drupal.org/u/amateescu) (Pfizer), [Alex Pott](https://www.drupal.org/u/alexpott) (Chapter Three), [Dave Hall](https://www.drupal.org/u/skwashd) (Pfizer), [Ken Rickard](https://www.drupal.org/u/agentrickard) (Palantir.net) and [Ani Gupta](https://www.drupal.org/u/anig) (Pfizer). Also thank you to [Gábor Hojtsy](https://www.drupal.org/u/g%C3%A1bor-hojtsy) (Acquia) for his contributions to this blog post.*
