---
url: 'https://dri.es/mollom-captchas-are-intelligent'
title: 'Mollom CAPTCHAs are "intelligent"'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2010-03-03T11:30:16-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Mollom
published: true
id: 1511
---

# Mollom CAPTCHAs are "intelligent"

Every other week or so, someone asks me the following question: *How are Mollom CAPTCHAs better than those created by [CAPTCHA module](https://www.drupal.org/project/captcha)?*. This is an important question, and understanding it is central to understanding our philosophy with [Mollom](https://mollom.com).

First, when using Mollom in *"text analysis"* mode, a CAPTCHA is only displayed when Mollom is uncertain about whether a message could be spam. Mollom analyzes the text of comments and combines that analysis with what it knows about the internal reputation of the posters, to determine whether a message is "spammy". Non-spam submissions are accepted without a CAPTCHA, and posts that are certainly spam are rejected automatically. By only presenting a CAPTCHA when necessary, we avoid penalizing normal (non-spamming) users with CAPTCHA challenges. The CAPTCHA module is different in that it does not perform text analysis and therefore must always display a CAPTCHA challenge.

Second, the [Mollom module for Drupal](https://www.drupal.org/project/mollom) has a *"CAPTCHA only"* mode, which is useful when clients would prefer not to use text analysis, or for when the forms have almost no text to analyze (like Drupal's user registration form). In "CAPTCHA only" mode, the user experience of the Mollom module is very similar to that of the CAPTCHA module – the user is always prompted to complete a CAPTCHA in order to perform a certain operation. The similarity ends here, however. While the user experience is the same, the actual CAPTCHA generation is not. Mollom CAPTCHAs are "intelligent", in the sense that Mollom tracks the behavior and reputation of IP addresses from all sites using Mollom. A known spammer, operating from a known IP with a poor reputation, won't be able to complete a Mollom CAPTCHA no matter how hard he tries. And, as more users install Mollom, its performance increases as it learns from the additional data. A stand-alone module like CAPTCHA doesn't learn from user behavior, as it simply generates CAPTCHAs without regard to their context and delivery.

This second difference between the [Mollom](https://mollom.com) and other CAPTCHA modules is, in fact, huge. When we analyze our server logs, we see that 20% of all correctly completed CAPTCHAs are submitted by known spammers. Spammers don't seem to solve CAPTCHAs algorithmically; instead, they persuade humans to solve CAPTCHAs for them by using botnet infected machines. Two blog posts that detail this process are [How to defeat Koobface](http://blog.threatexpert.com/2008/12/how-to-defeat-koobface.html) and [Breaking Koobface's CAPTCHA solving process](https://abuse.ch/?p=2330). As spammers evolve and their arsenal of tools become increasingly powerful, CAPTCHA solutions must keep up to remain effective. We believe Mollom's "intelligent CAPTCHA" processing represents a significant benefit from traditional CAPTCHA generation and is one way we'll continue to stay a step ahead in our goal to eliminate posting spam.

[image mollom/mollom-drupal-protection-modes resize=false]
