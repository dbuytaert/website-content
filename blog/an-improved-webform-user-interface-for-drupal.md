---
url: 'https://dri.es/an-improved-webform-user-interface-for-drupal'
title: 'An improved Webform user interface for Drupal'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2010-12-29T03:28:33-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
  - Acquia
  - 'Drupal Gardens'
published: true
id: 2076
---

# An improved Webform user interface for Drupal

At [Acquia](https://www.acquia.com), we spent a lot of time improving the [Webform module](https://www.drupal.org/project/webform), one of the top 10 most popular Drupal modules, as well as the [Form Builder module](https://www.drupal.org/project/form_builder), a companion module that provides an improved user interface for the Webform module. The Webform module and the Form Builder module allow people to create custom forms such as contact forms, online surveys and more.

Both modules are maintained by [Nate 'quicksketch' Haug](http://quicksketch.org/), one of the top Drupal contributors. Like anything Nate does, the modules are amazingly powerful and have great code quality. We wanted to add support for creating custom forms to [Drupal Gardens](http://www.drupalgardens.com/) and believed that the Webform and Form Builder modules were the right way to go. No need to reinvent the wheel.

Before making Webform and Form Builder available as part of Drupal Gardens, we wanted to try and see if we could make Webforms easier to use, without making it less powerful. We spent about 200 hours to explore various different design and interaction models. We used both paper prototypes and working prototypes to conduct usability tests, and used these to drive further optimizations. After we felt good about the direction, we ran it by quicksketch. With quicksketch's guidance, we helped upgrade both modules from Drupal 6 to Drupal 7, and implemented the new user interface on top of that. The new drag-and-drop interface puts some things in different locations on the page and has a number of different interaction patterns compared to the old user interface. To do so, we wrote a couple of modules that add our user interface on top of the Webform and Form Builder modules. It is layered like a stack: Webform → Form Builder → Alternate UI.

Fast forward 25 person-weeks, and we've now rolled out our improved user interface as part of [the latest Drupal Gardens release](http://www.drupalgardens.com/content/drupal-gardens-adds-custom-surveys-forms-and-questionnaires).

We're contributing everything back to the community – some things we've already contributed back, other things we're in the process to. We're also helping to back port some changes to Drupal 6, even though we don't need them for Drupal Gardens. With these contributions, everyone in the community can benefit.

The new user interface is an incredible achievement that a lot of people deserve recognition for, including [quicksketch](http://quicksketch.org) who spent many years of getting Webform and Form Builder modules to where we were able to use them as a starting point.

I'm pretty excited about this user interface, and would love your feedback and suggestions. *What do you think?*

**Update on January 10th, 2011:** the [Webform Alternate UI module](https://www.drupal.org/project/webform_alt_ui) is now available on drupal.org. This module provides an alternate user interface for the Webform module, allowing you to create and edit forms from within an easy-to-use form building tool.
