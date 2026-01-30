---
url: 'https://dri.es/ai-is-a-business-model-stress-test'
title: 'AI is a business model stress test'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2026-01-09T21:17:02-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: "AI commoditizes anything you can specify. It can't (yet) commoditize what requires ongoing operation."
tags:
  - 'Open Source'
  - 'Business model'
  - Acquia
  - 'Artificial Intelligence'
image: blog/sailing-into-the-unknown
discussions:
  - { platform: '', url: 'https://news.ycombinator.com/item?id=46567392' }
  - { platform: '', url: 'https://www.linkedin.com/posts/buytaert_ai-is-a-business-model-stress-test-activity-7415581530682826752-3kIu' }
published: true
featured: false
id: 6041
---

# AI is a business model stress test

[image blog/sailing-into-the-unknown priority=true schema=false]

[Tailwind Labs](https://tailwindcss.com/) laid off 75% of its engineering team last week.

Adam Wathan, CEO of Tailwind Labs, spent the holidays running revenue forecasts. In a [GitHub comment](https://github.com/tailwindlabs/tailwindcss.com/pull/2388#issuecomment-3717222957), he explained what happened:

> The reality is that 75% of the people on our engineering team lost their jobs here yesterday because of the brutal impact AI has had on our business. Traffic to our docs is down about 40% from early 2023 despite Tailwind being more popular than ever.

The story circulating is that AI is killing Open Source businesses. I don't think that is quite right.

AI didn't kill Tailwind's business. It stress tested it. Their business model failed the test, but that is not an indictment of all Open Source business models.

Tailwind's business model worked for years. It relied on developers visiting their documentation, discovering Tailwind Plus while browsing, and buying it. Tailwind Plus is a $299 collection of pre-built UI components. Traffic led to discovery, and discovery drove sales. It was a reasonable business model, but always fragile.

In the last year, more and more developers started asking AI for code instead of reading documentation, and their sales and marketing funnel broke.

There is a fairness issue here that I don't want to skip past. AI companies trained their models on Tailwind's documentation and everything the community wrote about it. And now those models generate Tailwind code and answer Tailwind questions without sending anyone to Tailwind's website. The value got extracted, but [compensation isn't flowing back](https://dri.es/the-webs-broken-deal-with-ai-companies). That bothers me, and it deserves a broader policy conversation.

What I keep coming back to is this: AI commoditizes anything you can fully _specify_. Documentation, pre-built card components, a CSS library, Open Source plugins. Tailwind's commercial offering was built on "specifications". AI made those things trivial to generate. AI can ship a specification but it can't run a business.

So where does value live now? In what requires showing up, not just specifying. Not what you can specify once, but what requires showing up again and again.

Value is shifting to operations: deployment, testing, rollbacks, observability. You can't prompt 99.95% uptime on Black Friday. Neither can you prompt your way to keeping a site secure, updated, and running.

That is why [Vercel](https://vercel.com/) created [Next.js](https://nextjs.org/) and gives it away for free. The Open Source framework is the conduit; the hosting is the product. Same with [Acquia](https://www.acquia.com/), my own company. A big part of Acquia's business model is selling products around [Drupal](https://www.drupal.org/): hosting, search, CI/CD pipelines, digital asset management, and more. We don't sell describable things; we sell operations.

Open Source was never the commercial product. It's the conduit to something else. 

When asked what to pivot to, Wathan was candid: "Still to this day, I don't know what we should be pivoting to". I've written about [how digital agencies might evolve](https://dri.es/ai-and-the-great-digital-agency-unbundling), but CSS frameworks and component libraries are a harder case. Some Open Source projects make for great features, but not great businesses.

Tailwind CSS powers millions of sites. The framework will survive. Whether the company does is a different question. I'm rooting for them. The world needs more successful Open Source businesses.

PS: Follow the discussion on [](https://news.ycombinator.com/item?id=46567392) or [](https://www.linkedin.com/posts/buytaert_ai-is-a-business-model-stress-test-activity-7415581530682826752-3kIu).
