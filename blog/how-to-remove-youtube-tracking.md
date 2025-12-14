---
title: 'How to remove YouTube tracking'
date: '2019-03-26T15:14:45-04:00'
author: Dries
image: blog/webpagetest-youtube-embed-2019-before
tags:
  - 'My site'
  - 'Web performance'
  - Privacy
published: true
type: blog
url: /how-to-remove-youtube-tracking
id: 4801
---

I don't use Google Analytics or any other web analytics service on [dri.es](https://dri.es). Why not? Because I don't desire to know how many people visit my site, where they come from, or what operating system they use.

Because I don't have a compelling reason to track my site's visitors, I don't have to bother anyone with a "cookies consent" popup either. That is a nice bonus because the web is littered with those already. I like that [dri.es](https://dri.es) is clutter-free.

This was all well and good until a couple of weeks ago, when I learned that when I embed a YouTube video in my blog posts, Google sends an [HTTP cookie](https://en.wikipedia.org/wiki/HTTP_cookie) to track my site's visitors. Be damned!

After some research, I discovered that YouTube offers a *privacy-enhanced way of embedding videos*. Instead of linking to `youtube.com`, link to `youtube-nocookie.com`, and no data-collecting HTTP cookie will be sent. This is Google's way of providing GDPR-compliant YouTube videos.

```html
<iframe width="640" height="360" src="https://www.youtube<strong>-nocookie.com</strong>/embed/<i>video-id</i>" frameborder="0"></iframe>
```

So I went ahead and updated all blog posts on [dri.es](https://dri.es) to use `youtube-nocookie.com`.

In addition to improving privacy, this change also makes my site faster. I used <https://webpagetest.org> to benchmark [a recent blog post with a YouTube video](https://dri.es/jsonapi-lands-in-drupal-core).

Before:

<div class="large">
  [image blog/webpagetest-youtube-embed-2019-before]
</div>

After:

<div class="large">
  [image blog/webpagetest-youtube-embed-2019-after]
</div>
