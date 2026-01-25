---
url: 'https://dri.es/we-have-a-test-framework-in-drupal-7'
title: 'We have a test framework in Drupal 7'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2008-04-21T11:10:13-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
  - Testing
published: true
id: 432
---

# We have a test framework in Drupal 7

Every major Drupal release we should ask ourselves what steps we can take to double the capacity of our community.

I spent the weekend in Paris where we had a two day code sprint. Our main accomplishment was getting Drupal's test framework into Drupal core – the culmination of three years of hard work carried out by many people and companies in the Drupal community.

[image drupalcamp-paris-2008/writing-tests-for-drupal]

Here is why a strong investment in testing will help double the capacity of our community:

- **For developers**, upgrading, maintaining and releasing your modules becomes easier. The combination of test results and code coverage reports makes it easier to determine the release readiness of your code. This translates to fewer betas, shorter code freeze periods and more frequent releases. Furthermore, *design for testability* leads to easier to use and more complete APIs. It is guaranteed to make Drupal a better development platform.
- **For end users**, it is important that we provide quantifiable reporting on the health of Drupal core and the many contributed modules.
- **For patch reviewers**, tests are great because it allows them to focus on the architectural and the algorithmic changes that the patch introduces. With good test coverage, we can rely on the tests to discover any unwanted side-effects. Patches can be committed faster.
- **For people new to Drupal**, tests lower the barrier to entry and encourage collaboration and innovation, two of Drupal's core values. With good test coverage, you don't necessarily have to understand the entire code base before you can comfortably propose changes or help maintain a module.
- **For me**, it means I'll sleep better at night. ;-) With hundreds of thousands of people using Drupal, the availability of a test framework takes some pressure of my shoulders.

As of today, it is expected that you submit test cases with your patches for Drupal 7. Writing good tests takes time: it is not unlikely that you'll spent twice as long working on a patch. This might take some time getting used to but you'll find that it pays off and that it is actually very rewarding.

Thanks to [Ori Pekelman of AF83](http://dev.af83.com/) for being such a great host when in Paris. And a special thanks to everyone who helped get the test framework in Drupal 7.
