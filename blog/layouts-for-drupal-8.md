---
title: 'Layouts for Drupal 8'
date: '2012-03-02T11:41:13-05:00'
author: Dries
tags:
  - Drupal
published: true
type: blog
url: /layouts-for-drupal-8
id: 2656
---

At the [Web Services and Context Core initiative sprint](https://dri.es/the-future-is-a-restful-drupal) earlier this month, we attempted to re-scope the initiative so that it was more manageable and less daunting. We decided to spin off one of the major components of what it was trying to tackle into its own separate initiative, the Layout initiative.

The goal of the Layout initiative is to make all elements on the page into contextual blocks that can be rearranged and organized into flexible layouts (and even layouts within layouts) through a drag and drop interface.

Specifically, the initiative breaks down as:

1. **Contextual blocks**: Provide the ability to pass in relevant configuration data to blocks so they can react on something other than the URL of the request.
2. **Blocks everywhere**: Make all page elements–from the site logo to menus to the main page content–into blocks which can be treated the same.
3. **Multiple page layouts**: Choose from either pre-configured layouts such as "3-Column" and "Grid" or make your own custom layouts for pages.
4. **Partial page rendering**: Allow for individual page components to be loaded and rendered independently, allowing for better performance and independent AJAX requests.
5. **Better UI/UX to manage blocks**: A visual, drag and drop interface for creating page layouts and populating with blocks.

This approach to building pages yields a number of benefits, including the ability to customize the look and feel of a site based on a variety of contextual information, the ability to render parts of the page independently for performance, increased consistency, and increased flexibility for site builders to re-use page elements in a number of contexts.

I've asked [Kris "EclipseGc" Vanderwater](https://www.drupal.org/user/61203) to head up the Layout initiative team. Kris has spent a lot of time working with Panels and Page Manager, and intends to work closely with Earl Miles and other maintainers of the CTools suite. Read [Kris's blog post](http://krisandju.e-webindustries.com/blog/drupal-8-blocks-layouts-everywhere) for an overview of the initiatives' goals. Note that like all initiatives, they don't actually materialize unless people decide to help. Please join the discussions in the [Blocks and Layouts Everywhere Initiative](https://groups.drupal.org/drupal-8-blocks-layouts-everywhere-initiative) on groups.drupal.org and help work on [Layout issues on drupal.org](https://www.drupal.org/sandbox/eclipsegc/1441840).
