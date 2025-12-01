---
title: 'State of Drupal presentation (October 2021)'
date: '2021-10-13T09:00:05-04:00'
author: Dries
summary: 'DrupalCon Europe 2021 Driesnote presentation'
image: drupalcon-europe-2021/opening-slide
tags:
  - Drupal
  - DrupalCon
  - 'State of Drupal'
  - 'Drupal Association'
published: true
type: blog
url: /state-of-drupal-presentation-october-2021
id: 5236
---

Last week, Drupalists around the world gathered virtually for DrupalCon Europe 2021.

In good tradition, I delivered my [State of Drupal keynote](https://dri.es/tag/state-of-drupal). You can [watch the video of my keynote](https://youtu.be/VuSBnL_uG2I), [download my slides](https://dri.es/files/state-of-drupal-october-2021.pdf) (156 MB), or read the brief summary below.

[video VuSBnL_uG2I]

I talked about end-of-life schedules for various Drupal versions, delivered some exciting updates on Drupal 10 progress, and covered the health of the Drupal community in terms of contributor dynamics. Last but not least, I talked about how we are attracting new users and contributors by making it much easier to contribute to Drupal.

### Drupal 7 and Drupal 8 end-of-life

If you are using Drupal 7 or Drupal 8, time is of the essence to upgrade to Drupal 9. Drupal 7 end-of-life is scheduled for November 2022.

Drupal 8's end-of-life is more pressing, as it is scheduled for November 2nd, 2021 (i.e. in less than a month). If you are wondering why Drupal 8 is end-of-life before Drupal 7, that is because [we changed how we develop Drupal in 2016](https://dri.es/the-transformation-of-drupal-8-for-continuous-innovation). These changes have been really great for Drupal. They've made it much easier to upgrade to the latest version without friction.

As a community, we've spent thousands of hours building tools and automations to make migrating to Drupal 9 as simple as possible.

### Drupal 10 timeline

Next, I gave an update on Drupal 10 timelines. Timing-wise, our preferred option would be to ship Drupal 10 in June 2022. That date hinges on how much work we can get done in the next few months.

[image drupalcon-europe-2021/drupal-7-8-9-and-10-timelines]

### Drupal core strategic initiatives

After these timelines, I walked through the six strategic initiatives for Drupal core. We've made really great progress on almost all of them. To see our progress in action, I invited key contributors to present video updates.

[image drupalcon-europe-2021/core-initiative-progress]

#### Project Browser

You may recall that I introduced the [Project Browser](https://www.drupal.org/about/core/strategic-initiatives/project-browser) initiative in [my April 2021 State of Drupal presentation.](https://dri.es/state-of-drupal-presentation-april-2021) The idea is to make it easy for site builders to find and install modules right from their Drupal site, much like an app store on a smartphone. The goal of this initiative is to help more evaluators and site builders fall in love with Drupal.

Today, just six months later, we have a working prototype! Take a look at the demo video:

[video YG8PCkO1txc]

#### Decoupled Menus

Drupal is an excellent headless CMS with support for [REST, JSON:API and GraphQL](https://dri.es/headless-cms-rest-vs-jsonapi-vs-graphql).

As a next step in our evolution, we want to expand the number of web service endpoints Drupal offers, and build a large repository of web components and JavaScript framework integrations.

With that big goal in mind, we launched the [Decoupled Menus](https://www.drupal.org/project/decoupled_menus_initiative) initiative about one year ago. The goal was to create a small web component that could ship quickly and solve a common use case. We focused on one component so we could take all the learnings from that one component to improve our development infrastructure and policies to help us create many more web service end points and JavaScript components.

I talked about the various improvements we made to Drupal.org to support the development and management of more JavaScript components. I also showed that we've now shipped Drupal menu components for [React](https://reactjs.org/), [Svelte](https://svelte.dev/) and more. Take a look at the video below to see where we're at today:

[video lqruGTpH6mk]

Our focus on inviting more JavaScript developers to the Drupal community is a transformative step. Why? Headless momentum is growing fast, largely driven by the growth of JavaScript frameworks. Growing right along with it is the trend of *composability*, or the use of independent, API-first micro-services. Building more web service endpoints and JavaScript components extends Drupal's leadership in both headless development and composability. This will continue to make Drupal one of the most powerful and flexible tools for developers.

#### Easy Out of the Box

The goal of this initiative is to have [Layout Builder](https://dri.es/why-drupal-layout-builder-is-so-unique-and-powerful), [Media](https://dri.es/a-plan-for-media-management-in-drupal-8), and Claro added to the Standard Profile. That means these features would be enabled by default for any new Drupal user.

Unfortunately, we have not made a lot of progress on this initiative. In my presentation, I talked about how I'd like to find a way for us to get it done by Drupal 10. My recommendation is that we reduce the scope of work that is required to get them into Standard Profile.

#### Automatic Updates

The [Automatic Updates](https://www.drupal.org/project/automatic_updates) initiative's goal is to make it easier to update Drupal sites. Vulnerabilities in software, if left unchecked, can lead to security problems. Automatic updates are an important step toward helping Drupal users keep their sites secure.

The initiative made excellent progress. For the very first time, I was able to show a working development version:

[video q8TYLCocdf8]

#### Drupal 10 Readiness

The [Drupal 10 Readiness](https://www.drupal.org/about/core/strategic-initiatives/drupal10) initiative is focused on upgrading the third-party components that Drupal depends on. This initiative has been a lot of work, but we are largely on track.

[image drupalcon-europe-2021/drupal-10-300-percent-more-automated]

The most exciting part? The upgrade to Drupal 10 will be easy thanks to careful management of deprecated code and continued investment in [Rector](https://www.drupal.org/project/rector). As it stands, upgrading modules from Drupal 9 to Drupal 10 can almost be entirely automated, which is a big 300% improvement compared to the Drupal 8 to Drupal 9 upgrade.

#### New front end theme

We are nearly at the finish line for our new front end theme, [Olivero](https://www.drupal.org/about/core/strategic-initiatives/olivero). In the past few months, a lot of effort has gone into ensuring that Olivero is fully accessible, consistent with [our commitment to accessibility](https://dri.es/drupal-commitment-to-accessibility).

Olivero already received a glowing review from the [National Federation of the Blind](https://nfb.org/) (USA):

> Olivero is very well done and low-vision accessible. We are not finding any issues with contrast, focus, or scaling, the forms are very well done, and the content is easy to find and navigate.

Something to be really proud of!

### The health of Drupal's contribution dynamics

Next, I took a look at Drupal's contribution data. These metrics show that contributions are down. At first I panicked when I saw this data, but then I realized that there are some good explanations for this trend. I also believe this trend could be temporary.

[image drupalcon-europe-2021/contribution-metrics]

To learn more about why this was happening, I looked at the attrition rate of Drupal's contributors – the percentage of individuals and organizations who stopped contributing within the last year. I compared this data to industry averages for software and services companies.

[image drupalcon-europe-2021/contributor-attrition]

I was very encouraged by this data. It shows that we have a very strong, loyal and resilient community of contributors. While many of our top contributors are contributing less (see the full recording for more data), almost none of them are leaving Drupal.

There are a number of reasons for the slowdown in contribution:

- The COVID-19 pandemic has made contribution more difficult and/or less desirable.
- We are in the slow period of the "Drupal Super Cycle" – after every major release, work shifts from active development to maintenance.
- Anecdotally, many Drupal agencies have told me they have less time to contribute because they are growing so fast (see quotes in image below). That is great news for Drupal adoption.
- Drupal is a stable and mature software project. Drupal has nearly all the features organizations need to deliver state-of-the-art digital experiences. Because of Drupal's maturity, there are simply fewer bug fixes and feature improvements to contribute.
- [Rector](https://www.drupal.org/project/rector)-automations have led to less contribution. It's good to work smarter, not harder.

I'll expand on this more in my upcoming [Who sponsors Drupal development](https://dri.es/tag/drupal-sponsors) post.

<div class="large">
  [image drupalcon-europe-2021/drupal-agencies-too-busy-growing]
</div>

### The magic of contribution

I wrapped up my presentation by talking about some of the things that we are doing to make it easier to adopt Drupal. I highlighted [DrupalPod](https://github.com/shaal/DrupalPod) and [Simplytest](https://simplytest.me/) as two examples of amazing community-driven innovations.

[image drupalcon-europe-2021/drupalpod-simplytest]

After people adopt Drupal, we need to make it easier for them to become contributors. To make contribution easier, Drupal has started adopting [GitLab](https://about.gitlab.com/) in favor of our home-grown development tools. Many developers outside the Drupal ecosystem are accustomed to using tools like GitLab. Allowing them to use tools with which they are already familiar is an important step to attracting new contributors. Check out this video to get the latest update on our GitLab effort:

[video 3CTMdy4VNyU]

### Thank you

To wrap up I'd like to thank all of the people and organizations who have contributed to Drupal since the last DriesNote. It's pretty amazing to see the momentum on our core initiatives! As always, your contributions are inspiring to me!

[image drupalcon-europe-2021/thank-you]
