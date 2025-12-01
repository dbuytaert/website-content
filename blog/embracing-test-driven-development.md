---
title: 'Embracing test-driven development'
date: '2008-02-15T02:37:31-05:00'
author: Dries
tags:
  - Drupal
  - Testing
published: true
type: blog
url: /embracing-test-driven-development
id: 404
---

At [DrupalCon Barcelona](https://dri.es/drupalcon-barcelona-wrapup) about 20 people gathered together for the Quality Assurance Birds of a Feather session. This led to the development of a [continuous testing infrastructure for Drupal](http://testing.drupal.org). People that want to write tests for Drupal can, but don't have to.

Second, in my [State of Drupal presentation at DrupalCon Barcelona](https://dri.es/state-of-drupal-presentation-september-2007), I shared a list of the top-10 most requested Drupal improvements. On spot 9 we had "better internal APIs" and on spot 10 we had "better external APIs (import/export, web services)". APIs that are designed for testability, are often better APIs. This comes from the fact that testability leads to more cohesive code with loose coupling. Important for readable, agile code.

Third, Drupal 6 has been in a code freeze for 6 month. Often times, the behavior introduced by one patch inadvertently breaks the behavior of existing functionality. In absence of tests, it takes a while to shake out all the bugs and before you're actually confident to roll a new major Drupal release.

As a result, people in the community have suggested to put more emphasis on testing in Drupal. Writing tests is expensive so it is hard to model the cost and benefits. However, the only way to past the costs and to experience the true benefits, is to take testing to the extreme. There is no middle ground. If we want to be serious about testing, we need to enforce, not just encourage, testing in the Drupal 7 development cycle and beyond. (And maybe we should consider introducing tests for Drupal 5 and Drupal 6 maintenance releases.)

In such a world, patches that fix bugs should come with a test case that demonstrates the behavior being fixed. That patch would then be added to the regression test suite and run continuously to avoid that the bug gets re-introduced. In addition, patches that add new features or enhancements should come with test cases for this new functionality. Everything should be tested.

Of course, this would require a significant commitment from the whole Drupal developer community. There is bound to be some controversy about the need to learn how to use [Drupal's test framework](https://www.drupal.org/project/simpletest) and the overhead and complications of having to write and submit a test. But over time, fewer people will be frustrated by bugs, the burden on patch reviewers will go down, code freezes will become shorter, APIs will continuously improve, and we would have more confidence in the stability of our releases. Last but not least, it actually improves overal productivity and encourages change and experimentation – something the Drupal community really takes pride in.

As [we learned before](https://dri.es/the-pain-before-the-payoff): sweeping changes are required to make major advances in technology, and often times there is a lot of pain before the pay-off. Are we willing to take some pain? Are we willing to enforce tests to be written as part of the Drupal 7 development process? I'm willing to fully embrace testing, but only if you are willing to write tests ...
