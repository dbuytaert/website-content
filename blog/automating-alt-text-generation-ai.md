---
title: 'Automating alt-text generation with AI'
date: '2025-02-20T06:22:29-05:00'
author: Dries
summary: 'How I created an automated system that uses AI to generate alt-text for all the images on my website.'
image: isle-of-skye-2024/journey-to-skye
tags:
  - 'My site'
  - Accessibility
  - 'Artificial Intelligence'
  - Drupal
  - Alt-text
  - Python
  - Automation
featured: false
published: true
type: blog
url: /automating-alt-text-generation-ai
id: 5761
---

Billions of images on the web lack proper `alt`-text, making them inaccessible to millions of users who rely on screen readers.

My own website is no exception, so [a few weeks ago](https://dri.es/comparing-local-llms-for-alt-text-generation), I set out to add missing `alt`-text to about 9,000 images on this website.

What seemed like a simple fix became a multi-step challenge. I needed to [evaluate different AI models](https://dri.es/comparing-local-llms-for-alt-text-generation) and [decide between local or cloud processing](https://dri.es/i-want-to-run-ai-locally-here-is-why-i-am-not-yet).

To make the web better, a lot of websites need to add `alt`-text to their images. So I decided to document my progress here on [my blog](https://dri.es/) so others can learn from it – or offer suggestions. This third post dives into the technical details of how I built an automated pipeline to generate `alt`-text at scale.

### High-level architecture overview

My automation process follows three steps for each image:

1. Check if `alt`-text exists for a given image
2. Generate new `alt`-text using AI when missing
3. Update the database record for the image with the new `alt`-text

The rest of this post goes into more detail on each of these steps. If you're interested in the implementation, you can find most of the [source code on GitHub](https://github.com/dbuytaert/image-caption).

### Retrieving image metadata

To systematically process 9,000 images, I needed a structured way to identify which ones were missing `alt`-text.

Since my site runs on [Drupal](https://www.drupal.org/), I built two REST API endpoints to interact with the image metadata:

- `GET /album/{album-name}/{image-name}/get` – Retrieves metadata for an image, including title, `alt`-text, and caption.
- `PATCH /album/{album-name}/{image-name}/patch` – Updates specific fields, such as adding or modifying `alt`-text.

I've built similar APIs before, including one for my [basement's temperature and humidity monitor](https://dri.es/building-my-own-temperature-and-humidity-monitor). That post provides a more detailed breakdown of how I build endpoints like this.

This API uses separate URL paths (`/get` and `/patch`) for different operations, rather than using a single resource URL. I'd prefer to follow RESTful principles, but this approach avoids caching problems, including content negotiation issues in CDNs.

Anyway, with the new endpoints in place, fetching metadata for an image is simple:

```shell
curl -H "Authorization: test-token" \
  "https://dri.es/album/isle-of-skye-2024/journey-to-skye/get"
```

Every request requires an authorization token. And no, `test-token` isn't the real one. Without it, anyone could edit my images. While crowdsourced `alt`-text might be an interesting experiment, it's not one I'm looking to run today.

This request returns a JSON object with image metadata:

```shell
{
  "title": "Journey to Skye",
  "alt": "",
  "caption": "Each year, Klaas and I pick a new destination for our outdoor adventure. In 2024, we set off for the Isle of Skye in Scotland. This stop was near Glencoe, about halfway between Glasgow and Skye."
}

```

Because the `alt`-field is empty, the next step is to generate a description using AI.

### Generating and refining `alt`-text with AI

<div class="large">
  [image isle-of-skye-2024/journey-to-skye caption=false]
</div>

In [my first post on AI-generated `alt`-text](https://dri.es/comparing-local-llms-for-alt-text-generation), I wrote a Python script to compare 10 different local [Large Language Models](https://en.wikipedia.org/wiki/Large_language_model) (LLMs). The script uses [PyTorch](https://pytorch.org/), a widely used machine learning framework for AI research and deep learning. This implementation was a great learning experience.

The original script takes an image as input and generates `alt`-text using multiple LLMs:

```shell
./caption.py journey-to-skye.jpg
{
  "image": "journey-to-skye.jpg",
  "captions": {
    "vit-gpt2": "A man standing on top of a lush green field next to a body of water with a bird perched on top of it.",
    "git": "A man stands in a field next to a body of water with mountains in the background and a mountain in the background.",
    "blip": "This is an image of a person standing in the middle of a field next to a body of water with a mountain in the background.",
    "blip2-opt": "A man standing in the middle of a field with mountains in the background.",
    "blip2-flan": "A man is standing in the middle of a field with a river and mountains behind him on a cloudy day.",
    "minicpm-v": "A person standing alone amidst nature, with mountains and cloudy skies as backdrop.",
    "llava-13b": "A person standing alone in a misty, overgrown field with heather and trees, possibly during autumn or early spring due to the presence of red berries on the trees and the foggy atmosphere.",
    "llava-34b": "A person standing alone on a grassy hillside with a body of water and mountains in the background, under a cloudy sky.",
    "llama32-vision-11b": "A person standing in a field with mountains and water in the background, surrounded by overgrown grass and trees."
  }
}
```

My original plan was to run everything locally for full control, no subscription costs, and optimal privacy. But after testing 10 local LLMs, I changed my mind.

I knew cloud-based models would be better, but wanted to see if local models were good enough for `alt`-texts. Turns out, they're not quite there. You can read the [full comparison](https://dri.es/comparing-local-llms-for-alt-text-generation), but I gave the best local models a B, while cloud models earned an A.

While local processing aligned with my principles, it compromised the primary goal: creating the best possible descriptions for screen reader users. So I abandoned my local-only approach and decided to use cloud-based LLMs.

To automate `alt`-text generation for 9,000 images, I needed programmatic access to cloud models rather than relying on their browser-based interfaces – though [browser-based AI can be tons of fun](https://dri.es/i-gave-an-ai-agent-edit-access-to-my-website).

Instead of expanding my script with cloud LLM support, I switched to [Simon Willison](https://simonwillison.net/)'s `llm` tool: <https://llm.datasette.io/>. `llm` is a command-line tool and Python library that supports both local and cloud-based models. It takes care of installation, dependencies, API key management, and uploading images. Basically, all the things I didn't want to spend time maintaining myself.

Despite enjoying my PyTorch explorations with vision language models and multimodal encoders, I needed to focus on results. My weekly progress goal meant prioritizing working `alt`-text over building homegrown inference pipelines.

I also considered you, my readers. If this project inspires you to make your own website more accessible, you're better off with a script built on a well-maintained tool like `llm` rather than trying to adapt my custom implementation.

Scrapping my PyTorch implementation stung at first, but building on a more mature and active open-source project was far better for me and for you. So I rewrote my script, now in the [v2 branch](https://github.com/dbuytaert/image-caption), with the original PyTorch version preserved in v1.

The new version of my script keeps the same simple interface but now supports cloud models like ChatGPT and Claude:

```shell
./caption.py journey-to-skye.jpg --model chatgpt-4o-latest claude-3-sonnet --context "Location: Glencoe, Scotland"
{
  "image": "journey-to-skye.jpg",
  "captions": {
    "chatgpt-4o-latest": "A person in a red jacket stands near a small body of water, looking at distant mountains in Glencoe, Scotland.",
    "claude-3-sonnet": "A person stands by a small lake surrounded by grassy hills and mountains under a cloudy sky in the Scottish Highlands."
  }
}
```

The `--context` parameter improves `alt`-text quality by adding details the LLM can't determine from the image alone. This might include GPS coordinates, album titles, or even [a blog post about the trip](https://dri.es/van-life-on-the-isle-of-skye).

In this example, I added `"Location: Glencoe, Scotland"`. Notice how ChatGPT-4o mentions Glencoe directly while Claude-3 Sonnet references the Scottish Highlands. This contextual information makes descriptions more accurate and valuable for users. For maximum accuracy, use all available information!

### Updating image metadata

With `alt`-text generated, the final step is updating each image. The `PATCH` endpoint accepts only the fields that need changing, preserving other metadata:

```shell
curl -X PATCH \
  -H "Authorization: test-token" \
  "https://dri.es/album/isle-of-skye-2024/journey-to-skye/patch" \
  -d '{
    "alt": "A person stands by a small lake surrounded by grassy hills and mountains under a cloudy sky in the Scottish Highlands.",
  }'

```

That's it. This completes the automation loop for one image. It checks if `alt`-text is needed, creates a description using a cloud-based LLM, and updates the image if necessary. Now, I just need to do this about 9,000 times.

### Tracking AI-generated `alt`-text

Before running the script on all 9,000 images, I added a label to the database that marks each `alt`-text as either human-written or AI-generated. This makes it easy to:

- Re-run AI-generated descriptions without overwriting human-written ones
- Upgrade AI-generated `alt`-text as better models become available

With this approach I can update the AI-generated `alt`-text when ChatGPT 5 is released. And eventually, it might allow me to return to my original principles: to use a high-quality local LLM trained on public domain data. In the mean time, it helps me make the web more accessible today while building toward a better long-term solution tomorrow.

### Next steps

Now that the process is automated for a single image, the last step is to run the script on all 9,000. And honestly, it makes me nervous. The perfectionist in me wants to review every single AI-generated `alt`-text, but that is just not feasible. So, I have to trust AI. I'll probably write one more post to share the results and what I learned from this final step.

Stay tuned.
