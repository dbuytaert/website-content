---
title: 'Custom content types'
date: '2006-05-03T11:40:47-04:00'
author: Dries
tags:
  - Drupal
published: true
type: blog
url: /custom-content-types
id: 65
---

Right now, creating a new content type in Drupal typically involves developing a new module, or extending an existing Drupal module to your needs. One of our long-term goals is to make it possible to create custom content types without having to write any code at all. We want users, not developers, to be able to create custom content types from within Drupal's administration interface. The need for this has been emerging gradually, and will become increasingly important for the success of Drupal, and content management systems in general. Eliminating developer intervention is a good example of how we can make Drupal more accessible to people that want to build websites.

The current code name for this project is the "content construction kit" (CCK). The project's goal is to allow users to create custom content types in Drupal through the web. The project is headed by [John VanDyk](https://www.sysarchitects.com/) and Johnatan Chaffer, who started working on the CCK almost two years ago. From day one, I've been keeping an eye on their work, hoping we can integrate it into Drupal core at some point. To understand the impact of such move, you can best think of it of as a heart transplantation. Much like open heart surgery, it needs careful planning and preparation.

It is part of [the larger goal to make Drupal easier to use and develop for](/complexity-is-a-disease).
