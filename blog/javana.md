---
url: 'https://dri.es/javana'
title: Javana
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2006-08-17T06:26:39-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - 'PhD research'
published: true
id: 125
---

# Javana

Our paper [Javana: a system for building customized Java program analysis tools](/files/oopsla06-paper.pdf) (PDF, 1.3MB) has been accepted for publication at OOPSLA'06 (17% acceptance rate).

Good news because [OOPSLA](http://oopsla.org/), which is short for *ACM conference on object-oriented programming, systems, languages, and applications* has incubated many state-of-the-art technologies, including design patterns, refactoring, aspect-oriented software development, dynamic compilation and optimization, the Unified Modeling Language, and more.

### Paper abstract

Understanding the behavior of applications running on high-level language virtual machines, as is the case in Java, is non-trivial because of the tight entanglement at the lowest execution level between the application and the virtual machine. This paper proposes Javana, a system for building Java program analysis tools. Javana provides an easy-to-use instrumentation infrastructure that allows for building customized profiling tools very quickly.

Javana runs a dynamic binary instrumentation tool underneath the virtual machine. The virtual machine communicates with the instrumentation layer through an event handling mechanism for building a vertical map that links low-level native instruction pointers and memory addresses to high-level language concepts such as objects, methods, threads, lines of code, etc. The dynamic binary instrumentation tool then intercepts all memory accesses and instructions executed and provides the Javana end user with high-level language information for all memory accesses and natively executed instructions.

We demonstrate the power of Javana through a number of applications: memory address tracing, vertical cache simulation and object lifetime computation. For each of these applications, the instrumentation specification requires only a small number of lines of code. Developing similarly powerful profiling tools within a virtual machine (as done in current practice) is both time-consuming and error-prone; in addition, the accuracy of the obtained profiling results might be questionable as we show in this paper.
