---
title: 'Refreshing the Drupal administration UI'
date: '2019-01-08T11:20:19-05:00'
author: Dries
summary: 'A modern and fresh look is coming to the Drupal administration interface soon. Take a look!'
image: drupal/carlo-spacing
tags:
  - Drupal
published: true
type: blog
url: /refreshing-the-drupal-administration-ui
id: 4711
---

Last year, I talked to nearly one hundred Drupal agency owners to understand what is preventing them from selling Drupal. One of the most common responses raised is that Drupal's administration UI looks outdated.

This critique is not wrong. Drupal's current administration UI was originally designed almost ten years ago when we were working on Drupal 7. In the last ten years, the world did not stand still; design trends changed, user interfaces became more dynamic and end-user expectations have changed with that.

To be fair, Drupal's administration UI has received numerous improvements in the past ten years; Drupal 8 shipped with a new toolbar, an updated content creation experience, more WYSIWYG functionality, and even some design updates.

<div class="large">
  [image drupal/drupal-7-vs-drupal-8-administration-ui]
</div>

While we made important improvements between Drupal 7 and Drupal 8, the feedback from the Drupal agency owners doesn't lie: we have not done enough to keep Drupal's administration UI modern and up-to-date.

This is something we need to address.

We are [introducing a new design system](https://www.drupal.org/project/ideas/issues/3017785) that defines a complete set of principles, patterns, and tools for updating Drupal's administration UI.

In the short term, we plan on updating the existing administration UI with the new design system. Longer term, we are working on [creating a completely new JavaScript-based administration UI](https://dri.es/working-toward-a-javascript-driven-drupal-administration-interface).

<div class="large">
  [image drupal/carlo-content-administration]
</div>

As you can see on Drupal.org, [community feedback on the proposal is overwhelmingly positive](https://www.drupal.org/project/ideas/issues/3017785#comment-12880593) with comments like <q>Wow! Such an improvement!</q> and <q>Well done! High contrast and modern look.</q>.

[image drupal/carlo-spacing]

I also ran the new design system by a few people who spend their days selling Drupal and they described it as "clean" with "good use of space" and a design they would be confident showing to prospective customers.

Whether you are a Drupal end-user, or in the business of selling Drupal, I recommend you [check out the new design system](https://www.drupal.org/project/ideas/issues/3017785) and provide your feedback on Drupal.org.

Special thanks to [Cristina Chumillas](https://www.drupal.org/u/ckrina), [Sascha Eggenberger](https://www.drupal.org/u/saschaeggi), [Roy Scholten](https://www.drupal.org/u/yoroy), [Archita Arora](https://www.drupal.org/u/archita-arora), [Dennis Cohn](https://www.drupal.org/u/dennis-cohn), [ Ricardo Marcelino](https://www.drupal.org/u/rfmarcelino), [Balazs Kantor](https://www.drupal.org/u/kiboman), [Lewis Nyman](https://www.drupal.org/u/lewisnyman),and [Antonella Severo](https://www.drupal.org/u/antonellasev) for all the work on the new design system so far!

We have started implementing the new design system as [a contributed theme with the name Claro](https://www.drupal.org/project/claro). We are aiming to release a beta version for testing in the spring of 2019 and to include it in Drupal core as an experimental theme by Drupal 8.8.0 in December 2019. With more help, we might be able to get it done faster.

Throughout the development of the refreshed administration theme, we will run usability studies to ensure that the new theme indeed is an improvement over the current experience, and we can iteratively improve it along the way.

Administration themes must meet large and varied use cases. For example, [accessibility is critical for the administration experience](https://dri.es/drupal-commitment-to-accessibility), and I'm happy to see that this initiative connected with and have taken feedback into account from the accessibility team.

Acquia has committed to being an early adopter of the theme through [the Acquia Lightning distribution](https://www.drupal.org/project/lightning), broadening the potential base of projects that can test and provide feedback on the refresh. Hopefully other organizations and projects will do the same.

### How can I help?

The team is looking for more designers and frontend developers to get involved. You can attend the weekly meetings on #javascript on Drupal Slack Mondays at 16:30 UTC and on #admin-ui on Drupal Slack Wednesdays at 14:30 UTC.

*Thanks to [Lauri Eskola](https://www.drupal.org/u/lauriii), [Gábor Hojtsy](https://www.drupal.org/u/g%C3%A1bor-hojtsy) and [Jeff Beeman](https://www.drupal.org/u/jrbeeman) for their help with this post.*
