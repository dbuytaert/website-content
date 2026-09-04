---
url: 'https://dri.es/open-source-is-four-kinds-of-economic-goods'
title: 'Open Source is four kinds of economic goods'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2026-09-01T06:50:24-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'Open Source code and the stewardship around it have different economics. That distinction helps show what a project might charge for, what it must budget for, and how it could fund stewardship without making the code less open.'
tags:
  - 'Open Source'
  - 'Open Source sustainability'
image: blog/open-source-makers-and-takers-1
discussions:
  - { platform: LinkedIn, url: 'https://www.linkedin.com/feed/update/urn:li:activity:7500535411987898369/' }
published: true
featured: false
id: 6316
---

# Open Source is four kinds of economic goods

![A scale that is in balance](http://default/files/cache/blog/open-source-makers-and-takers-1-640w.jpg)

An Open Source project contains several economic goods. Its code, infrastructure, services, maintainer time, and commercial ecosystem each behave differently. Treating all of them as a single commons hides who pays today, who controls access, and who needs to pay.

Economists often classify goods along two dimensions. The first is *excludability*: how easy it is to keep someone from using something. The second is *rivalry*: whether one person's use leaves less for everyone else.

Combining those dimensions produces [four kinds of goods](https://doi.org/10.1177/0951692803015003002).

<table>
  <colgroup>
  <col style="width: 14%">
  <col style="width: 43%">
  <col style="width: 43%">
</colgroup>
  <thead>
  <tr>
  <th></th>
  <th>Excludable</th>
  <th>Non-excludable</th>
</tr>
</thead>
  <tbody>
  <tr>
  <th>Rival</th>
  <td><strong>Private goods</strong><br>Sandwiches</td>
  <td><strong>Common-pool resources</strong><br>Fish in the ocean</td>
</tr>
  <tr>
  <th>Non-rival</th>
  <td><strong>Toll goods</strong><br>Toll roads, until they reach capacity</td>
  <td><strong>Public goods</strong><br>Weather forecasts</td>
</tr>
</tbody>
</table>

A *private good* is both excludable and rival. A sandwich is a simple example: the shop can choose whether to sell it to me (excludable), but once I eat it, nobody else can (rival).

A *public good* is hard to exclude people from and is not used up through use. A weather forecast is a good example: once published, it is hard to prevent people from using it (non-excludable), and one person's use does not make the forecast less available to anyone else (non-rival).

A *common-pool resource* is also hard to exclude people from, but it is rival. Fish in the ocean are the standard example. It's hard to prevent people from fishing the ocean (non-excludable), but one person's catch leaves fewer fish for everyone else (rival).

A *toll good* is excludable but largely non-rival until it reaches capacity. A toll road can keep drivers out (excludable), but one more car does not reduce anyone else's access until traffic builds up (non-rival until congestion). James Buchanan also called these [club goods](https://doi.org/10.2307/2552442).

## The four goods in an Open Source project

People often describe Open Source as both a public good and a commons, but the terms answer different questions. A public good describes a resource's economic characteristics; a commons describes how shared resources are governed. 

An ecosystem can be governed as a commons even when its parts have different economic characteristics. That is why it's useful to classify things like code, infrastructure, maintainer time, or collective reputation separately.

<table>
  <colgroup>
  <col style="width: 14%">
  <col style="width: 43%">
  <col style="width: 43%">
</colgroup>
  <thead>
  <tr>
  <th></th>
  <th>Excludable</th>
  <th>Non-excludable</th>
</tr>
</thead>
  <tbody>
  <tr>
  <th>Rival</th>
  <td><strong>Private goods</strong><br>Dedicated support, consulting, and maintainer attention</td>
  <td><strong>Common-pool resources</strong><br>The pool of commercial opportunities the project generates</td>
</tr>
  <tr>
  <th>Non-rival</th>
  <td><strong>Toll goods</strong><br>Access to project-operated package registries, update and security data services, and marketplace visibility</td>
  <td><strong>Public goods</strong><br>Released Open Source code</td>
</tr>
</tbody>
</table>

Open Source code itself behaves much like a [public good](https://doi.org/10.2307/1925895). Making another copy does not reduce what others can use. And because Open Source licenses allow recipients to redistribute the code, restricting access becomes difficult after release.

Steven Weber goes further in [*The Success of Open Source*](https://www.hup.harvard.edu/books/9780674018587), describing Open Source as *anti-rival* (not a dimension shown in the table). Under the right conditions, its value can grow as adoption and participation grow. More users can bring more testing, bug reports, features, documentation, promotion, and other contributions.

But the code is only one part of an Open Source project.

Many large projects are [Stewarded Open Source](https://dri.es/license-only-versus-stewarded-open-source). A foundation, company, or community operates its package registries and build systems, responds to security issues, coordinates releases, and more. Each of those activities has its own economics and can be mapped to the four types of economic goods.

A project-operated package registry or the data service behind in-product update and security notifications can behave like a toll good. The project could rate-limit access, require accounts, or reserve additional capacity and features for paying customers.

Support and consulting are private goods. A contract determines who receives the service, and an hour spent helping one customer cannot also be spent helping another.

Maintainer attention can also behave like a private good. Access to dedicated review time can be restricted (excludable), and time spent reviewing one patch cannot also be spent on another (rival).

However, that private input can produce a public good. A funder can pay a maintainer to fix a bug or review a patch, but once the improvement is released under the project's Open Source license, anyone can use and redistribute it. Economists call this the [private provision of a public good](https://doi.org/10.1016/0047-2727%2886%2990024-1).

The commercial opportunities an Open Source project generates are a common-pool resource. Customers arrive looking for help because the project has a reputation, and any provider can pursue them (non-excludable). But an engagement won by one provider is gone for the others (rival). The pool of potential customers is the ocean; a signed contract is a fish that has been caught.

What keeps that pool stocked is the project's [collective reputation](https://doi.org/10.18352/ijc.657). It is built by many contributors, and every provider draws on it, whether they contributed or not. A provider can win engagements from the pool without helping maintain the project that produces them. Poor-quality work or unhealthy competition can weaken the reputation, and a weaker reputation means fewer customers arrive for everyone.

This is why I have argued that Open Source communities should help customers distinguish between [Makers and Takers](https://dri.es/solving-the-maker-taker-problem). Making contribution visible steers commercial demand toward providers that help sustain the project and the reputation that keeps customers coming.

A project-operated marketplace that lists service providers is one way to do this. Access to it can behave like a toll good: the project controls which providers it lists (excludable), while listing one more provider usually does not prevent others from participating (non-rival). Open Source gives providers rights to the code, not a right to promotion by the project. A project can therefore require providers to contribute as a condition of marketplace participation.

## A funding rule for stewardship

For an Open Source project, this framework leads to two practical questions: what can it charge for, and what does it need to budget for?

Excludability shows where an Open Source project can control access and therefore where direct pricing is possible. For example, a project could charge for access to its package registry, security notification service, or provider listings in its marketplace. In each case, the project controls something separate from the released code, which remains available to everyone.

Rivalry shows what use can deplete and therefore where capacity must be budgeted. Copies of code do not run out. Bandwidth, server capacity, staff time, and maintainer attention do. A project may still choose to provide them for free, but [someone always has to absorb their cost](https://dri.es/open-source-is-a-cost-allocation-system).

Together, the two dimensions suggest a simple funding model: **revenue from excludable goods can pay for rival resources**, while Open Source code remains a public good.

That does not mean every excludable service should be put behind a paywall. Charging everyone to use a package registry could slow adoption by making the software harder to try. It's why I previously proposed [a tiered model for Open Source infrastructure](https://dri.es/open-source-infrastructure-deserves-a-business-model): keep core services free for individuals and small projects, while asking organizations that use them at scale to help pay for what they consume.

Across the four categories, projects can look to private and toll goods for funding, protect common-pool resources from depletion, and use that funding to pay for the work that produces public goods. 

Projects that do not make those arrangements explicit will continue to depend on invisible subsidies for infrastructure and maintainer work.

PS: Follow the discussion on [LinkedIn](https://www.linkedin.com/feed/update/urn:li:activity:7500535411987898369/).
