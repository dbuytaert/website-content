---
url: 'https://dri.es/drupal-commitment-to-accessibility'
title: "Drupal's commitment to accessibility"
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2018-12-05T05:56:22-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
  - WordPress
  - Accessibility
  - Diversity
image: blog/figure-opening-doors
published: true
featured: true
id: 4656
---

# Drupal's commitment to accessibility

[image blog/figure-opening-doors]

Last week, [WordPress Tavern](https://wptavern.com/) picked up [my blog post about Drupal 8's upcoming Layout Builder](https://dri.es/why-drupal-layout-builder-is-so-unique-and-powerful).

While I'm grateful that WordPress Tavern covered Drupal's Layout Builder, it is not surprising that the majority of [WordPress Tavern's blog post](https://wptavern.com/drupal-8-7-to-introduce-layout-builder-contributors-face-accessibility-challenges) alludes to the potential challenges with accessibility. After all, [Gutenberg's lack of accessibility has been a big topic of debate](https://wptavern.com/wordpress-accessibility-team-delivers-sobering-assessment-of-gutenberg-we-have-to-draw-a-line), and a point of frustration in the WordPress community.

I understand why organizations might be tempted to de-prioritize accessibility. Making a complex web application accessible can be a lot of work, and the pressure to ship early can be high.

In the past, I've been tempted to skip accessibility features myself. I believed that because accessibility features benefited a small group of people only, they could come in a follow-up release.

<p class="pullquote">Today, I've come to believe that accessibility is not something you do for a small group of people. Accessibility is about promoting inclusion. When the product you use daily is accessible, it means that we all get to work with a greater number and a greater variety of colleagues. Accessibility benefits everyone.</p>

As you can see in [Drupal's Values and Principles](https://www.drupal.org/about/values-and-principles), we are committed to building software that everyone can use. Accessibility should always be a priority. Making capabilities like the Layout Builder accessible is core to Drupal's DNA.

[Drupal's Values and Principles](https://www.drupal.org/about/values-and-principles) translate into our development process, as what we call an [accessibility gate](https://www.drupal.org/core/gates#accessibility), where we set a clearly defined "must-have bar". Prioritizing accessibility also means that we commit to trying to iteratively improve accessibility beyond that minimum over time.

Together with the accessibility maintainers, we jointly agreed that:

1. Our first priority is **WCAG 2.0 AA conformance**. This means that in order to be released as a stable system, the Layout Builder must reach Level AA conformance with [WCAG](https://www.w3.org/WAI/standards-guidelines/wcag/). Without WCAG 2.0 AA conformance, we won't release a stable version of Layout Builder.
2. Our next priority is **WCAG 2.1 AA conformance**. We're thrilled at the greater inclusion provided by these new guidelines, and will strive to achieve as much of it as we can before release. Because these guidelines are still new (formally approved in June 2018), we won't hold up releasing the stable version of Layout Builder on them, but are committed to implementing them as quickly as we're able to, even if some of the items are after initial release.
3. While **WCAG AAA conformance** is not something currently being pursued, there are aspects of AAA that we are discussing adopting in the future. For example, the new [2.1 AAA "Animations from Interactions"](https://www.drupal.org/project/ideas/issues/2928103), which can be framed as an achievable design constraint: anywhere an animation is used, we must ensure designs are understandable/operable for those who cannot or choose not to use animations.

Drupal's commitment to accessibility is one of the things that makes Drupal's upcoming Layout Builder special: it will not only bring [tremendous and new capabilities](https://dri.es/why-drupal-layout-builder-is-so-unique-and-powerful) to Drupal, it will also do so without excluding a large portion of current and potential users. We all benefit from that!
