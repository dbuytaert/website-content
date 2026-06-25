---
url: 'https://dri.es/yslow'
title: YSlow
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2007-07-25T07:09:56-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
  - 'Web performance'
  - Joomla
  - Typo3
  - WordPress
  - Plone
published: true
id: 303
---

# YSlow

Yahoo! released [YSlow](https://developer.yahoo.com/yslow/), a [Firefox](https://www.mozilla.org/firefox) extension that integrates with the popular [Firebug tool](http://www.getfirebug.com/). YSlow was originally developed as an internal tool at Yahoo! with the help of Steve Souders, Chief Performance at Yahoo! and author of O'Reilly's [High Performance Websites](https://www.oreilly.com/catalog/9780596514211/) book.

YSlow analyzes the front-end performance of your website and tells you why it might be slow. For each component of a page (images, scripts, stylesheets) it checks its size, whether it was gzipped, the *Expires*-header, the *ETag*-header, etc. YSlow takes all this information into account and computes a performance grade for the page you are analyzing.

![A YSlow performance report for Drupal.](http://default/files/images/drupal/yslow.jpg)
*The current <a href="http://developer.yahoo.com/yslow/">YSlow</a> score for the <a href="http://drupal.org">drupal.org front page</a> is 74 \(C\). YSlow suggests that we reduce the number of CSS background images using <a href="http://alistapart.com/articles/sprites">CSS sprites</a>, that we use a Content Delivery Network \(CDN\) like <a href="http://akamai.com">Akamai</a> for delivering static files, and identifies an Apache configuration issue that affects the <em>Entity Tags</em> or <em>ETags</em> of static files. The problem is that, by default, Apache constructs ETags using attributes that make them unique to a specific server. A stock Apache embeds <em>inode numbers</em> in the ETag which dramatically reduces the odds of the validity test succeeding on web sites with multiple servers; the ETags won't match when a browser gets the original component from server A and later tries to validate that component on server B.*

Here are some other YSlow scores (higher is better):

- <http://wordpress.org>: 78 (C)
- [http:/drupal.org](https://www.drupal.org): 74 (C)
- <http://plone.org>: 64 (D)
- <http://postnuke.com>: 63 (D)
- <http://typo3.org>: 56 (F)
- [http://mamboserver.com](https://www.mamboserver.com/): 56 (F)
- <https://joomla.org>: 53 (F)

From what I have seen, Apache configuration issues, and not CMS implementation issues, are the main source of low YSlow scores. Be careful not to draw incorrect conclusions from these numbers; they are often not representative for the CMS software itself.

And it doesn't change the fact that drupal.org is currently a lot slower than most of these other sites. That is explained by drupal.org's poor back-end performance, and not by the front-end performance as measured by YSlow. (We're working on adding a second database server to drupal.org.)
