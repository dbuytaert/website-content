---
title: 'Why the big architectural changes in Drupal 8'
date: '2013-09-09T13:33:02-04:00'
author: Dries
summary: 'Change is difficult but necessary for Drupal to stay relevant'
image: blog/why-the-big-architectural-changes-in-drupal-8
tags:
  - Drupal
  - 'The future'
published: true
type: blog
url: /why-the-big-architectural-changes-in-drupal-8
id: 3026
---

There has been a lot of chatter about Drupal 8. Will Drupal 8 be performant? Will Drupal 8 be easy to develop modules for? Will I have to learn Symfony? I want to address these concerns and explain why Drupal 8 introduces such big changes.

[image blog/why-the-big-architectural-changes-in-drupal-8 resize=false]

### Lessons from the past: the pain before the gain

The reason Drupal has been successful is because we always made big, forward-looking changes. It's a cliché, but change has always been the only constant in Drupal. The result is that Drupal has stayed relevant, unlike nearly every other Open Source CMS over the years. The biggest risk for our project is that we don't embrace change.

The downside is that with every major release of Drupal, we've gone through a lot of pain adjusting to this change. I first [wrote about it in 2006 when trying to get Drupal 4.7 released](https://dri.es/the-pain-before-the-payoff):

<q>So let's capture that thought for future reference. Sweeping changes are required to make major advances in technology, and often times there is a lot of pain before the pay-off.</q>

### We decided that big changes were required

Drupal 7 is a fantastic CMS, but at the same time there are some fairly big limitations, including an incomplete Entity API, a lack of separation between content and configuration, leading to deployment challenges, a lack of separation between logic and presentation in the theme layer, and more. We created solutions for those challenges using contributed modules, but those solutions were in many cases incomplete. In Drupal 8, we decided to tackle a lot of these problems head-on, through the Configuration Management Initiative, the Twig templating layer, and a complete Entity API.

The web landscape has also dramatically changed around Drupal since January 2011, when Drupal 7 was released. Mobile browsing is ubiquitous, and so are third-party services that people may want to integrate their Drupal sites with. Web site users expect a much higher bar when it comes to ease of use. We anticipated these trends and as a result, we spent the past 2.5 years working on Drupal 8's mobile features and user experience improvements.

But are all these great improvements enough?

### We need to modernize Drupal 8

One of our biggest challenges with Drupal, is that it is hard for organizations of all sizes to find Drupal talent (developers, themers, site builders, etc). Drupal 7 didn't address this problem (e.g. we held on to procedural programming instead of object-oriented programming), and in fact made it a bit worse with the introduction of even more "Drupalisms" (e.g. excessive use of structured arrays). For most people new to Drupal, Drupal 7 is really complex.

The most effective way to address the Drupal talent issue, as well as the complexity issue, is to bring Drupal in line with modern frameworks and platforms, so there is less Drupal-specific knowledge to learn in order to become proficient. We decided to adopt modern PHP concepts and standards, object-oriented programming, and the [Symfony framework](http://symfony.com). While a lot of the Drupal concepts (Fields, Views, Entities, Nodes) continue to exist in Drupal 8, they are now implemented using object-oriented programming design patterns.

The advantages and disadvantages of object-oriented programming are well-understood. The disadvantages are size, verbosity, the amount of work it takes to write (including the design planning that goes into it) and slower performance. For people new to object-oriented programming there may be a steep learning curve; some of the key programming techniques, such as inheritance and polymorphism, can be challenging initially. The advantages are encapsulation (both to hide implementation details and to avoid tampering with internal values), faster development thanks to re-use, extensibility, and better maintainability. Compared to procedural programs, object-oriented programs are easier to maintain, extend and refactor. So although a lot of work is spent to write the program, less work is needed to maintain it over time.

For Drupal 8 this means that the code will be more abstract, more verbose, and slower, yet also be more maintainable, more modular, and more accessible to non-Drupal developers. The end result is that Drupal 8 should help us attract new people to Drupal in a way Drupal 7 didn't.

This is exactly what happened with other projects like [Symfony](http://symfony.com); Symfony 2 was a complete rearchitecture of Symfony 1. A lot of people were alienated by that, yet at the same time Symfony 2 took off like a rocketship. The same thing has happened with the major releases of Drupal as well, despite how much change each one brings.

### Change is scary for the existing Drupal developers

However, as we get closer to the release of Drupal 8, existing Drupal developers have become increasingly aware of the massive changes that Drupal 8 will bring. This has resulted in some fear; some people feel like they have to re-learn everything they know, and that developing for Drupal 8 has changed to the point where it's no longer fun. This fear is completely understandable. Change is hard, it can be scary, and often takes a long time to be absorbed.

But even if we completely streamlined the Drupal 8 developer experience, Drupal 8 will still look and work radically different under the hood. As mentioned, there are advantages and disadvantages to object-oriented programming and modern design patterns. But if we care about the long-term success of Drupal, we can't preserve the past. The risk of sticking with the old Drupal 7 architecture is that we won't be able to attract many more Drupal developers, and that over time, Drupal will become the odd one out.

### There is a lot of work left to be done

Part of the fear out there is well-founded because in [the current state of development](https://dri.es/drupal-8-apis-are-freezing-but-not-frozen), Drupal 8 isn't good enough. While there are many things to like about Drupal 8, I'm also the first to admit that we have work to do on the Drupal 8 developer experience (as well as performance) before Drupal 8 can ship. Creating a well-designed object-oriented application takes more time and design work than creating a procedural one. Some major improvements have already landed, but we're still working hard on [improving the developer experience](https://www.drupal.org/node/2081777). We need more help, especially from Drupal 7 developers, on how we can make Drupal 8 more approachable for them. I'm not afraid to make major API changes if the developer experience improvement is suitably large. So if you have concerns about Drupal 8, [now is the time to step up and help](https://www.drupal.org/node/2081777#help). In return, I promise we'll work on Drupal 8 until it is ready. *Thank you!*
