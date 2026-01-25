---
url: 'https://dri.es/i-want-to-run-ai-locally-here-is-why-i-am-not-yet'
title: "I want to run AI locally. Here is why I'm not (yet)."
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2025-02-11T07:47:55-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'An exploration of whether to run AI locally or in the cloud for generating alt-text: balancing accuracy, accessibility, and open-source values.'
tags:
  - 'My site'
  - Accessibility
  - 'Artificial Intelligence'
  - Alt-text
published: true
id: 5756
---

# I want to run AI locally. Here is why I'm not (yet).

Last week, I wrote about my plan to [use AI to generate 9,000 `alt`-texts](https://dri.es/comparing-local-llms-for-alt-text-generation) for images on my website. I tested 12 LLMs – 10 running locally and 2 cloud-based – to assess their accuracy in generating `alt`-text for images. I ended that post with two key questions:

1. Should I use AI-generated `alt`-texts, even if it they are not perfect?
2. Should I generate these `alt`-texts with local LLMs or in the cloud?

Since then, I've received dozens of emails and LinkedIn comments. The responses were all over the place. Some swore by local models because they align with open-source values. Others championed cloud-based LLMs for better accuracy. A couple of people even ran tests using different models to help me out.

I appreciate every response. It's a great reminder of why building in the open is so valuable: it brings in diverse perspectives.

But one comment stood out. A visually impaired reader put it simply: <q>Imperfect `alt`-text is better than no `alt`-text</q>.

That comment made the first decision easy: AI-generated `alt`-text, even if not perfect, is better than nothing.

The harder question was which AI models to use. As a long-term open-source evangelist, I *really* want to run my own LLMs. Local AI aligns with my values: no privacy concerns, no API quotas, more transparency, and more control. They also align with my wallet: no subscription fees. And, let's be honest: running your own LLMs earns you some bragging rights at family parties.

But here is the problem: local models aren't as good as cloud models.

Most laptops and consumer desktops have 16–32GB of RAM, which limits them to small, lower-accuracy models. Even maxing out an Apple Mac Studio with 192GB of RAM doesn't change that. Gaming GPUs? Also a dead end, at least for me. Even high-end cards with 24GB of VRAM struggle with the larger models unless you stack multiple cards together.

The gap between local and cloud hardware is big. It's like racing a bicycle against a jet engine.

I could wait. Apple will likely release a new [Mac Studio](https://www.apple.com/mac-studio/) this year, and I'm hoping it supports more than 192GB of RAM. NVIDIA's [Digits project](https://www.nvidia.com/en-us/project-digits/) could make consumer-grade LLM hardware even more viable.

Local models are also improving fast. Just in the past few weeks:

- Alibaba released [Qwen 2.5 VL](https://huggingface.co/collections/Qwen/qwen25-vl-6795ffac22b334a837c0f9a5), which performs well in benchmarks.
- DeepSeek launched [DeepSeek-VL2](https://github.com/deepseek-ai/DeepSeek-VL2), a strong new open model.
- Mark Zuckerberg shared that Meta's Llama 4 is in testing and might be released in the next few months.

Consumer hardware and local models will continue to improve. But even when they do, cloud models will still be ahead. So, I am left with this choice:

1. Prioritize accessibility: use the best AI models available today, even if they're cloud-based.
2. Stick to Open Source ideals: run everything locally, but accept worse accuracy.

A reader, Kris, put it well: <q>Prioritize users while investing in your values</q>. That stuck with me.

I'd love to run everything locally, but making my content accessible and ensuring its accuracy matters more. So, for now, I'm moving forward with cloud-based models, even if it means compromising on my open-source ideals.

It's not the perfect answer, but it's the *practical* one. Prioritizing accessibility and end-user needs over my own principles feels like the right choice.

That doesn't mean I'm giving up on local LLMs. I'll keep testing models, tracking improvements, and looking for the right hardware upgrades. The moment local AI is good enough for generating `alt`-text, I'll switch. In my next post, I'll share my technical approach to making this work.
