---
title: 'Garbage collection hints'
date: '2006-08-03T05:35:38-04:00'
author: Dries
tags:
  - 'PhD research'
published: true
type: blog
url: /garbage-collection-hints
id: 119
---

Our paper [GCH: Hints for Triggering Garbage Collections](/files/hipeac06-paper.pdf) (PDF, 905KB) has been published in [Transactions on High-Performance Embedded Architectures and Compilers](https://www.springer.com/west/home/computer/lncs?SGWID=4-164-6-168361-0).

### Paper abstract

This paper shows that Appel-style garbage collectors often make suboptimal decisions both in terms of *when* and *how* to collect. We argue that garbage collection should be done when the amount of live bytes is low (in order to minimize the collection cost) and when the amount of dead objects is high (in order to maximize the available heap size after collection). In addition, we observe that Appel-style collectors sometimes trigger a nursery collection in cases where a full-heap collection would have been better.

Based on these observations, we propose *garbage collection hints (GCH)* which is a profile-directed method for guiding garbage collection. Off-line profiling is used to identify favorable collection points in the program code. In those favorable collection points, the garbage collector dynamically chooses between nursery and full-heap collections based on an analytical garbage collector cost-benefit model. By doing so, GCH guides the collector in terms of *when* and *how* to collect.

Experimental results using the SPECjvm98 benchmarks and two generational garbage collectors show that substantial reductions can be obtained in garbage collection time (up to 29X) and that the overall execution time can be reduced by more than 10%. In addition, we also show that GCH reduces the maximum pause times and outperforms user-inserted forced garbage collections.

### Background

The paper is an extended version of the [garbage collection hints paper](https://dri.es/files/hipeac05-paper.pdf) (PDF, 360KB) that we presented in [Barcelona last year](/album/barcelona-2005/).

Prof. Per Stenström, editor-in-chief, explains:

> In November 2005, the first in the series of International Conferences on High-Performance Embedded Architecture and Compilers was held in Barcelona. We were fortunate to attract close to a hundred submissions of which only 18 were selected for presentation. Among those, we asked the authors of the five most highly rated contributions to make extended versions of them. They all accepted to do that and their article appears in this issue.
