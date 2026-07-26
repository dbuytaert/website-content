---
url: 'https://dri.es/where-open-source-open-data-and-government-meet'
title: 'Where Open Source, Open Data and government meet'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2009-05-06T12:09:22-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: "The government's use of Drupal for recovery.gov opens a chance to advance Open Data through RDFa and Semantic Web tools in Drupal 7."
tags:
  - Drupal
  - 'Semantic web'
  - 'Open Source'
  - Government
published: true
featured: false
id: 645
---

# Where Open Source, Open Data and government meet

The Obama administration recently excited the world of Open Source software by choosing to [launch Recovery.gov on Drupal](https://dri.es/obama-using-drupal). Its choice of a free, Open Source platform over any proprietary system is as hopeful and promising as the purpose of the website it built: to bring transparency to the spending of $800 billion in economic stimulus funds. We should be happy both that the U.S. government is embracing Open Source software and that it is promoting Open Data.

I recently blogged about how [hundreds of thousands of Drupal sites contain vast amounts of structured data](https://dri.es/drupal-the-semantic-web-and-search), but that structure has been hidden deep in Drupal databases and never surfaced at the HTML level. To counter this, I'd like the upcoming version of Drupal to emit structured information through the addition of [RDFa metadata for both common and custom content types](https://dri.es/rdfa-and-drupal). This could help the Obama administration with its goals around Open Data.

Instead of needing to perform all of the data analysis themselves, governments should work on making data available in machine-readable formats. This would enable citizens and organizations to query and combine that data, answer interesting questions not asked before, and build new services that help other citizens. Just look at [Apps for Democracy](http://www.appsfordemocracy.org/).

According to George Thomas from Recovery.gov, the Obama administration wants to do exactly that. Thomas [presented some additional details](https://www.slideshare.net/george.thomas.name/recoverygov-1118057) on how the administration envisioned making all of that data available. Furthermore, it recently solicited proposals for which technologies to use.

Tim Berners-Lee, the inventor of the web, submitted [a proposal for Linked Open Data](http://www.thenationaldialogue.org/ideas/linked-open-data/). Various people, including me, wrote in to express our support for Tim Berners-Lee's proposal.

To achieve these goals and help governments transition into an era of open, linked data, Drupal has some growing to do. As mentioned earlier, we are [organizing code sprints](https://dri.es/rdf-in-drupal-core-code-sprint) that aim to make Drupal 7 a more powerful tool for managing RDF data.

Given that Recovery.gov already runs Drupal, and given that I would like to see more Semantic Web technologies in core, I couldn't be more excited. With the right encouragement and technological tools, government sites can expose vast amounts of data covering an enormous range of concepts and topics.

This data will be exposed in an open, reusable form that can be searched or leveraged by organizations and individuals as needed. We, the Drupal community, have a unique opportunity to help reshape how politics is done.

Step one is to make the data available – and that is exactly what we are trying to accomplish with Drupal 7 and beyond. Many of the technologies – such as RDF, RDFa, SIOC, FOAF, OAuth, and OpenID – are available. It's a simple matter of programming to start putting these together, and it takes projects like Drupal to help bootstrap them. *Time to get our hands dirty!*
