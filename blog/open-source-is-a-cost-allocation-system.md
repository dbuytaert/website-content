---
url: 'https://dri.es/open-source-is-a-cost-allocation-system'
title: 'Open Source is a cost-allocation system'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2026-08-27T15:21:42-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'Because the right to use the software is not tied to payment, the license does not connect the people who benefit, the people who decide, and the people who bear the costs. Projects have to build those connections deliberately through governance.'
tags:
  - Drupal
  - 'Open Source'
  - Governance
  - 'Open Source sustainability'
  - 'Drupal Association'
image: blog/cost-of-maintenance
discussions:
  - { platform: LinkedIn, url: 'https://www.linkedin.com/feed/update/urn:li:activity:7498825163527073792/' }
published: true
featured: false
id: 6311
---

# Open Source is a cost-allocation system

![View from under a sturdy stone bridge toward a fragile wooden bridge in the distance, with two people standing on it.](http://default/files/cache/blog/cost-of-maintenance-640w.jpg)

Open Source is usually described as a licensing model, a development model, or a production model. All three descriptions are useful, but they leave something out. Every Open Source ecosystem is also a *cost-allocation system*.

Keeping software relevant and dependable requires people to write code, review contributions, prepare releases, investigate security reports, operate infrastructure, write documentation, answer questions, and support upgrades and migrations. Someone always bears those costs.

A proprietary vendor can tie access to payment: every license or subscription sold helps fund developers, security work, infrastructure, and releases.

Open Source breaks the link between access and payment. Anyone can redistribute the software at any price, including zero. Payment is therefore not a condition of using or redistributing it, and those rights do not themselves provide a durable mechanism for funding production and maintenance.

But separating payment from access does not make the costs disappear. Costs are distributed across maintainers, employers, foundations, sponsors, and users. A maintainer may volunteer their time. An employer may pay a developer to contribute. A foundation may operate infrastructure.

Because these costs are distributed rather than collected through a single transaction, they are harder to see and harder to fund. 

Technical choices often shape where those costs fall. That allocation is not always deliberate; it can emerge slowly from decisions that were individually reasonable and become visible only years later.

Drupal's update service recently gave me a good example. Drupal sites periodically contact `updates.drupal.org` to ask whether new versions of Drupal or any installed add-ons are available. Drupal calls these add-ons "contributed projects", such as modules and themes maintained by members of the community.

The current design sends one request for Drupal itself and one for every contributed project installed on the site. A site with 100 contributed projects therefore makes 101 requests each time it checks for updates, by default, once a day.

There were good reasons for that design. Each project's release history could be stored as a static file and served repeatedly without rebuilding it for every request. The design was straightforward, and it worked.

But Drupal grew. Today, `updates.drupal.org` serves nearly a billion requests a month. The file containing [Drupal Core's release history](https://updates.drupal.org/release-history/drupal/current) is roughly half a megabyte by itself. Based on the number of requests for that file, I estimate that Drupal Core update checks alone may account for roughly 50 to 75 TB of data transfer each month. Traffic for contributed projects comes on top of that.

No one chose to make `updates.drupal.org` transfer tens of terabytes of release data each month. That scale emerged gradually as Drupal grew, from a design that had been reasonable when the ecosystem was smaller.

Part of the challenge is that, in Open Source, the people who benefit, the people who decide, and the people who bear the costs are often different and may have no formal obligations to one another.

Site owners benefit from reliable update notifications, usually without paying the Drupal Association for them. Drupal Association staff operate the update service, while the Association bears its traffic and infrastructure costs. But the code that determines how sites make those requests lives in Drupal Core, where changes require the involvement of Core committers. The Core committers do not report to the Drupal Association, so the Association cannot change that behavior on its own.

In practice, Drupal Association staff and Core committers collaborate closely. That collaboration is important because decision-making authority and cost-bearing sit with different groups.

The people bearing material costs need a way to make those costs visible and influence the decision, even if they do not control it.

This example shows why every Open Source architecture is also a cost-allocation system. Good governance considers that allocation up front, monitors its effects over time, and revisits it when it becomes unsustainable.

Understanding an Open Source system therefore requires more than understanding its code or license. We also need to understand who benefits, who decides, and who bears the costs as the system grows. Once those relationships are visible, a community can decide whether the allocation is sustainable or whether the architecture should change.

PS: Follow the discussion on [LinkedIn](https://www.linkedin.com/feed/update/urn:li:activity:7498825163527073792/).
