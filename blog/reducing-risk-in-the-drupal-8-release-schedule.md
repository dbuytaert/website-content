---
title: 'Reducing risk in the Drupal 8 release schedule'
date: '2013-05-08T21:22:40-04:00'
author: Dries
tags:
  - Drupal
published: true
type: blog
url: /reducing-risk-in-the-drupal-8-release-schedule
id: 2951
---

Post-Drupal 8's feature freeze, we find ourselves in a similar state as we did after Drupal 7's feature freeze:

- Some initiatives are mostly done, and now onto clean-ups.
- Others are mostly architecturally there, but still have some pretty big gaps.
- Still others are either not yet architecturally complete, have a major amount of integration/conversion work left, and/or have many outstanding critical/major bugs.

From here on out, we need to be more strategic about what patches we do and do not allow into Drupal core directly, and this means we have to make some tough decisions. Every patch we commit needs to not move Drupal 8 further from a "shippable state".

There are essentially two categories of initiatives (both official and unofficial) that are incomplete:

1. Code already in HEAD, that we do not plan on reverting, and completion of which is critical to releasing Drupal 8. Examples are [CMI](https://www.drupal.org/node/1775842), [Entity NG](https://www.drupal.org/node/1818580), [Router](https://www.drupal.org/node/1971384) conversions. Incremental patches committed to these issues help move Drupal towards release.
2. Code *not* currently in HEAD, or libraries that are sitting around effectively unused by the rest of Drupal. Examples are [Twig](https://www.drupal.org/node/1757550), [CSS re-organization](https://www.drupal.org/node/1921610), and [parts of SCOTCH](https://www.drupal.org/node/1812720). Incremental patches committed to these issues move Drupal towards "uncharted territory", and could put the release of Drupal 8 at risk.

Therefore, the core committers plan to employ the following strategy when deciding what we do/don't commit to Drupal 8 going forward:

[image drupal/commit-decision-flowchart no-resize no-resize]

First, a patch will be evaluated to see if it belongs to a larger "meta" issue. For the vast majority of issues in the Drupal 8 queue, the answer will be no. For example, routine bug fixes and self-contained DX (Developer Experience) improvements can simply be committed once they're ready.

If an issue *is* part of a larger meta issue, the question will be whether that meta issue is *critical* to shipping Drupal 8. If so, the "does this move us towards release?" question is satisfied, and these patches will be committed as they're ready. An example of this is individual CMI conversions; we cannot ship Drupal 8 without all parts of it being deployable through the configuration management system. Similarly, we cannot ship with two methods of declaring routes.

If the meta issue is *not* deemed critical for release, but we can still ship Drupal 8 with part of it done, then we will also commit patches as they're ready. Views conversions are a good example of this. While it would be nice to ship Drupal 8 with all administrative pages converted to Views, we can still ship Drupal 8 with some converted and others not.

If the patch is part of a larger, non-critical meta issue, but getting part of it done is worse than getting none of it done (an incomplete state will hold up release of Drupal 8), then we're in a "danger zone" and need to look at possible options:

1. First, we should see if the patch can be re-worked, or parts of it split off, into self-contained issues. Then those issues' patches can just be committed via the normal process.
2. If there is no other option than completing the entire meta issue, then core maintainers will work with each individual team to determine a "cut-off date" for their work (which allows sufficient time prior to July 1 for integration), as well as the safest way for their work to continue without holding up the release. Possible strategies could include:
   
   
   - A larger patch containing the meta issue in its entirety, with no follow-ups, where it is still feasible to use a patch-based workflow (e.g. CSS re-organization).
   - A branch off the Drupal core repository that is merged in when deemed acceptable in the case of larger conversion efforts (e.g. Twig)
   - A sandbox project where larger refactoring is still necessary (e.g. SCOTCH).
    
   If the work is ready *in its entirety* (i.e. working upgrade path, passing all core gates) by the cut-off date, it will be eligible for Drupal 8. However, if not ready in time, it will have to be postponed to Drupal 9. While this is definitely painful for teams that have worked so hard but yet still miss the deadline, it is preferable to delaying the Drupal 8 release indefinitely.

### Summary

The bottom line is that every patch we commit to Drupal 8 from now on has to help us get to a **shippable state**: it has to work, be performant (or be a *required* stepping stone towards more performant code), be well-documented and well-tested, and provide the right developer experience (DX). Getting Drupal 8 ready for release will take a big effort, and the core contributors could use all the help they can get. Now is the time to [jump in and help](https://www.drupal.org/community-initiatives/drupal-core).
