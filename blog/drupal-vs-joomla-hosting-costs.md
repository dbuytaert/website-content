---
title: 'Drupal vs Joomla: hosting costs'
date: '2006-08-25T08:19:35-04:00'
author: Dries
tags:
  - Drupal
  - Humor
  - Joomla
  - Statistics
published: true
type: blog
url: /drupal-vs-joomla-hosting-costs
id: 129
---

Sun's new [Fire T1000 and T2000 servers](http://www.sun.com/servers/coolthreads/) are [much touted for their low power consumption](http://blogs.sun.com/jonathan/entry/answer_to_the_roof_riddle). According to the [Sun Fire T2000 power calculator](http://www.sun.com/servers/coolthreads/t2000/calc/), an idle Sun Fire T2000 with 4 cores and 8GB of memory consumes 203 watts, and a busy one consumes 251 watts, resulting in a difference of 48 watts.

Now, hosting companies pay something like one dollar per month in power and cooling costs for every 6 watts of power used. Thus, a Sun Fire T2000 costs 33.83 USD per month (203 watts divided by 6.00 watts/USD/month), and a busy one costs 41.83 USD per month (251 watts divided by 6.00 watts/USD/month).

Imagine that you have one such machine for your Drupal website and one such machine for your Joomla website. Now, say that the Drupal website is on average 100 times more efficient than the Joomla website ([a theoretical example](/drupal-vs-joomla-performance)) and that the Drupal machine's workload is 0.8%, while the Joomla machine's workload is 80%. That means that the monthly cost to power and cool your server is 33.90 USD per month (203 / 6 + (0.008 \* 48 / 6)) for Drupal and 40.23 USD per month (203 / 6 + (0.8 \* 48 / 6)) for Joomla.

In this simplified and hypothetical example, you save 6.33 USD per month by choosing Drupal over Joomla, or 75.96 USD per year! Three years will save 227.88 USD. ;-)

That, and Greenpeace will love you! (Greenpeace UK, by the way, has [chosen Drupal as their platform of choice](http://importantprojects.com/archives/000084.php).)
