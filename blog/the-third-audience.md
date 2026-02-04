---
url: 'https://dri.es/the-third-audience'
title: 'The Third Audience'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2026-01-14T17:33:29-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'I made my website easier for AI agents and crawlers to read, and within an hour it was getting hundreds of requests.'
tags:
  - Drupal
  - 'Artificial Intelligence'
  - 'My site'
  - Markdown
image: blog/machines-reading-web-content
discussions:
  - { platform: LinkedIn, url: 'https://www.linkedin.com/posts/buytaert_the-third-audience-is-ai-activity-7417339417524076544-ZPDq' }
published: true
featured: false
id: 6051
---

# The Third Audience

[image blog/machines-reading-web-content priority=true schema=false]

I used Claude Code to build a new feature for my site this morning. Any URL on my blog can now return Markdown instead of HTML.

I added a small hint in the HTML to signal that the Markdown version exists, mostly to see what would happen. My plan was to leave it running for a few weeks and write about it later if anything interesting turned up. 

Within an hour, I had *hundreds* of requests from AI crawlers, including ClaudeBot, GPTBot, OpenAI's SearchBot, and more. So much for waiting a few weeks.

For two decades, we built sites for two audiences: humans and search engines. AI agents are now the third audience, and most websites aren't optimized for them yet.

We learned how to play the [SEO](https://en.wikipedia.org/wiki/Search_engine_optimization) game so our sites would rank in Google. Now people are starting to invest in things like [Generative Engine Optimization](https://en.wikipedia.org/wiki/Generative_engine_optimization) (GEO) and Answer Engine Optimization (AEO).

I wanted to understand what that actually means in practice, so I turned my own site into a small experiment and made every page available as Markdown.

If you've been following my blog, you know that [Drupal stores my blog posts as Markdown](https://dri.es/switching-to-markdown-after-20-years-of-html). But when AI crawlers visited, they got HTML like everyone else. They had to wade through navigation menus and wrapper divs to find the actual content. My content already existed in a more AI-friendly format. I just wasn't serving it to them.

It only took a few changes, and [Drupal](https://www.drupal.org/) made that easy.

First, I added content negotiation to my site. When a request includes `Accept: text/markdown` in the HTTP headers, my site returns the Markdown instead of the rendered HTML.

Second, I made it possible to append `.md` to any URL. For example, `https://dri.es/principles-for-life.md` gives you clean Markdown with metadata like title, date, and tags. You can also try adding `.md` to the URL of this post.

But how did those crawlers find the Markdown version so fast? I borrowed a pattern from RSS: [RSS auto-discovery](https://dri.es/rss-auto-discovery). Many sites include a link tag with `rel="alternate"` pointing to their RSS feed. I applied the same idea to Markdown: every HTML page now includes a link tag announcing that an alternative Markdown version exists at the `.md` URL.

That "Markdown auto-discovery" turned out to be the key. The crawlers parse the HTML, find the alternate Markdown link, and immediately switch. That explains the hundreds of requests I saw within the first hour.

The speed of adoption tells me AI agents are hungry for cleaner content formats and will use them the moment they find them. What I don't know yet is whether this actually benefits me. It might lead to more visibility in AI answers, or it might just make it easier for AI companies to use my content without sending traffic back.

I know not everyone will love this experiment. Humans, including me, are teaching machines how to read our sites better, while machines are teaching humans to stop visiting us. The [value exchange between creators and AI companies](https://dri.es/the-webs-broken-deal-with-ai-companies) is far from settled, and it's entirely possible that making content easier for AI to consume will accelerate the hollowing out of the web. 

I don't have a good answer to that yet, but I'd rather experiment than look away. I'm going to leave this running and report back.

PS: Follow the discussion on [LinkedIn](https://www.linkedin.com/posts/buytaert_the-third-audience-is-ai-activity-7417339417524076544-ZPDq).
