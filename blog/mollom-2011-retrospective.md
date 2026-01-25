---
url: 'https://dri.es/mollom-2011-retrospective'
title: 'Mollom 2011 retrospective'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2012-01-06T08:39:16-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Mollom
published: true
id: 2621
---

# Mollom 2011 retrospective

2011 was another excellent year for [Mollom](https://mollom.com). We ended the year having blocked 630 million spam messages, up from 352 million spam messages blocked in 2010 – and that doesn't even count some of our largest customers like Netlog and other large social networks. And, as in 2010, we ended 2011 with a spam classification efficiency of 99.95%, meaning that only 5 in 10,000 spam messages were not caught by Mollom.

The number of active sites protected by Mollom grew from 28,000 at the end of 2010 to almost 45,000 at the end of 2011. Revenues grew by more than 50% with virtually no sales or marketing efforts.

[image mollom/team-december-2011]

All our revenue is invested back into the company. In 2011, we used those funds to grow our team and to fund development on an entirely new product, which may end up rebooting or repositioning Mollom altogether.

Specifically, we have been worked hard on what will be a "hosted comment moderation interface". That interface will provide an optimized moderation environment that will make it easier to moderate multiple websites, either as an individual or as part of a team of moderators. To do so we introduced a new backend with a REST-based API to replace our original XML-RPC API, we rewrote the Mollom module for Drupal, and started to change our website.

[image mollom/moderation-ui-december-2011]

We also faced some new challenges in 2011 – our support requests increased substantially, mostly due to the variety of sites that are now using Mollom. Based on many of these user requests, we tweaked our classifier performance, which resulted in a dramatic decrease in how often Mollom presents a CAPTCHA challenge, and in doing so, solved a number of real-world issues our clients were having with Mollom performance. Rolling out changes without impacting our up-time statistics was no small challenge – every change we made on the backend has to be weighed against the impact it has on the effectiveness and responsiveness of Mollom on the client side.

2012 may also bring us some additional competition – some of the world's best venture capitalists invested $8 million in a company called [Impermium](http://impermium.com). Investments like this validate our belief that the social web needs good anti-spam filtering solutions. Impermium is still building its first product but will definitely be a company to watch.

Regardless of what happens in the social web spam market, we'll be busy in 2012. The first half of 2012, you'll notice some new things popping up on Mollom. Our primary goal for 2012 will be to make the "hosted comment moderation interface" available commercially and to refresh our website. Along with launching a new product, we plan to ramp up our sales and marketing efforts. It is time to do so now the Mollom technology has matured after years of intensive investment. We've also got additional work to do to continue to improve accuracy, maintain our high uptime statistics, and work with other open source developers on improvements to Mollom clients for non-Drupal systems.

In short, 2011 was a great year for [Mollom](https://mollom.com). We're happy doing what we do, and we feel that we're helping to make the web a slightly better place. We wouldn't have made it this far without you – our customers, users and friends. Without you, we wouldn't be a company at all. Thank you for 2011! We're looking forward to sharing a great 2012 with you.
