---
url: 'https://dri.es/scaling-open-source-communities'
title: 'Scaling Open Source communities'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2014-09-30T05:47:47-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'Successful Open Source projects must transition from pure volunteerism to include paid contributions, mirroring how public goods like roads evolved historically.'
tags:
  - Drupal
  - 'Open Source'
published: true
featured: true
id: 3241
---

# Scaling Open Source communities

We truly live in miraculous times. Open Source is at the core of the largest organizations in the world. Open Source is changing lives in emerging countries. Open Source has changed the tide of governments around the world. And yet, Open Source can be really difficult. Open Source can be largely a thankless job. It is hard to find volunteers, it is hard to find organizations to donate time or money, it is hard to organize the community, it is hard to learn, it is hard to attract full-time contributors, and more. As the project lead for Drupal, one of the largest Open Source projects/communities in the world, I live these challenges every day. In this blog post, I will analyze the challenge with scaling Open Source communities and recommend a solution for how to build very large Open Source communities.

### Open Source projects are public goods

In economic terms, for something to be a ["public good"](https://en.wikipedia.org/wiki/Public_good), it needs to match two criteria:

1. **non-excludability** - it is impossible to prevent anyone from consuming that good, and
2. **non-rivalry** - consumption of this good by anyone does not reduce the benefits available to others.

Examples of public goods include street lighting, national defense, public parks, basic education, the road system, etc. By that definition, Open Source software is also a "public good": we can't stop anyone from using Open Source software, and one person benefiting from Open Source software does not reduce the benefits available to others.

The realization that Open Source is a public good is a helpful one because there has been a lot of research about how to maintain and scale public goods.

### Public goods and the free-rider problem

The biggest problem with public goods is the ["free rider problem"](https://en.wikipedia.org/wiki/Free_rider_problem). A free rider is someone who uses a public good but who does not pay anything (or pay enough) towards its cost or production. If the maintainers of a public good do not address the free-rider problem it can lead to the non-production or under-production of a public good. This is generally known as the ["Tragedy of the Commons"](https://en.wikipedia.org/wiki/Tragedy_of_the_commons).

In Open Source, a free-rider is someone who uses an Open Source software project without contributing to it. If too few people or organizations contribute to the project, the project can become unhealthy, and ultimately could cease to exist.

The free-rider problem is typical for public goods and does not usually arise with private businesses. For example, community-maintained software like [Drupal](https://www.drupal.org) may have many free riders but proprietary competitors like Adobe or Sitecore have no problem excluding those who will not pay a license fee.

To properly understand the free-rider problem and public good provision, we need to understand both self-interest theory and the theory of collective action. I'll discuss both theories and apply them to Open Source.

### Self-interest theory

Open Source contributors do amazing things. They contribute to fixing the hardest problems, they share their expertise, and more. Actions like these are often described as altruistic, in contrast to the pursuit of self-interest. In reality, generosity is often driven by some level of self-interest: we provide value to others when it benefits ourselves.

Many reasons exist why people contribute to Open Source projects; people contribute because they enjoy being part of a community of like-minded people, to hone their technical skills, to get recognition, to try and make a difference in the world, because they are paid to, or for [different forms of "social capital"](https://dri.es/open-source-and-social-capital). Often we contribute because by improving the world we are living in, we are making our world better too.

Modern economics suggest that both individuals and organizations tend to act in their own self-interest, bound by morals, ethics, the well-being of future generations and more. The theory of self-interest goes back to the writings of the old Greeks, is championed by early modern economists, and is still being adhered to by late-modern economists. It follows from the theory of self-interest that we'd see more individuals and organizations contribute if they received more benefits.

While contributing to Open Source clearly has benefits, it is [not obvious if the benefits outweigh the cost](https://dri.es/the-investment-case-for-employing-a-drupal-core-contributor). If we can increase the benefits, there is no doubt we can can attract more contributors.

### Collective action theory

The theory of self-interest also applies to groups of individuals. In his seminal work on [collective action and public goods](https://www.amazon.com/The-Logic-Collective-Action-printing/dp/0674537513), economist [Mancur Olson](https://en.wikipedia.org/wiki/Mancur_Olson) shows that the incentive for group action diminishes as group size increases. Large groups are less able to act in their common interest than small ones because (1) the complexity increases and (2) the benefits diminish.

We see this first hand in Open Source projects. As an Open Source project grows, aspects of the development, maintenance and operation have to be [transferred from volunteers to paid workers](https://dri.es/the-commercialization-of-a-volunteer-driven-open-source-project). Linux is a good example. Without Red Hat, IBM and Dell employing full-time Linux contributors, Linux might not have the strong market share it has today.

The concept of major public goods growing out of volunteer and community-based models is not new to the world. The first trade routes were ancient trackways, which citizens later developed on their own into roads suited for wheeled vehicles in order to improve commerce. Transportation was improved for all citizens, driven by the commercial interest of some. Today, we certainly appreciate that full-time government workers maintain the roads. Ditto for the national defense system, basic education, etc.

The theory of collective action also implies that as an Open Source project grows, we need to evolve how we incent contributors or we won't be able to attract either part-time volunteers or full-time paid contributors.

### Selective benefits

Solutions for the free-rider problem and collective action problem exist, and this is where Open Source can learn from public goods theory and research. The most common solution for the free-rider problem is taxation; the government mandates all citizens to help pay for the production of the public good. Taxpayers help pay for our basic education system, the road system and national defense for example. Other solutions are privatization, civic duty or legislation. These solutions don't apply to Open Source.

I believe the most promising solution for Open Source is known as "privileged groups". Privileged groups are those who receive "selective benefits". Selective benefits are benefits that can motivate participation because they are available only to those who participate. The study of collective action shows that public goods are still produced when a privileged group benefits more from the public good than it costs them to produce it.

In fact, prominent "privileged groups" examples exist in the Open Source community; [Automattic](http://automattic.com) is a privileged group in the [WordPress community](http://wordpress.org) as it is in a unique position to make many millions of dollars from [WordPress.com](https://wordpress.com). [Mozilla Corporation](https://www.mozilla.org/en-US/foundation/moco/), the for-profit subsidiary of the Mozilla Foundation, is a privileged group as it is in a unique position to get paid millions of dollars by Google. As a result, both Automattic and Mozilla Corporation are willing to make significant engineering investments in WordPress and Mozilla, respectively. Millions of people in the world benefit from that every day.

Drupal is different from Automattic and Mozilla in that no single organization benefits uniquely from contributing. For example, my company Acquia currently employs the most full-time contributors to Drupal but does not receive any exclusive benefits in terms of monetizing Drupal. While Acquia does accrue some value from hiring the Drupal contributors that it does, this is something any company can do.

### Better incentives for Drupal contributors

It's my belief that we should embrace the concept of "privileged groups" and "selective benefits" in the Drupal community to help us grow and maintain the Drupal project. Furthermore, I believe we should provide "selective benefits" in a way that encourages fairness and equality, and doesn't primarily benefit any one particular organization.

From the theory of self-interest it follows that to get more paid core contributors we need to provide more and better benefits to organizations that are willing to let their employees contribute. Drupal agencies are looking for two things: customers and Drupal talent.

Many organizations would be eager to contribute more if, in return, they were able to attract more customers and/or Drupal talent. Hence, the "selective benefits" that we can provide them are things like:

- Organizational profile pages on drupal.org with badges or statistics that prominently showcase their contributions,
- Advertising on the drupal.org in exchange for fixing critical bugs in Drupal 8 (imagine we rewarded each company that helped fix a critical Drupal 8 bug 10,000 ad views on the front page of drupal.org),
- Better visibility on [Drupal.org's job board](http://jobs.drupal.org) for those trying to hire Drupal developers,
- The ability to sort the marketplace by contributions, rather than just alphabetically
- ...

I'm particularly excited about providing ads in exchange for contributing. Contributing to Drupal now becomes a marketing expense; the more you contribute, the more customers you can gain from drupal.org. We can even direct resources; award more ad views in exchange for fixing UX problems early in the development cycle, but award critical bugs and beta blockers later in the development cycle. With some relatively small changes to drupal.org, hiring a full-time core developer becomes a lot more interesting.

By matching the benefits to the needs of Drupal agencies, we candirect more resources towards Drupal development. I also believe this system to be fair; all companies can choose to contribute to Drupal 8 and earn advertising credits, and all participants are rewarded equally. We can turn Drupal.org into a platform that encourages and directs participation from a large number of organizations.

Systems like this are subject to gaming but I believe these challenges can be overcome. Any benefit is better than almost no benefit. In general, it will be interesting to see if fairness and heterogeneity will facilitate or impede contribution compared to Open Source projects like WordPress and Mozilla, where some hold unique benefits. I believe that if all participants benefit equally from their contributions, they have an incentive to match each other's contributions and it will facilitate the agreement and establishment of a contribution norm that fosters both cooperation and coordination, while minimizing gaming of the system. In contrast, when participants benefit very differently, like with WordPress and Mozilla, this decreases the willingness to cooperate, which, in turn, could have detrimental effects on contributions. While not necessarily the easiest path, I believe that making the system fair and heterogeneous is the "Drupal way" and that it will serve us in the long term.

### Conclusions

There are plenty of technical challenges ahead of us that we need to work on, fun ideas that we should experiment with, and more. With some relatively small changes, we could drastically change the benefits of contributing to Drupal. Better incentives mean more contributors, and more contributors mean that we can try more things and do things better and faster. It means we can scale Drupal development to new heights and with that, increase Open Source's impact on the world.

*(I talked about this in [my DrupalCon Amsterdam keynote](https://dri.es/state-of-drupal-presentation-september-2014). If you're hungry for more, I recommend that you check out my slides or video recording.)*
