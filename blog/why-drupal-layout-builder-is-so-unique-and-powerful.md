---
url: 'https://dri.es/why-drupal-layout-builder-is-so-unique-and-powerful'
title: "Why Drupal's Layout Builder is so powerful and unique"
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2018-11-12T07:02:32-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'Layout Builder, which will be in the next release of Drupal 8, is unique in that it can work with structured and unstructured content, and with templated and free-form pages.'
tags:
  - Drupal
image: drupal/layout-builder-gift-basket-regular
published: true
id: 4606
---

# Why Drupal's Layout Builder is so powerful and unique

Content authors want an easy-to-use page building experience; they want to create and design pages using drag-and-drop and WYSIWYG tools. For over a year the Drupal community has been working on a new Layout Builder, which is designed to bring this page building capability into Drupal core.

Drupal's upcoming Layout Builder is unique in offering a single, powerful visual design tool for the following three use cases:

1. **Layouts for templated content.** The creation of "layout templates" that will be used to layout all instances of a specific content type (e.g. blog posts, product pages).
2. **Customizations to templated layouts.** The ability to override these layout templates on a case-by-case basis (e.g. the ability to override the layout of a standardized product page)
3. **Custom pages.** The creation of custom, one-off landing pages not tied to a content type or structured content (e.g. a single "About us" page).

Let's look at all three use cases in more detail to explain why we think this is extremely useful!

### Use case 1: Layouts for templated content

For large sites with significant amounts of content it is important that the same types of content have a similar appearance.

A commerce site selling hundreds of different gift baskets with flower arrangements should have a similar layout for all gift baskets. For customers, this provides a consistent experience when browsing the gift baskets, making them easier to compare. For content authors, the templated approach means they don't have to worry about the appearance and layout of each new gift basket they enter on the site. They can be sure that once they have entered the price, description, and uploaded an image of the item, it will look good to the end user and similar to all other gift baskets on the site.

[image drupal/layout-builder-gift-basket-regular]

Drupal 8's new Layout Builder allows a site creator to visually create a layout template that will be used for each item of the same content type (e.g. a "gift basket layout" for the "gift basket" content type). This is possible because the Layout Builder benefits from Drupal's powerful "structured content" capabilities.

Many of Drupal's competitors don't allow such a templated approach to be designed in the browser. Their browser-based page builders only allow you to create a design for an individual page. When you want to create a layout that applies to all pages of a specific content type, it is usually not possible without a developer.

### Use case 2: Customizations to templated layouts

While having a uniform look for all products of a particular type has many advantages, sometimes you may want to display one or more products in a slightly (or dramatically) different way.

Perhaps a customer recorded a video of giving their loved one one of the gift baskets, and that video has recently gone viral (because somehow it involved a puppy). If you only want to update one of the gift baskets with a video, it may not make sense to add an optional "highlighted video" field to all gift baskets.

Drupal 8's Layout Builder offers the ability to customize templated layouts on a case per case basis. In the "viral, puppy, gift basket" video example, this would allow a content creator to rearrange the layout for just that one gift basket, and put the viral video directly below the product image. In addition, the Layout Builder would allow the site to revert the layout to match all other gift baskets once the world has moved on to the next puppy video.

[image drupal/layout-builder-gift-basket-puppy]

Since most content management systems don't allow you to visually design a layout pattern for certain types of structured content, they of course can't allow for this type of customization.

### Use case 3: Custom pages (with unstructured content)

Of course, not everything is templated, and content authors often need to create one-off pages like an "About us" page or the website's homepage.

In addition to visually designing layout templates for different types of content, Drupal 8's Layout Builder can also be used to create these dynamic one-off custom pages. A content author can start with a blank page, design a layout, and start adding blocks. These blocks can contain videos, maps, text, a [hero image](https://en.wikipedia.org/wiki/Hero_image), or custom-built widgets (e.g. a *Drupal View* showing a list of the ten most popular gift baskets). Blocks can expose configuration options to the content author. For instance, a hero block with an image and text may offer a setting to align the text left, right, or center. These settings can be configured directly from a sidebar.

[image drupal/layout-builder-gift-basket-settings]

In many other systems content authors are able to use drag-and-drop WYSIWYG tools to design these one-off pages. This type of tool is used in many projects and services such as [Squarespace](https://www.squarespace.com/) and the new [Gutenberg Editor](https://wordpress.org/gutenberg/) for [WordPress](https://wordpress.org/) (now available for [Drupal, too](https://www.drupal.org/project/gutenberg)!).

<p class="pullquote">On large sites, the free-form page creation is almost certainly going to be a scalability, maintenance and governance challenge.</p>

For smaller sites where there may not be many pages or content authors, these dynamic free-form page builders may work well, and the unrestricted creative freedom they provide might be very compelling. However, on larger sites, when you have hundreds of pages or dozens of content creators, a templated approach is going to be preferred.

### When will Drupal's new Layout Builder be ready?

Drupal 8's Layout Builder is still a beta level [experimental module](https://www.drupal.org/core/experimental), with [25 known open issues](https://www.drupal.org/project/issues/search?projects=Drupal+core&project_issue_followers=&status%5B%5D=1&status%5B%5D=13&status%5B%5D=8&status%5B%5D=14&status%5B%5D=4&status%5B%5D=16&issue_tags_op=%3D&issue_tags=Layout+Builder+stable+blocker) to be addressed prior to becoming stable. We're on track to complete this in time for Drupal 8.7's release in May 2019. If you are interested in increasing the likelihood of that, you can find out how to help on the [Layout Initiative homepage](https://www.drupal.org/about/strategic-initiatives/layout).

### An important note on accessibility

Accessibility is one of Drupal's core tenets, and [building software that everyone can use](https://www.drupal.org/about/values-and-principles#build-software-everyone-can-use) is part of [our core values and principles](https://dri.es/defining-drupal-values-and-principles). A key part of bringing Layout Builder functionality to a "stable" state for production use will be ensuring that it passes our [accessibility gate](https://www.drupal.org/core/gates#accessibility) (Level AA conformance with [WCAG](https://www.w3.org/WAI/standards-guidelines/wcag/) and [ATAG](https://www.w3.org/WAI/standards-guidelines/atag/)). This holds for both the authoring tool itself, as well as the markup that it generates. We take our commitment to accessibility seriously.

### Impact on contributed modules and existing sites

Currently there a few methods in the Drupal module ecosystem for creating templated layouts and landing pages, including the [Panels](https://www.drupal.org/project/panels) and [Panelizer](https://www.drupal.org/project/panelizer) combination. We are currently working on a migration path for Panels/Panelizer to the Layout Builder.

The [Paragraphs](https://www.drupal.org/project/paragraphs) module currently can be used to solve several kinds of content authoring use-cases, including the creation of custom landing pages. It is [still being determined](https://www.drupal.org/project/paragraphs/issues/2954487) how Paragraphs will work with the Layout Builder and/or if the Layout Builder will be used to control the layout of Paragraphs.

### Conclusion

[video qUkpzSllO30]

Drupal's upcoming Layout Builder is unique in that it supports multiple different use cases; from templated layouts that can be applied to dozens or hundreds of pieces of structured content, to designing custom one-off pages with unstructured content. The Layout Builder is even more powerful when used in conjunction with Drupal's other out-of-the-box features such as revisioning, content moderation, and translations, but that is a topic for a future blog post.

*Special thanks to [Ted Bowman](https://www.drupal.org/u/tedbow) (Acquia) for co-authoring this post. Also thanks to [Wim Leers](https://www.drupal.org/u/wim-leers) (Acquia), [Angie Byron](https://www.drupal.org/u/webchick) (Acquia), [Alex Bronstein](https://www.drupal.org/u/effulgentsia) (Acquia), [Jeff Beeman](https://www.drupal.org/u/jrbeeman) (Acquia) and [Tim Plunkett](https://www.drupal.org/u/timplunkett) (Acquia) for their feedback during the writing process.*
