---
url: 'https://dri.es/caring-for-old-links'
title: 'Caring for old links'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2020-01-06T05:17:40-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'It is important that we care for old links. Do we have best practices or good algorithms for how to?'
tags:
  - 'Open Web'
  - 'My site'
  - 'Digital preservation'
published: true
featured: false
id: 4956
---

# Caring for old links

I decided to use the holiday break to do a link audit for [my personal blog](https://dri.es). I found hundreds of links that broke and hundreds of links that now redirect. This wasn't a surprise, as I haven't spent much time maintaining links in the 13 years I've been blogging.

### Broken links

Some of the broken links were internal, but the vast majority were external.

"Internal links" are links that go from one page on <https://dri.es> to a different page on <https://dri.es>. Fixing broken links feels good so I went ahead and fixed all internal links.

It's a different story for external links. "External links" are links that point to domains not under my control.

For example, in 2007 [I thanked Sun Microsystems for donating a Sun Fire X4200 server to the Drupal project](https://dri.es/sun-and-drupal). In my post, I linked to `http://www.sun.com/servers/entry/x4200`, the Sun Fire X4200 product page. Sun has since been acquired by Oracle, the page has been removed, and the link is now dead. I saw the following options: change this particular link to point to (1) [a Wikipedia page on the Sun Fire series](https://en.wikipedia.org/wiki/Sun_Fire), (2) [an archived copy of the original page on archive.org](https://web.archive.org/web/20071013165015/http://www.sun.com/servers/entry/x4200/), or (3) remove the link. In this case, I decided to update the link to point to Wikipedia.

Some sites that I link to have since been hijacked by porn sites. The URL used for Hillary Clinton's 2008 campaign website now points to a porn site, for example. This is unfortunate so I simply removed those links.

### Redirects

Some of the external links now have [URL redirects](https://en.wikipedia.org/wiki/URL_redirection). I found what I call "obvious redirects" and "less obvious redirects".

An example of an "obvious redirect" was a link to Apple's pressroom. In my [2015 Acquia retrospective](https://dri.es/acquia-retrospective-2015) I linked to an Apple press release, `https://www.apple.com/pr/library/2015/12/03Apple-Releases-Swift-as-Open-Source.html`, to highlight that large organizations like Apple were starting to embrace Open Source. Today, that link automatically redirects to `https://www.apple.com/newsroom/2015/12/03Apple-Releases-Swift-as-Open-Source`. A slightly different URL, but ultimately the same content. One day, that redirect might cease to exist, so it felt like a good idea to update my blog post to use the new link instead. I went ahead and updated hundreds of "obvious redirects".

The more interesting case is what I call "less obvious redirects". For example, in 2012 I blogged about how the [White House contributed to Drupal](https://dri.es/white-house-contributes-to-drupal). It was the first time in history that the White House contributed to Open Source, and Drupal in particular. It's something that many of us in the Drupal community are very proud of. In my blog post, I linked to `http://www.whitehouse.gov/blog/2012/08/23/open-sourcing-we-the-people`, a page on `whitehouse.gov` explaining their decision to contribute. That link now redirects to `http://obamawhitehouse.archives.gov/blog/2012/08/23/open-sourcing-we-the-people`, a permanent archive of the Obama administration's White House website. For me, it is less obvious what to do about this link: updating the link future proofs my site, but at the cost of losing some of its significance and historic value. For now, I left the original `whitehouse.gov` link in place.

### How to best care for old links?

I'm not entirely sure why I picked the Wikipedia link over archive.org when I updated the Sun Fire X4200 blog post, or why I left the original whitehouse.gov link in place. I also left many broken links in place because I'm undecided about what to do with them.

It is important that we care for old links. Before I continue my link clean up, I'd like to come up with a more structured, and possibly automatable, approach for link maintenance. I'm curious to learn how others care for old links, and if you know of any best practices, guidelines, or even automations.
