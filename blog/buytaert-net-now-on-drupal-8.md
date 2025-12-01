---
title: 'Buytaert.net now on Drupal 8'
date: '2016-12-16T09:39:20-05:00'
author: Dries
summary: 'How I finally upgraded my personal blog from Drupal 7 to Drupal 8.'
tags:
  - Drupal
  - Personal
  - 'My site'
published: true
type: blog
url: /buytaert-net-now-on-drupal-8
id: 3836
---

Some of my readers may have noticed that I recently upgraded this blog from Drupal 7 to Drupal 8. You might be wondering why it took me so long, and the truth is that while I love working on my site, [it's hard to justify spending much time on it](https://dri.es/on-the-hard-choices-we-make-every-day).

I did most of the work on my commute to work, cramped in a small seat on the train to the tune of the rumbling train carriage. I finally pushed the site live during Thanksgiving weekend. Nothing like seeing the Drupal migration tool run on your computer to the smell of the turkey cooking in the oven. The comfortable atmosphere of Thanksgiving – and the glass of wine that was sitting on my desk – made it all the more fun.

While my blog has been around for more than a decade, it isn't very complex; I have approximately 1,250 blog posts and 8,000 photos. All of the photos on my website are managed by my Album module, a custom Drupal module whose first version I wrote about ten years ago. Since its inception, I've upgraded the module to each major Drupal version from Drupal 5 to 7, and now to Drupal 8.

Upgrading my little website was relatively simple, involving porting my custom Album module, porting my theme to use Twig, and migrating the data and configuration. Though I've reviewed and committed many patches that went into Drupal 8, this was the first time I'm actually undertaking a Drupal 8 module, theme, and migration from scratch.

Each of the steps in upgrading a Drupal site have undergone substantial changes in the transition from Drupal 7 to Drupal 8. Building a module, for instance, is completely different because of the new introduction of object-oriented programming paradigms, the new routing system, and more. Writing a module in Drupal 8 is so much nicer than writing a module in Drupal 7; my code is better organized, more reusable, and better tested. Theming has been completely reinvented to use Twig. I found Twig much more pleasant to use than PHPTemplate in Drupal 7, and I'm very happy with how the theming process has improved. That said, I've to give a special shoutout to [Preston So](https://www.drupal.org/u/prestonso) for helping me with my theme; I was painfully reminded I'm still not a designer or a CSS expert.

Overall, porting my site was a fun experience and I'm excited to be using Drupal 8. There is so much power packed into Drupal 8. Now that I've experienced Drupal 8 development from the other side of the equation, I believe even more in the decisions we made. While there is always room for improvement, Drupal 8 is a giant leap forward for Drupal.
