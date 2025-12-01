---
title: 'Drupal 7 code freeze: status update and next steps'
date: '2009-10-30T15:34:47-04:00'
author: Dries
tags:
  - Drupal
published: true
type: blog
url: /drupal-7-code-freeze-status-update-and-next-steps
id: 1156
---

It was a close race to the finish – or rather the beginning – of the [Drupal 7 code freeze](https://dri.es/drupal-7-code-freeze-almost-upon-us) process a couple of weeks ago. Now that we're in the middle of the code freeze, I wanted to update everyone on the current status of the freeze, and provide some guidance about where we go from here.

First and foremost, I know that both Angie (my Drupal 7 co-maintainer) and I want to express how excited we are about how everyone really pulled together as a team at the end, and who, by working together, got a lot of great stuff in before the deadline for the "code slush" passed. Of the exceptions we had previously noted (see [slides for details](https://dri.es/files/drupal-7-code-freeze-plan.pdf)), eight of the ten made it in. The two stated exceptions that didn't are (1) allowing user profiles to use the field API, and (2) the administrative overlay (see screenshot). Since the overlays patch got incredibly close, Angie and I are committed to having this as part of the final release. There is now a further exception for getting overlays in, and I encourage everyone to keep [working on it](https://www.drupal.org/node/610234) as fast as possible.

[image drupal/drupal-7-overlay]

Other than changes necessary for the overlay, and a few left-over patches that were ready by the 10/15 deadline, we have now entered the next phase of the code freeze: no more API changes and no additional features. At this point, we focus exclusively on usability, accessibility, and performance. (If a performance, accessibility, or usability patch requires an API change, webchick and I will make a decision on a patch by patch basis.) This current phase was originally said to be four weeks from API freeze, but we're extending it to six weeks instead. The new deadline is December 1st, instead of November 15th.

My guidance at this point: depending on your strengths, and how involved you've been with the various issues in the past, please devote some time to [the overlay patch](https://www.drupal.org/node/610234), to [D7UX issues](https://www.drupal.org/project/issues/search/drupal?issue_tags=D7UX) and [usability issues](https://www.drupal.org/project/issues/search/drupal?issue_tags=Usability), to [accessibility issues](https://www.drupal.org/project/issues/search/drupal?issue_tags=accessibility), or to [performance-related](https://www.drupal.org/project/issues/search/drupal?text=&assigned=&submitted=&participant=&issue_tags_op=or&issue_tags=Performance) issues. For the remaining five weeks, that's where the action is. *Get involved now!*
