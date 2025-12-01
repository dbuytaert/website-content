---
title: 'Website spam protection in the enterprise?'
date: '2008-06-24T04:42:43-04:00'
author: Dries
tags:
  - Drupal
  - Mollom
published: true
type: blog
url: /website-spam-protection-in-the-enterprise
id: 462
---

Kas Thomas, a CMS analyst at [CMS Watch](http://www.cmswatch.com), published [a great article on Mollom and the future of website spam](http://www.cmswatch.com/Trends/1272-Drupal,-Mollom,-and-the-Future-of-Blog-Spam):

> If you're in the process of selecting a Web CMS and/or Social Software vendor, and you plan to deploy public-facing blogs or wikis, be sure to take comment spam mitigation into account. Moderation of comments (by humans) is inherently costly. A SaaS service like [Mollom](https://mollom.com) or [Akismet](http://akismet.com) may not completely eliminate the need for moderation but could be money well-spent. One thing is certain: spam is something you need to budget for and architect around. Ask your vendors what kind of help you can expect from them. And don't settle for the sound of crickets chirping.

At the [Gilbane Boston 2008 Conference](https://gilbane.com/gilbane-boston-2008-where-content-management-meets-social-media/) last week, it was clear that nearly all enterprise WCMS vendors are working hard to integrate blogs, wikis, forums, tagging and voting into the core of their offering. Clearly, Web 2.0 is currently receiving the level of attention in the enterprise that it got in the open source world two years ago. Maybe by 2010, they'll have support for OpenID, oAuth, XFN, Twitter, etc. just like [Drupal](https://www.drupal.org) has today. ;)

Anyway, [Kas Thomas](http://www.cmswatch.com/Analyst/23-Thomas) of [CMS Watch](http://www.cmswatch.com) is right. Allowing users to react, participate and contribute while still keeping your site under control can be a challenge. Spam is something you need to budget for and architect around. At first glance, I don't think any of the vendors at Gilbane had a strong anti-spam offering, if an offering at all. In fact, I wonder if they understand the spam problem that is ahead of them now that they have begun opening the flood gates on user generated content.

At Mollom, we have a [Mollom client API](https://www.mollom.com/api) making it possible to integrate spam protection in your CMS and other web applications. The last couple of weeks, [Ben and I](https://www.mollom.com/about) have also been working on a *Mollom reseller API* that will allow vendors to seamlessly integrate Mollom into their SaaS offerings and eventually to become a Mollom reseller. You'll be able to create, update, delete and manage Mollom access keys without ever having to send your users to <https://www.mollom.com/>. The combined set of APIs should give more vendors access to anti-spam technology before 2010 ...

More about our reseller API later, but feel free to drop us an e-mail if you want to help beta test or become an early reference.
