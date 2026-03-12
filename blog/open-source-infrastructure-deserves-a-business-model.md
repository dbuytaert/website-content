---
url: 'https://dri.es/open-source-infrastructure-deserves-a-business-model'
title: 'Open Source infrastructure deserves a business model '
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2026-03-09T14:36:23-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'Open Source infrastructure is essential, invisible, and chronically underfunded. A more sustainable approach may be to connect the cost of running that infrastructure to the organizations that rely on it most.'
tags:
  - 'Open Source'
  - Drupal
image: blog/open-source-infrastructure-cracks
discussions:
  - { platform: LinkedIn, url: 'https://www.linkedin.com/posts/buytaert_open-source-software-is-free-to-download-share-7436849612445036544-Blfk' }
published: true
featured: true
id: 6126
---

# Open Source infrastructure deserves a business model 

[image blog/open-source-infrastructure-cracks priority=true]

Open Source software is free to download. But the infrastructure that makes it usable is not.

When developers install or update dependencies through npm, Composer, pip, or Cargo, those tools rely on package registries that host and distribute millions of software packages. When maintainers collaborate, they depend on hosted services: Git repositories, CI pipelines, and other tools to build, test, and release software.

Most of this infrastructure is invisible to end users, and almost no one thinks about what it costs to run.

But it is not free. Someone has to operate the servers, pay for bandwidth, respond to support questions, patch security issues, and keep everything reliable.

Much of the modern software ecosystem depends on these services working reliably. And yet the organizations operating them are almost always scrambling to fund them.

### A patchwork of fragile arrangements

Every large Open Source project has found some way to keep its infrastructure running. Usually that means a mix of donated services, sponsorships, fundraising, cross-subsidy, or patronage from a single company.

The table below highlights the primary funding mechanisms various Open Source projects depend on, even though most projects combine several.

<table>
  <thead>
  <tr>
  <th></th>
  <th>Donated infrastructure</th>
  <th>Multi-company sponsorship</th>
  <th>Community funding</th>
  <th>Single-company patronage</th>
</tr>
</thead>
  <tbody>
  <tr>
  <td>PyPI</td>
  <td style="text-align:center;">☑</td>
  <td style="text-align:center;">☐</td>
  <td style="text-align:center;">☐</td>
  <td style="text-align:center;">☐</td>
</tr>
  <tr>
  <td>Packagist</td>
  <td style="text-align:center;">☐</td>
  <td style="text-align:center;">☐</td>
  <td style="text-align:center;">☐</td>
  <td style="text-align:center;">☑</td>
</tr>
  <tr>
  <td>npm</td>
  <td style="text-align:center;">☐</td>
  <td style="text-align:center;">☐</td>
  <td style="text-align:center;">☐</td>
  <td style="text-align:center;">☑</td>
</tr>
  <tr>
  <td>WordPress</td>
  <td style="text-align:center;">☐</td>
  <td style="text-align:center;">☐</td>
  <td style="text-align:center;">☐</td>
  <td style="text-align:center;">☑</td>
</tr>
  <tr>
  <td>RubyGems</td>
  <td style="text-align:center;">☐</td>
  <td style="text-align:center;">☑</td>
  <td style="text-align:center;">☑</td>
  <td style="text-align:center;">☐</td>
</tr>
  <tr>
  <td>Drupal</td>
  <td style="text-align:center;">☑</td>
  <td style="text-align:center;">☑</td>
  <td style="text-align:center;">☑</td>
  <td style="text-align:center;">☐</td>
</tr>
</tbody>
</table>

The mix differs across ecosystems, and some rely on several mechanisms at once. But one thing stands out: none of these approaches tie funding directly to how much the infrastructure is used.

[PyPI](https://pypi.org/), the Python Package Index, illustrates the sponsorship model. It handles billions of downloads a day on infrastructure donated by Fastly, AWS, and Google Cloud. The [Python Software Foundation](https://www.python.org/psf-landing/) described this arrangement's fragility in a [post last October](https://pyfound.blogspot.com/2025/10/open-infrastructure-is-not-free-pypi.html): if a single sponsor decides not to renew, it would cost them tens of thousands of dollars a month to replace the lost infrastructure.

[Packagist](https://packagist.org/), the main PHP package repository, follows a different approach. It is run by a private company that also sells a commercial product called [Private Packagist](https://packagist.com/). Revenue from the paid product subsidizes the free public registry. It's one of the more sustainable models out there, though it means a public good depends on one company's continued success.

[npm](https://www.npmjs.com/) tried to operate as an independent company, ran into serious financial trouble, and was eventually acquired by GitHub in 2020. The end result is that critical JavaScript infrastructure is now owned by Microsoft.

[WordPress.org](https://wordpress.org/) runs on a different version of the same dynamic: corporate patronage. Automattic, by far the ecosystem's largest commercial beneficiary, subsidizes most of the infrastructure. It works, but it also means that whoever funds the infrastructure controls it. 

The [FAIR project](https://fair.pm/), a federated package manager backed by the Linux Foundation, was designed to give the WordPress ecosystem an independent alternative. The software works but its organizers recently stepped back after [failing to secure long-term funding commitments](https://joost.blog/fair-wordpress-and-knowing-when-to-stop/).

[RubyGems](https://rubygems.org/) took the community fundraising route, [launching a program](https://rubycentral.org/news/rubygems-org-funding-model-a-new-path-for-community-led-growth/) last year asking businesses for $2,500 to $5,000 annually, with about 110 supporters needed to cover the registry's operations.

[Drupal](https://www.drupal.org), the Open Source CMS I help lead, depends on the Drupal Association to run much of the infrastructure behind the project: Composer endpoints, GitLab repositories, CI pipelines, automatic update notifications, and more. Running all of this costs roughly $3 million a year. Funding comes from a mix of donated infrastructure, community funding, DrupalCon revenue, and sponsorship.

When the economics break, the consequences become visible. In February 2026, [GNOME](https://www.gnome.org/) began [redirecting Git traffic from its own GitLab to GitHub mirrors](https://www.phoronix.com/news/GNOME-GitHub-GitLab-Redirect) to reduce bandwidth costs. As a result, GitHub and its owner Microsoft now absorb some of GNOME's bandwidth cost.

Taken together, these examples point to the same underlying problem. Most Open Source infrastructure does not have a real business model. It survives through donations, corporate sponsorship, and community fundraising, rather than revenue tied to the value it delivers.

### From steward to service provider

One direction that makes sense to me is a simple _value exchange_: keep core infrastructure free for individuals and small projects, while organizations using it at scale help pay for what they consume. Not as a donation, but as payment for the infrastructure their software depends on.

I look at Drupal as a concrete example of this in a follow-up post: [what it costs to run Drupal's infrastructure](https://dri.es/what-it-costs-to-run-drupal-infrastructure).

In practice, this could mean the backend infrastructure around Open Source projects operating more like a SaaS service: the software remains open, but the infrastructure that powers updates and security becomes a paid service for large organizations.

Some people will instinctively resist the idea of charging for the infrastructure behind an Open Source project. That reaction may feel familiar to anyone who remembers [the early debates about paid contributors](https://dri.es/the-commercialization-of-a-volunteer-driven-open-source-project). At the time, many feared corporate money would drive volunteers away. In practice, the opposite happened. Projects grew, contributor bases expanded, and paid engineers became some of their most active contributors.

That does not mean every new funding idea is a good one. But instinctive discomfort alone is not a reason to reject it. 

In Open Source, what looks like fairness often is not. Free for everyone sounds equitable, but the cost does not disappear. It is absorbed by those who can least afford it, while the organizations that benefit most often pay the least. When a Fortune 500 company consumes Open Source infrastructure for free, that is not a neutral outcome. It is a subsidy flowing in the wrong direction.

If the problem is that costs are disconnected from usage, the obvious place to start is linking them. Exactly how that would work in practice is a separate design question, and the answer will likely differ from one Open Source project to another. One possible approach is usage-based fees, tiered by download volume or API consumption. Questions about measurement, thresholds, and enforcement would need careful community discussion.

### Governance is downstream of funding

If infrastructure funding models need to change, the obvious question is who decides. In Open Source, questions like this ultimately belong to the community.

But communities do not decide these things in a vacuum. In practice, governance tends to follow funding.

Discussions about Open Source infrastructure often focus on governance: who should control it and who gets to make the decisions. In reality, those questions are often settled by something simpler: who pays for it.

FAIR is a recent example. The organizers didn't step back because federation was the wrong idea. They stepped back because no host would commit funding.

When one organization pays for the infrastructure, it ultimately controls it. When a broader set of stakeholders funds it, governance broadens with it.

That is why Open Source infrastructure needs more than better fundraising. It needs a business model that connects the cost of operating shared infrastructure to the organizations that rely on it most.

Infrastructure that entire ecosystems depend on cannot rely indefinitely on goodwill alone. It deserves a business model.

Solving the funding problem is a prerequisite to solving the governance problem.

*Thanks to [Tiffany Farriss](https://www.drupal.org/u/farriss), [Tim Lehnen](https://www.drupal.org/u/hestenet), [Gábor Hojtsy](https://www.drupal.org/u/gábor-hojtsy) and [Lauri Timmanee](https://www.drupal.org/u/lauriii) for reviewing my draft.*

PS: Follow the discussion on [LinkedIn](https://www.linkedin.com/posts/buytaert_open-source-software-is-free-to-download-share-7436849612445036544-Blfk).
