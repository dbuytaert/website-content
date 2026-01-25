---
url: 'https://dri.es/goodbye-third-party-cookies'
title: 'Goodbye third-party cookies'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2024-02-05T06:57:52-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'The phase-out of invasive third-party cookies marks a big step towards an Open Web that values privacy.'
tags:
  - 'Open Web'
  - Privacy
image: drupal/cookieless-future
published: true
id: 5561
---

# Goodbye third-party cookies

[image drupal/cookieless-future schema=false]

For nearly three decades, **third-party cookies** have been a major privacy concern on the web. They allow organizations, such as advertisers, to track users' browsing activities across multiple websites, often without explicit consent.

Unlike third-party cookies, **first-party cookies** are restricted to the website you are on. They are often used to improve the user experience, such as keeping you logged in, remembering what is in your shopping cart, and more.

Of course, first-party cookies can *also* be used to track your activity, like with Google Analytics, but they can't be used to follow you beyond that site. While both types of cookies can be used to track users, third-party cookies are much more invasive and problematic.

In 2018, I made the decision to remove all tracking tools, including Google Analytics, from my personal site. My website aspires to the privacy of printed works. The anonymity of a book holds a unique charm, and I find joy in not knowing who visits my website.

That said, I have no issue with the use of first-party cookies, provided it's consensual and used to improve the user experience. I understand their importance for many organizations, especially in marketing.

Fortunately, the era of third-party cookies is coming to a close. Browsers like Safari and Firefox have already taken steps to limit third-party tracking. They still allow certain third-party cookies to ensure websites work properly. Two examples include:

1. E-commerce sites often rely on third-party cookies for integrating payment systems. Blocking these cookies could disrupt the payment process.
2. Complex digital platforms, like healthcare and government websites, sometimes use cross-site authentication to link departmental websites. Blocking these could prevent access to important services.

While Safari and Firefox have been limiting third-party cookies for some time, Google Chrome is lagging behind. Google only began phasing out third-party cookies in early 2024 (a few weeks ago), starting with just 1% of its users. Their plan is to expand this to all users by the end of 2024.

Google's strategy can be viewed in two ways:

1. Negatively, it could look like Google is delaying the phase-out because it profits from the advertising revenue these cookies generate.
2. Positively, Google is cautious in removing third-party cookies to avoid disrupting websites that rely on them for non-advertising purposes.

As a regular Chrome user, I didn't want to wait until the end of 2024. If you feel the same, you can block third-party cookies in Chrome now. Just head to `Settings`, select `Privacy and Security` and activate `Block third-party cookies`. Just beware, as some sites might stop working.

If you manage or develop websites, check they rely on third-party cookies. Use [my HTTP Header Analyzer](https://dri.es/the-little-http-header-analyzer-that-could) to check for `SameSite=None` attributes indicating third-party cookies, or test by disabling them in Chrome.
