---
title: 'The little HTTP Header Analyzer that could'
date: '2024-02-01T08:49:25-05:00'
author: Dries
summary: 'My HTTP Header Analyzer quietly and surprisingly surpassed 5 million scans.'
tags:
  - 'HTTP headers'
  - Performance
  - Security
  - Drupal
featured: true
published: true
type: blog
url: /the-little-http-header-analyzer-that-could
id: 5556
---

HTTP headers play a crucial part in making your website fast and secure. For that reason, I often inspect HTTP headers to troubleshoot caching problems or review security settings.

The complexity of the [HTTP standard](https://www.rfc-editor.org/rfc/rfc9110.html) and the challenge to remember all the best practices led me to develop an [HTTP Header Analyzer](https://dri.es/headers) four years ago.

It is pretty simple: enter a URL, and the tool will analyze the headers sent by your web application. It then explains these headers, provides a score, and suggests possible improvements.

For a demonstration, click 1. As the URL suggests, it will analyze the HTTP headers of [Reddit.com](https://www.reddit.com/).

I began this as a weekend project in the early days of COVID, seeing it as just another addition to my toolkit. At the time, I simply added it to my [projects page](https://dri.es/projects) but never announced or mentioned it on my blog.

So why write about it now? Because I happened to check my log files and, lo and behold, the little scanner that could clocked in more than 5 million scans, averaging over 3,500 scans a day.

So four years and five million scans later, I'm finally announcing it to the world!

If you haven't tried my HTTP header analyzer, [check it out](https://dri.es/headers). It's free, easy to use, requires no sign-up, and is built to help improve your website's performance and security.

The crawler works with all websites, but naturally, I added some special checks for [Drupal](https://www.drupal.org) sites.

I don't have any major plans for the crawler. At some point, I'd like to move it to its own domain, as it feels a bit out of place as part of my personal website. But for now, that isn't a priority.

For the time being, I'm open to any feedback or suggestions and will commit to making any necessary corrections or improvements.

It's rewarding to know that this tool has made thousands of websites faster and safer! It's also a great reminder to share your work, even in the simplest way – you never know the impact it could have.
