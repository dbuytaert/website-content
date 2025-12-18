---
title: 'I open-sourced my blog content'
date: '2025-12-15T05:15:17-05:00'
author: Dries
tags:
  - 'Digital preservation'
  - 'Open Source'
  - Drupal
featured: false
published: true
type: blog
url: /i-open-sourced-my-blog-content
id: 5991
---

Last week I wrote that [a blog is a biography](/a-blog-is-a-biography). But sometimes our most advanced technology is also our most fragile. With my blog turning twenty years old in fifteen days, I have been thinking a lot about digital preservation.

The question I keep coming back to is simple: how do you preserve a website for hundreds of years?

I don't have the answer yet, but it's something I plan to slowly work on over the next 10 years. What I'm describing here is a first step.

Humans have been trying to preserve their words since we learned to write. Medieval monks hand-copied manuscripts that survived centuries. Clay tablets from ancient Mesopotamia still tell us about daily life from 5,000 years ago. They worked because they asked very little of the future. A clay tablet basically just sits there. 

In contrast, websites require continuous maintenance and recurring payments. Miss either, and they quietly disappear.  That makes it hard for websites to survive for hundreds of years.

Traditional backups may help content survive, but they only work if someone knows they exist and what to do with them. Not a safe bet over hundreds of years.

So I am trying something different. I exported my blog as Markdown files and put them on GitHub. Nearly twenty years of posts are now in a public repository at [github.com/dbuytaert/website-content](https://github.com/dbuytaert/website-content).

I'm essentially making two bets. First, GitHub does not need me to keep paying bills or renewing domains. Second, a public Git repository can be cloned. Each clone becomes an independent copy that does not depend on me.

If you use a static site generator like Jekyll or Hugo, you are probably thinking: "Welcome to 2010!". Fair enough. You have been storing content as Markdown in Git since before my kids could walk. The difference is that most people keep their Git repositories private. I am making mine public.

To be clear, my site still runs on [Drupal](/tag/drupal), and that is not changing. No need to panic. I just made my Drupal site export its content as Markdown.

For the past two weeks, my site has been auto-committing to GitHub daily. Admittedly, it feels a bit strange to share everything like this. New blog posts show up automatically, but so does everything else: [tag maintenance](https://github.com/dbuytaert/website-content/commit/746700c29270d6e63489701c2fc6280b541fb3f5), even [deleted posts](https://github.com/dbuytaert/website-content/commit/8f00e4b3f03817a8b97316d129a35338b9a1bcf1) I decided were not worth keeping. 

My blog has a publish button, an edit button, and a delete button. In my view, they are all equally legitimate. Now you can see me use all three. Git hides nothing.

Exporting my content to GitHub is my first bet, not my last. My plan is to build toward something like a <a href="https://dri.es/a-raid-for-web-content">RAID for web content</a>, spreading copies across multiple systems.
