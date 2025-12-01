---
title: 'State of Drupal presentation (July 2020)'
date: '2020-07-20T07:38:59-04:00'
author: Dries
summary: 'DrupalCon Global Driesnote presentation'
image: drupalcon-global-2020/drupalcon-global-2020-driesnote
tags:
  - Drupal
  - DrupalCon
  - 'State of Drupal'
published: true
type: blog
url: /state-of-drupal-presentation-july-2020
id: 5051
---

[video RIeRpLgI1mM]

Last week, Drupalists from around the world gathered for [DrupalCon Global](https://events.drupal.org/global2020). This DrupalCon was the first ever virtual event of this scale for the Drupal community.

As a matter of tradition, I delivered the opening keynote. You can [watch a video recording of my keynote](https://youtu.be/RIeRpLgI1mM), [download a copy of my slides](https://dri.es/files/state-of-drupal-july-2020.pdf) (212 MB), or read the brief summary below.

<div class="large">
  [image drupalcon-global-2020/drupalcon-global-2020-live-view]
</div>

I announced that we are [targeting the release of Drupal 10 around June 2022](https://dri.es/drupal-10-target-release-date-and-drupal-9-end-of-life).

Next, I spent the majority of my presentation proposing five strategic initiatives for Drupal 10. While it seems early to speak about Drupal 10, we need to start working on these strategic goals now to have them ready by the time Drupal 10 is released.

[image drupalcon-global-2020/drupalcon-global-2020-goals]

We decided to go with just five initiatives so we're more focused and because [the Drupal 10 release cycle will be shorter than Drupal 9's](https://dri.es/drupal-10-target-release-date-and-drupal-9-end-of-life). Selecting only five initiatives was hard, but guided by the results of the [2020 Drupal Product Survey](https://dri.es/drupal-2020-product-survey) I launched earlier in the year.

If you'd like to do your own analysis of the survey data, you can [download a copy of the raw survey results](https://dri.es/files/state-of-drupal-survey-2020-raw.xlsx) (Microsoft Excel format) and look at the raw data yourself. I anonymized the data by removing the names, e-mail addresses and IP address information.

I spent 35 minutes walking the audience through the selection process. The five proposed initiatives:

1. Drupal 10 readiness
2. An easier out-of-the-box experience
3. A new front-end theme (Olivero)
4. Automated updates for security releases
5. An official JS menu component for React and Vue

### 1. Drupal 10 readiness

Drupal depends on third-party software components, many of which will go end-of-life (EOL) in the next few years. When a component goes EOL, it will no longer receive security support.

The "Drupal 10 Readiness" initiative will focus on upgrading these third-party components. Not only does this keep Drupal secure, it also allows us to take advantage of any new capabilities that come with these updated components.

[image drupalcon-global-2020/drupal-10-third-party-components]

### 2. Easy out-of-the-box

Improving Drupal's ease-of-use remains the number one most impactful item for the community to work on.

Drupal 9 dramatically improved Drupal's ease-of-use. Several of our most promising improvements made it very far, but still need some finishing touches. Specifically, our new Media Library, Layout Builder and Administration Theme (Claro) are not yet enabled by default.

I proposed the "Easy out-of-the-box" initiative to work towards *enabling these features by default*. I believe this initiative will be very impactful in terms of attracting new users to Drupal.

[image drupalcon-global-2020/drupal-10-easy-out-of-the-box]

### 3. Front end theme

One of the most important features to complete is our modern front end theme, Olivero. While there has been a lot of progress in this area, Olivero does not ship with Drupal yet. We want to make sure this beautiful front end theme is available by default.

[image drupalcon-global-2020/drupal-10-new-front-end-theme]

### 4. Automatic updates

As shown by the [Drupal 2020 Product Survey](https://dri.es/drupal-2020-product-survey), by far the most requested feature is automated updates.

Fortunately, it's something we have been working on for some time. Our first milestone will be to automate security updates so all site owners can sleep well at night, no matter when security releases are taking place.

Beyond security, automated updates help us work towards our long-term vision of building a composable – or [Assembed Web](https://dri.es/the-assembled-web) – architecture for Drupal.

[image drupalcon-global-2020/drupal-10-automated-updates]

### 5. JavaScript menu component

As I have been saying for years now, [many websites are evolving into personalized, omnichannel digital experiences](https://dri.es/from-content-management-to-digital-experience-management). It's a multi-decade trend, and one of the most powerful ones in our industry.

Drupal needs to keep evolving with this trend in mind. On the back end, we need to continue to make Drupal the best structured data engine and web service platform. On the front end, JavaScript continues to grow fast. While Drupal is recognized as a capable headless or decoupled CMS, there is still more we can do.

Furthermore, the second most requested feature in the [Drupal 2020 Product Survey](https://dri.es/drupal-2020-product-survey) was a more modern administration UI. These kinds of UIs are typically built using JavaScript and web service APIs. When done well, a JavaScript UI can offer major usability improvements.

Clearly, there is more than one reason to invest in web service APIs and to embrace more JavaScript in Drupal:

1. Many of Drupal's end users are focused on building decoupled front ends and omnichannel digital experiences.
2. Drupal could improve its own administration UI with more WYSIWYG, drag-and-drop, and other ease-of-use features.

To make a start toward improving Drupal's headless capabilities and administration UI, I proposed we start to add official Drupal JavaScript components to Drupal Core.

As a first step, I recommended implementing a JavaScript menu component in Vue and React. This would mark the first official JavaScript component in Drupal.

[image drupalcon-global-2020/drupal-10-javascript-menu-component-1]

Developing a JavaScript menu component solves a very real problem that many front end developers face. This menu component would render a menu and could be placed in a front end JavaScript application. The content of the menu comes from Drupal. This would allow content authors and non-developers to make simple menu changes without the need for custom code.

Releasing a first official JavaScript component will require us to set up the tools and processes to manage and release JavaScript components. This will establish a pattern or recipe for more components. Once we build one component, it will be easier to add many more in parallel.

[image drupalcon-global-2020/drupal-10-javascript-menu-component-2]

### Let's do this!

<div class="large">
  [image drupalcon-global-2020/drupal-10-press-release]
</div>

With [the release of Drupal 10 targeted for June 2022](https://dri.es/drupal-10-target-release-date-and-drupal-9-end-of-life), our community has a big opportunity to make the beginner and non-developer experiences much simpler, while still keeping Drupal's power as strong as ever for experts. I believe the proposed strategic initiatives will help achieve that.

For more details, I recommend you [watch the recording of my presentation](https://youtu.be/RIeRpLgI1mM).

Whether you're just getting started with Drupal or have been here for years, we want you to contribute to Drupal 10! The best way to get involved in any of these initiatives is to join their discussion channels on [Drupal Slack](https://www.drupal.org/slack):

- Drupal 10 readiness: `#d10readiness`
- Claro: `#admin-ui`
- Olivero: `#d9-theme`
- Automated updates: `#autoupdates`
- JS Menu Component: `#js-menu-component`

Thank you to everyone who attended the very first Drupalcon Global and contributed to the event's success. Even though we were unable to meet in person, I was blown away by the energy of everyone involved, and grateful for the time to connect with old and new friends.
