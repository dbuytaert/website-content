---
title: "Evolving Drupal's Layout Builder to an Experience Builder"
date: '2024-04-23T12:30:15-04:00'
author: Dries
summary: 'The Drupal community will evolve the Layout Builder into the Experience Builder, enhancing its intuitiveness, expanding its out-of-the-box functionality, and introducing in-browser theming capabilities.'
image: drupal/experience-builder-announcement
tags:
  - Drupal
published: true
type: blog
url: /evolving-drupal-layout-builder-to-an-experience-builder
id: 5601
---

[image drupal/experience-builder-announcement]

Imagine a world where installing [Drupal](https://www.drupal.org/) instantly offers a creative experience that allows you to build and style pages right out of the box, without any need for additional modules or configuration.

The introduction of [Drupal's Layout Builder](https://dri.es/why-drupal-layout-builder-is-so-unique-and-powerful) in 2018 was an important milestone toward this vision, but it was just the first step. Layout Builder provides site builders with a powerful drag-and-drop interface for creating and arranging content within customizable layouts.

Despite its success, there is a clear and pressing need to improve the existing Layout Builder. The numerous community-developed modules enhancing Layout Builder highlight the need for a more comprehensive solution.

That is why at DrupalCon Lille last year, I was excited to [announce the "Next Generation Page Builder" initiative](https://dri.es/state-of-drupal-presentation-october-2023), aimed at improving and expanding the Layout Builder to provide a truly intuitive, out-of-the-box page-building experience.

Since announcing the 'Next Generation Page Builder', led by [Lauri Eskola](https://www.drupal.org/u/lauriii) (Acquia), a [Drupal Core Committer](https://www.drupal.org/about/core/policies), we've done extensive research and planning.

Inspired by user feedback, we decided to make two changes. First, we decided to broaden our focus: not only will we improve the page-building features of Layout Builder, we will also integrate basic theming capabilities, enabling users to style their pages effortlessly without having to edit Twig files. Second, reflecting on this wider scope, we renamed the initiative from 'Next Generation Page Builder' to 'Experience Builder'.

In recent months, we explored several options for how to create such an Experience Builder, including accelerating development of the Layout Builder, switching to [Gutenberg](https://wordpress.org/gutenberg/), adopting [Paragraphs](https://www.drupal.org/project/paragraphs), or using the newly open-sourced [Plasmic](https://github.com/plasmicapp/plasmic).

After thorough analysis and discussions with key stakeholders, including Automattic's Gutenberg team, the Drupal Core Committers decided the best approach is to expand the Layout Builder while also incorporating the best elements of Paragraphs.

Looking to the future, I hope the Experience Builder becomes the preferred Drupal tool for layout design, page building, and basic theming. Our main goal is to create a tool that site builders love, with an amazing out-of-the-box experience. By integrating key features from Paragraphs, we also aim to create a unified solution that reduces fragmentation, accelerates innovation, and ensures Drupal remains at the forefront of site building.

Our future success hinges on expanding Drupal's usability to a wider audience. Our CMS capabilities are often better than our competitors', but aren't always as user friendly. In the Drupal 7 era, Drupal was the OG (Original Great) of low-code but today we are being outpaced by competitors in terms of ease of use. Without user experience improvements, we'll lose ground. The Experience Builder initiative is all about introducing more people to the power of Drupal.

<p class="pullquote">I feel strongly that a unified Experience Builder is one of the most important initiatives we can undertake right now.</p>

Developing an Experience Builder is a big task that will require substantial effort, extensive collaboration, and significant expertise in user experience and design. As Drupal Core Committers, we are driven by a sense of urgency to advance this initiative. We are committed to moving quickly and iterating rapidly, but to succeed, we also need your support. There will be many opportunities for the community to collaborate and contribute to this initiative.

For more information, please check [Lauri's latest blog post on the topic](https://www.drupal.org/about/core/blog/working-toward-an-experience-builder). Additionally, I will discuss this further in my upcoming DrupalCon Portland keynote in a few weeks.
