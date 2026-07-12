---
url: 'https://dri.es/license-only-versus-stewarded-open-source'
title: 'License-only versus Stewarded Open Source'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2026-07-09T17:26:00-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'Some Open Source is simply shared. Some is maintained as infrastructure. Naming the difference changes the conversation.'
tags:
  - 'Open Source'
image: blog/cost-of-maintenance
discussions:
  - { platform: LinkedIn, url: 'https://www.linkedin.com/posts/buytaert_not-all-open-source-is-the-same-some-is-activity-7481110706843496448-hije' }
published: true
featured: false
id: 6256
---

# License-only versus Stewarded Open Source

![View from under a sturdy stone bridge toward a fragile wooden bridge in the distance, with two people standing on it.](http://default/files/cache/blog/cost-of-maintenance-640w.jpg)

Near the end of most Open Source licenses, usually in capital letters, sits a clause that disclaims almost everything: no warranty, no liability, use at your own risk.

For an organization that depends on that code, the clause is harsh. If the code fails and takes your data or revenue with it, the license owes you nothing. No fix, no refund, and no one to explain what went wrong.

That is the Open Source license doing its job. It makes the code available and protects the people who share it. Without that protection, sharing code could become a gift that backfires: a generous act turned into unlimited legal risk.

But the license can only answer the legal questions: who may use the code, on what terms, and what risk the authors are willing to accept. It cannot tell you what kind of Open Source project you are working with.

Some Open Source is "License-only Open Source": code released under an Open Source license, without active stewardship or any promise of ongoing care. There is no guarantee of updates, fixes, security response, or long-term support.

Other Open Source is "Stewarded Open Source": code cared for as shared infrastructure. Maintainers review contributions, fix bugs, respond to security issues, manage releases, provide long-term support, and much more. Organizations fund maintainers, support core development, donate infrastructure, and absorb costs end users never see.

Both types of projects are Open Source, but they are _not_ the same. A weekend hobby project and business-critical software can ship under the exact same license. Legally, they look identical. Practically, they are worlds apart.

The difference is _stewardship_. The license makes code available; stewardship makes it dependable. And the more people or organizations depend on a project, the more stewardship it often requires.

<p class="pullquote">Responsibility is the tax on relevance.</p>

Distinguishing license-only from stewarded Open Source gives us the vocabulary to describe two very different realities that the words "Open Source" alone do not capture.

For example, the distinction becomes useful when we talk about contribution. If a company depends on Open Source, should it give back?

For license-only Open Source, the answer is simple: no one is required to contribute. The code was shared freely, without a promise of care or an expectation of return.

For stewarded Open Source, the answer is not so simple. The license may still say the software is provided as-is, used at your own risk. Legally, no one has to contribute back. But there is also an entire layer of stewardship on top of the code: security, release management, infrastructure, governance, marketing, long-term maintenance, and more. People and organizations take on responsibilities well beyond what the license requires so the software can be safer to adopt, easier to upgrade, and dependable in production.

For projects like Drupal, that layer costs millions of dollars a year, and someone pays for every piece of it. I explored this more concretely in [Open Source infrastructure deserves a business model](https://dri.es/open-source-infrastructure-deserves-a-business-model) and [what it costs to run Drupal's infrastructure](https://dri.es/what-it-costs-to-run-drupal-infrastructure).

When we call everything simply "Open Source", we hide the difference between code that was simply shared and infrastructure that is being cared for and de-risked. Better language will not solve the funding problem by itself, but it makes the responsibility visible. More honest conversations start there.

PS: Follow the discussion on [LinkedIn](https://www.linkedin.com/posts/buytaert_not-all-open-source-is-the-same-some-is-activity-7481110706843496448-hije).
