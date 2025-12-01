---
title: "Don't blame open-source software for poor security practices"
date: '2017-09-15T10:28:59-04:00'
author: Dries
summary: 'Running an old, insecure version of software — open-source or proprietary — can and will jeopardize the security of any site.'
tags:
  - Drupal
  - Acquia
published: true
type: blog
url: /dont-blame-open-source-software-for-poor-security-practices
id: 4021
---

Last week, Equifax, one of the largest American credit agencies, was hit by a cyberattack that may have compromised the personal data of nearly 143 million people, including name, address, social security numbers, birth dates and more. The forfeited information reveals everything required to steal someone's identity or to take out a loan in someone else's name. Considering that the current US population is 321 million, this cyberattack is now considered to be one of the [largest and most intrusive breaches in US history](https://www.bloomberg.com/news/articles/2017-09-07/equifax-says-cyber-intrusion-affected-143-million-customers).

### It's Equifax that is to blame, not open-source

As Equifax began to examine how the breach occurred, many unsubstantiated reports and theories surfaced in an attempt to pinpoint the vulnerability. One such theory targeted [Apache Struts](https://struts.apache.org) as the software responsible for the breach. Because Apache Struts is an open-source framework used for developing Java applications, this resulted in some unwarranted open-source shaming.

Yesterday, [Equifax confirmed](https://www.equifaxsecurity2017.com) that the security breach was due to an Apache Struts vulnerability. However, here is what is important; it wasn't because Apache Struts is open-source or because open-source is less secure. Equifax was hacked because the firm failed to patch a well-known Apache Struts flaw that was [disclosed months earlier in March](https://arstechnica.com/information-technology/2017/09/massive-equifax-breach-caused-by-failure-to-patch-two-month-old-bug/). Running an old, insecure version of software – open-source or proprietary – can and will jeopardize the security of any site. It's Equifax that is to blame, not open-source.

### The importance of keeping software up-to-date

The Equifax breach is a good reminder of why organizations need to remain vigilant about properly maintaining and updating their software, especially when security vulnerabilities have been disclosed. In an ideal world, software would update itself the moment a security patch is released. WordPress, for example, offers automatic updates in an effort to promote better security, and to streamline the update experience overall. It would be interesting to consider automatic security updates for [Drupal](https://www.drupal.org) (just for patch releases, not for minor or major releases).

In absence of automatic updates, I would encourage users to work with PaaS companies that keep not only your infrastructure secure, but also your Drupal application code. Too many organizations underestimate the effort and expertise it takes to do it themselves.

At [Acquia](https://www.acquia.com), we provide customers with automatic security patching of both the infrastructure and Drupal code. We monitor our customers' sites for intrusion attempts, DDoS attacks, and other suspicious activity. If you prefer to do the security patching yourself, we offer continuous integration or continuous delivery tools that enable you to get security patches into production in minutes rather than weeks or months. We take pride in assisting our customers to keep their sites current with the latest patches and upgrades; it's good for our customers and helps dispel the myth that open-source software is more susceptible to security breaches.
