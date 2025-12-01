---
title: 'RSS auto-discovery'
date: '2018-03-14T21:21:11-04:00'
author: Dries
tags:
  - 'My site'
published: true
type: blog
url: /rss-auto-discovery
id: 4256
---

While working on [my POSSE plan](https://dri.es/my-posse-plan-for-evolving-my-site), I realized that my site no longer supported "RSS auto-discovery". RSS auto-discovery is a technique that makes it possible for browsers and RSS readers to automatically find a site's RSS feed. For example, when you enter <https://dri.es> in an RSS reader or browser, it should automatically discover that the feed is <https://dri.es/rss.xml>. It's a small adjustment, but it helps improve the usability of the [open web](https://dri.es/tag/open-web).

To make your RSS feeds auto-discoverable, add a `<link>` tag inside the `<head>` tag of your website. You can even include multiple `<link>` tags, which will allow you to make multiple RSS feeds auto-discoverable at the same time. Here is what it looks like for my site:

```html
<link rel="alternate" type="application/rss+xml" title="Dries Buytaert" href="https://dri.es/rss.xml" />
```

Pretty easy! Make sure to check your own websites – it helps the open web.
