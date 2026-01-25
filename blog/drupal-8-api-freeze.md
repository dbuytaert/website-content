---
url: 'https://dri.es/drupal-8-api-freeze'
title: 'Drupal 8 API freeze'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2013-07-01T10:51:48-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
published: true
id: 2991
---

# Drupal 8 API freeze

July 1st has arrived. As announced earlier, this marks the start of the Drupal 8 API freeze (formerly known as the "code freeze"). I'm very excited about how Drupal 8 is shaping up; it will be a much more powerful and easier to use Drupal. While there is a lot of work ahead of us, I feel good about moving forward with the next phase of the Drupal 8 development cycle.

The two main goals of the "API freeze" are (a) to resolve release-blocking issues known as ["critical bugs"](https://www.drupal.org/project/issues/search/drupal?status%5B%5D=1&status%5B%5D=13&status%5B%5D=8&status%5B%5D=14&status%5B%5D=4&priorities%5B%5D=1&categories%5B%5D=bug&version%5B%5D=8.x) and ["critical tasks"](https://www.drupal.org/project/issues/search/drupal?status%5B%5D=1&status%5B%5D=13&status%5B%5D=8&status%5B%5D=14&status%5B%5D=4&priorities%5B%5D=1&categories%5B%5D=task&version%5B%5D=8.x) and (b) to provide developers with a stable API to port their modules from Drupal 7 to Drupal 8. This means that during the API freeze we will no longer make backwards compatibility-breaking changes to public APIs except when deemed that it is necessary to resolve important bugs or where the API has already been deprecated. Changes that do not break backwards compatibility are still allowed, including API additions, at the maintainers' discretion.

During this API freeze, we're also going to do a few things differently than we did with previous release cycles. I'll explain each of those changes below.

### Deprecating Drupal 7 APIs

Currently, Drupal 8 includes backwards compatibility layers that support Drupal 7 APIs while we complete conversions of core modules to the new Drupal 8 APIs. An example is the routing support in hook\_menu(), which will replaced by the Drupal 8 routing system. The Drupal 7 APIs are being marked deprecated in phpDoc, and contributed module developers should not use them because they will be removed prior to the Drupal 8 release.

### Deprecating Drupal 8 APIs

When appropriate, maintainers can still add new APIs to Drupal 8 that deprecate existing APIs. In this case, the deprecated APIs will continue to be supported and not be removed until Drupal 9. This is to avoid breaking contributed modules that have been upgraded to Drupal 8 already.

### Adding stand-alone features

A certain class of features may get committed despite being over [our commit thresholds](https://www.drupal.org/core/thresholds). The main criteria are that these features have to be self contained (no follow-up tasks) and easy to roll back (limited inter-module dependencies). If a single critical or major is filed as a result of these commits, we will favour rollback over going forward. As a result, these kind of features should have almost no impact on the rest of core development, nor introduce technical debt.

### The road to the first beta

During the API freeze, we will also switch from publishing alpha releases to beta releases. This will happen when there are no known [critical bugs in the upgrade path from the last Drupal 7 release](https://www.drupal.org/project/issues/search/drupal?status%5B%5D=1&status%5B%5D=13&status%5B%5D=8&status%5B%5D=14&status%5B%5D=4&priorities%5B%5D=1&categories%5B%5D=task&version%5B%5D=8.x).

Between API freeze and beta 1, removing temporary backward compatibility layers and deprecated Drupal 7 functions is allowed and encouraged. After beta 1, we get more strict about backward compatibility breaks (temporary backward compatibility layers and deprecated functions not removed by then might not be eligible for removal any more).

### Summary

After more than 2 years of non-stop work, it is pretty exciting to enter API freeze. It is a big milestone for all of us. Frankly, Drupal 8 will be our best release ever, by far, and I can't wait to get it in your hands. But we can't get Drupal 8 released without you. Please take a moment of your time to [download and try out the alpha releases](https://www.drupal.org/node/3060/release). If you are a module developer, make sure the things that are important to you are working, and working well so you can start [upgrading your modules](https://www.drupal.org/node/1911346) the day we start releasing betas. If you find a problem, please report it. Every bug you uncover is a chance to improve the experience for millions of users. Thank you, and we hope to see you in the issue queues!
