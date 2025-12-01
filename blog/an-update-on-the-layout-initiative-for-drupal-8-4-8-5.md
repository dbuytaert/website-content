---
title: 'An update on the Layout Initiative for Drupal 8.4/8.5'
date: '2017-11-14T21:57:53-05:00'
author: Dries
summary: 'Want to know what has been happening with the Layout Initiative in Drupal? Read my update.'
image: blog/drupal-8-5-field-layouts-prototype
tags:
  - Drupal
published: true
type: blog
url: /an-update-on-the-layout-initiative-for-drupal-8-4-8-5
id: 4076
---

Now Drupal 8.4 is released, and Drupal 8.5 development is underway, it is a good time to give an update on what is happening with Drupal's Layout Initiative.

### 8.4: Stable versions of layout functionality

Traditionally, site builders have used one of two layout solutions in Drupal: [Panelizer](https://www.drupal.org/project/panelizer) and [Panels](https://www.drupal.org/project/panels). Both are contributed modules outside of Drupal core, and both achieved stable releases in the middle of 2017. Given the popularity of these modules, having stable releases closed a major functionality gap that prevented people from building sites with Drupal 8.

### 8.4: A Layout API in core

The Layout Discovery module added in Drupal 8.3 core has now been marked stable. This module adds a [Layout API](https://www.drupal.org/docs/8/api/layout-api) to core. Both the aforementioned Panelizer and Panels modules have already adopted the new Layout API with their 8.4 release. A unified Layout API in core eliminates fragmentation and encourages collaboration.

### 8.5+: A Layout Builder in core

Today, Drupal's layout management solutions exist as contributed modules. Because creating and building layouts is expected to be out-of-the-box functionality, we're working towards adding layout building capabilities to Drupal core.

Using the Layout Builder, you start by selecting predefined layouts for different sections of the page, and then populate those layouts with one or more blocks. I showed the Layout Builder in [my DrupalCon Vienna keynote](https://dri.es/state-of-drupal-presentation-september-2017) and it was really well received:

[video Hx4EEzI7aNE]

### 8.5+: Use the new Layout Builder UI for the Field Layout module

One of the nice improvements that went in Drupal 8.3 was the [Field Layout module](https://www.youtube.com/watch?v=mJBHQJFHqws), which provides the ability to apply pre-defined layouts to what we call "entity displays". Instead of applying layouts to individual pages, you can apply layouts to types of content regardless of what page they are displayed on. For example, you can create a content type 'Recipe' and visually lay out the different fields that make up a recipe. Because the layout is associated with the recipe rather than with a specific page, recipes will be laid out consistently across your website regardless of what page they are shown on.

The basic functionality is already included in Drupal core as part of the experimental Fields Layout module. The goal for Drupal 8.5 is to stabilize the Fields Layout module, and to improve its user experience by using the new Layout Builder. Eventually, designing the layout for a recipe could look like this:

[image blog/drupal-8-5-field-layouts-prototype resize=false]

Layouts remains a strategic priority for Drupal 8 as it was the second most important site builder priority identified in my [2016 State of Drupal survey](https://dri.es/state-of-drupal-presentation-may-2016), right behind Migrations. I'm excited to see the work already accomplished by the Layout team, and look forward to seeing their progress in Drupal 8.5! If you want to help, check out the [Layout Initiative roadmap](https://www.drupal.org/node/2884601).

*Special thanks to [Angie Byron](https://www.drupal.org/u/webchick) for contributions to this blog post, to [Tim Plunkett](https://www.drupal.org/u/timplunkett) and [Kris Vanderwater](https://www.drupal.org/u/eclipsegc) for their feedback during the writing process, and to [Emilie Nouveau](https://www.drupal.org/u/dyannenova) for the screenshot and video contributions.*
