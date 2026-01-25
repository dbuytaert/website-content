---
url: 'https://dri.es/christmas-lights-powered-by-drupal'
title: 'Christmas lights, powered by Drupal'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2025-12-24T07:49:19-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
  - Electronics
image: drupal/drupal-blue-led-christmas-lights
published: true
featured: false
id: 6011
---

# Christmas lights, powered by Drupal

[image drupal/drupal-blue-led-christmas-lights]

It's Christmas Eve, and Phil Norton is [controlling his Christmas lights with Drupal](https://www.hashbangcode.com/article/drupal-11-controlling-led-lights-using-rest-service). You can visit his site, pick a color, and across the room, a strip of LEDs changes to match. That feels extra magical on Christmas Eve.

I like how straightforward his implementation is. A Drupal form stores the color value using the State API, a REST endpoint exposes that data as JSON, and MicroPython running on a Pimoroni Plasma board polls the endpoint and updates the LEDs. 

I've gone down the electronics rabbit hole myself with [my solar-powered website](https://dri.es/my-solar-powered-and-self-hosted-website) and [basement temperature monitor](https://dri.es/building-my-own-temperature-and-humidity-monitor), both using [Drupal](https://www.drupal.org) as the backend. I didn't do an [electronics project](/tag/electronics) in 2025, but this makes me want to do another one in 2026.

I also didn't realize you could buy light strips where each LED can be controlled individually. That alone makes me want to up my Christmas game next year. 

But addressable LEDs are useful for more than holiday decorations. You could show how many people are on your site, light up a build as it moves through your CI/CD pipeline, flash on failed logins, or visualize the number of warnings in your Drupal logs. This quickly stops being a holiday decoration and starts looking like a tax-deductible business expense.

Beyond the fun factor, [Phil's tutorial](https://www.hashbangcode.com/article/drupal-11-controlling-led-lights-using-rest-service) does real teaching. It uses Drupal features many of us barely think about anymore: the State API, REST resources, flood protection, even the built-in HTML color field. It's not just a clever demo, but also a solid tutorial.

The Drupal community gets stronger when people share work this clearly and generously. If you've been curious about IoT, this is a great entry point. 

Merry Christmas to those celebrating. Go build something that blinks. May your deployments be smooth and your Drupal-powered Christmas lights shine bright.
