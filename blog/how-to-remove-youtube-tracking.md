---
url: 'https://dri.es/how-to-remove-youtube-tracking'
title: 'How to remove YouTube tracking'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2019-03-26T15:14:45-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - 'My site'
  - 'Web performance'
  - Privacy
image: blog/webpagetest-youtube-embed-2019-before
published: true
featured: false
id: 4801
---

# How to remove YouTube tracking

![A waterfall diagram that shows requests and load times before replacing youtube.com with youtube-nocookie.com](http://default/files/cache/blog/webpagetest-youtube-embed-2019-before-640w.png)

I don't use Google Analytics or any other web analytics service on [dri.es](https://dri.es). Why not? Because I don't desire to know how many people visit my site, where they come from, or what operating system they use.

Because I don't have a compelling reason to track my site's visitors, I don't have to bother anyone with a "cookies consent" popup either. That is a nice bonus because the web is littered with those already. I like that [dri.es](https://dri.es) is clutter-free.

This was all well and good until a couple of weeks ago, when I learned that when I embed a YouTube video in my blog posts, Google sends an [HTTP cookie](https://en.wikipedia.org/wiki/HTTP_cookie) to track my site's visitors. Be damned!

After some research, I discovered that YouTube offers a *privacy-enhanced way of embedding videos*. Instead of linking to `youtube.com`, link to `youtube-nocookie.com`, and no data-collecting HTTP cookie will be sent. This is Google's way of providing GDPR-compliant YouTube videos.

```html
<iframe width="640" height="360" src="https://www.youtube-nocookie.com/embed/video-id" frameborder="0"></iframe>
```

So I went ahead and updated all blog posts on [dri.es](https://dri.es) to use `youtube-nocookie.com`.

In addition to improving privacy, this change also makes my site faster. I used <https://webpagetest.org> to benchmark [a recent blog post with a YouTube video](https://dri.es/jsonapi-lands-in-drupal-core).

Before:

<div class="large">
  ![A waterfall diagram that shows requests and load times before replacing youtube.com with youtube-nocookie.com](http://default/files/cache/blog/webpagetest-youtube-embed-2019-before-640w.png)
*When embedding a video using <code>youtube.com</code>, Google uses DoubleClick to track your users \(yellow bar\). A total of 22 files were loaded, and the total time to load the page was 4.4 seconds \(vertical blue line\). YouTube makes your pages slow, as the vast majority of requests and load time is spent on loading the YouTube video.*
</div>

After:

<div class="large">
  ![A waterfall diagram that shows requests and load times after replacing youtube.com with youtube-nocookie.com](http://default/files/cache/blog/webpagetest-youtube-embed-2019-after-640w.png)
*When using <code>youtube-nocookie.com</code>, Google no longer uses DoubleClick to track your users. No HTTP cookie was sent, "only" 18 files were loaded, and the total page load time was significantly faster at 2.9 seconds \(vertical blue line\). Most of the load time is still the result of embedding a single YouTube video.*
</div>
