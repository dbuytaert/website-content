---
url: 'https://dri.es/canonical-urls'
title: 'Canonical URLs'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2018-03-14T21:30:02-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - 'My site'
published: true
id: 4261
---

# Canonical URLs

[Google Search Console](https://www.google.com/webmasters/) showed me that I have some duplicate content issues on <https://dri.es>, so I went ahead and tweaked my use of the `rel="canonical"` link tag.

When you have content that is accessible under multiple URLs, or even on multiple websites, and you don't explicitly tell Google which URL is *canonical*, Google makes the choice for you. By using the `rel="canonical"` link tag, you can tell Google which version should be prioritized in search results.

Doing canonicalization well improves your site's SEO, and [doing canonicalization wrong can be catastrophic](https://moz.com/blog/catastrophic-canonicalization). Let's hope I did it right!
