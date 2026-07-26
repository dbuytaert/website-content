---
url: 'https://dri.es/drupal-7-testing-status-update-and-next-steps'
title: 'Drupal 7 testing: status update and next steps'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2009-06-16T15:07:57-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: "Drupal 7's automated test framework has improved core development velocity, and Jimmy Berry's Acquia internship will extend testing to contributed modules and drupal.org infrastructure."
tags:
  - Drupal
  - Acquia
  - 'Automated testing'
published: true
featured: false
id: 675
---

# Drupal 7 testing: status update and next steps

The [first version of Drupal's automated test framework](https://cvs.drupal.org/viewvc.py/drupal/contributions/modules/simpletest/simpletest.module?revision=1.1&view=markup) was developed in 2004 by [Moshe Weitzman](http://www.tejasa.com). It started as a simple wrapper around the [SimpleTest unit testing framework](http://www.simpletest.org/).

Later, [Thomas Ilsche](https://www.drupal.org/user/26486) and [Rok Zlender](https://www.drupal.org/user/61873) extended it as part of the [Google Summer of Code projects](https://dri.es/google-to-invest-70000-usd-in-drupal) of 2005 and 2006. [NowPublic](http://www.nowpublic.com) and others continued to sponsor Rok's work into 2008.

Today, [Jimmy Berry](http://www.boombatower.com/) is the principal contributor to the Drupal test framework, as well as the main developer and maintainer of Drupal.org's automated test infrastructure. Behind the scenes, [Kieran Lal](https://www.drupal.org/user/18703) was instrumental in helping to ensure our test framework received financial support, project management, hardware resources, and server administrators.

In February 2008, I declared that [Drupal should embrace test-driven development](https://dri.es/embracing-test-driven-development), and shortly thereafter, [we added the test framework to Drupal 7 core](https://dri.es/we-have-a-test-framework-in-drupal-7). In addition to a test framework for core, [Jimmy Berry](http://www.boombatower.com/) and [Chad Phillips](https://www.drupal.org/user/22079) developed a second-generation automated testing framework for Drupal.org. So far, [it has tested over 8,500 unique patches](https://testing.drupal.org/pifr/stats) on Drupal.org.

Yesterday, [Jimmy announced that he will be working part-time as an intern for Acquia](http://blog.boombatower.com/acquia-internship) this summer. At [Acquia](https://www.acquia.com), we like what Jimmy is doing. Because he has been looking for a financial sponsor for a while, I decided Acquia should step up and help Jimmy for part of the summer.

Frankly, Jimmy's work has the potential to double the velocity of our developer community, and that is well worth sponsoring. Jimmy will spend his time with Acquia continuing his work on Drupal 7's test framework and the automated test infrastructure for Drupal.org.

For well over a year now, core development has used a test-driven development strategy combined with automated testing. I think all core developers working on Drupal 7 will agree when I say that our test infrastructure has drastically improved our velocity and effectiveness.

Overall, patches get accepted faster. The automated tests allow us to focus on the architectural and algorithmic changes introduced by a patch rather than having to worry about unexpected side effects. This helps both patch reviewers and core developers contributing patches.

Furthermore, thanks to the tests, we have a much better sense of the stability and health of Drupal 7. I am optimistic that our code freeze period for Drupal 7 could be shorter than those of prior releases. As the project lead, I sleep better at night because of our test framework. The stability and health of our codebase are important to me, but frankly, they are at least as important to the many Drupal users and to the people and organizations looking to adopt Drupal.

By adopting a test-driven development strategy, we raised the bar for core development, and I strongly believe we have to do the same for contributed modules. While the community cannot force module maintainers to write tests for their modules, I do want to support those who write tests.

The best way to support them is to provide them with the same tools and infrastructure that we use for core development. As the maintainer of a contributed module myself (i.e. the [Mollom module](https://www.drupal.org/project/mollom)), I can't wait to have access to the same tools I use when working on Drupal Core.

Jimmy is working on making Drupal.org's automated test infrastructure available to contributed modules, integrating the test results into project pages as an incentive tool, improving the documentation to help people get started, and closing some functional gaps, such as the ability to test Drupal's installer and upgrade system.

We're also working on deploying the third generation of the automated testing framework. This new version will make it easier to add testing servers so we can triple the number of servers available to run tests and start testing the non-MySQL backends that are supported by Drupal 7.

All in all, I'm very optimistic that we'll succeed in [our goal to adopt a test-driven development strategy](https://dri.es/embracing-test-driven-development).
