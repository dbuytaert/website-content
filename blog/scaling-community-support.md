---
url: 'https://dri.es/scaling-community-support'
title: 'Scaling community support'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2006-12-07T06:50:59-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
published: true
id: 186
---

# Scaling community support

Over at his weblog [Earl Miles wrote](http://www.angrydonuts.com/another_post_on_email_and_suppor):

> The user base for Drupal has been growing exponentially, and even though the number of people who stick around and are willing to spend their time giving support are growing at the same pace, it's an exponential comparison, not a linear one. Which means the gap is growing. Compare the graphs of 10^n and 2^n. Where n = 1, 10 users per 2 support people, that is 20%. But where n = 8, that is 10,000,000 users and 256 support people, or .002% (give or take a decimal point).

I disagree with this assessment and the mathematical projections. I think that new developments, and not a growing user base, are the main cause for the quality of community support to degrade. Allow me to explain ...

To me, it looks like community support follows a [Zipf distribution](https://en.wikipedia.org/wiki/Zipf's_law). If we apply Zipf's law to the Drupal documentation, it says that in a distribution of support requests, there is a huge number of requests for a small number of answers and a small number of requests for a large number of less common answers.

Applied to the Drupal handbook, this means that a relative small number of pages in the Drupal handbook, satisfy a large fraction of our users. People who don't find a quick answer in the Drupal handbook, might post a support request in the forums. Here too, Zipf's law applies. A huge number of support requests can be answered by a large number of people, and only a fraction of the forum topics can be answered by one or two people in the Drupal community.

As our user base grows, more and more questions get answered and more and more questions go unanswered. Fiddle with the parameters of the [mathematical equation](https://en.wikipedia.org/wiki/Zipf's_law) and you'll observe that as the popularity of support requests grows, their relative popularity remains the same. In other words, if Zipf's law applies to community support, the quality of support won't degrade as the community grows.

However, that is not what people perceive. People will focus on the increasing number of support requests that go unanswered and incorrectly conclude that the quality of support is going downhill. The truth is that, while we see more support requests, we are also successfully answering an increasing number of support requests. Thus, the problem is one of perception. As the user base grows, the [long tail](https://en.wikipedia.org/wiki/The_Long_Tail) of Zipf's distribution becomes more visible ...

Clearly, these observations only hold for a static project. Drupal is a dynamic project as the community continues to add bells and whistles to the software. By doing so we introduce new support requests to the system. These new requests alter the relative popularity of the existing requests in the Zipf distribution, and therefore, can impact the quality of support. So what does this mean? It means that as long all developers do a good job documenting all the new aspects of Drupal, the quality of Drupal's support can only improve. It also means that if developers don't document new aspects of Drupal, or document them poorly, the quality of Drupal's support will degrade. At all cost, new developments and documentation updates need to progress at the same pace.

Anyway, my point is that (i) it is not the growing user base but [the growing developer base that is to be held responsible](/responsible-maintainers) and that (ii) the problem is one of perception because the relative quality of support can easily remain constant. Of course, [perception matters a lot](/garland) and it is not something we can ignore. After all, [the (perceived) quality of support will be a key differentiator](/ockhams-razor-principle-of-content-management-systems) in the future. To solve the perception issue, we need to make [Drupal easier to use](/complexity-is-a-disease) so we can [turn new users into contributors](/drupal-mentors-needed) more easily. The lower the barrier, the faster you're an expert that can help others.
