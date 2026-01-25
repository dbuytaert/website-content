---
url: 'https://dri.es/acquia-stack-installer-aka-damp'
title: 'Acquia Stack Installer (aka DAMP)'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2009-03-04T23:01:53-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
  - Acquia
published: true
id: 612
---

# Acquia Stack Installer (aka DAMP)

If you're looking to evaluate [Drupal](https://www.drupal.org), or if you're a Drupal developer, you have got to check out [Acquia's Stack Installer](https://dev.acquia.com/downloads), aka DAMP, that we released at DrupalCon DC today.

No doubt most of you are familiar with LAMP, MAMP, WAMP or XAMPP, which are installers designed to help people get started with PHP applications. DAMP is similar to MAMP, WAMP, and XAMPP, except that it comes with Acquia Drupal, and is specifically tuned for Drupal. The Acquia Stack Installer includes [Acquia Drupal](https://www.acquia.com/web-content-management-drupal), Apache, MySQL, PHP, PhpMyAdmin, and an Acquia Drupal Control Panel.

The installer has been tested on Macs with OS 10.5 (Intel-based, not PowerPC) as well as all major flavors of Microsoft Windows. For Windows and Mac users, it is the easiest way to get started with Drupal. The installer is available for free, and is part of Acquia's efforts to simplify the Drupal experience for non-technical users. We think it will help the Drupal project grow. If you have friends, family, or co-workers that want to get started with Drupal, the [Acquia Stack Installer](https://dev.acquia.com/downloads) is a great starting point.

While designed for end users, the installer is also good for web development. In fact, as part of our alpha testing, I switched from MAMP to Acquia's Stack Installer, and have already suggested some developer improvements for future releases. One will be to compile the Process Control Extension (PCNTL) into PHP – something which is not available on MAMP or XAMPP. Enabling PCNTL allows SimpleTest to take advantage of multi-core processors; on a dual core machine this should cut the running time roughly in half.

Give it a try, and let us know if you have other suggestions or recommendations.
