---
url: 'https://dri.es/updated-drupal-8-release-schedule'
title: 'Updated Drupal 8 release schedule'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2012-09-07T11:30:28-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
published: true
id: 2776
---

# Updated Drupal 8 release schedule

*Note: some of the information on this page is out of date. For the latest information about how Drupal releases are managed, see <https://www.drupal.org/core/release-cycle>.*

In talking to Drupal developers at DrupalCon, it was clear that there are some questions about the Drupal 8 feature freeze and code freeze. Questions like: What can we still work on after feature freeze? When do I start porting my Drupal modules to Drupal 8? When can I start testing Drupal 8? Let's address these questions and more in this blog post.

In addition to that, I am aligning our use of alpha and beta releases more inline with industry standards and changing the date of the code freeze, to leave more room to work on improving coherence. Lastly, I also wanted to document my expectations for contributed module developers/authors – when they are expected or encouraged to do what.

### During development phase (now to December 1)

Here are things we do while we're still in development; we aim to prioritize new features and major API changes.

- New features and major new APIs.
- Initial conversions of major new APIs, to ensure additional features are not needed to support them.
- Refactoring required to unblock additional functionality.

### During feature freeze (December 1 to April 1)

The goal of the feature freeze is to improve the implementation of existing features and to improve consistency and coherence of core by removing special cases, and unifying duplicate ways of doing things by converting core to use new APIs, etc.

During this phase we stop adding new subsystems. Refactoring of existing subsystems, smaller API changes and API additions are allowed if they help improve consistency and coherence of the existing functionality or are necessary in order to resolve specific critical tasks and bugs.

For example, the following are still welcome and encouraged during feature freeze:

- Completing conversions of `variable_X()` to CMI, and removing the variable system.
- Optimizing and cleaning up bootstrap by refactoring page caching and session handling to use Symfony components.
- Better integrating features added before feature freeze (e.g., integrating an existing Layout UI with existing context-aware Blocks, or Views with EntityFieldQuery).

We will start rolling *alpha* releases during the feature freeze. Contributed project authors who want to help improve the core APIs to better support their projects, can use these alpha releases to begin porting their modules, themes, and distributions. Core developers seek feedback and suggestions from contributed project authors on how to streamline the core APIs.

### During code freeze (April 1 to RC1)

The goal of the code freeze is to fix remaining bugs, and prepare for release. Improving coherence of the code base is no longer the goal. Hence, we discourage refactoring, and shift attention from things that are *nice to do* to things that we *must do*.

From the code freeze on, we will roll *beta* releases. Contributed project authors should use the beta releases to port and improve their projects. We encourage contributed authors to start early in the code freeze, as we can still make API changes, if necessary, to work around problems.

Site builders are encouraged to test new installations of Drupal 8 on their development servers.

From code freeze until RC1, we want to do this:

- Improve the Drupal 7 to Drupal 8 upgrade path
- Performance optimization
- Security hardening
- Minor UI improvements
- String and documentation improvements
- Other tasks that didn't get done by code freeze, but that core committers consider necessary; these will likely be marked as 'critical tasks'.

### Release Candidate to Release

We release a first Release Candidate when nearly all critical bugs and tasks are fixed, and a Drupal 7 to Drupal 8 upgrade path is functional. We aim to do this at least two months (around July, 2013) before the scheduled release date (around September, 2013).

We encourage Drupal 7 site owners to test the upgrade path and test contributed modules on their staging sites. We also encourage all contributed project authors to finalize their ports, with the goal of stable releases by Drupal 8.0's release date.

Our guiding principles during this phase of development:

- We try not to change Strings in order to preserve translator efforts.
- We try not to change UI in order to preserve documentation efforts.
- We try to support RC to RC upgrades, in order to help early adopters.
- We try to avoid breaking APIs except in the case of a critical issue.

*Special thanks to Nathaniel Catchpole ([catch](https://www.drupal.org/user/35733)), Angie Byron ([webchick](https://www.drupal.org/user/24967)), Alex Bronstein ([effulgentsia](https://www.drupal.org/user/78040)) and Moshe Weitzman ([moshe](https://www.drupal.org/moshe)) for their input. I'll continue to evolve these guidelines so more feedback is always welcome.*
