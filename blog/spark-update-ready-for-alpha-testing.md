---
title: 'Spark update: ready for alpha testing'
date: '2012-08-16T13:49:48-04:00'
author: Dries
tags:
  - Drupal
  - 'Spark distribution'
published: true
type: blog
url: /spark-update-ready-for-alpha-testing
id: 2751
---

The [Spark distribution](https://www.drupal.org/project/spark) is a Drupal 7 distribution which aims to prototype cutting-edge authoring experience improvements that we hope to propose for inclusion in Drupal 8 core. Since [we announced Spark](https://dri.es/announcing-spark-authoring-improvements-for-drupal-7-and-drupal-8) back in May, we've shown videos of prototypes of [inline editing](https://dri.es/spark-update-in-line-editing-in-drupal), [responsive layout building](https://dri.es/spark-update-responsive-layouts-in-drupal) and [mobile administration](https://dri.es/spark-update-mobile-administration-in-drupal). The rest of the Spark team (Angela Byron, Kevin O'Leary, Wim Leers, Gábor Hojtsy, Jesse Beach, Preston So and Dharmesh Mistry) has also been working hard to make these designs a reality.

There has been a lot of great progress over the past months, and with the release of [Spark 7.x-1.0-alpha4](https://www.drupal.org/node/1724152), Spark is now ready for some community testing! Each module/theme that Spark builds upon is a separate, standalone contributed project that can be integrated into existing sites. This alpha release includes:

- **Inline Editing**, courtesy of [Edit module](https://www.drupal.org/project/edit). You can click into a node, switch the "View / Edit" toggle in the toolbar, and then click directly into any field to edit its contents, instead of having to be redirected to the backend.
- **True WYSIWYG**, courtesy of [Aloha Editor](http://www.alohaeditor.org/). Edit your rich text with your theme's direct styling through the inline editor. It even works with images + captions, links directly to content in the site, and has basic support for tokenized strings.
- **Responsive Layout Builder**, courtesy of the [Layout](https://www.drupal.org/project/layout) and [Gridbuilder](https://www.drupal.org/project/gridbuilder) modules. You can configure layouts for separate breakpoints (e.g. Mobile, Tablet, Desktop) and even define your own grids for them to snap to. These technologies layer on top of [Panels](https://www.drupal.org/project/panels),though it's been architected so it could be integrated with other layout solutions as well.
- **New admin theme**, brought to you by [Ember](https://www.drupal.org/project/ember). This brings some nice light styling on Drupal core's Seven admin theme as well integrating the [Admin module](https://www.drupal.org/project/admin) to better support mobile devices. A more fleshed out mobile toolbar and administrative experience is slated for implementation soon.

If you'd like to try the distribution out without downloading and installing it, check our demo site at <http://demo.sparkdrupal.com>. (Note that since this site is open to anyone, it might look a bit funny at any given time. If things are really broken, please check back later.)

There is still much to do, but hopefully this release will provide a good understanding of the direction Spark is taking, and what we hope to propose for inclusion in Drupal 8 core. We greatly welcome feedback, bug reports and patches in the [Spark issue queue](https://www.drupal.org/project/issues/spark).

At DrupalCon Munich next week, we'd love to talk more about how we can move some of these things into Drupal 8 core. We've setup [various Spark sessions and BoFs at DrupalCon Munich](http://webchick.net/node/110) to plan and brainstorm about this.
