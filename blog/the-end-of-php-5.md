---
title: 'The end of PHP 5 '
date: '2018-11-08T18:19:13-05:00'
author: Dries
summary: 'If you are still using PHP 5, now is the time to upgrade to a newer version of PHP.'
tags:
  - Drupal
  - PHP
published: true
type: blog
url: /the-end-of-php-5
id: 4601
---

PHP, the Open Source scripting language, is used by [nearly 80 percent of the world's websites](https://w3techs.com/technologies/details/pl-php/all/all).

According to [W3Techs](https://w3techs.com/), around [61 percent of all websites on the internet still use PHP 5](https://w3techs.com/technologies/details/pl-php/5/all), a version of PHP that was first released fourteen years ago.

Now is the time to give PHP 5 some attention. In less than two months, on December 31st, [security support for PHP 5 will officially cease](https://secure.php.net/supported-versions.php). (Note: Some Linux distributions, such as Debian Long Term Support distributions, will still try to backport security fixes.)

<p class="pullquote">If you haven't already, now is the time to make sure your site is running an updated and supported version of PHP.</p>

Beyond security considerations, sites that are running on older versions of PHP are missing out on the significant performance improvements that come with the newer versions.

### Drupal and PHP 5

#### Drupal 8

Drupal 8 will drop support for PHP 5 on March 6, 2019. We recommend updating to at least PHP 7.1 if possible, and ideally PHP 7.2, which is supported as of Drupal 8.5 (which was released March, 2018). Drupal 8.7 (to be released in May, 2019) will support PHP 7.3, and we may backport PHP 7.3 support to Drupal 8.6 in the coming months as well.

#### Drupal 7

Drupal 7 will drop support for older versions of PHP 5 on December 31st, but will continue to support PHP 5.6 as long there are one or more third-party organizations providing reliable, extended security support for PHP 5.

Earlier today, we released Drupal 7.61 which now supports PHP 7.2. This should make upgrades from PHP 5 easier. Drupal 7's support for PHP 7.3 is being worked on but we don't know yet when it will be available.

### Thank you!

It's a credit to the PHP community that they have maintained PHP 5 for fourteen years. But that can't go on forever. It's time to move on from PHP 5 and upgrade to a newer version so that we can all innovate faster.

I'd also like to thank the Drupal community – both those contributing to Drupal 7 and Drupal 8 – for keeping Drupal compatible with the newest versions of PHP. That certainly helps make PHP upgrades easier.
