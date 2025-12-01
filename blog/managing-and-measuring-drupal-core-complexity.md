---
title: 'Managing and measuring Drupal core complexity'
date: '2011-09-19T13:52:33-04:00'
author: Dries
tags:
  - Drupal
published: true
type: blog
url: /managing-and-measuring-drupal-core-complexity
id: 2496
---

While we made Drupal 7 easier to use and more feature-rich for site builders, we also added complexity for the core developers. We shouldn't be surprised though. As a software application evolves, its complexity increases unless work is done to maintain or reduce it.

When that happens, it is can be frustrating as software complexity is an obstacle to introducing change, can be a source of bugs and makes it harder for new contributors to get involved. The general sentiment among the core developers is that steps must be taken to reduce Drupal's complexity. I wholeheartedly agree.

Many people in the community put forward a lot of good suggestions to reduce the complexity of Drupal core; from removing unnecessary functionality, to decoupling systems, to improving our APIs and abstractions. All things we should consider doing. In fact, we have already removed some unnecessary modules and features from the Drupal 8 development branch. Last but not least, I'm looking to appoint a Drupal 8 co-maintainer that has the technical skillset to help manage Drupal core's complexity.

I also had a thought I wanted to run by you. It would be good if we could measure the evolution of Drupal's complexity over time. That would allow us to say things like: "Drupal 7 is 30% more complex compared to Drupal 6", "This Drupal site build has a complexity score of 420", or "This patch reduces the complexity by 12 points".

I'd like to see if we can come up with a "Drupal complexity score". It would obviously be important to combine different metrics such as (1) number of calls per function, (2) number of inter-module calls per function, (3) mean function size, (4) number of input arguments for API functions, (5) number of comments per function, (6) number of references to global variables, (7) number of different code paths, etc.

A "Drupal complexity score" is not the panacea, and neither will we ever have a perfect scoring system. However, I still believe that even a basic "Drupal complexity score" integrated in the patch review workflow (including our testbots and DrEditor) would be a big win. It is hard to manage what you can't measure. At a minimum, it would put reducing complexity at the front and center of every reviewer and maintainer.

Thoughts?
