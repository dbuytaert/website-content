---
url: 'https://dri.es/java-performance-evaluation-through-rigorous-replay-compilation'
title: 'Java performance evaluation through rigorous replay compilation'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2008-09-02T07:16:33-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - 'PhD research'
  - Java
published: true
id: 495
---

# Java performance evaluation through rigorous replay compilation

Our paper [Java Performance Evaluation through Rigorous Replay Compilation](https://dri.es/files/oopsla08-georges.pdf) (PDF, 1.9MB) has been accepted for publication at OOPSLA'08. This is joint work with [Andy Georges](http://itkovian.net) and [Lieven Eeckhout](https://www.elis.ugent.be/~leeckhou) that I worked on before [I got my PhD](https://dri.es/dr-dre) and [left the university to start Acquia](https://dri.es/acquia-my-drupal-startup).

Good news because [OOPSLA](http://oopsla.org), which is short for *ACM conference on object-oriented programming, systems, languages, and applications* has incubated many state-of-the-art technologies, including design patterns, refactoring, aspect-oriented software development, dynamic compilation and optimization, the Unified Modeling Language, and more.

### Paper abstract

A managed runtime environment, such as the Java virtual machine, is non-trivial to benchmark. Java performance is affected in various complex ways by the application and its input, as well as by the virtual machine (JIT optimizer, garbage collector, thread scheduler, etc.). In addition, non-determinism due to timer-based sampling for JIT optimization, thread scheduling, and various system effects further complicate the Java performance benchmarking process.

Replay compilation is a recently introduced Java performance analysis methodology that aims at controlling non-determinism to improve experimental repeatability. The key idea of replay compilation is to control the compilation load during experimentation by inducing a pre-recorded compilation plan at replay time. Replay compilation also enables teasing apart performance effects of the application versus the virtual machine.

This paper argues that in contrast to current practice which uses a single compilation plan at replay time, multiple compilation plans add statistical rigor to the replay compilation methodology. By doing so, replay compilation better accounts for the variability observed in compilation load across compilation plans. In addition, we propose matched-pair comparison for statistical data analysis. Matched-pair comparison considers the performance measurements per compilation plan before and after an innovation of interest as a pair, which enables limiting the number of compilation plans needed for accurate performance analysis compared to statistical analysis assuming unpaired measurements.
