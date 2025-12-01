---
title: 'Three new features for the Mollom module'
date: '2010-11-04T17:15:26-04:00'
author: Dries
tags:
  - Drupal
  - Mollom
published: true
type: blog
url: /three-new-features-for-the-mollom-module
id: 1961
---

We've just released a new version of the [Mollom module for Drupal 6](https://www.drupal.org/project/mollom), which contains a number of important new features. We always try to listen to our users, and many of these new features are a direct result of your feedback. Read on for an overview of the most important changes.

### Retain spam instead of discarding it

Not all of our users are comfortable with the idea of [Mollom](https://mollom.com) discarding spam without the possibility of manual review (no matter how spammy the message appears to be). We've solved this in a simple way: a new basic configuration option that causes the Mollom module to retain spam comments as unpublished posts in your site's moderation queue. Moderators and site administrators can review the moderation queue periodically to review Mollom's decisions. You can see the new option in the screenshot below.

[image mollom/mollom-discard-retain resize=false]

### Better protection for user registration forms

Based on the growing number of support tickets, user registration spam has become a significant problem. To help combat this type of spam, the new module release can optionally protect Drupal's user registration form using text analysis instead of the CAPTCHA-only solution previously available. Text analysis is especially useful when the user registration form is extended with additional fields (like "Bio" or "About me").

### Identify spam bots using a hidden honeypot

Further, we've added a basic honeypot to all forms protected by Mollom, through the use of a hidden field. Since many spam bots blindly pour data into all available form fields (including the hidden ones), the presence of data in a hidden field inserted by Mollom is a good indicator of spam activity. I have been testing this feature on [my personal blog](https://dri.es) and observed that over 80% of spam attempts trigger the honeypot. The additional form field is hidden by CSS. Since spam bots generally do not parse nor understand CSS, they simply do not realize the field is hidden, and therefore complete it, revealing themselves as bots in the process.

### Conclusion

In addition to these three big new features, the new version, as always, includes a number of usability improvements and bug fixes. If you're using Mollom on a Drupal 6 site, we strongly encourage you to upgrade as soon as possible, to run `update.php` after upgrading, and then finally, to visit your Mollom settings page to adjust the new options now available to you. You can download the latest module from the [Mollom project page on drupal.org](https://www.drupal.org/project/mollom).

We want to thank you for using Mollom, and ask that you keep the feature suggestions coming, at either the [Mollom issue queue on drupal.org](https://www.drupal.org/project/mollom), or by using our [contact page to e-mail our support team](https://www.mollom.com/contact). We'll continue to listen!
