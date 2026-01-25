---
url: 'https://dri.es/mollom-now-has-captcha-only-mode'
title: 'Mollom now has "CAPTCHA only" mode'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2009-01-12T05:16:47-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
  - Mollom
published: true
id: 573
---

# Mollom now has "CAPTCHA only" mode

We're excited to announce a new release of the [Mollom module for Drupal 6](https://www.drupal.org/project/mollom). The [Mollom 1.7 release for Drupal 6](https://www.drupal.org/node/357580) is our most extensive update so far, and contains a number of new features.

For end-users, the most obvious new feature is our ability to now protect forms with [CAPTCHAs](https://en.wikipedia.org/wiki/Captcha) only. Previously, all forms enabled for Mollom were protected by Mollom's text analysis algorithms, with CAPTCHA challenges used as backup. Though that is still the default option, you may set individual forms to use a "CAPTCHA only" form of protection. Data on forms protected with "CAPTCHA only" is not sent for analysis, and the forms always present a remotely-hosted CAPTCHA challenge. With these changes, the Mollom module for Drupal can now act as a replacement to the [CAPTCHA module](https://www.drupal.org/project/captcha). For a screenshot of the configuration page, please see the Drupal module tutorial at https://www.mollom.com/tutorials/drupal.

Mollom's CAPTCHA service also provides audio CAPTCHAs, an important feature that allows greater participation from the visually impaired. Further, Mollom's CAPTCHA challenges are generated remotely, allowing us to constantly monitor CAPTCHA quality. If (when!) hackers solve them, we tweak them in ways that make them more difficult to crack. We believe this makes Mollom's CAPTCHAs better than locally generated CAPTCHAs.

We've made a lot of other improvements under the hood, including many that will allow greater support for additional forms in the future.

*Thanks to Damien Tournoud from [AF83](https://www.af83.com/) and Keith Smith for their contributions to the 1.7 release.*
