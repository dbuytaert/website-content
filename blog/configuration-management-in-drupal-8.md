---
title: 'Configuration management in Drupal 8'
date: '2011-03-28T08:18:25-04:00'
author: Dries
tags:
  - Drupal
  - Configuration
published: true
type: blog
url: /configuration-management-in-drupal-8
id: 2281
---

In [my DrupalCon keynote in Chicago](https://dri.es/state-of-drupal-presentation-march-2011), I talked about the key initiatives that I believe we should focus on for Drupal 8 core. One of those key initiatives that I talked about was *configuration management*.

For some, *configuration management* is a bit of an abstract term. In short, it refers to a mechanism for handling configuration changes. Site owners often want to have fine-grained visibility and control over configuration changes with the purpose of maintaining integrity and traceability throughout the life-cycle of the website. For example, they might want to lock down a site's configuration so site builders can't make changes in a production environment, they might want tools to automatically apply a set of configuration changes made to site A to site B, they might want to rollback changes, or go back in time to see who made what configuration change when. It will also paves the path for better *staging*; some site owners want to be able to merge user generated content into their development environment, and new content back to the production.

To enable all of the above in a modern and elegant way, we need to make a number of changes to Drupal. These changes will be worked on as part of the *Configuration Management Initiative* for Drupal 8 core.

### Greg Dunlap (and David Strauss)

Also in my DrupalCon keynote in Chicago, I outlined changes to the Drupal development process. Each of the Drupal 8 initiatives will have an *Initiative Owner* that reports to me, and that acts as a project manager and/or technical lead.

I'm excited to announce Drupal 8's first initiative owner today. After some back and forth with various people and in-person meetings, I've decided that [Greg Dunlap](http://heyrocker.com) (aka [heyrocker on drupal.org](https://www.drupal.org/user/128537)) will be responsible for leading Drupal 8's Configuration Management initiative. Not only is Greg both passionate and knowledgeable about the about the topic of configuration management, his employer [NodeOne](http://nodeone.se) has generously offered that Greg can work on it half of his time.

I've also asked [David Strauss](https://www.drupal.org/user/93254) to be an 'architecture gatekeeper' for the Configuration Management Initiative. He needs to sign off on the architectural choices and the API design. Like Greg, David has been an evangelist for better configuration management in core. When both Greg and David are happy with the implementation, I'll consider including it in Drupal 8 core.

For more details, [read Greg's announcement blog post](http://nodeone.se/blogg/configuration-management-initiative), or better yet, [participate in the design discussions](https://groups.drupal.org/node/134569).
