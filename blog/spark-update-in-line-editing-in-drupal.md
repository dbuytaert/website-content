---
title: 'Spark update: in-line editing in Drupal'
date: '2012-05-30T20:23:55-04:00'
author: Dries
tags:
  - Drupal
  - Acquia
  - Usability
  - 'Spark distribution'
published: true
type: blog
url: /spark-update-in-line-editing-in-drupal
id: 2701
---

The goal of the [Spark distribution](https://www.drupal.org/project/spark) is to incubate authoring experience improvements in a Drupal 7 and Drupal 8. It was [announced earlier this month](https://dri.es/announcing-spark-authoring-improvements-for-drupal-7-and-drupal-8), and since then we've been hard at work on initial research and design.

The Spark team's primary focus is on improving Drupal's content authoring and editing experience, and the first feature we're prioritizing is in-place editing: the ability to edit content, menus, etc. directly on the page, without the need to navigate to a separate edit form. Think of it as "true" WYSIWYG.

Members of [Acquia](https://www.acquia.com/)'s design team spent time analyzing how some of the most widely adopted Open Source as well as proprietary CMSs do in-place editing. We then prototyped some initial ideas, and performed usability testing on those prototypes to see what works and what doesn't. After a number of iterations, we're happy to report that the usability testing has validated Spark's general design direction. People loved the prototype. Now is a good time for us to share our initial prototype and to solicit further feedback from the community so we can shift gears into implementation.

The following 5-minute video walks through the HTML/JS prototype, and also provides a bit of background on the Spark project:

[video a53Wcq31LmY]

Our goal is to deliver this functionality in a contributed module for Drupal 7 first and foremost, which will live at the [In-Place Editing project on drupal.org](https://www.drupal.org/project/ipe). This module will be bundled into the [Spark distribution](https://www.drupal.org/project/spark). Depending on how it is received, I hope we can also target this functionality for Drupal 8 core.

From a technical architecture standpoint, we are currently in the process of [selecting the WYSIWYG editor to use in Spark](https://www.drupal.org/node/1580210) for in-place editing of HTML content. For now, we plan to focus on supporting only the Filtered/Full HTML text formats in order to get us to something testable faster.

Later, we are hoping to branch out into other areas of authoring experience too, including helping with the [content creation form improvements](https://www.drupal.org/node/1510532) that the Drupal usability team has been spear-heading, as are well as the [layouts UI work](https://groups.drupal.org/node/227543) being actively discussed in the [usability group](https://groups.drupal.org/usability). The Drupal usability team is doing an incredible job with these issues, and once fully staffed, I would like to see the Spark team help implement these improvements for Drupal 8 and backport them to Drupal 7 so we can ship it with the Spark distribution.

As you can see, things are starting to move along quite nicely. Please [join the discussion in the Spark issue queue](https://www.drupal.org/project/issues/spark) if this functionality sounds exciting to you and you'd like to help!
