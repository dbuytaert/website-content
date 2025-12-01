---
title: 'Code freeze and thresholds'
date: '2013-02-25T08:42:05-05:00'
author: Dries
tags:
  - Drupal
  - 'Software development'
published: true
type: blog
url: /code-freeze-and-thresholds
id: 2906
---

*Note: some of the information on this page is out of date. For the latest information about how Drupal releases are managed, see <https://www.drupal.org/core/release-cycle>.*

As of Monday, February 18, [Drupal 8 feature completion phase](https://dri.es/drupal-8-feature-freeze-extended) has officially ended. Since December 1, the original code freeze date, we've managed to add numerous awesome features that were previously in-progress, such as:

- WYSIWYG with CKEditor
- In-Place Editing
- Entity Reference Field
- Date and Time Field
- Revised content creation form
- Tour module to offer step-by-step help
- API support for Multilingual configuration
- Revamped and far more usable UI for configuring translatable entities and fields
- A RESTful API for entity CRUD in Drupal core
- Support for Views to be output in JSON, XML, or other formats made available by contributed modules
- Important under-the-hood improvements to allow for native ESI/CSI/SSI caching support in Drupal.

There are also a handful of [features that were RTBC by Feb 18](https://www.drupal.org/project/issues/search/drupal?text=&assigned=&submitted=&participant=&status%5B%5D=Open&version%5B%5D=8.x&issue_tags_op=or&issue_tags=RTBC+Feb+18), but not quite ready for commit. They are still undergoing consideration. All things considered, I'm glad we extended the code freeze.

### What happens now?

We now enter the ["clean-up" phase](https://dri.es/updated-drupal-8-release-schedule) of Drupal 8, where focus turns to refactoring of existing subsystems, better integrating features, and improving the consistency and coherence of the existing functionality. While APIs can and will still change as this coherence shapes up, contributed module authors are nevertheless encouraged to start porting their modules now, as there is still time to influence and fix APIs and the overall developer experience in Drupal 8. This will become much harder as we get closer to code freeze.

### So ... REALLY, what happens now?

In the course of adding all of the great features we've added so far to Drupal 8, we've accumulated some technical debt and are currently well over the [issue queue thresholds for Drupal core](https://dri.es/issue-queue-thresholds-for-drupal-core). We roll a release candidate of Drupal 8 when there are 0 critical bugs and tasks remaining. Our over-arching goal should therefore be to reduce the number of threshold issues over time.

At the same time, there are a lot of small, non-destabilizing features that would make Drupal 8 better. Especially for the kinds of iterative improvements that we would allow into 8.1 or 8.2, it doesn't make sense to hold those up until then, if we're able to get them into 8.0 without it delaying the 8.0 release date.

To help with this goal, catch and I have discussed a plan for allowing *some* features to continue to be committed to core up until RC1, providing we are under thresholds. To help guide us towards release, we plan to reduce the critical task/bug thresholds by one per week, starting the week of code freeze:

- July 1: 14
- July 8: 13
- July 15: 12
- ...
- September 2: 5
- September 9: 4
- September 16: 3
- **September 23: 2**

September 23 is the week of [DrupalCon Prague](https://prague2013.drupal.org/), and our goal would be to come out of the conference with a first Drupal 8 RC by fixing the last two critical bugs and two critical tasks (or however many there actually are) at the sprint. :-)

However, there are some caveats:

- Features can't require any new major/critical follow-ups, as that would impact the timing of release. In general, this means no new "big" features, as those tend not to be possible to accomplish without some fairly large follow-ups needed (e.g. Responsive Layout Builder, Project Browser, a new core theme, Symfony Form API). These kinds of issues will likely be moved to Drupal 9.
- Primarily, this means small, self-contained, iterative improvements that we'd be willing to backport to Drupal 8 (see <https://groups.drupal.org/node/210973>).
- Committer attention will generally be prioritized on tasks/bugs first, rather than features.

For now, we've decided to leave the major bugs/tasks threshold at 100 throughout release, and *not* tie them to the release date trigger for Drupal 8. I will re-evaluate this as we get closer to release.

### What isn't bound by thresholds?

We obviously want Drupal 8 to ship as a coherent product, so a major focus will be around better *integration* of existing features. For example, work required to get the Symfony pieces of Drupal working well with blocks and enabling ESI/CSI/SSI caching. Turning administrative pages into Views so that they can be better tuned for the task at hand. Completing conversions of major APIs such as Twig, new Entity API, CMI, and so on, to fix rough edges such as the inability to translate/in-place-edit node titles.

General guidance on what constitutes a task or a feature is available at <https://www.drupal.org/node/1181250>. As we work through the list of these integration items, some features may be recategorized into tasks. At the same time, some issues currently categorized as tasks go beyond strictly integration and polish and will be descoped or recategorized as features.

### Kudos!

While we still have a lot of work to do, I want to pause and give a sincere thanks to each and every one of the 1,077+ contributors to Drupal 8 so far. You've all done absolutely amazing work and helped establish Drupal 8 as a far more usable, flexible, designer-friendly, future-proof framework for all of us to use for the years to come. Now let's band together and get our baby polished up and out in the world for everyone to enjoy! :-)
