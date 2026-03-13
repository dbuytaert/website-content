---
url: 'https://dri.es/what-it-costs-to-run-drupal-infrastructure'
title: "What it costs to run Drupal's infrastructure"
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2026-03-10T18:30:34-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
  - 'Drupal Association'
image: blog/complex-infrastructure
discussions:
  - { platform: LinkedIn, url: 'https://www.linkedin.com/posts/buytaert_what-does-it-cost-to-run-drupals-infrastructure-share-7437295844397125632-feut/' }
published: true
featured: false
id: 6131
---

# What it costs to run Drupal's infrastructure

[image blog/complex-infrastructure priority=true]

Yesterday I wrote about [how Open Source infrastructure across many ecosystems is fragile and underfunded](https://dri.es/open-source-infrastructure-deserves-a-business-model). 

Drupal is no exception.

Like most Open Source projects, Drupal runs on infrastructure that millions of people depend on but very few people directly pay for. 

Drupal's infrastructure costs roughly $3 million per year, including servers, bandwidth, CDNs, software, and staff.

Funding comes from a mix of donated infrastructure from [AWS](https://aws.amazon.com/) and the [OSU Open Source Lab](https://osuosl.org/), corporate memberships through our [Drupal Certified Partner program](https://www.drupal.org/drupal-services), in‑kind contribution from [Tag1](https://www.tag1.com/), revenue from DrupalCon, donations, and sponsorship on [Drupal.org](https://www.drupal.org).

Last year, Drupal Association board member [Tiffany Farriss](https://www.drupal.org/u/farriss) and CTO [Tim Lehnen](https://www.drupal.org/u/hestenet) analyzed the project's infrastructure costs. Their estimate: infrastructure for Drupal 8+ sites costs about $10 per active website per year. 

But the Drupal Association has only about $7.50 per site per year to work with. About $3 comes from DrupalCon and the Certified Partner program. The remaining $4.50 comes from in-kind support: donated hosting, Tag1's infrastructure partnership, volunteer contributions and more.

The missing $2.50 per site shows up as technical debt: certain upgrades get deferred, legacy systems persist longer than they should, and the community sometimes wonders why infrastructure progress feels slow.

Plus, the $7.50 per site we currently fund is fragile. DrupalCon revenue depends on event attendance. Advertising depends on traffic. Tag1's in-kind contribution depends on one company's continued generosity. Our donated infrastructure from AWS and OSU could disappear at any time. If any of that support disappears, the funding gap grows, more infrastructure work gets deferred, and things could start breaking.

Before talking about new funding models, it is worth asking whether the Drupal Association could reduce its infrastructure costs. Ten dollars per site per year may sound like a lot. Should we operate all of this infrastructure ourselves, or rely more on hosted platforms like GitHub or GitLab.com? Are parts of our infrastructure more complex than they need to be? Could we customize less to reduce costs and move faster?

These are the right questions to ask. I believe we need to work both sides of the ledger: take a hard look at what we spend and build a funding model that depends less on goodwill. In practice, infrastructure decisions rarely optimize for everything at once. They involve tradeoffs between cost, speed, flexibility, and control.

Corporate patronage is worth considering. A single well-resourced sponsor could fund Drupal's infrastructure in a way community fundraising cannot, and if the choice were between a patron and a crisis, a patron wins. It's fast, requires no technical changes, and doesn't touch the social contract with site owners.

But patronage trades one fragility for another. Instead of depending on event attendance or AWS cloud credits, you depend on one company's continued generosity and strategic alignment with the project. If their priorities shift, we're back where we started. 

A patron funding infrastructure at this scale would also expect meaningful benefits. That could mean greater visibility, access to lead flow, and some level of control over Drupal.org.

Most infrastructure systems connect usage to funding. Cloud platforms charge for compute. Roads are funded by taxes paid by the people who drive them. Drupal's infrastructure has no such mechanism: hundreds of thousands of sites depend on Drupal.org services, but the cost of operating those services is disconnected from the people who rely on them.

A funding model tied to usage avoids some of the issues with corporate patronage, but comes with its own trade-off. Open Source culture is built on anonymous access. You can download any package, no questions asked, no account required. Any usage-based model has to break that norm. 

The simplest version would probably require a Drupal.org API key to download packages or receive automatic update notifications. Requiring an API key is standard practice for any commercial API, but in Open Source it feels different. Requiring site owners to identify themselves to Drupal.org is a cultural shift, even if the key itself is free forever. 

Any such mechanism requires changes to Drupal Core, which could take years to reach the installed base. If we go down this route, we can't wait for a funding crisis to begin this work. By the time a real crisis arrives, we could still be years away from a solution.

I don't have a specific mechanism to propose yet. My goal here is to lay out the problem, explore potential solutions, and start the conversation. But we should start that conversation now, while we have the time and stability to get it right. Otherwise we may end up having this conversation later, under more pressure and with fewer options.

*Thanks to [Tiffany Farriss](https://www.drupal.org/u/farriss), [Tim Lehnen](https://www.drupal.org/u/hestenet), [Gábor Hojtsy](https://www.drupal.org/u/gábor-hojtsy) and [Lauri Timmanee](https://www.drupal.org/u/lauriii) for reviewing my draft.*

PS: Follow the discussion on [LinkedIn](https://www.linkedin.com/posts/buytaert_what-does-it-cost-to-run-drupals-infrastructure-share-7437295844397125632-feut/).
