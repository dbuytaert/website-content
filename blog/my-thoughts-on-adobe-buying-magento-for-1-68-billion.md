---
url: 'https://dri.es/my-thoughts-on-adobe-buying-magento-for-1-68-billion'
title: 'My thoughts on Adobe buying Magento for $1.68 billion'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2018-05-22T15:20:56-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'My thoughts on Adobe buying Magento for $1.68 billion'
tags:
  - Drupal
  - Acquia
  - Commerce
  - Acquisitions
image: blog/adobe-acquires-magento
published: true
id: 4361
---

# My thoughts on Adobe buying Magento for $1.68 billion

[image blog/adobe-acquires-magento]

Yesterday, [Adobe](https://www.adobe.com) announced that it agreed to buy [Magento](https://magento.com) for $1.68 billion. When I woke up this morning, 14 different people had texted me asking for my thoughts on the acquisition.

Adobe acquiring Magento isn't a surprise. One of our industry's worst-kept secrets is that Adobe first tried to buy Hybris, but lost the deal to SAP; subsequently Adobe tried to buy DemandWare and [lost out against Salesforce](https://dri.es/demandware-acquisition-heats-up-customer-experience-market). It's evident that Adobe has been hungry to acquire a commerce platform for quite some time.

### The product motivation behind the acquisition

Large platform companies like Salesforce, Oracle, SAP and Adobe are trying to own the digital customer experience market from top to bottom, which includes providing support for marketing, commerce, personalization, and data management, in addition to content and experience management and more.

Compared to the other platform companies, Adobe was missing commerce. With Magento under its belt, Adobe can better compete against Salesforce, Oracle and SAP.

While Salesforce, SAP and Oracle offer good commerce capability, they lack satisfactory content and experience management capabilities. I expect that Adobe closing the commerce gap will compel Salesforce, SAP and Oracle to act more aggressively on their own content and experience management gap.

While Magento has historically thrived in the SMB and mid-market, the company recently started to make inroads into the enterprise. Adobe will bring a lot of operational maturity; how to sell into the enterprise, how to provide enterprise grade support, etc. Magento stands to benefit from this expertise.

### The potential financial outcome behind the acquisition

According to Adobe press statements, Magento has achieved "approximately $150 million in annual revenue". We also know that in early 2017, Magento raised $250 million in funding from Hillhouse Capital. Let's assume that $180 million of that is still in the bank. If we do a simple back-of-the-envelope calculation, we can subtract this $180 million from the $1.68 billion, and determine that Magento was valued at roughly $1.5 billion, or a 10x revenue multiple on Magento's trailing twelve months of revenue. That is an incredible multiple for Magento, which is primarily a licensing business today.

Compare that with Shopify, which is trading at a $15 billion dollar valuation and has $760 million of twelve month trailing revenue. This valuation is good for a 20x multiple. Shopify deserves the higher multiple, because it's the better business; all of its business is delivered in the cloud and at 65% year-over-year revenue growth, it is growing much faster than Magento.

Regardless, one could argue that Adobe got a great deal, especially if it can accelerate Magento's transformation from a licensing business into a cloud business.

### Most organizations prefer best-of-breed

While both the product and financial motivations behind this acquisition are seemingly compelling, I'm not convinced organizations want an integrated approach.

Instead of being confined to proprietary vendors' prescriptive suites and roadmaps, global brands are looking for an open platform that allows organizations to easily integrate with their preferred technology. Organizations want to build content-rich shopping journeys that integrate their experience management solution of choice with their commerce platform of choice.

We see this first hand at [Acquia](https://www.acquia.com). These integrations can span various commerce platforms, including IBM WebSphere Commerce, Salesforce Commerce Cloud/Demandware, Oracle/ATG, SAP/hybris, Magento and even custom transaction platforms. Check out Quicken (Magento), Weber (Demandware), Motorola (Broadleaf Commerce), Tesla (custom to order a car, and Shopify to order accessories) as great examples of Drupal and Acquia working with various commerce platforms. And of course, we've quite a few projects with Drupal's native commerce solution, [Drupal Commerce](https://www.drupal.org/project/commerce).

Owning Magento gives Adobe a disadvantage, because commerce vendors will be less likely to integrate with Adobe Experience Manager moving forward.

### It's all about innovation through integration

Today, there is an incredible amount of innovation taking place in the marketing technology landscape ([full-size image](https://dri.es/files/images/blog/marketing-technology-landscape-2018.jpg)), and it is impossible for a single vendor to have the most competitive product suite across all of these categories. The only way to keep up with this unfettered innovation is through integrations.

[image blog/marketing-technology-landscape-2018]

Most customers want an open platform that allows for open innovation and unlimited integrations. It's why Drupal and Acquia are winning, why the work on [Drupal's web services](https://dri.es/tag/web-services) is so important, and why [Acquia](https://www.acquia.com) remains committed to a best-of-breed strategy for commerce. It's also why Acquia has [strong conviction around Acquia Journey as a marketing integration platform](https://dri.es/the-evolution-of-acquia-product-strategy). It's all about innovation through integration, making those integrations easy, and removing friction from adopting preferred technologies.

### If you acquire a commerce platform, acquire a headless one

If I were Adobe, I would have looked to acquire a headless commerce platform such as [Elastic Path](https://www.elasticpath.com), [Commerce Tools](https://commercetools.com), [Moltin](https://moltin.com), [Reaction Commerce](https://reactioncommerce.com) or even [Salsify](https://www.salsify.com/).

Today, there is a lot of functional overlap between Magento and Adobe Experience Manager – from content editing, content workflows, page building, user management, search engine optimization, theming, and much more. The competing functionality between the two solutions makes for a poor developer experience and for a poor merchant experience.

In a headless approach, the front end and the back end are decoupled, which means the experience or presentation layer is separated from the commerce business layer. There is a lot less overlap of functionality in this approach, and it provides a better experience for merchants and developers.

Alternatively, you could go for a deeply integrated approach like [Drupal Commerce](https://www.drupal.org/project/commerce). It has zero overlap between its commerce, content management and experience building capabilities.

### For Open Source, it could be good or bad

How Adobe will embrace Magento's Open Source community is possibly the most intriguing part of this acquisition – at least for me.

For a long time, Magento operated as Open Source in name, but wasn't very Open Source in practice. Over the last couple of years, the Magento team worked hard to rekindle its Open Source community. I know this because I attended and keynoted one of its conferences on this topic. I have also spent a fair amount of time with Magento's leadership team discussing this. Like other projects, Magento has been [taking inspiration from Drupal](https://dri.es/how-drupal-influences-other-open-source-projects).

For example, the introduction of Magento 2 allowed the company to move to GitHub for the first time, which gave the community a better way to collaborate on code and other important issues. The latest release of Magento cited [194 contributions from the community](https://devdocs.magento.com/guides/v2.2/release-notes/ReleaseNotes2.2.4EE.html). While that is great progress, it is [small compared to Drupal](https://dri.es/who-sponsors-drupal-development-2017).

My hope is that these Open Source efforts continue now that Magento is part of Adobe. If they do, that would be a tremendous win for Open Source.

On the other hand, if Adobe makes Magento cloud-only, radically changes their pricing model, limits integrations with Adobe competitors, or doesn't value the Open Source ethos, it could easily alienate the Magento community. In that case, Adobe bought Magento for its install base and the Magento brand, and not because [it believes in the Open Source model](https://dri.es/loosen-control-the-open-source-way).

This acquisition also signals a big win for PHP. Adobe now owns a $1.68 billion PHP product, and this helps validate PHP as an enterprise-grade technology.

Unfortunately, Adobe has a history of being "Open Source"-second and not "Open Source"-first. It acquired [Day Software](https://en.wikipedia.org/wiki/Day_Software) in July 2010. This technology was largely made using open source frameworks – Apache Sling, Apache Jackrabbit and more – and was positioned as an open, best-of-breed solution for developers and agile marketers. Most of that has been masked and buried over the years and Adobe's track record with developers has been mixed, at best.

Will the same happen to Magento? Time will tell.
