---
title: 'Measuring Drupal core code complexity'
date: '2026-01-07T17:22:23-05:00'
author: Dries
image: miscellaneous-2025/vibe-coding-van/
tags:
  - Drupal
  - Statistics
featured: false
published: true
type: blog
url: /measuring-drupal-core-code-complexity
id: 6036
---

[image miscellaneous-2025/vibe-coding-van priority=true caption=false]

I built a dashboard that tracks [Drupal Core](https://www.drupal.org/project/drupal)'s code quality over time, across major releases from Drupal 7 through Drupal 11. It measures lines of code, cyclomatic complexity, maintainability index, anti-patterns, and API surface area. Think of it as a health report for Drupal's codebase. 

The dashboard updates automatically and is available at <a href="https://dbuytaert.github.io/drupal-core-metrics/">https://dbuytaert.github.io/drupal-core-metrics/</a>.

The charts tell a clear story of steady, hard-won progress. A story to be proud of and worth sharing. Code quality is dramatically better than it was in Drupal 7: lower complexity, easier to maintain, fewer anti-patterns, and dramatically better test coverage. Drupal now has nearly twice as much test code as production code!

Drupal Core's API surface has modernized too. As Drupal shifted from procedural to object-oriented patterns, global procedural functions gave way to classes implementing interface methods, services, plugins, and events.

By tracking these metrics publicly, I hope to inform decisions about both code quality and developer experience. When we refactor complex code, we can measure the impact. We can set goals and track progress. 

All charts use static code analysis. Static analysis can't measure the experience of learning Drupal, but it can hint at it. As a next step, I'd love to measure developer experience more directly. Dynamic analysis could help, for example by tracking call stack depth or how many files and APIs you need to touch to make a simple change.

The dashboard is open source, and contributions are welcome at [https://github.com/dbuytaert/drupal-core-metrics](https://github.com/dbuytaert/drupal-core-metrics).

*Special thanks to [catch](https://www.drupal.org/u/catch) for multiple rounds of feedback. As the most active Core Committer over the past 12 months, his input was invaluable.*
