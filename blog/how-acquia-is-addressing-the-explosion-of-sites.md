---
url: 'https://dri.es/how-acquia-is-addressing-the-explosion-of-sites'
title: 'How Acquia is addressing the explosion of sites'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2015-09-15T05:50:27-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'How Acquia Cloud Site Factory helps enterprises standardize on Drupal to manage hundreds of sites through shared infrastructure, code, content, and personalization.'
tags:
  - Drupal
  - Acquia
  - 'Acquia Cloud'
published: true
featured: true
id: 3426
---

# How Acquia is addressing the explosion of sites

I believe that the "digitalization" of the world is a "megatrend" that will continue for decades. On the one hand, organizations are shifting their businesses online, often inventing new ways to do business. On the other hand, customers are expecting better and smarter online experiences.

This has led to two important subtrends: (1) the number of sites an organization creates and manages is growing at a rapid clip, and (2) the underlying complexity of each website is growing as well.

Forrester Research recently surveyed large enterprises about their website portfolios and found that, on average, they manage 268 properties across various channels. On top of that, each website is becoming more advanced. Websites have evolved from simple HTML pages to dynamic websites to [digital experience platforms](https://dri.es/from-content-management-to-digital-experience-management) that need to integrate with many other business systems. The combination of these two trends, the increasing number of sites and the growing complexity of each one, poses real challenges for most organizations.

At [Acquia](https://www.acquia.com), we see this explosion of enterprise websites every day. Many organizations have different websites for different brands and products, want a separate website for each country or region in which they operate, or offer separate portals for their affiliates, dealers, agents, or franchises. We're also seeing organizations, both small and large, operate many marketing campaign websites. These organizations aren't focused on scaling back their online properties but rather on how best to manage them over time.

I outlined this trend and its challenges almost five years ago in [Acquia product strategy and vision](https://dri.es/acquia-product-strategy-and-vision), and most of it is still relevant today, if not more relevant. In this blog post, I want to provide an update and share some lessons learned.

## Current situation

Most larger organizations run many different types of websites. It's not unusual for a small organization to have ten websites and for a large organization to have hundreds. Some of Acquia's largest customers operate thousands of websites.

![](http://default/files/cache/blog/acquia-cloud-site-factory-many-sites-640w.jpg)

Most organizations struggle to manage their growing portfolios of digital properties. You'd be surprised how many organizations have more than 20 different content management systems in use. Often, this means that different teams are responsible for them and that they are hosted in different environments. This fragmentation is expensive, creates unnecessary security risks, poses governance challenges, leads to brand inconsistency, and makes it difficult to create a unified customer experience. It costs large organizations millions of dollars a year.

![Logos of various content management systems, including Drupal, WordPress, Joomla, and Adobe, arranged in a circular pattern.](http://default/files/cache/blog/acquia-cloud-site-factory-many-platforms-640w.jpg)

## Drupal's unfair advantage

When managing many sites, Drupal has an unfair advantage because it scales easily from simple to complex. That scalability, coupled with a vast ecosystem of modules, elevates Drupal from a single-site point solution to a platform on which you can build almost any kind of site, including a brand site, a corporate website, a customer support community, a commerce website, or an intranet. You name it.

This contrasts with many of Drupal's competitors, which are either point solutions, such as SharePoint for intranets, or do not lend themselves to managing many different types of sites because of their complexity or cost. Adobe Experience Manager and Sitecore, for example, are expensive solutions for a quick marketing campaign site, while WordPress can be challenging for building complex websites. The first thing organizations can do, therefore, is standardize on Drupal as a platform for all their site needs.

![](http://default/files/cache/blog/acquia-cloud-site-factory-many-drupals-640w.jpg)

By standardizing on Drupal, organizations can simplify training, reduce maintenance costs, streamline security, and optimize internal resources, all without sacrificing quality or requirements. Standardizing on Drupal certainly doesn't mean that every single site needs to use Drupal. Transitioning from 20 different systems to three still translates into dramatic cost savings.

## The Acquia advantage

Once an organization decides to standardize on Drupal, the question is how best to manage all these sites. In 2013, [we launched Acquia Cloud Site Factory (ACSF)](https://dri.es/announcing-acquia-cloud-site-factory), a scalable, enterprise-grade multisite management platform that helps organizations easily create, deploy, and govern all their sites. Today, some of Acquia's biggest customers use ACSF to manage hundreds of sites. In fact, the average ACSF customer currently manages 170 websites on Site Factory, and that number is growing rapidly.

Acquia commissioned Forrester Research to [analyze the benefits to organizations](https://www.acquia.com/forrester-tei-acquia-cloud-site-factory) that have unified their sites on a single platform. Forrester found that moving to a single platform dramatically reduced site development and support costs, conserved IT and marketing resources, and improved standardization, governance, and scalability, all while accelerating time to market and the delivery of better digital experiences.

One of the things we've learned is that a complete multisite management solution needs to include advanced tools for both developers and content managers. The following image illustrates the different layers of a complete multisite management solution:

![A diagram showing the five layers of the Acquia Cloud Site Factory solution stack, including personalization and site management.](http://default/files/images/blog/acquia-cloud-site-factory-solution-stack.jpg)
*The different layers of the Acquia Cloud Site Factory solution stack.*

Let's go through these individually from the bottom up.

### Infrastructure management

Consider an organization that currently has 50 websites and plans to add 10 to 15 more every year. With ACSF, these sites run on a platform that is scalable, secure, and highly reliable. The infrastructure allows hardware resources to be logically isolated based on each site's needs and scaled up or down to accommodate unexpected traffic spikes. These capabilities enable organizations to simplify multisite management and eliminate operational headaches.

### Code management

If this organization had an individual codebase for each of its 50 sites, it would have 50 disparate codebases to manage. With ACSF, the underlying code can be shared and managed in one central place, while the content, configuration, and look and feel can be tailored to each site's needs. ACSF also enables developers to easily add or remove features for individual sites and includes tools for automating the rollout of updates across all sites.

### Site management

Organizations with many sites need efficient ways to manage and govern them. They need developer tools such as Git, Travis, and Behat to build, test, and maintain sites, as well as tools that allow non-developers to quickly clone and launch sites using templates defined by a brand manager or digital design team. ACSF enables customers to manage all their sites from a single, intuitive dashboard.

Developers can create groups of users and sites, allowing certain users to manage their dedicated group of sites without affecting others. Nontechnical content managers can quickly launch new sites by cloning existing ones they have access to and updating their configuration, content, and look and feel. These features allow organizations to launch sites at unprecedented speed, improving their overall time to market.

### Content sharing

Write once, publish anywhere. We learned from customers managing multiple sites that they often need the ability to easily share content between sites. For example, if an organization has a privacy policy that needs to be updated, it doesn't make sense to update all 50 of its sites individually. There needs to be an easier way to discover existing content that can be repurposed across other sites and to author new content once within a platform and deliver it to other sites as needed.

### Personalization

Finally, I should mention personalization. For a few years now, [we have been developing Acquia Lift](https://dri.es/announcing-acquia-lift). Acquia Lift builds unified customer profiles across all your websites and uses that information to deliver real-time, contextual, and personalized experiences. For instance, if the organization in the example above had 50 websites, one for each of its products, Acquia Lift could present relevant content to users as they browse across those sites. This enables organizations to convert anonymous site visitors into known customers and build meaningful relationships with them.

## Conclusion

I believe that the "multisite era" will continue to accelerate. We will not only see more sites, but each site will also become increasingly complex. Organizations need to think about how to efficiently manage their website portfolios. *If you're not thinking ahead, you're falling behind.*
