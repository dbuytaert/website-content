---
url: 'https://dri.es/how-wikipedia-implemented-link-previews'
title: 'How Wikipedia implemented link previews'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2018-05-03T15:20:10-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'How Wikipedia serves 10,000 link previews per second'
tags:
  - 'Web performance'
image: blog/wikipedia-link-previews
published: true
id: 4326
---

# How Wikipedia implemented link previews

You might have noticed that [Wikipedia recently started enabling link previews](https://medium.com/freely-sharing-the-sum-of-all-knowledge/wikipedia-page-previews-738cddac7a21); when you hover over a link, it displays a card with more information about the linked page.

[image blog/wikipedia-link-previews resize=false]

My first reaction was: what took them so long? Link previews help to solve an important usability problem of having to open many articles, often in multiple browser tabs. However, after I started to read more about how [Wikipedia](https://www.wikipedia.org/) implemented the link previews, I was reminded of how hard it is to do things at the scale Wikipedia requires.

[Nirzar Pangarka](https://medium.com/@nirzar), who works as a designer at the Wikimedia Foundation, shared that [more than 10,000 links get hovered each second across Wikipedia](https://medium.com/freely-sharing-the-sum-of-all-knowledge/how-we-designed-page-previews-for-wikipedia-and-what-could-be-done-with-them-in-the-future-7a5fa6b07b96). In another post, [David Lyall](https://medium.com/@dlyall), an engineering manager at the Wikimedia Foundation, shared that they are seeing [up to half a million hits every minute on the API that serves the link preview cards](https://medium.com/freely-sharing-the-sum-of-all-knowledge/why-it-took-a-long-time-to-build-that-tiny-link-preview-on-wikipedia-d5bd734df8fe).

I have a great appreciation for Wikipedia's seemingly straightforward link previews. Delivering a feature at this scale is an impressive achievement.
