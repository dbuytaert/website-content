---
title: "Drupal's Project Browser empowers ambitious site builders"
date: '2022-12-09T08:25:19-05:00'
author: Dries
summary: "The Project Browser Initiative simplifies Drupal module installation, leveraging Drupal's new Package Manager."
image: drupal/project-browser
tags:
  - Drupal
published: true
type: blog
url: /drupal-project-browser-empowers-ambitious-site-builders
id: 5386
---

[image drupal/project-browser resize=false]

Last year in [my DrupalCon North America keynote](https://dri.es/state-of-drupal-presentation-april-2021), I proposed the [Project Browser Initiative for Drupal](https://www.drupal.org/about/core/strategic-initiatives/project-browser). Project Browser makes it easy for site builders to find and install Drupal modules without having to use the command line!

Ever since, the initiative has been in full swing with work taking place on various fronts. Aside from building the browser itself, we are working on various other aspects to provide the best possible user experience: logos are being designed for the top Drupal.org projects, categories are being streamlined to make discovery more intuitive, and project descriptions are being improved for clarity. We are also defining various quality metrics to make sure Project Browser can easily surface the best projects. All combined, these efforts should make it a lot easier for end users to discover and install Drupal modules.

In the past 18 months, [Project Browser](https://www.drupal.org/project/project_browser) has gone from announcement to beta. And the latest beta has a full-featured user interface for discovering and installing projects, fulfilling the original vision of users not needing a command line.

Check out this video to see how it works:

[video Pfoq_c_GydY]

The Project Browser team would love for many people to [try out the latest beta](https://www.drupal.org/project/project_browser).

As a side note, Project Browser is built on top of Drupal's new Package Manager. We are building Package Manager for both the [Automatic Updates initiative](https://www.drupal.org/about/core/strategic-initiatives/automatic-updates) and the [Project Browser initiative](https://www.drupal.org/about/core/strategic-initiatives/project-browser). Package Manager provides these initiatives the ability to programmatically utilize [Composer](https://getcomposer.org/), a tool commonly used to manage modern PHP applications like Drupal.

The net result is that:

1. Project Browser (and Automatic Updates) will support any kind of contributed project, even those with complex third party dependency chains.
2. You can switch between using the Project Browser and the command line. Projects installed via Project Browser can be managed from the command line using Composer, and vice versa.

I wanted to highlight the Package Manager work because it illustrates how much care and effort has gone into building Project Browser and Automatic Updates. The end results will be one of the most powerful, secure and cutting-edge installation and update systems in the market.

I'm excited about this work for many reasons, but I want to highlight two of them. First, it will help bring more people to [Drupal](https://www.drupal.org/), and therefore the [Open Web](https://dri.es/tag/open-web), something that I am very passionate about. Second, this work is fundamental to making Drupal an even more [composable platform](https://dri.es/a-composable-digital-experience-manifesto).

*A special thank you to [Chris Wells](https://www.drupal.org/u/chrisfromredfin) ([Redfin Solutions](https://redfinsolutions.com/)), [Leslie Glynn](https://www.drupal.org/u/leslieg) ([Redfin Solutions](https://redfinsolutions.com/)), [Fran Garcia-Linares](https://www.drupal.org/u/fjgarlin) ([Drupal Association](https://www.drupal.org/association)), [Ben Mullins](https://www.drupal.org/u/bnjmnm) ([Acquia](https://www.acquia.com/)), [Narendra Singh](https://www.drupal.org/u/narendrar) ([Acquia](https://www.acquia.com/)), [Srishti Bankar](https://www.drupal.org/u/srishtiiee) ([Acquia](https://www.acquia.com/)), [Utkarsh Patidar](https://www.drupal.org/u/utkarsh_33) ([Acquia](https://www.acquia.com/)), and [Tim Plunkett](https://www.drupal.org/u/timplunkett) ([Acquia](https://www.acquia.com/)) for leading much of the work. Also a special thank you to [Ted Bowman](https://www.drupal.org/u/tedbow) ([Acquia](https://www.acquia.com/)), [David Strauss](https://www.drupal.org/u/david-strauss)<a></a> ([Pantheon](https://pantheon.io/)<a>) and the Automatic Updates team for working on the Package Manager.</a>*
