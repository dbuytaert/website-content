---
title: "Trusting AI with my images wasn't easy"
date: '2025-02-24T09:11:42-05:00'
author: Dries
summary: "Trusting AI to describe my photos wasn't easy. But after 9,000 images, I had to admit: it often did the job better than me, and at a fraction of the cost."
tags:
  - 'My site'
  - Accessibility
  - 'Artificial Intelligence'
  - Alt-text
published: true
type: blog
url: /trusting-ai-with-my-images-was-not-easy
id: 5766
---

I did it. I just finished generating `alt`-text for 9,000 images on my website.

What began as a simple task evolved into a four-part series where I [compared different LLMs](https://dri.es/comparing-local-llms-for-alt-text-generation), [evaluated local versus cloud processing](https://dri.es/i-want-to-run-ai-locally-here-is-why-i-am-not-yet), and [built an automated workflow](https://dri.es/automating-alt-text-generation-ai).

But this final step was different. It wasn't about technology. It was about trust and letting things go.

### My AI tool in action

In my last blog post, I shared [scripts](https://github.com/dbuytaert/image-caption) to [automate `alt`-text generation for a single image](https://dri.es/automating-alt-text-generation-ai). The final step? Running my scripts on the 9,000 images missing `alt`-text. This covers over 20 years of images in [photo albums](https://dri.es/albums) and [blog posts](https://dri.es/blog).

Here is my tool in action:

[image blog/ai-generating-alt-text no-resize]

And yes, AI generated the `alt`-text for this GIF. AI describing AI, a recursion that should have ripped open the space-time continuum. Sadly, no portals appeared. At best, it might have triggered a stack overflow in a distant dimension. Meanwhile, I just did the evening dishes.

ChatGPT-4o processed all 9,000 images at half a cent each, for less than $50 in total. And despite hammering their service for a couple days, I never hit a rate limit or error. Very impressive.

### AI is better than me

Trusting a script to label 9,000 images made me nervous. What if mistakes in auto-generated descriptions made my website less accessible? What if future AI models trained on any mistakes?

I started cautiously, stopping after [each album](https://dri.es/albums) to check every `alt`-text. After reviewing 250 images, I noticed something: I wasn't fixing errors, I was just tweaking words.

Then came the real surprise. I tested my script on albums I had manually described five years ago. The result was humbling. AI wrote better `alt`-text: spotting details I missed, describing scenes more clearly, and capturing nuances I overlooked. Turns out, past me wasn't so great at writing `alt`-text.

Not just that. The LLM understood Japanese restaurant menus, decoded Hungarian text, interpreted German Drupal books, and read Dutch street signs. It recognized conference badges and correctly labeled events. It understood cultural contexts across countries. It picked up details about my photos that I had forgotten or didn't even know existed.

I was starting to understand this wasn't about AI's ability to describe images; it was about me accepting that AI often described them better than I could.

### Conclusion

AI isn't perfect, but it can be very useful. People worry about hallucinations and inaccuracy, and I did too. But after generating `alt`-text for 9,000 images, I saw something different: real, practical value.

It didn't just make my site more accessible; it challenged me. It showed me that sometimes, the best way to improve is to step aside and let a tool do the job better.
