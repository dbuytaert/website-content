---
title: 'A better runtime for component-based web applications'
date: '2014-08-27T15:53:44-04:00'
author: Dries
tags:
  - Drupal
  - WordPress
  - 'Software development'
featured: true
published: true
type: blog
url: /a-better-runtime-for-component-based-web-applications
id: 3211
---

I have an idea but currently don't have the time or resources to work on it. So I'm sharing the idea here, hoping we can at least discuss it, and maybe someone will even feel inspired to take it on.

The idea is based on two predictions. First, I'm convinced that the future of web sites or web applications is component-based platforms (e.g. Drupal modules, WordPress plugins, etc). Second, I believe that the best way to deploy and use web sites or web applications is through a SaaS hosting environment (e.g. [WordPress.com](https://wordpress.com), [DrupalGardens](http://drupalgardens.com), [SalesForce's Force.com platform](http://force.com), [DemandWare's SaaS platform](http://demandware.com), etc). Specifically, I believe that in the big picture [on-premise software](https://en.wikipedia.org/wiki/On-premises_software) is a "transitional state". It may take another 15 years, but on-premise software will become the exception rather than the standard. Combined, these two predictions present a future where we have component-based platforms running in SaaS environments.

To get the idea, imagine a [WordPress.com](https://wordpress.com), [SquareSpace](http://squarespace.com), [Wix](http://wix.com) or [DrupalGardens](http://drupalgardens.com) where you can install every module/plugin available, including your own custom modules/plugins, instead of being limited to those modules/plugins manually approved by their vendors. This is a big deal because one of the biggest challenges with running web sites or web applications is that almost every user wants to extend or customize the application beyond what is provided out of the box.

Web applications have to be (1) manageable, (2) extensible, (3) customizable and (4) robust. The problem is that we don't have a programming language or an execution runtime that is able to meet all four of these requirements in the context of building and running dynamic component-based applications.

Neither PHP, JavaScript, Ruby, Go or Java allow us to build truly robust applications as the runtimes don't provide proper resource isolation. Often all the components (i.e. Drupal modules, WordPress plugins) run in the same memory space. In the Java world you have [Enterprise Java Beans](https://en.wikipedia.org/wiki/Enterprise_JavaBeans) or [OSGi](https://en.wikipedia.org/wiki/OSGi) which add some level of isolation and management, but it still doesn't provide full component-level isolation or component-level fault containment. As a result, it is required that one component pretty much trusts the other components installed on the system. This means that usually one malfunctioning component can corrupt the other component's data or functional logic, or that one component can harm the performance of the entire platform. In other words, you have to review, certify and test components before installing them on your platform. As a result, most SaaS vendors won't let you install untrusted or custom components.

What we really need here is an execution runtime that allows you to install untrusted components and guarantee application robustness at the same time. Such technology would be a total game-changer as we could build unlimited customizable SaaS platforms that leverage the power of community innovation. You'd be able to install any Drupal module on [DrupalGardens](http://drupalgardens.com), any plugin on [WordPress.com](https://wordpress.com) or custom code on [Squarespace](http://squarespace.com) or [Wix](http://www.wix.com). It would fundamentally disrupt the entire industry and would help us achieve [the assembled web dream](https://dri.es/the-assembled-web).

I've been giving this some thought, and what I think we need is the ability to handle each HTTP request in a [micro-kernel-like environment](https://en.wikipedia.org/wiki/Micro_kernel) where each software component (i.e. Drupal module, WordPress plugin) runs in its own isolated process or environment and communicates with the other components through a form of [inter-process communication](https://en.wikipedia.org/wiki/Inter-process_communication) (i.e. think remote procedure calls or web service calls). It is a lot harder to implement than it sounds as the inter-process communication could add huge overhead (e.g. we might need fast or clever ways to safely share data between isolated components without having to copy or transfer a lot of data around). Alternatively, virtualization technology like [Docker](http://docker.com) might help us move in this direction as well. Their goal of a lightweight container is a step towards micro-services but it is likely to have more communication overhead. In both scenarios, Drupal would look a lot like a collection of micro web services (Drupal 10 anyone?).

Once we have such a runtime, we can implement and enforce governance and security policies for each component (e.g. limit its memory usage, limit its I/O, security permission, but also control access to the underlying platform like the database). We'd have real component-based isolation along with platform-level governance: (1) manageable, (2) extensible, (3) customizable and (4) robust.

Food for thought and discussion?
