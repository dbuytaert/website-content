---
title: 'A plan for Drupal 11'
date: '2022-05-09T16:27:11-04:00'
author: Dries
image: drupalcon-portland-2022/drupal-11-composable-core
tags:
  - Drupal
published: true
type: blog
url: /a-plan-for-drupal-11
id: 5331
---

Two weeks later, I'm still feeling the energy from our first in-person DrupalCon in two years!

This blog post is Part 3 of my DrupalCon keynote recap. In case you missed it, you can read up on [Part 1](https://dri.es/state-of-drupal-presentation-april-2022) and [Part 2](https://dri.es/drupal-is-for-ambitious-site-builders). Part 1 focused on [Drupal 10 updates](https://dri.es/state-of-drupal-presentation-april-2022). Part 2 talked about [our new vision statement](https://dri.es/drupal-is-for-ambitious-site-builders).

In my keynote, I also mapped out a potential strategy for Drupal 11. In this blog post, I explain Drupal 11's strategy, and how it aligns with our updated vision statement.

[image drupalcon-portland-2022/drupal-11-composable-core]

Drupal 11's strategy is focused on (1) empowering ambitious site builders and (2) accelerating innovation in our contributed modules repository.

To accomplish these two goals, Drupal will have to double down on "composability", which is reflected by the six proposed initiatives below. I'm code-naming the two-year strategy for Drupal 11 "Composable Core".

<div class="large">
  [image drupalcon-portland-2022/drupal-11-strategy resize=false]
</div>

### Project Browser

In Drupal 9, we have over 8,000 modules and themes. In those 8,000 projects are some amazing innovations. But right now, it's hard for site builders to find them.

Many first-time adopters don't even realize Drupal can be extended with all these contributed modules and themes. Some site builders even give up on Drupal because once Drupal is installed, they don't know what to do next.

So, we have an opportunity to make all these great innovations easier to find. The [Project Browser Initiative](https://www.drupal.org/about/core/strategic-initiatives/project-browser) would recommend or highlight great Drupal modules to use. It would also enable a one-click install process.

Under the hood, modules are still installed with [Composer](https://getcomposer.org/), making them easy to maintain and update.

Check out this video to learn more about Project Browser:

[video ZL5WfAsE1MQ]

### Starter Templates

While Project Browser would help site builders discover and install individual modules, it is not unusual to use 30+ contributed modules to build a site. It can take a lot of work to find and configure these modules, and to make sure they all work well together.

This is where the new Starter Templates concept comes in. Starter Templates are about installing and configuring groups of modules. For example, Starter Templates for an event website or a product website would include all of the necessary modules and configuration required for that type of website.

This concept bears a lot of resemblance with Drupal's 15-year-old concept of [Drupal distributions](https://dri.es/tag/drupal-distributions). The goal of Starter Templates, however, is to be a lot easier to build and maintain than distributions.

[image drupalcon-portland-2022/drupal-site-starter-templates]

We don't know yet how exactly we'd implement Starter Templates, but we have [some initial ideas](https://www.drupal.org/project/ideas/issues/3274999). Join the [\#distributions-starter-templates Slack channel](https://drupal.slack.com/archives/C2THUBAVA) if you're interested in contributing.

### Automated Updates

For Drupal 11, we will continue our work on the [Automated Updates Initiative](https://www.drupal.org/about/core/strategic-initiatives/automatic-updates), which is meant to make updates to Drupal much easier.

Check out the video below for an update on Drupal's Automated Updates initiative:

[video mH2THdCRuJI]

### GitLab Initiative

Accelerating innovation by empowering contributors continues to be a key priority for Drupal. We will keep working on the [GitLab Initiative](https://www.drupal.org/drupalorg/roadmap/gitlab-acceleration) to bring better collaboration and development tools to Drupal contributors.

Check out this video for the latest on the GitLab Initiative:

[video 5hTKuNVSPfU]

### The Great Module Migration

This proposed initiative focuses on making Drupal Core smaller. How? By *responsibly* moving more modules from core to contrib. This mean less code to maintain in core, so that Drupal can focus on innovation. Certain modules can also innovate faster as a contributed module.

To evaluate which core modules we might migrate, we developed [a ranking system](https://www.drupal.org/project/ideas/issues/3279792). The system evaluates each module's capabilities, adoption, strategic value, and maintenance effort.

Based on this early ranking system, we found that we could remove approximately 16 modules from core and keep approximately 64. Some of these modules could already be removed in Drupal 10. Drupal 11 could be 20% smaller compared to Drupal 9.

We believe it's safe to make core smaller, especially with a strong focus on Project Browser, Starter Templates and Automatic Updates.

### Drupal 11 readiness

As a part of Drupal 11 readiness, we will continue to manage our third-party dependencies to keep Drupal secure.

### Should we do more?

I'd love to see us do more in Drupal 11. I wish we could invest in embracing web components, building a decoupled administration backend, modernizing Views, and much more.

Investment like this often require small teams of dedicated developers; i.e. 3-5 developers for 6 to 12 months.

To get even more done for Drupal 11, it's important that organizations consider paying Drupal developers to work on larger, long-term contributions.

I covered this concept in past blog posts, such as [the privilege of free time in Open Source](https://dri.es/the-privilege-of-free-time-in-open-source) and [balancing Makers and Takers to sustain Open Source](https://dri.es/balancing-makers-and-takers-to-scale-and-sustain-open-source).

In the next year, the [Drupal Association](https://www.drupal.org/association) will start taking additional steps towards incentivizing larger contributions. Needless to say, I'm very excited about that. Stay tuned for more on that topic.

### Let's get building

The early planning phases of a new release are an exciting time to discuss Drupal's potential for the future, and focus on ideas that will make the most impact for our users. I'm excited for us all to collaborate on Drupal 11 in the coming years.
