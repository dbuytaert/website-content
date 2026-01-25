---
url: 'https://dri.es/adding-support-for-dark-mode-to-web-applications'
title: 'Adding support for Dark Mode to web applications'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2018-10-29T10:00:03-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - CSS
  - 'My site'
image: blog/dark-mode-dri-es-2018
published: true
id: 4581
---

# Adding support for Dark Mode to web applications

MacOS Mojave, Apple's newest operating system, now features [a Dark Mode interface](https://developer.apple.com/design/human-interface-guidelines/macos/visual-design/dark-mode/). In Dark Mode, the entire system adopts a darker color palette. Many third-party desktop applications have already been updated to support Dark Mode.

Today, more and more organizations rely on cloud-based web applications to support their workforce; from Gmail to Google Docs, SalesForce, Drupal, WordPress, GitHub, Trello and Jira. Unlike native desktop applications, web applications aren't able to adopt the Dark Mode interface. I personally spend more time using web applications than desktop applications, so not having web applications support Dark Mode defeats its purpose.

This could change as [the next version of Safari](https://developer.apple.com/safari/technology-preview/) adds a new [CSS media query](https://en.wikipedia.org/wiki/Media_queries) called `prefers-color-scheme`. Websites can use it to detect if Dark Mode is enabled.

I learned about the `prefers-color-scheme` media query on [Jeff Geerling's blog](https://www.jeffgeerling.com/blog/2018/jeff-geerlingcom-now-supports-dark-mode-macos-1014), so I decided to give it a try on my own website. Because I use CSS variables to set the colors of my site, it took less than 30 minutes to add Dark Mode support on [dri.es](https://dri.es). Here is all the code it took:

```css
@media (prefers-color-scheme: dark) {
  :root {
    --primary-font-color: #aaa;
    --secondary-font-color: #777;
    --background-color: #222;
    --table-zebra-color: #333;
    --table-hover-color: #444;
    --hover-color: #333;
  }
}
```

If you use MacOS Mojave, Safari 12.1 or later, and have Dark Mode enabled, my site will be shown in black:

[image blog/dark-mode-dri-es-2018 resize=false]

It will be interesting to see if any of the large web applications, like Gmail or Google Docs will adopt Dark Mode. I bet they will, because it adds a level of polish that will be expected in the future.
