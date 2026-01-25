---
url: 'https://dri.es/hundred-million-spam-attempts-blocked'
title: 'Hundred million spam attempts blocked'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2009-07-09T03:21:16-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
  - Mollom
published: true
id: 801
---

# Hundred million spam attempts blocked

[image mollom/100-million-milestone resize=false]

At [Mollom](https://mollom.com), our spam-filtering startup targeted toward eliminating comment and post spam, we've just reached two important milestones: we blocked our 100,000,000th spam message, and we're now actively protecting over 10,000 websites.

It was only about three months ago that [we celebrated our 50 million message milestone](https://www.mollom.com/blog/fifty-million-spam-attempts-blocked), and two months before that [we reached twenty-five million](https://dri.es/more-milestones-for-mollom). These milestones are coming fast now. Will we double again in the next three months? Only time will tell.

In fact, these statistics are for our public servers only, and don't include message processing on private servers we operate on behalf of our larger clients. [Mollom filters about an additional 4 million messages each day](https://dri.es/mollom-filtering-millions-of-messages-for-netlog) for [Netlog](http://www.netlog.com/), for instance.

All things combined, we're processing up to 150 million messages a month! Since it can take multiple HTTP requests to process a single message, we're handling well over 200 million HTTP requests per month. Each of these requests is dynamic and fairly expensive; they retrieve data and invoke a parser, statistical classifiers, reputation models, etc. As you can imagine, that isn't exactly trivial at the volumes we are now seeing. (As a reference, that is 5 times more than a site like [drupal.org](https://www.drupal.org) which serves less than 20 million dynamic pages a month.)

We're currently working on some important architectural changes to the Mollom backend to allow it to learn faster while making it easier for us to debug, analyze and oversee its actions. We're also busy upgrading our infrastructure to cope with our growth. It is a work in process, but once completed, it should allow us to focus more on improving the effectiveness of our classifiers and adding new features.

One thing is for sure though – we're going to keep doing what we're doing, and if you're a Mollom user, we're glad to have you along for the ride.
