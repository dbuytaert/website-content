---
title: 'The transformation of Drupal 8 for continuous innovation'
date: '2016-09-28T04:46:09-04:00'
author: Dries
tags:
  - Drupal
featured: true
published: true
type: blog
url: /the-transformation-of-drupal-8-for-continuous-innovation
id: 3776
---

In the past, after every major release of Drupal, most innovation would shift to two areas: (1) contributed modules for the current release, and (2) core development work on the next major release of Drupal. This innovation model was the direct result of several long-standing policies, including [our culture of breaking backward compatibility](https://dri.es/backward-compatibility) between major releases.

In many ways, this approach served us really well. It put strong emphasis on big architectural changes, for a cleaner, more modern, and more flexible codebase. The downsides were lengthy release cycles, a costly upgrade path, and low incentive for core contributors (as it could take years for their contribution to be available in production). Drupal 8's development was a great example of this; the [architectural changes in Drupal 8](https://dri.es/why-the-big-architectural-changes-in-drupal-8) really propelled Drupal's codebase to be more modern and flexible, but also came at the cost of four and a half years of development and a complex upgrade path.

As Drupal grows – in lines of code, number of contributed modules, and market adoption – it becomes harder and harder to rely purely on backward compatibility breaks for innovation. As a result, we decided to evolve our philosophy starting after the release of Drupal 8.

The only way to stay competitive is to have the best product and to help people adopt it more seamlessly. This means that we have to continue to be able to reinvent ourselves, but that we need to make the resulting changes less scary and easier to absorb. We decided that we wanted more frequent releases of Drupal, with new features, API additions, and an easy upgrade path.

To achieve these goals, we adopted three new practices:

1. [Semantic versioning](https://semver.org/): a *major.minor.patch* versioning scheme that allows us to add significant, backwards-compatible improvements in minor releases like Drupal 8.1.0 and 8.2.0.
2. [Scheduled releases](https://www.drupal.org/core/release-cycle-overview): new minor releases are timed twice a year for predictability. To ensure quality, each of these minor releases gets its own beta releases and release candidates with strict guidelines on allowed changes.
3. [Experimental modules in core](https://www.drupal.org/core/experimental): optional alpha-stability modules shipped with the core package, which allow us to distribute new functionality, gather feedback, and iterate faster on the modules' planned path to stability.

Now that Drupal 8 has been released for about 10 months and Drupal 8.2 is scheduled to be released next week, we can look back at how this new process worked. Drupal 8.1 introduced two new experimental modules (the [BigPipe module](https://dri.es/bigpipe-no-longer-just-for-the-top-50-websites) and a user interface for data migration), various API additions, and usability improvements like spell checking in CKEditor. Drupal 8.2 further stabilizes the migration system and introduces numerous experimental alpha features, including [significant usability improvements](https://dri.es/drupal-8-2-now-with-more-outside-in) (i.e. [block placement](https://www.youtube.com/watch?v=Osbegr_d_GY) and [block configuration](https://www.youtube.com/watch?v=yqmAvOA8MS0)), date range support, and advanced content moderation – among a long list of other stable and experimental improvements.

It's clear that these regular feature updates help us innovate faster – we can now add new capabilities to Drupal that previously would have required a new major version. With experimental modules, we can get features in users' hands early, get feedback quickly, and validate that we are implementing the right things. And with the scheduled release cycle, we can deliver these improvements more frequently and more predictably. In aggregate, this enables us to innovate continuously; we can bring more value to our users in less time in a sustainable manner, and we can engage more developers to contribute to core.

It is exciting to see how Drupal 8 transformed our capabilities to continually innovate with core, and I'm looking forward to seeing what we accomplish next! It also raises questions about what this means for Drupal 9 – I'll cover that in a future blog post.
