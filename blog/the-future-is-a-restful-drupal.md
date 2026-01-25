---
url: 'https://dri.es/the-future-is-a-restful-drupal'
title: 'The future is a RESTful Drupal'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2012-02-16T14:34:38-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
  - 'Web services'
  - 'Headless Drupal'
published: true
id: 2646
---

# The future is a RESTful Drupal

Last weekend, we held a sprint at the Acquia offices for the [Web Services and Context Core (WSCCI) Initiative for Drupal 8](https://www.garfieldtech.com/blog/web-services-initiative). This was an important sprint for the future of Drupal. This blog post provides a high-level overview of what was discussed and agreed upon; the different sprint participants will be laying out more technical details in follow-up blog posts.

Overall, a wide range of experience levels, skill sets, and perspectives were brought to the table, with the goal of the sprint being to clearly define the initiative's scope, get agreement on what we wanted to accomplish and why, and lay out a clear plan for how to accomplish this.

[image drupal/wscci-sprint-group-photo-february-2012]

In attendance were:

- [Larry "Crell" Garfield](https://www.drupal.org/user/26398), lead architect of the WSCCI initiative
- [Daniel "sun" Kudwien](https://www.drupal.org/user/54136), top Drupal core contributor
- [Fabien "fabpot" Potencier](http://fabien.potencier.org/), lead developer of the Symfony project
- [Kris "EclipseGc" Vanderwater](https://www.drupal.org/user/61203) and [James "neclimdul" Gilliland](https://www.drupal.org/user/48673), who have helped develop and implement the plugin system as part of WSCCI
- [Greg "heyrocker" Dunlap](https://www.drupal.org/user/128537), initiative lead of the Configuration Management Initiative for Drupal 8
- [Moshe Weitzman](https://www.drupal.org/user/23), long-time Drupal core contributor
- [Angela "webchick" Byron](https://www.drupal.org/user/24967), community cat herder and Drupal 7 core co-maintainer
- [Randy "rfay" Fay](https://www.drupal.org/user/30906), [Justin "beejeebus" Randall](https://www.drupal.org/user/38580) and [Alex "effulgentsia" Bronstein](https://www.drupal.org/user/78040), core developers and sane voices of reason with an outside perspective
- [Dries Buytaert](https://www.drupal.org/user/1) (me), project lead

### Scope

The [WSCCI initiative](https://www.garfieldtech.com/blog/web-services-initiative), as envisioned by Larry Garfield, was originally set to address Drupal's web services and flexible page layout capabilities. We discovered that both would require significant changes to Drupal core, and it was difficult to build consensus online, so we decided to get together for 3 days and to flesh out what we actually wanted to accomplish, and how.

At the sprint, we first attempted to articulate all of the problems that WSCCI was trying to solve, which included: multiple page layouts, better UI/UX to manage blocks, partial page rendering (ESI, AHAH), contextual blocks, different response types per delivery callback/URL, plugin system / swappable subsystems, lazy loading bootstrap (convert subsystems to PSR-0 classes), infrastructure for building web services, dependency injection, and so on.

We then did a round of voting where we could each choose 3 of those things in order to try to determine which of those were the most important.

[image drupal/wscci-sprint-post-it-notes-february-2012]

Two things became instantly clear during this exercise:

1. The items encompassed under WSCCI really spanned at least 3 separate major areas: Web Services, more robust ESI-based layouts (think Panels only more powerful), and cleaning up our underlying toolset to be a more loosely-coupled framework.
2. The underlying architecture to support RESTful calls to Drupal that makes all of the other things possible was deemed the most important thing to focus on.

### Scope resolution

After a good chunk of discussions, all were in agreement to scale back the scope of the initiative to just the "Web Services" piece, and spin off the Layout/blocks/related-UI parts to a separate effort.

Furthermore, some efforts, such as PSR-0 and Unified Plugin system, were only semi-related to the WSCCI initiative in the first place, and just happened to become relevant for it. Work on those efforts will continue as part of the general [Framework community efforts](https://www.drupal.org/node/1224666).

### Architecture

Fabien was able to offer a tremendous number of insights as to how various Symfony2 components could help provide underlying structure for Drupal core to support Web Services out of the box. Essentially, most of what the WSCCI team had been trying to work toward, in the abstract, was already implemented within Symfony2. While some implementation details were different than what we had in mind, the end result is almost exactly what we have been trying to accomplish. We therefore agreed that the best way forward was to leverage several Symfony2 components within Drupal as a way to speed progress toward that end.

### Benefits

Some of the concrete benefits that would come out of these changes are

- An underlying framework that is a first-class REST citizen. That means developing web services becomes easier and more efficient, because the plumbing is already in place. An HTML page is a particular case of a REST service.
- Because the core system will be fully REST-ified, we'll be able to improve existing APIs and expose Drupal content in a natively RESTful way. For example, our current AJAX system doesn't comply with REST standards, but with these changes, can be cleaned up to do so.
- That in turn makes Drupal-to-Drupal communication, content staging, content sharing, and a host of other related tasks easier.
- The use of widely used libraries and techniques makes Drupal more approachable to new developers.

### Why does this matter?

As it has evolved into an increasingly powerful system, Drupal has gotten increasingly complex and is not as easy to start developing with as it once was. Many developers are nervous about continuing that trend. Managing complexity is a challenge faced by many software projects, and one approach is to use standardized patterns and components.

Due to its long support for PHP 4, as well as some unique needs, Drupal does not take full advantage of standardized patterns and components. The complexity of the custom code that's used and the non-standard architecture combines to create a barrier to entry for developers new to Drupal (both experienced and novice developers alike).

Meanwhile, the web is constantly changing around us. Web services and mobile are more important than ever, and with that comes the need to have more flexible page and layout capabilities. Now feels like the right time to modernize Drupal's capabilities to bring it to the forefront of modern PHP systems and web systems in general.

While changing Drupal's core plumbing to address these needs, it's also a good opportunity to do so using more widely understood and modern techniques and libraries. Leveraging the work of a fellow open source community lets us get a jump on these changes to build a more powerful, more flexible, and more easily learnable system in less time than it would take to go it our own.

While these changes may seem large, and some of them are, we believe that they will achieve the right balance between empowering Drupal's design and architecture, and moving toward more modern, standard, well-tested code and techniques to empower a new generation of developers. I hope you are as excited as we are!
