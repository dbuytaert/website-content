---
title: 'Drupal 7 testing: status update and next steps'
date: '2009-06-16T15:07:57-04:00'
author: Dries
tags:
  - Drupal
  - Acquia
  - Testing
published: true
type: blog
url: /drupal-7-testing-status-update-and-next-steps
id: 675
---

The [first version of Drupal's automated test framework](https://cvs.drupal.org/viewvc.py/drupal/contributions/modules/simpletest/simpletest.module?revision=1.1&view=markup) was developed in 2004 by [Moshe Weitzman](http://www.tejasa.com). It started as a simple wrapper around the [SimpleTest unit testing framework](http://www.simpletest.org/). Later, [Thomas Ilsche](https://www.drupal.org/user/26486) and [Rok Zlender](https://www.drupal.org/user/61873) extended it as part of the [Google Summer of Code projects](https://dri.es/google-to-invest-70000-usd-in-drupal) of 2005 and 2006. [NowPublic](http://www.nowpublic.com) and others continued to sponsor Rok's work into 2008. Today, [Jimmy Berry](http://www.boombatower.com/) is the principal contributor of the Drupal test framework, as well as the main developer and maintainer of Drupal.org's automated test infrastructure. Behind the scenes, [Kieran Lal](https://www.drupal.org/user/18703) was instrumental in helping to ensure our test framework received financial support, project management, hardware resources, and server administrators.

In the February 2008, I declared that [Drupal should embrace test-driven development](https://dri.es/embracing-test-driven-development), and shortly thereafter, [we added the test framework to Drupal 7 core](https://dri.es/we-have-a-test-framework-in-drupal-7). In addition to a test framework for core, [Jimmy Berry](http://www.boombatower.com/) and [Chad Phillips](https://www.drupal.org/user/22079) developed a second generation automated testing framework for drupal.org – so far, [it has tested over 8500 unique patches](https://testing.drupal.org/pifr/stats) on Drupal.org.

Yesterday, [Jimmy announced that he will be working part-time as an intern for Acquia](http://blog.boombatower.com/acquia-internship) this summer. At [Acquia](https://www.acquia.com), we like what Jimmy is doing, and because he has been looking for a financial sponsor for a while now, I decided Acquia should step up and help Jimmy for part of the summer. Frankly put, Jimmy's work has the potential of doubling the velocity of our developer community, and that is well worth sponsoring. Jimmy will spend his time with Acquia to continue his work on Drupal 7's test framework and the automated test infrastructure for drupal.org.

For well over a year now, core development has used a test-driven development strategy combined with automated testing. I think all core developers working on Drupal 7 will unanimously agree when I say that our test infrastructure has drastically improved our velocity and effectiveness. Overall, patches get accepted faster. The automated tests allow us to focus on the architectural and the algorithmic changes introduced by a patch, rather than having to worry about unexpected side-effects. This helps both patch reviewers and core developers contributing patches. Furthermore, thanks to the tests, we have a much better feel about the stability and the health of Drupal 7. I am optimistic that our code freeze period for Drupal 7 could be shorter than prior releases. As the project lead, our test framework helps me sleep better at night. The stability and health of our code base is important to me, but frankly, it is at least as important for the many Drupal users, or for those people and organizations looking to adopt Drupal.

By adopting a test-driven development strategy we raised the bar for core development, and I strongly believe we have to do the same for contributed modules. While the community cannot force module maintainers to write tests for their modules, I do want to support those that do write tests. The best way to support them, is to provide them the same tools and infrastructure that we use for core development. And as the maintainer of a contributed module myself (i.e. the [Mollom module](https://www.drupal.org/project/mollom)), I can't wait to have the same tools available that I have available when working on Drupal core.

Jimmy is working on making drupal.org's automated test infrastructure available to contributed modules, integrating the test results in the project pages as an incentive tool, improving the documentation to help people get started, and closing some functional gaps such as the ability to test Drupal's installer and upgrade system. We're also working on deploying the third generation of the automated testing framework. This new version will make it easier to add testing servers so we can triple the number of servers needed to run tests, and start testing the non-MySQL backends that are supported by Drupal 7.

All in all, I'm very optimistic that we'll succeed in [our goal to adopt a test-driven development strategy](https://dri.es/embracing-test-driven-development).
