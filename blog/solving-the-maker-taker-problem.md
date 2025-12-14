---
title: 'Solving the Maker-Taker problem'
date: '2024-10-02T12:06:58-04:00'
author: Dries
summary: "How open source projects can balance Makers and Takers: lessons from Drupal's contribution credit system and recommendations for WordPress and other open source communities."
image: blog/open-source-makers-and-takers-6
tags:
  - Drupal
  - WordPress
  - 'Open Source'
  - 'Drupal Association'
featured: true
published: true
type: blog
url: /solving-the-maker-taker-problem
id: 5691
---

[image blog/open-source-makers-and-takers-6]

Recently, a [public dispute](https://lwn.net/SubscriberLink/991906/e5bc182f5602ffca/) has emerged between WordPress co-founder Matt Mullenweg and hosting company WP Engine. Matt has accused WP Engine of misleading users through its branding and profiting from WordPress without adequately contributing back to the project.

As the Founder and Project Lead of [Drupal](https://www.drupal.org/), another major open source Content Management System (CMS), I hesitated to weigh in on this debate, as this could be perceived as opportunistic. In the end, I decided to share my perspective because this conflict affects the broader open source community.

I've known Matt Mullenweg since the early days, and we've grown both our open source projects and companies alongside each other. With our shared interests and backgrounds, [I consider Matt a good friend](https://dri.es/two-internet-entrepreneurs-walk-into-an-old-publishing-house) and can relate uniquely to him. Equally valuable to me are my relationships with WP Engine's leadership, including CEO Heather Brunner and Founder Jason Cohen, both of whom I've met several times. I have deep admiration for what they've achieved with WP Engine.

Although this post was prompted by the controversy between Automattic and WP Engine, it is *not* about them. I don't have insight into their respective contributions to WordPress, and I'm not here to judge. I've made an effort to keep this post as neutral as possible.

Instead, this post is about two key challenges that many open source projects face:

1. The imbalance between major contributors and those who contribute minimally, and how this harms open source communities.
2. The lack of an environment that supports the fair coexistence of open source businesses.

These issues could discourage entrepreneurs from starting open source businesses, which could harm the future of open source. My goal is to spark a constructive dialogue on creating a more equitable and sustainable open source ecosystem. By solving these challenges, we can build a stronger future for open source.

This post explores the "Maker-Taker problem" in open source, using Drupal's contribution credit system as a model for fairly incentivizing and recognizing contributors. It suggests how WordPress and other open source projects could benefit from adopting a similar system. While this is unsolicited advice, I believe this approach could help the WordPress community heal, rebuild trust, and advance open source productively for everyone.

### The Maker-Taker problem

At the heart of this issue is the Maker-Taker problem, where creators of open source software ("Makers") see their work being used by others, often service providers, who profit from it without contributing back in a meaningful or fair way ("Takers").

Five years ago, I wrote a blog post called [Balancing Makers and Takers to scale and sustain Open Source](https://dri.es/balancing-makers-and-takers-to-scale-and-sustain-open-source), where I defined these concepts:

> The difference between Makers and Takers is not always 100% clear, but as a rule of thumb, Makers directly invest in growing both their business and the open source project. Takers are solely focused on growing their business and let others take care of the open source project they rely on.

In that post, I also explain how Takers can harm open source projects. By not contributing back meaningfully, Takers gain an unfair advantage over Makers who support the open source project. This can discourage Makers from keeping their level of contribution up, as they need to divert resources to stay competitive, which can ultimately hurt the health and growth of the project:

> Takers harm open source projects. An aggressive Taker can induce Makers to behave in a more selfish manner and reduce or stop their contributions to open source altogether. Takers can turn Makers into Takers.

Solving the Maker-Taker challenge is one of the biggest remaining hurdles in open source. Successfully addressing this could lead to the creation of tens of thousands of new open source businesses while also improving the sustainability, growth, and competitiveness of open source. It would make such a positive impact on the world.

### Drupal's approach: the Contribution Credit System

In Drupal, we've adopted a positive approach to encourage organizations to become Makers rather than relying on punitive measures. Our approach stems from a key insight, also explained in [my Makers and Takers blog post](https://dri.es/balancing-makers-and-takers-to-scale-and-sustain-open-source): customers are a "common good" for an open source project, not a "public good".

Since a customer can choose only one service provider, that choice directly impacts the health of the open source project. When a customer selects a Maker, part of their revenue is reinvested into the project. However, if they choose a Taker, the project sees little to no benefit. This means that open source projects grow faster when commercial work flows *to Makers* and *away from Takers*.

For this reason, it's crucial for an open source community to:

1. Clearly identify the Makers and Takers within their ecosystem
2. Actively support and promote their Makers
3. Educate end users about the importance of choosing Makers

To address these needs and solve the Maker-Taker problem in Drupal, I proposed a [contribution credit system](https://dri.es/a-method-for-giving-credit-to-organizations-that-contribute-code-to-open-source) 10 years ago. The concept was straightforward: incentivize organizations to contribute to Drupal by giving them tangible recognition for their efforts.

We've since implemented this system in partnership with the [Drupal Association](https://www.drupal.org/association), our non-profit organization. The Drupal Association transparently tracks contributions from both individuals and organizations. Each contribution earns credits, and the more you contribute, the more visibility you gain on [Drupal.org](https://www.drupal.org/) (visited by millions monthly) and at events like [DrupalCon](https://dri.es/tag/drupalcon) (attended by thousands). You can earn credits by contributing code, submitting case studies, organizing events, writing documentation, financially supporting the Drupal Association, and more.

[image drupal/example-issue-credit-on-drupal-org-2016 resize=false]

Drupal's credit system is unique and groundbreaking within the Open Source community. The Drupal contribution credit system serves two key purposes: it helps us identify who our Makers and Takers are, and it allows us to guide end users towards doing business with our Makers.

Here is how we accomplish this:

- Certain benefits, like event sponsorships or advertising on Drupal.org, are reserved for organizations with a minimum number of credits.
- The [Drupal marketplace](https://www.drupal.org/drupal-services) only lists Makers, ranking them by their contributions. Organizations that stop contributing gradually drop in ranking and are eventually removed.
- We encourage end users to require open source contributions from their vendors. Drupal users like Pfizer and the State of Georgia only allow Makers to apply in their vendor selection process.

<div class="large">
  [image drupalcon-barcelona-2024/certified-partner-contributions]
</div>

### Governance and fairness

To make sure the contribution credit system is fair, it benefits from the oversight from an independent, neutral party.

In the Drupal ecosystem, the Drupal Association fulfills this crucial role. The Drupal Association operates independently, free from control by any single company within the Drupal ecosystem. Some of the Drupal Association's responsibilities include:

1. Organizing DrupalCons
2. Managing Drupal.org
3. Overseeing the contribution tracking and credit system

It's important to note that while I serve on the Drupal Association's Board, I am just one of 12 members and have not held the Chair position for several years. My company, Acquia, receives no preferential treatment in the credit system; the visibility of any organization, including Acquia, is solely determined by its contributions over the preceding twelve months. This structure ensures fairness and encourages active participation from all members of the Drupal community.

Drupal's credit system certainly isn't perfect. It is hard to accurately track and fairly value diverse contributions like code, documentation, mentorship, marketing, event organization, etc. Some organizations have tried to game the system, while others question whether the cost-benefit is worthwhile.

As a result, Drupal's credit system has evolved significantly [since I first proposed it ten years ago](https://dri.es/a-method-for-giving-credit-to-organizations-that-contribute-code-to-open-source). The Drupal Association continually works to improve the system, aiming for a credit structure that genuinely drives positive behavior.

### Recommendations for WordPress

WordPress has already taken steps to address the Maker-Taker challenge through initiatives like the [Five for the Future](https://wordpress.org/five-for-the-future/) program, which encourages organizations to contribute 5% of their resources to WordPress development.

Building on this foundation, I believe WordPress could benefit from adopting a contribution credit system similar to Drupal's. This system would likely require the following steps to be taken:

1. Expanding the current governance model to be more distributed.
2. Providing clear definitions of Makers and Takers within the ecosystem.
3. Implementing a fair and objective system for tracking and valuing various types of contributions.
4. Implementing a structured system of rewards for Makers who meet specific contribution thresholds, such as priority placement in the WordPress marketplace, increased visibility on WordPress.org, opportunities to exhibit at WordPress events, or access to key services.

This approach addresses both key challenges highlighted in the introduction: it balances contributions by incentivizing major involvement, and it creates an environment where open source businesses of all sizes can compete fairly based on their contributions to the community.

### Conclusion

Addressing the Maker-Taker challenge is essential for the long-term sustainability of open source projects. Drupal's approach may provide a constructive solution not just for WordPress, but for other communities facing similar issues.

By transparently rewarding contributions and fostering collaboration, we can build healthier open source ecosystems. A credit system can help make open source more sustainable and fair, driving growth, competitiveness, and potentially creating thousands of new open source businesses.

As Drupal continues to improve its credit system, we understand that no solution is perfect. We're eager to learn from the successes and challenges of other open source projects and are open to ideas and collaboration.
