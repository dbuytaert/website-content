---
title: "The evolution of Drupal's composability: from the command line to the browser"
date: '2023-04-04T09:10:01-04:00'
author: Dries
summary: "Discover Drupal's future: how Automatic Updates and Project Browser will empower ambitious site builders with a no-code composable platform and modern development practices."
image: drupal/evolution-drupal-composability
tags:
  - Drupal
featured: true
published: true
type: blog
url: /the-evolution-of-drupal-composability-from-the-command-line-to-the-browser
id: 5441
---

[image drupal/evolution-drupal-composability resize=false]

Drupal's modularity allows developers to combine and reuse modules, themes, and libraries to create custom solutions. This modularity is one of the key ingredients that makes Drupal a [composable platform](https://dri.es/a-composable-digital-experience-manifesto). The [original motivation](https://dri.es/the-assembled-web) behind Drupal's modularity was to accelerate the pace of innovation and democratize the experience of site building.

This blog post has two main goals.

First, we'll explore how Drupal's composability is evolving to empower [ambitious site builders](https://dri.es/drupal-is-for-ambitious-site-builders) with modern, no-code development practices. Through exciting initiatives like [Automatic Updates](https://www.drupal.org/about/core/strategic-initiatives/automatic-updates) and [Project Browser](https://www.drupal.org/about/core/strategic-initiatives/project-browser), Drupal will simplify the task of installing, composing, and updating Drupal sites, all within the Drupal user interface.

Second, we'll provide a retrospective on the past 10+ years of decisions that have led to significant changes in how end-users install, extend, develop, and maintain Drupal sites. By delving into Drupal's innovation process through a timeline approach, we'll showcase key contributors, significant milestones, and pivotal shifts in thinking that have influenced Drupal's approach to composability.

Let's start!

### 2011

Drupal 7 was released, and introduced the "Update Manager". Derek Wright (3281d Consulting), Jacob Singh (Acquia), and Joshua Rogers (Acquia) had begun developing the Update Manager feature starting in 2009.

The Update Manager can be considered Drupal's first no-code update system. This feature introduced the ability for users to easily download and upload modules from Drupal.org to a Drupal site.

Under the hood, the Update Manager uses either the File Transfer Protocol (FTP) or Secure Shell Protocol (SSH). An end user can upload a module to their Drupal site through a form, and Drupal will FTP or SSH the module to the web server's file system.

Interestingly, fifteen years after its development started, Drupal 10 still uses the same basic Update Manager. However, this is about to change.

The Update Manager has several drawbacks: modules can conflict with each other, updates are applied directly to your live site, and if something goes wrong, there is no way to recover.

[image drupalcon-chicago-2011/drupal-8-branch-1]

In March 2011, we started working on Drupal 8, and later that year, in August, we agreed to adopt components from the [Symfony project](https://symfony.com/). This decision was made to help reduce the amount of code we had to build and maintain ourselves.

### 2012

The Symfony project was using [Composer](http://getcomposer.org/). Composer is a PHP package management system similar to [npm](https://www.npmjs.com/). With Composer, developers can define the dependencies required by their PHP application in a file called `composer.json`. Then, Composer will automatically download and install the required components and their dependencies.

At first, we added Symfony components directly to Drupal Core's Git repository. Core Committers would regularly run `composer update` and commit their updated code to Drupal Core's Git repository. This left the end user experience relatively unchanged.

Some people in the Drupal community had concerns with storing third-party dependencies in Drupal Core's Git repository. To address this, [we moved the Symfony components out of Git](https://www.drupal.org/project/drupal/issues/1475510), and required Drupal's end users to download and install third-party components themselves. To do so, end users need to run `composer install` on the command line.

This approach is still used today. Drupal Core Committers maintain `composer.json` and `composer.lock` in Git to specify the components that need to be installed, and end users run `composer install` to download and install the specified components on their system.

Looking back, it is easy to see how embracing both Symfony components and Composer was a defining moment for Drupal. It made Drupal more powerful, more flexible, and more modular. It also helped us focus. But as will become clear in the remainder of this blog post, it also changed how end users install and manage Drupal. While it brought benefits, there were also drawbacks: it increased the maintenance, integration, and testing workload for end users. For many, it made Drupal more complex and challenging to maintain.

### 2013

We decided that [Drupal Core would adopt semantic versioning](https://www.drupal.org/project/drupal/issues/2135189). This marked a massive shift in [Drupal's innovation model](https://dri.es/the-transformation-of-drupal-8-for-continuous-innovation), moving away from long and unpredictable release cycles that broke backward compatibility between major releases.

To understand why this decision was important for Automatic Updates and Project Browser – and Drupal's composability more broadly – it's worth discussing semantic versioning some more.

[Semantic versioning](https://semver.org/) is a widely-used versioning system for software that follows a standard format. The format is `X.Y.Z`, where `X` represents the major version, `Y` the minor version, and `Z` the patch version.

When a new version is released, semantic versioning requires that the version number is updated in a predictable way. Specifically, you increment `Z` when a release only introduces backward compatible bug fixes. If new features are added in a backward compatible manner, you increment `Y`. And you increment `X` when you introduce changes that break the existing APIs.

This versioning system makes it easy to know when an automatic update is safe. For example, if a Drupal site is running version 10.0.2 and a security update is released as version 10.0.3, it's safe to automatically update to version 10.0.3. But if a major release is made as version 11.0.0, the site owner will need to manually update, as it likely contains changes that aren't compatible with their current version. In other words, the introduction of semantic versioning laid the groundwork for safe, easy Drupal updates.

### 2015

Drupal 8 was released. It came with big changes on all the fronts mentioned above: a shift towards object-oriented programming, support for Composer, the introduction of Symfony components, semantic versioning, and an unwavering commitment to simplifying upgrades for users.

Unfortunately, the reaction to Composer was mixed. Many Drupal contributors greatly appreciated the introduction of Composer, as it made it easier to share and utilize code with others. On the other hand, site owners often found it difficult to use Composer. Composer necessitates using the command line, something typically used by more advanced technical users. Moreover, unexpected failures during a Composer update can be complex to resolve for both developers and non-developers alike.

### 2016

The Drupal Association's engineering team, together with members of the community, launched the "Composer Façade". This meant that all Drupal.org hosted projects automatically became available as packages that could be installed by Composer.

There was some behind-the-scenes magic going on to help the Drupal community transition to Composer. For example, Drupal.org extensions were available to Composer even though they were not using semantic versioning.

Over the coming months and years, additional features would be added to Composer Façade, including solutions to help manage compatibility issues, sub-modules, and namespace collisions.

### 2017

Because Drupal has users with different levels of technical sophistication and different technical environments, we supported multiple distribution methods: zip files, tarballs, and Composer.

In the end, we were living in an increasingly Composer-centric world and updates via zip files or tarballs became less and less viable. So we agreed that we had to take a difficult path by fully embracing Composer. We began a long-running effort to make Composer easier for Drupal end users.

For example, the Drupal Association engineering team started building zip files and tarballs with Composer support: you could start with a zip/tar file, and then continue updating your site using Composer.

Separately, we also introduced new ways to install Drupal Core via Composer, such as using a new `drupal/core-recommended` project template. This template specifies the exact dependencies used to test a particular version of Drupal Core. Drupal Core is only released when all tests pass, so using `drupal/core-recommended` helps to prevent any problems caused by using different versions of the dependencies.

[image drupalcon-vienna-2017/automatic-updates-timeline resize=false]

Lastly, in my [DrupalCon Vienna keynote](https://dri.es/state-of-drupal-presentation-september-2017), I declared the need for automatic updates, and made it a top priority for the Drupal community based on community surveys and interviews. This led to the formation of the Automatic Updates Initiative. The basic idea was to make updating Drupal sites easier by making Composer invisible to most users, thus empowering more people, regardless of their technical expertise.

### 2018

From 2017 into 2018, David Strauss (Pantheon) and Peter Wolanin (SciShield) took the lead on planning out the Automatic Updates Initiative, and presented [possible architectural approaches at DrupalCon Nashville](https://www.youtube.com/watch?v=wmhD6lA3PRs).

Their approaches drew inspiration from a multitude of Open Source projects like CoreOS, Fedora Atomic/Silverblue, and systemd. Some of the ideas outlined in their presentation have since been implemented. This is the beauty of Open Source; you can stand on the shoulders of other Open Source projects.

In 2018, the Drupal Security Team and Drupal Core release managers also extended the security coverage of Drupal minor releases from six to twelve months. This enabled site owners to update Drupal on their own schedule, but also introduced "security updates only" branches which will make automatic updates safer. This work was implemented with help from Ted Bowman, Emilie Nouveau, xjm, and Neil Drumm, with sponsorship from Acquia and the Drupal Association.

Later that year, at the Midwest Developer Summit organized by Michael Hess (University of Michigan), the new initiative team (composed of members of the Drupal Security Team, Drupal Association staff, and other interested contributors) defined a full initiative roadmap and began development. Key contributors were Angela Byron, David Strauss, Michael Hess, Mike Baynton, Neil Drumm, Peter Wolanin, Ryan Aslett, Tim Lehnen and xjm (sponsored by Acquia, Pantheon, the Drupal Association, SciShield, and the Universities of Michigan and Minnesota).

This work continued at Drupal Europe in Darmstadt, when the Automatic Updates Initiative team met with contributors from the Composer Initiative to compare needs and goals.

### 2019

In 2019, with sponsorship from the European Commission (EC), the Drupal Association contracted additional developers to build the first iteration of the Automatic Updates concept.

On the server-side, the funding from the EC resulted in all packages hosted on Drupal.org being signed with [PHP Signify](https://github.com/drupal/php-signify). PHP Signify is a PHP implementation of [OpenBSD's Signify](https://packages.debian.org/sid/utils/signify-openbsd). PHP Signify assists in verifying the authenticity of Drupal modules, safeguarding against malicious forgeries. Additionally, Drupal extended OpenBSD's Signify to support chained signatures (CSIG) for better key rotation and maintenance.

On the client-side, the funding resulted in a contributed module for Drupal 7. Due to the European Commission's exclusive use of Drupal 7 at the time, a Drupal 8 module was out of scope. The Drupal 7 module updates tar-based installations of Drupal, as Composer wasn't introduced until Drupal 8.

In my [DrupalCon Amsterdam keynote](https://dri.es/state-of-drupal-presentation-october-2019) in late 2019, I provided an update on the Automatic Updates initiative with the assistance of Tim Lehnen from the Drupal Association:

[video 46KwI8ufOKQ]

### 2020

Up until 2020, contributed modules used version numbers like `8.x-2.1`. This example meant the module was compatible with Drupal 8, and that it was major version 2 with patch level 1. In other words, we supported major and patch level releases, but no minor releases.

We finally updated Drupal.org to [enable semantic versioning for contributed modules](https://www.drupal.org/node/3108648), which brought them up to date with best practices, including the ability to have minor releases, which was consistent with Drupal Core.

Composer Façade continued to support modules that had not adopted semantic versioning.

[image drupalcon-global-2020/drupal-10-automated-updates resize=false]

Meanwhile, work on Automatic Updates continued. Because we had already embraced Composer, it seemed obvious that we would use Composer under the hood to power Automatic Updates. However, there was one feature we identified as missing from the existing Composer/Packagist ecosystem: package signing.

Composer's main security measure is at the transport layer: communication between the client (Drupal) and the package repository (drupal.org, packagist.org, github.com) is protected by https (TLS). However, we didn't believe that to be sufficient for an automatic update system.

Early in 2020, at a CMS security conference sponsored by Google, David Strauss proposed that Drupal implement [The Update Framework](https://theupdateframework.io/) (TUF), which would resolve several architectural issues with PHP Signify and also provide a specification to mitigate numerous kinds of supply chain attacks that we had not considered previously.

To start off this project, developers from the Drupal community met with leaders of [TYPO3](https://typo3.org/) (Benni Mack, Oliver Hader) and [Joomla!](https://www.joomla.org/) (David Jardin, Tobias Zuluaf) to ensure this implementation of TUF would be beneficial not only to [Drupal](https://www.drupal.org/), but to the broader PHP ecosystem, especially to other Composer-driven projects.

With guidance from [Trishank Karthik Kuppusamy](https://github.com/trishankkarthik) (Datadog) and [Joshua Lock](https://github.com/joshuagl) ([Python TUF](https://github.com/theupdateframework/python-tuf)), Ted Bowman, Adam Globus-Hoenich, xjm, David Strauss, David Stoline, and others developed [PHP-TUF](https://github.com/php-tuf/php-tuf), with sponsorship from Acquia, Pantheon, and DDEV. PHP-TUF handles the client-side part of TUF that will run as part of every Drupal site.

At this time, the Drupal Association also began working on the server-side of the TUF implementation so that Drupal.org would be able to sign packages.

In addition to securing the update process with TUF, we also needed to figure out how to apply updates to a live site with minimal interruption. David Strauss, Mike Baynton, and Lucas Hedding (sponsored by Pantheon, Tag1, and MTech, respectively) had previously [prototyped a blue-green deployment approach](https://github.com/php-rot/rot) similar to the one used by CoreOS.

We decided that the required changes to support this would be too disruptive to Drupal, so we pivoted to a new approach proposed by David Strauss: to perform updates in a temporary copy of the site's codebase and then copy the changes to the live codebase as the final step.

While not perfectly atomic in the way that a [blue-green deployment](https://en.wikipedia.org/wiki/Blue-green_deployment) would have been, the key advantage to this approach is that it didn't require any changes to Drupal Core's file structure, which meant that it could also be easily adopted by other PHP projects. Travis Carden (Acquia) began implementing this approach as the [Composer Stager](https://github.com/php-tuf/composer-stager) library.

### 2021

<div class="large">
  [image drupal/automatic-updates-2021 resize=false]
</div>

The second iteration of the Automatic Updates module was released as a beta. Unlike the first iteration sponsored by the European Commission, this version worked for Composer-based projects by leveraging the newly created Composer Stager library.

I had also gone on a virtual listening tour around the same time, and when I asked people why they fell in love with Drupal, the most common response had to do with the empowerment they felt from Drupal's no-code/low-code approach.

With that in mind, I proposed the [Project Browser Initiative](https://www.drupal.org/project/ideas/issues/2940733). The idea was that anyone should be able to install modules, including their third party dependencies, all without having to resort to using Composer on the command line.

This dovetailed nicely with the Automatic Updates initiative. The combination of Automatic Updates and Project Browser would give Drupal the equivalent of an 'app store', making it easy for anyone to discover, install, and update a module and its components.

### 2022

<div class="large">
  [image drupal/project-browser-2022 resize=false]
</div>

In 2022, we began work on making Automatic Updates' Composer functionality available for Project Browser, so that module installs and updates are handled in the same seamless, robust way. The new [Package Manager](https://www.drupal.org/project/drupal/issues/3346707) (a sub-module of Automatic Updates) provides this functionality for both Automatic Updates and Project Browser, and will be the cornerstone of Drupal's install and update functionality.

Ben Mullins (Acquia), Narendra Singh Rathore (Acquia) and Fran Garcia-Linares (Drupal Association) from the Project Browser team collaborated with Ted Bowman (Acquia), Adam Globus-Hoenich (Acquia), Kunal Sachdev (Acquia), Omkar Podey (Acquia), and Yash Rode (Acquia) from the Automatic Updates team in order to enhance the Package Manager's capabilities in order to cater to both use cases.

While work was ongoing on the client side of both Automatic Updates and the Project Browser, the Drupal Association remained focused on the server side. The Drupal Association put out an RFP to implement the TUF signing specification in a way that would integrate with Drupal.org's packaging pipeline. Together with Christopher Gervais and his team at Consensus Enterprises, they developed and released the Open Source [Rugged server](https://gitlab.com/rugged/rugged). A server-side TUF implementation that is the companion to the PHP TUF client implementation.

Drupal Association team member Fran Garcia-Linares also started work on new Drupal.org endpoints that will feed the necessary data for the Project Browser. These endpoints were built on modern Drupal, with JSON:API, and will be deployed to production in the first half of 2023.

### 2023

That brings us to today. [Project Browser](https://www.drupal.org/about/core/strategic-initiatives/project-browser) and [Automatic Updates](https://www.drupal.org/about/core/strategic-initiatives/automatic-updates) are still two of the biggest initiatives for Drupal. Chris Wells (Redfin Solutions) and Leslie Glynn (Redfin Solutions) are leading the Project Browser initiative, and Ted Bowman (Acquia) and Tim Lehnen (Drupal Association) are leading the Automatic Updates initiatives.

Both are built on top of Drupal's new [Package Manager](https://www.drupal.org/project/drupal/issues/3346707). Package Manager provides these initiatives with the ability to programmatically utilize Composer under the hood. Acquia and the Drupal Association are funding several people to work on these initiatives full-time, while other organizations like Redfin Solutions, Agileana, PreviousNext, Third &amp; Grove, and more have provided extensive part-time contributions.

At the time of writing this, Narayan Newton (Tag1 Consulting), as part of the Drupal.org infrastructure team, is working on deploying the Rugged TUF server on the Drupal.org infrastructure. xjm (Agileana) and catch (Third &amp; Grove), two of Drupal Core's release managers, are also collaborating on both the client and server sides of the initiative to help smooth the path to inclusion into Drupal Core.

We have built key parts of our solution in such a way that they can easily be adopted by any PHP project: from [PHP-TUF](https://github.com/php-tuf/php-tuf) to [Rugged](https://gitlab.com/rugged/rugged) and [Composer Stager](https://github.com/php-tuf/composer-stager). In the spirit of Open Source, our implementation was based on other Open Source projects, and now our work can be leveraged by others in turn. We encourage any PHP project that seeks to implement automated updates and a UI-based package manager to do so.

[Automatic Updates](https://www.drupal.org/project/automatic_updates) is currently available as contributed module, which facilitates updates for Drupal Core. The Automatic Updates Extensions module (a sub-module that ships with Automatic Updates) provides automatic updates for contributed modules and themes. The [Project Browser](https://www.drupal.org/project/project_browser) is also currently available as a contributed module.

Our goal is to have both Automatic Updates and Project Browser included in Drupal Core, making them out-of-the-box features for all end users. I'm hopeful we can take the final steps to flush out the remaining bugs, finalize the Drupal.org services and APIs, and move these modules to Drupal Core in the second half of 2023.

### Conclusion

Getting Automatic Updates and Project Browser into Drupal Core will be the result of 10+ years of hard work.

After all these years, we believe Drupal's Automatic Updates and Project Browser to be both the most user-friendly and most security-conscious tools of their kind among all PHP applications.

We were also able to overcome most of the drawbacks of the original Drupal 7 Update Manager: Composer helps us manage module conflicts, and updates are first applied to a staged copy of the site's codebase to ensure they do not cause any unintended side effects.

In the end, Drupal will offer an 'app-store'-like experience. Drupal contributors can register, promote, update, version, and certify modules through Drupal.org. And Drupal end users can securely install and update modules from within their Drupal site without having to use the command line.

I'm excited about achieving this milestone because it will make Drupal a lot easier to use. In fact, Drupal will be easier to install and update than Drupal 7 ever was. Think about that. Furthermore, Drupal will help showcase how one can democratize composability and advanced dependency management. I'm optimistic that in a few years, we'll realize that adopting Composer for dependency management was the correct decision, even if it was difficult initially.

Hundreds of people have been involved in climbing to reach this summit, and hundreds more outside of the Drupal project have influenced and guided our thinking. I'm grateful to everyone involved in helping to make Drupal more composable and easier to use for people worldwide. Thank you!

*Special thanks to Alex Bronstein, Christopher Wells, David Strauss, Derek Wright, Gábor Hojtsy, Lee Rowlands, Nathaniel Catchpole, Neil Drumm, Ted Bowman, Tim Lehnen, Tim Plunkett, Peter Wolanin, Wim Leers, and xjm for their contributions to this blog post. Taking a stroll down memory lane with you was a blast!*

*With the help of the above reviewers, I made an effort to acknowledge and give credit to those who deserve it. However, there is always a possibility that we missed significant contributors. If you have any corrections or additions, feel free to email me at <dries@buytaert.net>, and I'll update the blog post accordingly.*
