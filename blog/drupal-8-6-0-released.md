---
title: 'Drupal 8.6.0 released'
date: '2018-09-06T03:23:35-04:00'
author: Dries
summary: 'Learn what is new in Drupal 8.6.0, and how content authors, evaluators and developers can all take advantage.'
image: drupal/drupal-8-6-layout-builder
tags:
  - Drupal
published: true
type: blog
url: /drupal-8-6-0-released
id: 4501
---

Last night, we shipped Drupal 8.6.0! I firmly believe this is the most significant Drupal 8 release to date. It is significant because we made a lot of progress on [all twelve of Drupal 8 core's strategic initiatives](https://www.drupal.org/about/strategic-initiatives). As a result, Drupal 8.6 delivers a large number of improvements for content authors, evaluators, site builders and developers.

## What is new for content authors?

For content authors, Drupal 8.6 adds support for "remote media types". This means you can now easily embed YouTube or Vimeo videos in your content.

[image drupal/drupal-8-6-media-library]

Content authors want Drupal to be easy to use. We made incredible progress on a variety of features that will help to achieve that: we've delivered an experimental media library, added [the Workspaces module](https://dri.es/an-update-on-the-workflow-initiative-for-drupal-8-4-8-5) as experimental, providing sophisticated content staging capabilities, and made great strides on the upcoming Layout Builder. The Layout Builder is shaping up to be a very powerful tool that solves a lot of authoring challenges, and is something many are looking forward to.

[image drupal/drupal-8-6-workspaces]

Each initiative related to content authoring is making disciplined and steady progress. These features not only solve for the most requested authoring improvements, but provide a solid foundation on which we can continue to innovate. This means we can provide better compatibility and upgradability for contributed modules.

[image drupal/top-requests-for-content-authors-2016 resize=false]

## What is new for evaluators?

Evaluators want an out-of-the-box experience that allows them to install and test drive Drupal in minutes. With Drupal 8.6, we have finally delivered on this need.

Prior to Drupal 8.6, [downloading and installing Drupal was a complex and lengthy process](https://dri.es/three-ways-we-can-improve-drupal-evaluator-experience) that ended with an underwhelming "blank slate".

Now, you can install Drupal with the new "Umami demo profile". The Umami demo profile showcases some of Drupal's most powerful capabilities by providing a beautiful website filled with content right out of the box. A demo profile will not only help to onboard new users, but it can also be used by Drupal professionals and digital agencies to showcase Drupal to potential customers.

[image drupal/drupal-8-6-layout-builder]

In addition to a new installation profile, we added a "quick-start" command that allows you to launch a Drupal site in one command using only one dependency, PHP. If you want to try Drupal, you no longer have to setup a webserver, a database, containers, etc.

Last but not least, the download experience and evaluator documentation on Drupal.org has been vastly improved.

With Drupal 8.6, you can download and install a fully functional Drupal demo application in less than two minutes. That is something to be very excited about.

## What is new for developers?

You can now upgrade a single-language Drupal 6 or Drupal 7 site to Drupal 8 using the built-in user interface. While we saw good progress on multilingual migrations, they will remain experimental as we work on the final gaps.

I recently wrote about our [progress in making Drupal an API-first platform](https://dri.es/how-drupal-continues-to-evolve-towards-an-api-first-platform), including an overview of REST improvements in Drupal 8.6, an update on JSON API, and the reasons why JSON API didn't make it into this release. I'm looking forward to JSON API being added in Drupal 8.7. Other decoupled efforts, including [a React-based administration application](https://dri.es/working-toward-a-javascript-driven-drupal-administration-interface) and GraphQL support are still under heavy development, but making rapid progress.

We also converted almost all of our tests from SimpleTest to [PHPUnit](https://phpunit.de); and we've added [Nightwatch.js](http://nightwatchjs.org) and [Prettier](https://prettier.io) for JavaScript developers. While Drupal 8 has extensive back-end test coverage, using PHPUnit and Nightwatch.js provides a more modern platform that will make Drupal more familiar to PHP and JavaScript developers.

## Drupal 8 continues to hit its stride

These are just some of the highlights that I'm most excited about. If you'd like to read more about Drupal 8.6.0, check out [the official release announcement](https://www.drupal.org/blog/drupal-8-6-0) and [important update information from the release notes](https://www.drupal.org/project/drupal/releases/8.6.0). The next couple of months, I will write up more detailed progress reports on initiatives that I didn't touch upon in this blog post.

In my [Drupal 8.5.0 announcement](https://dri.es/drupal-8-5-0-released), I talked about how Drupal is hitting its stride, consistently delivering improvements and new features:

> In future releases, we plan to add a media library, support for remote media types like YouTube videos, support for content staging, a layout builder, JSON API support, GraphQL support, a React-based administration application and a better out-of-the-box experience for evaluators.

As you can see from this blog post, Drupal 8.6 delivered on a number of these plans and made meaningful progress on many others.

In future releases we plan to:

- Stabilize more of the features targeting content authors
- Add JSON API, allowing developers to more easily and rapidly create decoupled applications
- Provide stable multilingual migrations
- Make big improvements for developers with Composer and configuration management changes
- Continually improve the evaluator experience
- Iterate towards an entirely new decoupled administrative experience
- ... and more

Releases like Drupal 8.6.0 only happen with the help of hundreds of contributors and organizations. Thank you to everyone that contributed to this release. Whether you filed issues, wrote code, tested patches, funded a contributor, tested pre-release versions, or cheered for the team from the sidelines, you made this release happen. *Thank you!*
