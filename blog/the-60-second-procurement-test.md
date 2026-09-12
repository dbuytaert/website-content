---
url: 'https://dri.es/the-60-second-procurement-test'
title: 'The 60-second procurement test'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2026-09-09T14:45:17-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'Anyone paying for Open Source work should be able to check whether a vendor contributes. Open Source projects should take responsibility for making that easy by publishing contribution records.'
tags:
  - 'Open Source'
  - 'Open Source sustainability'
  - Policy
  - Drupal
discussions:
  - { platform: LinkedIn, url: 'https://www.linkedin.com/feed/update/urn:li:activity:7503623136488144896/' }
published: true
featured: false
id: 6326
---

# The 60-second procurement test

I believe any Open Source project with a commercial or institutional funding ecosystem should publish an official contribution record: who contributes, how much and over what period, what kind of work they do, which parts of the project they work on, and, where disclosed, who paid for the work.

The test for a good record is simple. A buyer should be able to answer three questions in about a minute: does this vendor contribute at all, how much do they contribute compared to other vendors, and do they work on the parts of the project I care about?

A good record serves both sides. Buyers get answers they can check, and vendors who contribute get credit for work that often goes unseen.

Of course, contribution does not prove that a vendor can deliver. It is one procurement factor alongside delivery capability, expertise, and price. 

## Vendor claims are hard to verify and compare

Say you need a vendor for your Drupal site, your Kubernetes cluster, or whatever Open Source software you use, and two firms bid. Both say they're deeply involved in the project, and both might be telling the truth by their own definition of "involved".

Without a project record, verifying those claims often means reconstructing each vendor's contribution history yourself.

The code repository seems like the obvious place to start, but even counting commits by vendor is not simple. A project has to connect individual contributors to the organizations that employed or funded their work, and those relationships can change over time.

More importantly, Open Source contribution can include documentation, support, event organization, governance work, promotion, and more. Much of that work happens outside the code repository or isn't recorded in a form a buyer can easily interpret. The data may all be public, but public is not the same as usable. A contribution record exists to close that gap.

## Projects are best placed to decide which contributions matter

Drupal has tracked contribution credits since 2015, following [a method I proposed in 2014](https://dri.es/a-method-for-giving-credit-to-organizations-that-contribute-code-to-open-source) and now [governed by the Drupal Association](https://www.drupal.org/contribution-credit). Its system records more than code and gives credit not only to individual contributors, but also to the organizations and customers that fund their work.

Not every contribution counts the same. A contribution to Drupal Core or a strategic initiative earns more credit than one to a module that few sites use, and work on contributed projects counts for more when more sites depend on them.

Raw contribution data does not tell buyers which work matters most to the project. The project has the context to decide what advances its priorities and how different contributions should be weighted. Its record should publish those rules, link to the underlying contributions, and explain how mistakes are corrected. 

In Drupal, contribution credits feed into the [Drupal.org marketplace](https://www.drupal.org/drupal-services) where buyers can look up agencies and compare them. While we have a strong foundation, we still have work to do to make the record easier to find, understand, and compare.

## The record is the project's job, not the vendor's

A fair objection is that this puts the burden on the wrong party: if a vendor claims to contribute, the vendor should prove it, and the project shouldn't spend scarce time tracking contributions.

Suppose the two firms from earlier both send proof. Each proves its own numbers, in the measure it looks best on, and it is still not clear who has the better record. Buyers meet this problem everywhere, which is why procurement leans on third parties: auditors, certifiers, industry analysts, references.

For vendor contribution, the project is often the natural third party. The work happens inside it, so it has the data and is uniquely placed to express an opinion on the value and strategic impact of a vendor's contribution.

A contribution record is a way for a project to recognize its [Makers](https://dri.es/balancing-makers-and-takers-to-scale-and-sustain-open-source) and to say who it would like to see win bids. It also settles the question once, for every buyer, instead of every buyer auditing every bid.

A project should take on the burden when publishing the record is in its interest. Making contribution visible steers commercial work toward the vendors that sustain the project, and that work is what pays for the contribution. So the project gets more contribution, and public credit is how the project gives back to the vendors that contribute.

## Projects can start with a simple record

Not every project may want or need a system as elaborate as Drupal's. How much record a project needs depends on how services around it are bought and sold: a project with hundreds of firms competing for work needs more than one with a handful of known vendors, and a project with no commercial ecosystem may not need a record at all. 

For a small project, a text file in the official repository listing its recognized organizational contributors and what they worked on can be enough for a first version.

More complex ecosystems may need to categorize vendors, support searches by location, or weight different kinds of contribution. Whatever form it takes, the record has to be easy to find and quick to use.

So if you maintain an Open Source project with a commercial or institutional funding ecosystem, start publishing a contribution record and improve it over time. 

If you buy services built on Open Source, ask for the project's contribution record. Decide at the start how contribution should count in your purchasing decision, then check bidder claims against the record. 

Finally, if you fund Open Source, use the record to find contributors working on the parts of the project you want to support.

Where buyers and funders can consider contribution, I expect projects with clear records to see more commercial opportunities go to their maintainers than projects that rely on appeals alone.

*Special thanks to [Henry Poole](https://en.wikipedia.org/wiki/Henry_Poole_\(technologist\)) for his contributions to this blog post, and to [Sachiko Muto](https://www.linkedin.com/in/sachikomuto/), [Tiffany Farriss](https://www.drupal.org/u/farriss), [Tim Lehnen](https://www.drupal.org/u/hestenet), and [Amandine Le Pape](https://www.linkedin.com/in/amandinelepape/) for their review.*

PS: Follow the discussion on [LinkedIn](https://www.linkedin.com/feed/update/urn:li:activity:7503623136488144896/).
