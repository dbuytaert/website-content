---
title: 'Life beyond social media: a more intentional way to share photos'
date: '2025-10-08T06:29:01-04:00'
author: Dries
image: isle-of-skye-2024/exploring-the-quiraing
tags:
  - 'My site'
  - Drupal
  - Photography
  - 'Photo stream'
  - 'Social media'
featured: false
published: true
type: blog
url: /life-beyond-social-media-a-more-intentional-way-to-share-photos
id: 5886
---

[image isle-of-skye-2024/exploring-the-quiraing caption=false lazy=false priority=true] 

Several years ago, [I built a photo stream](https://dri.es/a-photo-stream-for-my-site) on my website and pretty much stopped posting on Instagram.

I didn't like how Instagram made me feel, or the fact that it tracks my friends and family when they look at my photos. And while it was a nice way to stay in touch with people, I never found a real sense of community there.

Instead, I wanted a space that felt genuinely mine. A place that felt like home, not a podium. No tracking, no popularity contests, no clickbait, no ads. Just a quiet corner to share a bit of my life, where friends and family could visit without being tracked.

Leaving Instagram meant giving up its biggest feature: subscribers and notifications. On Instagram, people follow you and automatically see your posts. On my website, you have to remember to visit. 

To bridge this gap, I first added [an RSS feed for my photos](https://dri.es/photos.xml). But since not everyone uses RSS, I later started [a monthly photo newsletter](https://buttondown.com/dries-buytaert-photos). Once a month, I pick my favorite photos, format them for email, and send them out.

After sending five or six photo newsletters, I could already feel my motivation fading. Each one only took about twenty minutes to make, but it still felt like too much friction. So, I decided to fix that.

Under the hood, my photo stream runs on [Drupal](https://www.drupal.org), built as a custom module. I added two new routes to my custom Drupal module:  
- `/photos/$year/$month`: shows all photos for a given month, with the usual features: lazy loading, responsive images, [Schema.org](https://schema.org/) markup, and so on.  
- `/photos/$year/$month?email=true`: shows the same photos, but stripped down and formatted specifically for email clients.  

Now my monthly workflow looks like this: visit `/photos/2025/9?email=true`, copy the source HTML, paste it into [Buttondown](https://buttondown.com/), and hit 'Send'. That twenty-minute task became a one-minute task.

I spent two hours coding this to save nineteen minutes a month. In other words, it takes about six months before the time saved equals the time invested. The math checks out: 120 / 19 ≈ 6. My developer brain called it a win. My business brain called it a write-off.

But the real benefit isn't the time saved. The easier something is, the more likely I am to stick with it. Automation doesn't just save time. It also preserves good intentions.  

Could I automate this completely? Sure. I'm a developer, remember. Maybe I will someday. But for now, that one-minute task each month feels right. It's just enough involvement to stay connected to what I'm sharing, without the friction that kills motivation.
