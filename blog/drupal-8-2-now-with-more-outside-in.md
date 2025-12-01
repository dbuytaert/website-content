---
title: 'Drupal 8.2, now with more outside-in'
date: '2016-08-23T03:10:44-04:00'
author: Dries
tags:
  - Drupal
  - Usability
  - Outside-in
published: true
type: blog
url: /drupal-8-2-now-with-more-outside-in
id: 3756
---

Over the weekend, [Drupal 8.2 beta was released](https://www.drupal.org/project/drupal/releases/8.2.0-beta2). One of the reasons why I'm so excited about this release is that it ships with "more outside-in". In an "outside-in experience", you can click anything on the page, edit its configuration in place without having to navigate to the administration back end, and watch it take effect immediately. This kind of on-the-fly editorial experience could be a game changer for Drupal's usability.

When I last discussed [turning Drupal outside-in](https://dri.es/turning-drupal-outside-in), we were still in the conceptual stages, with [mock-ups illustrating the concepts](https://dri.es/examples-of-how-to-make-drupal-outside-in). Since then, those designs have gone through multiple rounds of feedback from [Drupal's usability team](https://groups.drupal.org/usability) and a round of user testing led by [Cheppers](https://cheppers.com). This study identified some issues and provided some insights which were incorporated into subsequent designs.

Two policy changes we introduced in Drupal 8 – [semantic versioning](https://www.drupal.org/core/release-cycle-overview) and [experimental modules](https://www.drupal.org/core/experimental) – have fundamentally changed Drupal's innovation model starting with Drupal 8. I should write a longer blog post about this, but the net result of those two changes is ongoing improvements with an easy upgrade path. In this case, it enabled us to add outside-in experiences to Drupal 8.2 instead of having to wait for Drupal 9. The authoring experience improvements we made in Drupal 8 are well-received, but that doesn't mean we are done. It's exciting that we can move much faster on making Drupal easier to use.

### In-place block configuration

As you can see from the image below, Drupal 8.2 adds the ability to trigger "Edit" mode, which currently highlights all blocks on the page. Clicking on one – in this case, the block with the site's name – pops out a new tray or sidebar. A content creator can change the site name directly from the tray, without having to navigate through Drupal's administrative interface to theme settings as they would have to in Drupal 7 and Drupal 8.1.

[image blog/outside-in-site-name resize=false]

### Making adjustments to menus

In the second image, the pattern is applied to a menu block. You can make adjustments to the menu right from the new tray instead of having to navigate to the back end. Here the content creator changes the order of the menu links (moving "About us" after "Contact") and toggles the "Team" menu item from hidden to visible.

[image blog/outside-in-menu resize=false]

### In-context block placement

In Drupal 8.1 and prior, placing a new block on the page required navigating away from your front end into the administrative back end and noting the available regions. Once you discover where to go to add a block, which can in itself be a challenge, you'll have to learn about the different regions, and some trial and error might be required to place a block exactly where you want it to go.

Starting in Drupal 8.2, content creators can now just click "Place block" without navigating to a different page and knowing about available regions ahead of time. Clicking "Place block" will highlight the different possible locations for a block to be placed in.

[image blog/outside-in-block-placement resize=false]

### Next steps

These improvements are currently tagged "experimental". This means that anyone who downloads Drupal 8.2 can test these changes and provide feedback. It also means that we aren't quite satisfied with these changes yet and that you should expect to see this functionality improve between now and 8.2.0's release, and even after the Drupal 8.2.0 release.

As you probably noticed, things still look pretty raw in places; as an example, the forms in the tray are exposing too many visual details. There is more work to do to bring this functionality to the level of the designs. We're focused on improving that, as well as the underlying architecture and accessibility. Once we feel good about how it all works and looks, we'll remove the experimental label.

We deliberately postponed most of the design work to focus on introducing the fundamental concepts and patterns. That was an important first step. We wanted to enable Drupal developers to start experimenting with the outside-in pattern in Drupal 8.2. As part of that, we'll have to determine how this new pattern will apply broadly to Drupal core and the many contributed modules that would leverage it. Our hope is that once the outside-in work is stable and no longer experimental, it will trickle down to every Drupal module. At that point we can all work together, in parallel, on making Drupal much easier to use.

Users have proven time and again in usability studies to be extremely "preview-driven", so the ability to make quick configuration changes right from their front end, without becoming an expert in Drupal's information architecture, could be revolutionary for Drupal.

If you'd like to help get these features to stable release faster, please join us in the [outside-in roadmap issue](https://www.drupal.org/node/2762505).

### Thank you

I'd also like to thank everyone who contributed to these features and reviewed them, including [Bojhan](https://www.drupal.org/u/bojhan), [yoroy](https://www.drupal.org/u/yoroy), [pwolanin](https://www.drupal.org/u/pwolanin), [andrewmacpherson](https://www.drupal.org/u/andrewmacpherson), [gtamas](https://www.drupal.org/u/gtamas), [petycomp](https://www.drupal.org/u/petycomp), [zsofimajor](https://www.drupal.org/u/zsofimajor), [SKAUGHT](https://www.drupal.org/u/skaught), [nod\_](https://www.drupal.org/u/nod_), [effulgentsia](https://www.drupal.org/u/effulgentsia), [Wim Leers](https://www.drupal.org/u/wim-leers), [catch](https://www.drupal.org/u/catch), [alexpott](https://www.drupal.org/u/alexpott), and [xjm](https://www.drupal.org/u/xjm).

And finally, a special thank you to [Acquia](https://www.acquia.com)'s outside-in team for driving most of the design and implementation: [tkoleary](https://www.drupal.org/u/tkoleary), [webchick](https://www.drupal.org/u/webchick), [tedbow](https://www.drupal.org/u/tedbow), [Gábor Hojtsy](https://www.drupal.org/u/g%C3%A1bor-hojtsy), [tim.plunkett](https://www.drupal.org/u/timplunkett), and [drpal](https://www.drupal.org/u/drpal).

[image blog/octo-outside-in-team resize=false]
