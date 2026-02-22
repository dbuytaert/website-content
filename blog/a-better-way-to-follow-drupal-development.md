---
url: 'https://dri.es/a-better-way-to-follow-drupal-development'
title: 'A better way to follow Drupal development'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2026-02-19T11:14:58-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
discussions:
  - { platform: LinkedIn, url: 'https://www.linkedin.com/posts/buytaert_a-better-way-to-follow-drupal-development-activity-7430287742812610561-kjfy' }
published: true
featured: false
id: 6101
---

# A better way to follow Drupal development

I've been reading [Drupal Core](https://www.drupal.org/project/drupal) commits for more than 15 years. My workflow hasn't changed much over time. I subscribe to the [Drupal Core commits RSS feed](https://git.drupalcode.org/project/drupal/-/commits/11.x?format=atom), and every morning, over coffee, I scan the new entries. For many of them, I click through to the issue on Drupal.org and read the summary and comments. 

That workflow served me well for a long time. But when [Drupal Starshot](https://dri.es/tag/drupal-starshot) expanded my focus beyond [Drupal Core](https://www.drupal.org/project/drupal) to include [Drupal CMS](https://www.drupal.org/project/cms), [Drupal Canvas](https://www.drupal.org/project/canvas), and the [Drupal AI initiative](https://www.drupal.org/project/ai), it became much harder to keep track of everything. All of this work happens in the open, but that doesn't make it easy to follow. 

So I built a small tool I'm calling [Drupal Digests](https://github.com/dbuytaert/drupal-digests). It watches the Drupal.org issue queues for Drupal Core, Drupal CMS, Drupal Canvas, and the Drupal AI initiative.  When something noteworthy gets committed, it feeds the discussion and diff to AI, which writes me a summary: what changed, why it matters, and whether you need to do anything. You can see [an example summary](https://github.com/dbuytaert/drupal-digests/blob/main/issues/drupal-ai/3556181.md) to get a feel for the format.

Each issue summary currently lives as its own Markdown file in a [GitHub repository](https://github.com/dbuytaert/drupal-digests/tree/main/issues). Since I still like my morning coffee and RSS routine, I also generate [RSS feeds](https://github.com/dbuytaert/drupal-digests/tree/main/feeds) that you can subscribe to in your favorite reader.

I built this to scratch my own itch, but realized it could help with something bigger. Staying informed is one of the hardest parts of contributing to a large Open Source project. These digests can help new contributors ramp up faster, help experienced module maintainers catch API changes, and make collaboration across the project easier.

I'm still tuning the prompts. Right now it costs me less than $2 a day in tokens, so I'm committed to running it for at least a year to see whether it's genuinely useful. If it proves valuable, I could imagine giving it a proper home, with search, filtering, and custom feeds.

For now, [subscribe to a feed](https://github.com/dbuytaert/drupal-digests) and tell me what you think.

PS: Follow the discussion on [LinkedIn](https://www.linkedin.com/posts/buytaert_a-better-way-to-follow-drupal-development-activity-7430287742812610561-kjfy).
