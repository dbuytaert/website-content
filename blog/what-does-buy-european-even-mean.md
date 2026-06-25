---
url: 'https://dri.es/what-does-buy-european-even-mean'
title: "What does 'Buy European' even mean?"
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2026-04-15T08:13:15-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - 'Digital sovereignty'
  - 'Open Source'
  - Policy
discussions:
  - { platform: LinkedIn, url: 'https://www.linkedin.com/posts/buytaert_i-co-authored-a-new-post-with-nicholas-gates-share-7450156559273398272-my5p/' }
published: true
featured: false
id: 6166
---

# What does 'Buy European' even mean?

*This post was co-authored with [Nicholas Gates](https://www.linkedin.com/in/nckgts/), senior policy advisor at [OpenForum Europe](https://openforumeurope.org/). It was originally published on [EUobserver](https://euobserver.com/210047/when-it-comes-to-techs-software-dependency-what-does-buy-european-even-mean/), an independent online newspaper widely read by EU policymakers, journalists and advocacy groups. The article summarizes a series of posts I've been writing about [digital sovereignty](https://dri.es/tag/digital-sovereignty).*

European digital assets have a habit of not staying European – a problem current discussions about sovereignty are overlooking.

For example, Skype had Swedish and Danish founders, Estonian engineers, a Luxembourg headquarters, and proprietary code.

Every sovereignty credential was correct on the day it would have been assessed – and meaningless after eBay acquired it, Microsoft bought it, and eventually shut it down in 2025.

This speaks to a core tension at the heart of Europe's digital sovereignty moment. The real story has to do with licensing, dependencies, and supply chains more than it has to do with ownership or operational control – both of which can (and often do) change in Europe.

The current conception of cloud sovereignty asks the right questions about where data is stored, where companies are headquartered, and whether supply chains are European.

What they don't yet ask is whether the sovereignty they are assessing is durable and resilient – for example, whether it will survive a change of ownership, a corporate acquisition, or a disruption in the infrastructure the software depends on.

The European Commission's [Cloud Sovereignty Framework](https://commission.europa.eu/document/download/09579818-64a6-4dd5-9577-446ab6219113_en?filename=Cloud-Sovereignty-Framework.pdf) provides a non-legislative assessment tool designed to evaluate the digital independence of cloud services in Europe.

It enables public authorities to rank services based on factors such as immunity from non-EU laws, operational control, and data protection.

The forthcoming [Cloud and AI Development Act](https://www.eu-cloud-ai-act.com/) (CAIDA) – expected at the end of May – will possibly go further.

That said, while both are serious and welcome efforts, they are likely to solve only part of the problem.

## 'Buy European' is a fragile concept

[Europe's 'Buy European' strategy](https://euobserver.com/203466/leaked-details-of-what-will-be-in-brussels-new-made-in-europe-rules/) is being built on two fragile foundations it hasn't yet explicitly addressed, and this could have disastrous implications in the cloud domain in particular.

Proprietary software with a perfect sovereignty score today is one acquisition away from a different answer tomorrow. Open Source software means the question doesn't arise.

The legal right to fork changes the power dynamic entirely: it gives you leverage, lets a community step in, and means the technology cannot be held hostage.

This is the distinction the Cloud Sovereignty Framework currently misses.

When Oracle acquired Sun Microsystems in 2010, governments running MySQL faced an immediate question: what happens to this software now?

The answer turned on one thing – the licence. Because MySQL was GPL-licensed, the right to fork and maintain it independently was already being exercised before the acquisition even completed.

MySQL's creator, Monty Widenius, forked it in 2009 precisely because he saw the acquisition coming – that fork exists today as MariaDB. The licence didn't prevent Oracle from buying Sun. It meant the acquisition couldn't end the software, and anyone paying attention could act on that right before any harm materialised.

Getting the licence right is necessary, but it is not sufficient.

In 2024, a conflict between WordPress co-founder Matt Mullenweg and WP Engine disrupted updates for millions of websites.

The code was Open Source. The delivery infrastructure had a single point of control. Most programming languages rely on a single central registry and most are controlled by US companies.

In 2019, GitHub restricted access for developers in sanctioned countries; since GitHub also owns npm, the JavaScript ecosystem's delivery infrastructure became subject to the same trade controls. These aren't interchangeable download sites you can swap out.

Sovereign software on fragile infrastructure is not sovereign. It is software waiting for a supply chain to break.

Both fragility problems point to the same conclusion: a 'Buy European' label is not a sovereignty guarantee unless it embraces licensing as a tool and helps to safeguard the supply chains the software depends on.

Consider two scenarios. A government running proprietary software on a European cloud has jurisdiction, but no exit if the provider is acquired – replacing the software could take years.

A government running Open Source software on Amazon Web Services (AWS) in Europe can move the same software to a European provider whenever it wants. Neither is ideal, but they are not equal.

Europe's sovereignty frameworks need to internalise this asymmetry. Structural sovereignty – the kind that survives change – requires open foundations that flow from licensing through the critical supply chains on which that software depends.

## A call-to-action for the Cloud and AI Development Act

CAIDA should not make the same mistakes as the Cloud Sovereignty Framework. It would be a mistake to simply extend a 'Buy European' checklist. The legislation should instead define what makes sovereignty durable.

Two concrete steps would make an immediate difference.

First, it can make Open Source licensing a pass/fail gate for mission-critical procurement under the Cloud Sovereignty Framework – a condition of eligibility at the highest assurance levels, not a weighted factor in a composite score.

Second, it should require supply chain resilience assessments that distinguish between dependencies switchable in weeks and those that would take an entire language community years to replicate, with federated or mirrored European alternatives required where no fallback exists.

Yes, requiring Open Source for mission-critical systems narrows the field in the short term.

But the providers you lose are the ones whose sovereignty credentials don't survive change.

In the longer term, these requirements push European companies toward Open Source software – technology that no one can take away.

PS: Follow the discussion on [LinkedIn](https://www.linkedin.com/posts/buytaert_i-co-authored-a-new-post-with-nicholas-gates-share-7450156559273398272-my5p/).
