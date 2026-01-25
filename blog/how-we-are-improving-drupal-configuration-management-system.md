---
url: 'https://dri.es/how-we-are-improving-drupal-configuration-management-system'
title: "How we are improving Drupal's configuration management system"
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2018-10-30T13:39:19-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: "Next steps for Drupal's configuration management system."
tags:
  - Drupal
  - Configuration
image: drupal/configuraton-management-initiative
published: true
id: 4586
---

# How we are improving Drupal's configuration management system

Configuration management is an important feature of any modern content management system. Those following modern development best-practices use a development workflow that involves some sort of development and staging environment that is separate from the production environment.

[image drupal/configuration-management-example-1]

Given such a development workflow, you need to push configuration changes from development to production (similar to how you need to push code or content between environments). Drupal's configuration management system helps you do that in a powerful yet elegant way.

Since [I announced the original Configuration Management Initiative](https://dri.es/configuration-management-in-drupal-8) over seven years ago, we've developed and shipped a strong configuration management API in Drupal 8. Drupal 8's configuration management system is a huge step forward from where we were in Drupal 7, and a much more robust solution than what is offered by many of our competitors.

All configuration in a Drupal 8 site – from one-off settings such as site name to content types and field definitions – can be seamlessly moved between environments, allowing for quick and easy deployment between development, staging and production environments.

However, now that we have a couple of years of building Drupal 8 sites behind us, various limitations have surfaced. While these limitations usually have solutions via contributed modules, it has become clear that we would benefit from extending Drupal core's built-in configuration management APIs. This way, we can establish best practices and standard approaches that work for all.

<div class="large">
  [image drupal/configuraton-management-initiative resize=false]
</div>

I first talked about this need in [my DrupalCon Nashville keynote](https://dri.es/state-of-drupal-presentation-april-2018), where I announced the Configuration Management 2.0 initiative. The goal of this initiative is to extend Drupal's built-in configuration management so we can support more common workflows out-of-the-box without the need of contributed modules.

What is an example workflow that is not currently supported out-of-the-box? Support for different configurations by environment. This is a valuable use case because some settings are undesirable to have enabled in all environments. For example, you most likely don't want to enable debugging tools in production.

[image drupal/configuration-management-example-3]

The contributed module [Config Filter](https://www.drupal.org/project/config_filter) extends Drupal core's built-in configuration management capabilities by providing an API to support different workflows which filter out or transform certain configuration changes as they are being pushed to production. [Config Split](https://www.drupal.org/project/config_split), another contributed module, builds on top of Config Filter to allow for differences in configuration between various environments.

The Config Split module's use case is just one example of how we can improve Drupal's out-of-the-box configuration management capabilities. The community created a [longer list of pain points and advanced use cases for the configuration management system](https://www.drupal.org/project/ideas/issues/2957423).

While the initiative team is working on executing on these long-term improvements, they are also focused on delivering incremental improvements with each new version of Drupal 8, and have distilled the most high-priority items into a [configuration management roadmap](https://www.drupal.org/project/cmi2/issues/3008882).

- In Drupal 8.6, we added support for [creating new sites from existing configuration](https://www.drupal.org/project/drupal/issues/2980670). This enables developers to launch a development site that matches a production site's configuration with just a few clicks.
- For Drupal 8.7, we're planning on shipping an experimental module for dealing with environment specific configuration, moving the capabilities of Config Filter and the basic capabilities of Config Split to Drupal core through the [addition of a Configuration Transformer API](https://www.drupal.org/project/drupal/issues/2991683).
- For Drupal 8.8, the focus is on supporting configuration updates across different sites. We want to allow both sites and distributions to package configuration (similar to the well-known [Features module](https://www.drupal.org/project/features)) so they can easily be deployed across other sites.

### How to get involved

There are many opportunities to contribute to this initiative and we'd love your help.

If you would like to get involved, check out the [Configuration Management 2.0 project](https://www.drupal.org/project/cmi2) and [various Drupal core issues tagged as "CMI 2.0 candidate"](https://www.drupal.org/project/issues/search?issue_tags=CMI%202.0%20candidate).

*Special thanks to [Fabian Bircher](https://www.drupal.org/u/bircher) (Nuvole), [Jeff Beeman](https://www.drupal.org/u/jrbeeman) (Acquia), [Angela Byron](https://www.drupal.org/u/webchick) (Acquia), [ASH](https://www.drupal.org/u/burnashburn) (Acquia), and [Alex Pott](https://www.drupal.org/u/alexpott) (Thunder) for contributions to this blog post.*
