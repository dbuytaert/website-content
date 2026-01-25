---
url: 'https://dri.es/using-hpm-sampling-to-drive-dynamic-compilation'
title: 'Using HPM-Sampling to Drive Dynamic Compilation'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2007-08-01T06:22:46-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - 'PhD research'
published: true
id: 309
---

# Using HPM-Sampling to Drive Dynamic Compilation

Our paper [Using HPM-Sampling to Drive Dynamic Compilation](https://dri.es/files/oopsla07-buytaert.pdf) (PDF, 0.6MB) has been accepted for publication at OOPSLA'07.

Good news because [OOPSLA](http://oopsla.org), which is short for *ACM conference on object-oriented programming, systems, languages, and applications* has incubated many state-of-the-art technologies, including design patterns, refactoring, aspect-oriented software development, dynamic compilation and optimization, the Unified Modeling Language, and more.

### Paper abstract

All high-performance production Java virtual machines employ an adaptive strategy for program execution. Methods are first executed unoptimized and then an online profiling mechanism is used to find a subset of methods that should be optimized during the same execution. This paper empirically evaluates the design space of several profilers for initiating dynamic compilation and shows that existing online profiling schemes suffer from several limitations. They provide an insufficient number of samples, are untimely, and have limited accuracy at determining the frequently executed methods. We describe and comprehensively evaluate HPM-sampling, a simple but effective profiling scheme for finding optimization candidates using hardware performance monitors (HPMs) that addresses the aforementioned limitations. We show that HPM-sampling is more accurate; has low overhead; and improves performance by 5.7% on average and up to 18.3% when compared to the default system in Jikes RVM, without changing the JIT compiler.
