---
title: 'Drupal site crawler project'
date: '2009-05-11T09:05:37-04:00'
author: Dries
tags:
  - Drupal
  - Acquia
published: true
type: blog
url: /drupal-site-crawler-project
id: 646
---

For years now, people have been asking me how many Drupal sites there are. This is, of course, something of a moving target and I figured that the only way to answer that question was to count all the Drupal sites out there one by one. Three years ago, I was finally motivated enough to write a *Drupal site crawler* that looks over the millions of websites online to find those powered by Drupal. The crawler initially ran for about 3 months, and it returned a lot of Drupal sites. For each one it found, I then did some data-mining to extract the location of their hosting servers. I made a heatmap visualization of all the Drupal sites on a map of the world, and was able to start tracking Drupal's geographical growth patterns over time. As a bonus, the crawler also counted Joomla!, Mambo, and WordPress sites, as well as a number of other open source content management systems - it is good data on Drupal and the competition.

Writing that crawler was a really fun project. It taught me a ton about how Drupal is used, where Drupal was growing, and how we compared to other content management systems. On the technical side, I learned a ton about scalability. Thanks to my engineering background and my work on Drupal, scalability issues weren't new to me, but writing a crawler that processes information from billions of pages on the web, is a whole different ball park. At various different stages of the project and index sizes, some of the crawler's essential algorithms and data structures got seriously bogged down. I made a lot of trade-offs between scalability, performance and resource usage. In addition to the scalability issues, you also have to learn to deal with massive sites, dynamic pages, wild-card domain names, rate limiting and politeness, cycles in the page/site graph, discovery of new sites, etc.

Even though the crawler ran for many months, I never really launched it or talked about it publicly. I personally lacked the resources (both my time and the money to run the servers) to keep it running all the time. I ultimately stopped the crawler altogether and to put the project on hold. Since then, a couple of things have changed: I learned a lot more about scalability thanks to my ongoing work on Drupal and on [Mollom](https://mollom.com), which now processes hundreds of thousands of spam messages a day. I also co-founded [Acquia](https://www.acquia.com) along the way. Acquia shares my personal interest in tracking Drupal's growth and has the resources to help me revive my crawler. Last but not least, there has been a lot of innovation and knowledge sharing around how to solve scalability problems. As such, I'd now like to pick up the project where I left off 3 years ago, and relaunch it under the Acquia umbrella.

One thing hasn't changed: the day remains +/- 24 hours long. I still don't have enough time to work on this, and have many priorities I didn't have 3 years ago. That is why I'm looking for a summer intern who wants to take the lead on this project for a few months. The crawler is written in Java, so I'm looking for a student proficient in Java, and who also understands fundamental internet protocols such as DNS, HTTP and HTML. Experience with building scalable multi-server systems is a plus but not strictly required. I don't care where you live, but I only want to work with people who work hard and who have strong programming skills. Are you interested in being my intern for the summer? Contact me at my [contact form](https://dri.es/contact) and send me a copy of your resume. Or if you know someone who would be a good candidate, please point them to this blog post.
