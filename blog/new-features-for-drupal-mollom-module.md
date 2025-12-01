---
title: "New features for Drupal's Mollom module "
date: '2010-02-16T03:54:17-05:00'
author: Dries
tags:
  - Drupal
  - Mollom
published: true
type: blog
url: /new-features-for-drupal-mollom-module
id: 1442
---

It's been a year since our last significant changes to the [Mollom module for Drupal](https://www.drupal.org/project/mollom), so we're excited to announce a major update. The most exciting new features in the new Mollom 1.11 release include:

- Enables use of Mollom for any form; with [Webform module integration](https://www.drupal.org/node/686136) almost completed
- Includes an embedded audio CAPTCHA player that works on all browsers
- Adds optional blacklist functionality to block spammers by text patterns and URLs
- Adds an optional link to Mollom's privacy policy from forms protected via textual analysis
- Adds support for serving CAPTCHAs over SSL (for Mollom Plus and Mollom Premium customers only)
- Makes Mollom compatible with Pressflow
- Integrates with CCK to change the position of the CAPTCHA field
- Provides many more unit tests for continuous integration testing
- Improves the APIs to enable module developers to better integrate with the Mollom module
- Implements various usability improvements (e.g., better permission names and better error messages)
- Updates several of the translations

We spent several months working on this release, and it marks our biggest upgrade to date. Upgrading requires some database updates, so remember to run `update.php`.

*Thanks to [Daniel F. Kudwien (sun)](http://www.unleashedmind.com/en/user/sun), [Dave Reid](https://www.drupal.org/user/53892) and [Keith Smith](https://www.drupal.org/user/85980) for their contributions to the 1.11 release.*
