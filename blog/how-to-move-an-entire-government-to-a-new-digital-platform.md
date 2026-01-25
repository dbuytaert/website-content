---
url: 'https://dri.es/how-to-move-an-entire-government-to-a-new-digital-platform'
title: 'How to move an entire government to a new digital platform'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2016-12-29T07:35:13-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'What the Canadian government can learn from the Australian government when it it comes to migrating to a new digital platform'
tags:
  - 'Open Source'
  - Policy
  - Drupal
  - Innovation
  - Australia
  - Canada
  - Government
published: true
id: 3846
---

# How to move an entire government to a new digital platform

In this era of Open Government, constituents expect to be offered great services online. This can require moving an entire government to a new digital platform in order to deliver [ambitious digital experiences](https://dri.es/drupal-is-for-ambitious-digital-experiences) that support the needs of citizens. It takes work, but many governments from the [United States](https://dri.es/whitehouse-gov-using-drupal) to [Australia](http://www.australia.gov.au) have demonstrated that with the right technology and strategy in place, governments can successfully adopt a new platform. Unfortunately this is not always the case.

### How not to do it: Canada.ca

In 2014, the Government of Canada began a project to move all of its web pages onto a single site, [Canada.ca](https://www.canada.ca). A $1.54 million contract for a content management system was awarded to a proprietary vendor in 2015. Fast forward to today, and the [project is a year behind schedule and 10x over budget](http://www.cbc.ca/news/politics/canadaca-federal-website-delays-1.3893254). The contract is now approaching $10 million. As only 0.05% of the migration to Canada.ca has been completed, [many consider the current project to be disservice to its citizens](https://www.linkedin.com/pulse/what-isnt-being-said-canadaca-mike-gifford).

I find the impending outcomes of this project to be disheartening as [current timelines](http://ottawacitizen.com/business/local-business/canada-ca-web-renewal-costs-soaring-with-more-expenses-coming) suggest that the migration will continue to be delayed, run over budget, and strain taxpayers. While I hope that Canada.ca will develop into a valuable resource for its citizens, I agree with Tom Cochran, Acquia's Chief Digital Strategist for Public Sector – who ran digital platforms at the White House and U.S. Department of State – that the [prospects for Canada.ca are dim](https://www.huffingtonpost.ca/tom-cochran/canada-government-website-failure_b_13790426.html) given the way the project was designed and is being implemented.

The root of Canada.ca's problem appears to be the decision to migrate 1,500 departments and 17 million pages into a single site. I'm guessing that the goal of having a single site is to offer citizens a central entry point to connect with their government. A single site strategy can be extremely effective, for example the [City of Boston's single site is home to over 200,000 web page spanning 120 city departments](https://dri.es/city-of-boston-launches-boston-gov-on-drupal), and offers a truly user-centric experience. With 17 million pages to migrate, Canada.ca is eighty-five times bigger than Boston.gov. A project of this magnitude should have considered using a multi-site approach where different agencies and departments have their own sites, but can use a common platform, toolset and shared infrastructure.

While difficulties with Canada.ca may have started with the ambitious attempt to move every department to a single domain, the complexities of this strategy are likely amplified through the implementation of a single-source proprietary solution. I find it unfortunate that Canada's procurement models did not favor Open Source. The Canadian government has a tenured history of utilizing Open Source, and there is a lot of existing Drupal talent in the country. In rejecting an open platform, the Canadian Government lost the opportunity to engage a skilled community of native, Open Source developers.

### How to do it: Australian Government

Transforming an entire nation's digital strategy is challenging, but other public sector leaders have proven it is possible. Take the Australian Government. In 2015, John Sheridan, Sharyn Clarkson and their team in the [Department of Finance](https://www.finance.gov.au) moved their department's site from a legacy environment to Drupal and the cloud. The Department of Finance's success has grown into the Drupal distribution [govCMS](https://www.govcms.gov.au), which is currently supporting over 52 government agencies across 6 jurisdictions in Australia. Much like Canada.ca, the goal of govCMS is to provide citizens with a more intuitive platform to engage with their government.

The guiding principle of govCMS is to govern but to not seek control. Each government department requires flexibility to service the needs of their particular audiences. While single-site solutions do work as umbrellas for some organizations, the City of Boston being a great example, most large (government) organizations that have a state-of-the-art approach follow a hub and spoke model where different sites share code, templates and infrastructure. While sharing is strongly encouraged it is not required. This allows each department to independently innovate and adopt the platform how they choose.

The Open Source nature of govCMS has encouraged both innovation and collaboration across many Australian departments. One of the most remarkable examples of this is that a federal agency and a state agency coordinated their development efforts to build a data visualization capability on [an open data CKAN repository](https://en.wikipedia.org/wiki/CKAN). The Department of Environment initiated the development of the [CKAN module](https://www.govcms.gov.au/news/open-source-collaboration-implement-data-visualisation-module-govcms) necessary to pull and analyze data from a variety of departments. The Victorian Department of Premier and Cabinet recognized that they too could utilize the module to propel their budget report and aided in the co-development of the [govCMS CKAN](https://www.drupal.org/project/govcms_ckan). This is an incredible example of how Open Source allows agencies to extend functionality across departments, regardless of vendor involvement. By setting up a model which removed the barriers to share, govCMS has provided Australia the freedom to truly innovate.

### Seeing is believing: shifting the prevailing mindset

A distributed model using multiple sites to leverage an Open Source platform where infrastructure, code and templates are shared allows for governance and innovation to co-exist. I've written about this model here in a post about [Loosening control the Open Source Way](https://dri.es/loosen-control-the-open-source-way). I believe that a multi-site approach based on Open Source is the *only* way to move an entire government to a new digital strategy and platform.

It can be incredibly hard for organizations to understand this. After all, this is not about product features, technical capabilities or commercial support, but about a completely different way of working and innovating. It's a hard sell because we have to change the lens through which organizations see the world; away from procuring proprietary software that provides perceived safety and control, to a world that allows frictionless innovation and sharing through the loosening of control without losing control. For us to successfully market and sell the innovation that comes out of Drupal, Open Source and cloud, we have to shift how people think and challenge the prevailing model.

In many ways, organizations have to see it to believe it. What is exciting about the Australian government is that it helps others see the potential of a decentralized service model predicated on Open Source software with a Drupal distribution at its heart. The Australian government has created an ecosystem of frictionless sharing that is cheaper, faster, and enables better results.

### What is next for Canada?

It's difficult for me to see a light at the end of the tunnel for Canadian citizens. While the Canadian government can stay the course -– and all indications so far are that they will – that path has a high price tag, long delays and slow innovation. An alternative would be for Ottawa to hit the pause button and reassess their strategy. They could look externally to how governments in Washington, Canberra, and countless others approached their mission to support the digital needs of its citizens. I know that there are countless Drupal experts working both within the government and at dozens of Drupal agencies throughout Canada that are eager to show their government a better way forward.
