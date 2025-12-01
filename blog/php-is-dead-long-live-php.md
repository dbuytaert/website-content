---
title: 'PHP is dead ... long live PHP!'
date: '2007-05-08T06:46:38-04:00'
author: Dries
tags:
  - Drupal
published: true
type: blog
url: /php-is-dead-long-live-php
id: 267
---

People are getting increasingly worried about PHP5's adoption rate. And rightly so. PHP5 has been released more than two years ago. If you look at the adoption rate in the graph below, you see that after more than two years, PHP5 commands for less than 20% of PHP's install base. With the current adoption rate (even if it is assumed to be exponential), PHP6 is dead before it is even born.

[image drupal/php5-adoption-rate resize=false]
[image drupal/php5-naive-forecast resize=false]

As [Nick Lewis pointed out](http://www.nicklewis.org/node/911): PHP is dying, and if we don't migrate to PHP5, the Drupal project will die along with the PHP project. It won't happen overnight, but it might happen several years down the road ... The point? Drupal's success depends on that of PHP.

Part of the problem is that the [PHP team has their target audience wrong](http://blog.case.edu/gps10/2007/04/29/so_many_untapped_php_features). If they want to drive PHP5's adoption, they need to make PHP5 attractive to ISPs and end-users, and focus less on application developers.

Many websites use a content management system, a forum or a blog tool and these systems work with both PHP4 and PHP5. And for a long time, they've worked better with PHP4 than with PHP5. I can only talk about Drupal, but from what I've seen, very few Drupal users show incentive to upgrade from PHP4 to PHP5. They are pretty much ignorant to what version of PHP they use, as long Drupal works well.

Isn't the Drupal team interested in using PHP5's new functionality? Sure we are. We'd love nothing more than to drop PHP4 support and to use PHP5's new functions. Unfortunately, we are dependent on our users too, and these users don't care about better OOP support, SimpleXML, PDO, DOM, etc. The only things they care about are performance, stability, compatibility and security.

If the PHP team would show that existing applications run *faster* by upgrading from PHP4 to PHP5, ISPs and end-users would have a strong incentive to upgrade. However, last time I checked, [PHP5 was slower than PHP4](https://dri.es/drupal-webserver-configurations-compared). For anonymous users, Drupal is 13% slower with PHP5 than with PHP4. For authenticated users, this difference is only 4%. In other words, this gives them a good reason **not** to upgrade to PHP5.

If the PHP team would show that PHP5 is *more stable* than PHP4, people might start to care. Unfortunately, PHP 5.0 was rather buggy and *less compatible* than hoped for. Even today, PHP5.x+APC feels less stable than PHP4.4+APC.

Anyway, it is all about targeting the right users, and giving them a compelling reason to upgrade. Convince the ISPs and the applications' users to upgrade, not only the application developers. It would help us break out of this chicken-and-egg problem.

That said, the Drupal project can't just stand here and watch. Drupal's success depends on that of PHP, and PHP5's slow adoption rate is becoming annoying. So let us help the PHP project by giving Drupal users a compelling reason to upgrade to PHP5: **With every Drupal release, let us make some of the new (non-critical) features PHP5-only, and gradually drop support for PHP4.**

For example, let us start with making the *module update notification* feature, scheduled for inclusion in Drupal 6, depend on PHP5's SimpleXML parser. It is likely to upset some of our users and developers, but by giving back to the PHP project we help serve a bigger cause. After all, we really want PHP to shine.

And if projects like [Wordpress](https://wordpress.org/), [Joomla!](https://www.joomla.org/), [Typo3](https://typo3.org/), [phpBB](https://www.phpbb.com/), [Gallery](http://galleryproject.org/) and [phpMyAdmin](http://www.phpmyadmin.net) would do the same (if not already), we can help drive PHP5's adoption before it might be too late ...
