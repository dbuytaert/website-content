---
title: "My phone's battery has been blogging for 7 years"
date: '2025-04-13T04:59:59-04:00'
author: Dries
tags:
  - Drupal
  - POSSE
published: true
type: blog
url: /my-phone-battery-has-been-blogging-for-7-years
id: 5796
---

Seven years ago, I wrote a post about a tiny experiment: [publishing my phone's battery status to my website](https://dri.es/posting-my-phone-battery-status-to-my-site). The updates have quietly continued ever since, appearing at <https://dri.es/status>.

Every 20 minutes or so, my phone sends its battery level and charging state to a REST endpoint on my Drupal site. The exact timing depends on iOS background scheduling, which has a mind of its own.

For years, this lived quietly at <https://dri.es/status>. I never linked to it outside the [original blog post](https://dri.es/posting-my-phone-battery-status-to-my-site), so it felt like a forgotten corner of my site. Still working, but mostly invisible.

Despite its low profile, people still mention it occasionally after all this time. This prompted me to bring it into the light.

I have now added a battery icon to my site's header. It's a dynamically generated SVG that displays my phone's current battery level and charging state.

It's a bit goofy, but that is what makes personal websites special. You get to experiment with it and make it yours.
