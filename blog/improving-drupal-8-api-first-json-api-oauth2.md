---
url: 'https://dri.es/improving-drupal-8-api-first-json-api-oauth2'
title: "Improving Drupal 8's API-first: JSON API and OAuth2?"
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2016-12-09T10:10:51-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: "Recommended next steps for Drupal 8's API-first initiative; including JSON API and OAuth2 in Drupal 8 core."
tags:
  - Drupal
  - JavaScript
  - 'Web services'
image: drupal/api-first-building-blocks
published: true
id: 3831
---

# Improving Drupal 8's API-first: JSON API and OAuth2?

Among the most important initiatives for Drupal 8's future is the "API-first initiative", whose goal is to improve Drupal's web services capabilities for building decoupled applications. In my previous blog posts, I [evaluated the current state](https://dri.es/an-overview-of-web-service-solutions-in-drupal-8) of, [outlined a vision](https://dri.es/advancing-drupal-web-services) for, and [mapped a path forward](https://dri.es/a-roadmap-for-making-drupal-more-api-first) for Drupal's web services solutions.

In the five months since [my last update](https://dri.es/a-roadmap-for-making-drupal-more-api-first), web services in Drupal have moved forward substantially in functionality and ease of use. This blog post discusses the biggest improvements.

[image drupal/api-first-building-blocks resize=false]

### Core REST improvements

With the release of Drupal 8.2, the core REST API now supports important requirements for decoupled applications. First, you can now [retrieve configuration entities](https://www.drupal.org/node/2746015) (such as blocks and menus) as REST resources. You can also conduct [user registration](https://www.drupal.org/node/2752071) through the REST API. The developer experience of core REST has improved as well, with [simplified REST configuration](https://www.drupal.org/node/2747231) and better response messages and status codes for requests causing errors.

Moreover, you can now access Drupal content from decoupled applications and sites hosted on other domains thanks to [opt-in cross-origin resource sharing](https://www.drupal.org/node/2715637) (CORS) support. This is particularly useful if you have a JavaScript application hosted directly on AWS, for instance, while your Drupal repository is hosted on a separate platform. Thanks to all this progress, you can now build more feature-rich decoupled applications with Drupal.

All of these improvements are thanks to the hard work of [Wim Leers](https://www.drupal.org/u/wim-leers) (Acquia), [Ted Bowman](https://www.drupal.org/u/tedbow) (Acquia), [Daniel Wehner](https://www.drupal.org/u/dawehner) (Chapter Three), [Clemens Tolboom](https://www.drupal.org/u/clemenstolboom), [José Manuel Rodríguez Vélez](https://www.drupal.org/u/marthinal), [Klaus Purer](https://www.drupal.org/u/klausi), [James Gilliland](https://www.drupal.org/u/neclimdul) (APQC), and [Gabe Sullice](https://www.drupal.org/u/gabesullice) (Aten Design Group).

### JSON API as an emerging standard

[JSON API](http://jsonapi.org/) is a specification for REST APIs in JSON which offers several compelling advantages over the current core REST API. First, JSON API provides a standard way to query not only single entities but also all relationships tied to that entity and to perform query operations through query string parameters (for example, listing all tags associated with an article). Second, JSON API allows you to fetch lists of content entities (including filtering, sorting and paging), whereas the only options for this currently available in core are to issue multiple requests, which is undesirable for performance, or to query Drupal views, which require additional work to create.

Moreover, JSON API is increasingly common in the JavaScript community due to its adoption by developers creating REST APIs in JSON and by members of both the Ruby on Rails and Ember communities. In short, the momentum outside of Drupal currently favors JSON API over HAL. It's my belief that JSON API should become an experimental core module, and it may one day potentially even supersede HAL, Views-based REST endpoints, and more. Though Views REST exports will always be valuable for special needs, JSON API is suitable for more common tasks due to query operations needing no additional configuration. All this being said, we should discuss and evaluate the implications of prioritizing JSON API.

Thanks to the efforts of [Mateu Aguiló Bosch](https://www.drupal.org/u/e0ipso) (Lullabot) and [Gabe Sullice](https://www.drupal.org/u/gabesullice) (Aten Design Group), the [JSON API module](https://www.drupal.org/project/jsonapi) in Drupal 8 is quickly approaching a level of stability that could put it under consideration as a core experimental module.

### OAuth2 bearer token authentication

One of the issues facing many decoupled applications today is the lack of a robust authentication mechanism when working with Drupal's REST API. Currently, core REST only has two options available out of the box, namely cookie-based authentication, which is unhelpful for decoupled applications on domains other than the Drupal site, and [basic authentication](https://www.drupal.org/documentation/modules/basic_auth), which is less secure than other mechanisms.

Due to its wide acceptance, OAuth2 seems a logical next step for Drupal sites that need to authenticate requests. Because it is more secure than what is available in core REST's basic authentication, OAuth2 would help developers build more secure decoupled Drupal architectures and allow us to deprecate the other less secure approaches.

It would make sense to see an OAuth2 solution such as [Simple OAuth](https://www.drupal.org/project/simple_oauth), the work of [Mateu Aguiló Bosch](https://www.drupal.org/u/e0ipso) (Lullabot), as an experimental core module, so that we can make REST APIs in Drupal more secure.

### Waterwheel, Drupal's SDK ecosystem

The API-first initiative's work goes beyond making improvements on the Drupal back end. Acquia released [Waterwheel.js](https://github.com/acquia/waterwheel.js) as open-source, the first iteration of a helper SDK for JavaScript developers. The Waterwheel.js SDK helps JavaScript developers perform requests against Drupal without requiring extensive knowledge of how Drupal's REST API functions. For example, the [Waterwheel module](https://www.drupal.org/project/waterwheel) allows you to benefit from resource discovery, which makes your JavaScript application aware of Drupal's data model. Waterwheel.js also integrates easily with the JSON API contributed module.

### Conclusion

Thanks to the hard work of the many contributors involved, the API-first initiative is progressing with great momentum. In this post, we ended with the following conclusions:

- The JSON API and Simple OAuth modules could be candidates for inclusion in Drupal 8 core – this is something we should discuss and evaluate.
- We should discuss where support for HAL and JSON API stops and starts, because it helps us focus our time and effort.

If you are building decoupled applications with Drupal 8, we would benefit significantly from your impressions of the core REST API and JSON API implementations now available. What features are missing? What queries are difficult or need work? How can we make the APIs more suited to your requirements? Use the comments section on this blog post to tell us more about the work you are doing so we can learn from your experiences.

Of course, if you can help accelerate the work of the API-first initiative by contributing code, reviewing and testing patches, or merely by participating in the discussions within the issues, you will not only be helping improve Drupal itself; you'll be helping improve the experience of all developers who wish to use Drupal as their ideal API-first back end.

*Special thanks to [Preston So](https://www.drupal.org/u/prestonso) for contributions to this blog post and to [Wim Leers](https://www.drupal.org/u/wim-leers), [Angie Byron](https://www.drupal.org/u/webchick), [Ted Bowman](https://www.drupal.org/u/tedbow) and [Chris Hamper](https://www.drupal.org/u/hampercm) for their feedback during the writing process.*
