---
url: 'https://dri.es/how-acquia-is-addressing-the-explosion-of-sites'
title: 'How Acquia is addressing the explosion of sites'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2015-09-15T05:50:27-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
  - Acquia
  - 'Acquia Cloud'
published: true
id: 3426
---

# How Acquia is addressing the explosion of sites

I believe that the "digitalization" of the world is a "megatrend" that will continue for decades. On the one hand, organizations are shifting their businesses online, often inventing new ways to do business. On the other hand, customers are expecting a better and smarter user experience online.

This has led to two important sub-trends: (1) the number of sites an organization is creating and managing is growing at a rapid clip, (2) so is the underlying complexity of each website.

Forrester Research recently surveyed large enterprises about their website portfolio and found that on average they manage 268 properties across various channels. On top of that, each website is becoming more and more advanced. They evolved from simple HTML pages to dynamic websites to [digital experience platforms](https://dri.es/from-content-management-to-digital-experience-management) that need to integrate with many other business systems. The combination of these two trends – increasing number of sites and the growing complexity of each site – poses real challenges to most organizations.

At [Acquia](https://www.acquia.com), we are seeing this explosion of websites in the enterprise every day. Many organizations have different websites for different brands and products, want different websites for each country or region they operate in, or offer separate portals for their affiliates, dealers, agents or franchises. We're also seeing organizations, small and large, operate a large number of marketing campaign websites. These organizations aren't focused on scaling back their online properties but rather how best to manage them over time.

I outlined this trend and its challenges almost five years ago (see [Acquia product strategy and vision](https://dri.es/acquia-product-strategy-and-vision)) and most of it is still relevant today, if not more relevant. In this blog post, I want to give you an update and share some lessons learned.

### Current situation

Most larger organizations run many different types of websites. It's not unusual for a small organization to have ten websites and for a large organization to have hundreds of websites. Some of Acquia's largest customers operate thousands of websites.

[image blog/acquia-cloud-site-factory-many-sites]

Most organizations struggle to manage their growing portfolio of digital properties. You'd be surprised how many organizations have more than 20 different content management systems in use. Often this means that different teams are responsible for them and that they are hosted on different hosting environments. It is expensive, creates unnecessary security risks, poses governance challenges, leads to brand inconsistency, makes it difficult to create a unified customer experience, and more. It costs large organizations millions of dollars a year.

[image blog/acquia-cloud-site-factory-many-platforms]

### Drupal's unfair advantage

When managing many sites, Drupal has an unfair advantage in that it scales from simple to complex easily. That scalability, coupled with a vast ecosystem of modules, elevate Drupal from a single site point solution to a platform on which you can build almost any kind of site: a brand site, a corporate website, a customer support community, a commerce website, an intranet, etc. You name it.

This is in contrast to many of Drupal's competitors that are either point solutions (e.g. SharePoint is mainly used for intranets) or whose complexity and cost don't lend themselves to managing many sites (e.g. Adobe Experience Manager and Sitecore are expensive solutions for a quick marketing campaign site, while WordPress can be challenging for building complex websites). So the first thing people can do is to standardize on Drupal as a platform for all of their site needs.

[image blog/acquia-cloud-site-factory-many-drupals]

By standardizing on Drupal, organizations can simplify training, reduce maintenance costs, streamline security and optimize internal resources – all without sacrificing quality or requirements. Standardizing on Drupal certainly doesn't mean every single site needs to be on Drupal. Transitioning from 20 different systems to 3 still translates into dramatic cost savings.

### The Acquia advantage

Once an organization decides to standardize on Drupal, the question is how best to manage all these sites? In 2013 [we launched Acquia Cloud Site Factory (ACSF)](https://dri.es/announcing-acquia-cloud-site-factory), a scalable enterprise-grade multi-site management platform that helps organizations to easily create, deploy and govern all their sites. Today, some of Acquia's biggest customers use ACSF to manage hundreds of sites - in fact on average an ACSF customer is currently managing 170 websites within their Site Factory platform and that number is growing rapidly.

Acquia commissioned Forrester Research to [analyze the benefits to organizations](https://www.acquia.com/forrester-tei-acquia-cloud-site-factory) who have unified their sites on a single platform. Forrester found that moving to a single platform dramatically reduced site development and support costs, conserved IT and marketing resources, and improved standardization, governance and scalability – all while accelerating time-to-market and the delivery of better digital experiences.

One of the things we've learned is that a complete multi-site management solution needs to include advanced tools for both developers and content managers. The following image illustrates the different layers of a complete multi-site management solution:

[image blog/acquia-cloud-site-factory-solution-stack resize=false]

Let's go through these individually from the bottom up.

#### Infrastructure management

Consider an organization that currently has 50 websites, and plans to add 10-15 more sites every year. With ACSF these sites run on a platform that is scalable, secure and highly reliable. This infrastructure also allows hardware resources to be logically isolated based on the site's needs as well as scaled up or down to meet any ad-hoc traffic spikes. These capabilities enable organizations to simplify multi-site management efforts and eliminate operational headaches.

#### Code management

If this organization with 50 sites had individual codebases for each site, that would be 50 disparate codebases to manage. With ACSF, the underlying code can be shared and managed in one central place but the content, configuration, and creative look-and-feel can be catered to each individual sites' needs. ACSF also enable developers to easily add or remove features from their codebases for individual sites. ACSF also comes with tools to automate the process of rolling out updates across all their sites.

#### Site management

Organizations with many sites also need efficient ways to manage and govern them effectively; from developer tools such as Git, Travis, or Behat that enable them to build, test and maintain sites, to tools for non-developers to quickly clone and spin up sites using site templates defined by a brand manager or a digital design team. ACSF enables customers to effortlessly manage all their sites from a single intuitive dashboard. Developers can create groups of users as well as sites allowing certain users to manage their dedicated domain of sites without stepping over other sites. Non-technical content managers can quickly spin up new sites by cloning existing ones they have access to and updating their configuration, content and look-and-feel. These features allow organizations to launch sites at unprecedented speed inherently improving their overall time to market.

#### Content sharing

Write once, publish anywhere. We learned from customers managing multiple sites that one thing they often need is the ability to easily share content between sites. For example, if an organization has a privacy policy that needs to be updated, it doesn't make sense to update all their 50 sites individually. There needs to be an easier way to discover existing content that can be repurposed across other sites as well as the ability to author new content once within a platform and deliver it to other sites as needed.

#### Personalization

Finally, I should mention personalization. For a few years now [we have been developing Acquia Lift](https://dri.es/announcing-acquia-lift). Acquia Lift builds unified customer profiles across all your websites, and uses that information to deliver real-time, contextual, and personalized experiences. For instance, if the organization in the above example had 50 websites for each of their 50 different products, Acquia Lift can present relevant content to its users as they browse across these different sites. This enables organizations to convert anonymous site visitors into known customers and establish a meaningful engagement between them.

### Conclusion

I believe that the "multi-sites era" will continue to accelerate; not only will we see more sites, but every site will become increasingly complex. Organizations need to think about how to efficiently manage their website portfolio. *If you're not thinking ahead, you're falling behind.*
