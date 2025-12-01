---
title: 'A method for giving credit to organizations that contribute code to Open Source'
date: '2014-06-04T07:46:44-04:00'
author: Dries
tags:
  - Drupal
  - 'Open Source'
featured: true
published: true
type: blog
url: /a-method-for-giving-credit-to-organizations-that-contribute-code-to-open-source
id: 3156
---

If we want to encourage more organizations to contribute to Drupal and hire core developers, we should start to give them credit for their code contributions. I'd love to see us maintain a page on Drupal.org that shows which companies contribute to Drupal and in what capacity. This credit provides these organizations a tangible benefit in recruiting developers, demonstrating their expertise, and more. Credit is a powerful motivator for individuals, but also for businesses. It is a form of trust currency.

It is great that we give individual contributors credit for their code contributions, and we should continue to do so. However, I'd like to extend that to organizations, both to the Drupal agencies as well as their customers. Mapping out how code contributions get funded can be great for individuals, customers and digital agencies.

A great way to start doing this, is to adopt a new format for Git commit messages. I'd like to propose the following format:

`$ git commit -am "Issue #n by INDIVIDUAL@AGENCY*CUSTOMER: message."`

We prefix agencies with @ and customers with \*. I believe this provides us the necessary flexibility. We could choose to store this in [Git Notes](https://mirrors.edge.kernel.org/pub/software/scm/git/docs/git-notes.html), if we prefer, but that is not the main point.

Contributed a feature as an individual consultant directly for a customer or end-user:

`$ git commit -am "Issue #n by INDIVIDUAL*CUSTOMER: message."`

Contributed something in your spare time and don't want to give credit to your employer:

`$ git commit -am "Issue #n by INDIVIDUAL: message."`

Let's put it all together with a real example. Imagine Sam, Megan and Tim collaborated on fixing a performance bug. Sam helped in the "20% time" provided by her employer Acquia, Megan helped in her spare time after work, and Tim worked on this on behalf of his employer, Pfizer, who is affected by this bug. Ideally, the commit message would look like this:

`$ git commit -am "Issue #42 by Sam@Acquia, Megan, Tim*Pfizer: fixed performance bug."`

The great thing about this approach is that we can adopt it today and worry about analyzing the data later. It also works regardless of where your Drupal code is hosted (Drupal.org, GitHub, etc) or what your source code management system of choice is (Git, SVN, etc). In fact, I believe all Open Source projects would benefit from this level of transparency and that giving credit directly into the commit message makes it very transferable.

If adopted, we'll want to build tools to help us create these commit messages (i.e. have contributors provide proper attribution in a new project issue field so the maintainers/committers don't have to manually create it).

With this level of transparency, we can start to study how our ecosystem actually works; we can see which companies contribute back code and how much, we can see how much of the Drupal project is volunteer driven, we can better identify potential conflicts of interest, and more. But most of all, we can provide credit where credit is due and provide meaningful incentives for organizations to contribute back to Drupal. I believe this could provide a really important step in making Drupal core development more scalable.

I'd love to hear your thoughts about us giving organizations credit.

**Update**: this was rolled out on drupal.org in 2015. Instead of providing the credit in a Git commit message we built a user interface for it.
