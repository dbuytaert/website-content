---
title: 'Issue queue thresholds for Drupal core'
date: '2011-08-04T05:31:37-04:00'
author: Dries
tags:
  - Drupal
published: true
type: blog
url: /issue-queue-thresholds-for-drupal-core
id: 2466
---

In the ongoing efforts to [build on lessons learned during the Drupal 7 cycle](https://dri.es/drupal-7-development-process-retrospective-summary) and [fast-track Drupal 7 bug fixes](https://dri.es/fast-tracking-drupal-7-bug-fixes), a new policy has been introduced to help ensure stability of the code base, based on recommendations by key members of the core contributor team, most notably [Nathaniel "catch" Catchpole](https://www.drupal.org/user/35733).

During my [keynote at DrupalCon Chicago](https://dri.es/state-of-drupal-presentation-march-2011), I introduced a new "cap" of 15 on the number of critical bugs. If the number of critical bugs creeps higher than this, no new features or clean-up patches would be committed until the bug count went back down below the threshold. This would ensure that serious bugs are able to be addressed without having to "chase" the code base due other patches performing major under-the-hood refactoring.

However, it became clear that this was not sufficient. Despite heroic efforts on bringing the number of critical bugs to zero before launch, Drupal 7 still shipped with several hundred "major" bugs. While this situation has dramatically improved since launch, it is important to keep this number down, so that when Drupal 8 is released it is stable and ready to go. Additionally, sometimes bugs are fixed or features introduced that do not perform requisite refactoring of underlying systems, and we accumulate "technical debt". This technical debt makes the code base more complex and difficult to understand, and makes Drupal harder to approach for new developers.

Going forward, new features and other major refactoring patches will only be committed to Drupal 8 if the following conditions are met:

- [Critical bugs, across D7 and D8](https://www.drupal.org/project/issues/search/drupal?status%5B%5D=1&status%5B%5D=13&status%5B%5D=8&status%5B%5D=14&status%5B%5D=15&priorities%5B%5D=1&categories%5B%5D=bug&version%5B%5D=8.x&version%5B%5D=7.x): no more than 15
- [Major bugs, across D7 and D8](https://www.drupal.org/project/issues/search/drupal?status%5B%5D=1&status%5B%5D=13&status%5B%5D=8&status%5B%5D=14&status%5B%5D=15&priorities%5B%5D=4&categories%5B%5D=bug&version%5B%5D=8.x&version%5B%5D=7.x): no more than 100
- [Critical tasks, across D7 and D8](https://www.drupal.org/project/issues/search/drupal?status%5B%5D=1&status%5B%5D=13&status%5B%5D=8&status%5B%5D=14&status%5B%5D=15&priorities%5B%5D=1&categories%5B%5D=task&version%5B%5D=8.x&version%5B%5D=7.x): no more than 15
- [Major tasks, across D7 and D8](https://www.drupal.org/project/issues/search/drupal?status%5B%5D=1&status%5B%5D=13&status%5B%5D=8&status%5B%5D=14&status%5B%5D=15&priorities%5B%5D=4&categories%5B%5D=task&version%5B%5D=8.x&version%5B%5D=7.x): no more than 100

See also the [Drupal core code freeze, code thaw, issue queue thresholds](https://www.drupal.org/node/1201874) documentation page for more information. The "Contributor links" dashboard block on Drupal.org now also contains these counts for easy reference.

The hope is that this will allow us to strike a balance between innovation in the future Drupal release, and stability in the stable Drupal release of today, which will in turn help increase Drupal 7 adoption.
