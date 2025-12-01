---
title: 'Drupal 6 support'
date: '2014-06-18T13:08:14-04:00'
author: Dries
tags:
  - Drupal
published: true
type: blog
url: /drupal-6-support
id: 3171
---

The policy of the Drupal community is to support only the current and previous stable versions of Drupal. If we maintain that policy, Drupal 6 support would be dropped the day that Drupal 8 is released. We'd only support Drupal 8 and Drupal 7.

We're changing that policy slightly as there are [still around 200K known Drupal 6 sites in the wild](https://www.drupal.org/project/usage/drupal), and we want to ensure that sites that wish to move from Drupal 6 to Drupal 8 have a supported window within which to upgrade.

The short version is that Drupal 6 core and modules will transition to unsupported status three months after Drupal 8 is released. A three month extension is not a lot, but continuing to support Drupal 6 is difficult for many reasons, including lack of automated test coverage. This gives Drupal 6 users a few options:

1. Upgrade to Drupal 7 any time between now and 3 months after Drupal 8.0.0 is released.
2. Upgrade to Drupal 8 after it is released, but before Drupal 6 is not supported anymore. There's already a Drupal 6 to Drupal 8 migration path in core which can be used for testing. Keep in mind though that if your site relies on contributed and custom modules, you may need to port the code and write the migration paths yourself if they're not done by the community in time for Drupal 8's release.
3. Find an organization that will provide extended support for Drupal 6. We hope that organizations that rely on Drupal 6 will step up to help maintain it after community support winds down. The Drupal Security Team will provide a method for companies or individuals to work together in the private security issue queue to continue developing updates, and will provide a reasonable amount of time for companies to provide patches to Drupal 6 security issues that also affect Drupal 7 or Drupal 8.

You can read the details on https://www.drupal.org/node/2288521.
