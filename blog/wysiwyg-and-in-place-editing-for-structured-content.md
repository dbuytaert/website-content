---
url: 'https://dri.es/wysiwyg-and-in-place-editing-for-structured-content'
title: 'WYSIWYG and in-place editing for structured content'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2013-05-31T10:45:00-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
published: true
id: 2961
---

# WYSIWYG and in-place editing for structured content

Karen McGrane gave a great keynote at DrupalCon Portland on [future-friendly content with Drupal](http://karenmcgrane.com/2013/05/23/drupalcon-keynote-video-and-talk-notes/). It's worth watching the [video recording](http://karenmcgrane.com/2013/05/23/drupalcon-keynote-video-and-talk-notes/). I agree with Karen's vision for the future. With the proliferation of different devices, screen sizes and input devices, there is a growing need for structured content that can be reused in multiple channels.

From the early days, Drupal has been doing structured content and content reuse better than most competitors. Drupal's node system was introduced in Drupal 3 in 2001, and was ahead of its time compared to the "page tree"-model used by most competitors. With every release, Drupal has gotten better and better at structured content and content reuse, leading to things like CCK and Views in core. Still to date, Drupal is one of the leaders in modeling structured content and content reuse. It is is one of the primary reasons we've seen so much growth. It was great to see that recognized by Karen.

One of the biggest gaps in Drupal has been the authoring experience. Two of the most noticeable authoring experience improvements that we are adding to Drupal 8 core are [WYSIWYG editing](https://dri.es/from-aloha-to-ckeditor) and [in-place editing](https://dri.es/spark-update-unified-in-place-editing). Where I disagree with Karen is with her belief that in-place editing and WYSIWYG editing are bad. Sure, WYSIWYG and in-place editing definitely *can* be problematic when combined with structured content. However, I believe we've implemented them in a good way – it can't be compared to Microsoft Word's blob-like approach. I wish that Karen better understood how we have implemented this functionality. It would have been helpful if she had offered concrete suggestions on what better solutions would look like. Until we know what better tools look like, I'm convinced that Drupal 8's approach to WYSIWYG and in-place editing are a big step forward. It makes for another intermediate step towards a bigger vision.

We've been talking about the advantages and disadvantages of WYSIWYG for more than 10 years now, and we still haven't figured out better approaches. The best we've been able to do is to evolve WYSIWYG editing and in-place editing to apply to individual chunks instead of the entire page, to generate clean markup and to better guide authors to make them aware that their input may end up in many forms of output.

While implementing Drupal 8's WYSIWYG and in-place editing functionality, a lot of attention was spent on ensuring that these features are compatible with structured content:

- WYSIWYG editors used to generate bad markup. Drupal 8's WYSIWYG editor guarantees clean markup thanks to the [new "Advanced Content Filter" feature in CKEditor](https://ckeditor.com/blog/CKEditor-4.1-Released).
- Drupal applies WYSIWYG editors to individual form fields instead of the entire page. You are encouraged to break up your content in many fields. Similarly, in-place editing is triggered on the entity level, not the page level, which means the user declares his intent to edit a specific entity and can then edit a specific field within that entity. In-place editing is only designed for quick edits, it wants to *delight* the author for those small edits, rather than forcing him to go back to the potentially overwhelming back-end form every time. At no point are authors given the impression they are editing the entire page.

For a more detailed explanation, see Wim's article: ["Drupal 8: best authoring experience for structured content?"](https://wimleers.com/article/drupal-8-structured-content-authoring-experience).
