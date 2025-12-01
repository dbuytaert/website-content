---
title: 'Drupal 10 target release date and Drupal 9 end-of-life'
date: '2020-07-15T08:17:52-04:00'
author: Dries
summary: "We are targeting to release Drupal 10 around June 2022 and will end-of-life Drupal 9 around November 2023.  Don't worry: we'll make it easy to upgrade to Drupal 10."
image: drupal/drupal-10-targeted-for-june-2022
tags:
  - Drupal
published: true
type: blog
url: /drupal-10-target-release-date-and-drupal-9-end-of-life
id: 5046
---

We are targeting to release Drupal 10 around June 2022. That is less than two years from the day of this post.

[image drupal/drupal-10-targeted-for-june-2022]

### Why June 2022, you ask?

Drupal 9's biggest dependency is Symfony 4, which has an end-of-life date in November 2023. This means that after November 2023, security bugs in Symfony 4 will not get fixed. Drupal has to adopt Symfony 5 (or later) and end-of-life Drupal 9 no later than November 2023.

For security purposes, all Drupal 9 users will need to upgrade to Drupal 10 by November 2023. We like to give site owners at least one year to upgrade from Drupal 9 to Drupal 10, therefore we are targeting Drupal 10 to be released in June 2022.

[video umnGfAe9dvs]

### Will the upgrade to Drupal 10 be easy?

Yes, it will be easy, and here is why.

New functionality for Drupal 10 is actually added to Drupal 9 releases. This means module developers can start adopting any new APIs right away. Along the way, we deprecate old functionality but keep backwards compatibility. Once we are ready to release Drupal 10, we remove all deprecated code. Removing deprecated code breaks backwards compatibility, but because module developers had a chance to stay up to date with API changes, the upgrade to Drupal 10 should be easy.

If that makes your head spin, think of it this way: Drupal 10 is identical to the last version of Drupal 9, with its deprecations removed. Because of that, there should be no last-minute, big or unexpected changes.

We used this approach for Drupal 9, and it was successful: 95 of the top 100 contributed modules were ready the day Drupal 9.0.0 was released. We know from Drupal 9 that this approach to upgrades works, and we'll continue to refine it going forward.
