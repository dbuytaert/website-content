---
title: 'Mollom blacklisting and language detection APIs'
date: '2010-02-07T16:43:35-05:00'
author: Dries
tags:
  - Mollom
published: true
type: blog
url: /mollom-blacklisting-and-language-detection-apis
id: 1427
---

If you're a regular reader of this blog, you know that [Mollom](https://mollom.com) is a continual work in progress. By studying how people use Mollom, by listening to feature requests, and by examining the [plugins](https://www.mollom.com/download) that our [software partners](https://www.mollom.com/partners) and others have made available, we've introduced new ways to interact with Mollom.

First, we're announcing support for blacklisting. We introduced two new methods: [one based on detecting the presence of user-specified URLs](https://www.mollom.com/api/addBlacklistURL), and another that detects [specific phrases or keywords](https://www.mollom.com/api/addBlacklistText). In both cases, Mollom maintains custom, site-specific URL and text blacklists, and knows to search for the presence of these links or phrases when analyzing text for your site. We're adding support for this API to the next version of the [Mollom module for Drupal](https://www.drupal.org/project/mollom).

Second, we've implemented [a new method that detects the language of any given text](https://www.mollom.com/api/detectLanguage). We currently support detection of about 75 languages and this new functionality allows our end-users to take action based on posting language. It could be used to help segment web postings into different forums by language, or to help moderate the languages spoken on your site, for instance. The language detection API is used by some of our customers, but probably won't make it into the next version of the [Mollom module for Drupal](https://www.drupal.org/project/mollom).

We've got other new features that we're working on as well, and will introduce them as they're ready. In the meantime, I'm excited to see what our plugin developers do with this new level of control.
