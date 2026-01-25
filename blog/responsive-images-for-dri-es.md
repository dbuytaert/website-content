---
url: 'https://dri.es/responsive-images-for-dri-es'
title: 'Responsive images for dri.es'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2018-10-14T18:36:30-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'It''s Sunday afternoon, I''m on a plane to San Francisco, and I just rolled out "responsive images" support on dri.es from 30,000 feet in the air.'
tags:
  - 'My site'
  - POSSE
  - 'Web performance'
published: true
id: 4551
---

# Responsive images for dri.es

For a few years now I've been planning to add support for [responsive images](https://internetingishard.com/html-and-css/responsive-images/) to my site.

The past two weeks, I've had to take multiple trips to the West Coast of the United States; last week I traveled from Boston to San Diego and back, and this week I'm flying from Boston to San Francisco and back. I used some of that airplane time to add responsive image support to my site, and just pushed it to production from 30,000 feet in the air!

When a website supports [responsive images](https://internetingishard.com/html-and-css/responsive-images/), it allows a browser to choose between different versions of an image. The browser will select the most optimal image by taking into account not only the device's dimensions (e.g. mobile vs desktop) but also the device's screen resolution (e.g. regular vs retina) and the browser viewport (e.g. full-screen browser or not). In theory, a browser could also factor in the internet connection speed but I don't think they do.

First of all, with responsive image support, images should always look crisp (I no longer serve an image that is too small for certain devices). Second, my site should also be faster, especially for people using older smartphones on low-bandwidth connections (I no longer serve an image that is too big for an older smartphone).

<p class="pullquote">Serving the right image to the right device can make a big difference in the user experience.</p>

Many articles suggest supporting three image sizes, however, based on my own testing with [Chrome's Developer Tools](https://developers.google.com/web/tools/chrome-devtools/), I didn't feel that three sizes was sufficient. There are so many different screen sizes and screen resolutions today that I decided to offer six versions of each image: 480, 640, 768, 960, 1280 and 1440 pixels wide. And I'm on the fence about adding 1920 as a seventh size.

Because [I believe in being in control of my own data](https://dri.es/to-pesos-or-to-posse), I host almost 10,000 original images on my site. This means that in addition to the original images, I now also store 60,000 image variants. To further improve the site experience, I'm contemplating adding [WebP](https://en.wikipedia.org/wiki/WebP) variants as well – that would bring the total number of stored images to 130,000.

If you notice that my photos are clearer and/or page delivery a bit faster, this is why. Through small changes like these, my goal is to continue to improve the user experience on dri.es.
