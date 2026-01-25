---
url: 'https://dri.es/mollom-highly-scalable-backend-infrastructure-reviewed'
title: "Mollom's highly-scalable backend infrastructure reviewed"
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2011-02-10T09:58:39-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Mollom
published: true
id: 2181
---

# Mollom's highly-scalable backend infrastructure reviewed

[High Scalability](http://highscalability.com), a site dedicated to describing and cataloging successful, highly-scalable, websites, has recently posted a [detailed review of Mollom's highly-scalable backend infrastructure](http://highscalability.com/blog/2011/2/8/mollom-architecture-killing-over-373-million-spams-at-100-re.html).

As a web service protecting close to 40,000 websites, and handling about 100 requests per second, Mollom certainly qualifies as a site with much traffic. Currently, Mollom finds and prevents about half a million spam posts per day, and does a single spam check quickly, with low latency. Every feature we add to Mollom is carefully analyzed for its impact on speed. Personally, I can't wait to see Mollom grow even larger so that our scalability challenges become even more interesting.

The article, written from a series of interviews with Ben and Johan from the Mollom team and then interspersed with the author's own experiences with installing and using the service for himself, is incredibly detailed. It accurately describes much of Mollom's history, the challenges that we faced early on, and how those challenges were overcome. All in all, it provides a great look behind the scenes of the Mollom service. Thanks for the profile, HighScalability!
