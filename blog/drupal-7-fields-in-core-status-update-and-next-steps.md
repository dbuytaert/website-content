---
url: 'https://dri.es/drupal-7-fields-in-core-status-update-and-next-steps'
title: 'Drupal 7 fields in core: status update and next steps'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2009-06-17T08:07:55-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
published: true
id: 676
---

# Drupal 7 fields in core: status update and next steps

With less than 10 weeks to go before the Drupal 7 code freeze, an update on the current state of "Fields in core" is in order. After all, the fields system will be one of the most significant new features in Drupal 7, and [something we've been dreaming about since 2004](https://dri.es/custom-content-types). If you're familiar with Drupal's *Content Construction Kit* (CCK), you can think of "Fields in core" as "CCK in core, except better". If you're not familiar with CCK, "Fields in core" allows you to define custom content types like reviews, blog posts, press releases, articles, events, products, ... whatever you can think of.

### Current state

In my [DrupalCon Boston keynote presentation](https://dri.es/state-of-drupal-presentation-march-2008) two years ago, I laid down the challenge to put *fields in core and make them first class citizens*. We had talked and brainstormed about it a lot by then, and many people felt like it was the logical next step for Drupal. We began implementation at the "Fields in core" code sprint in December 2008. Thanks to the hard work of [Yves Chedemois](https://www.drupal.org/user/39567), [Karen Stevenson](https://www.drupal.org/user/45874), [Barry Jaspan](https://www.drupal.org/user/46413), [Moshe Weitzman](https://www.drupal.org/user/23), [David Strauss](https://www.drupal.org/user/93254), [Florian Loretan](https://www.drupal.org/user/66163), [David Rothstein](https://www.drupal.org/user/124982) and [Károly Négyesi](https://www.drupal.org/user/9446), an initial version of the [Field API was committed to the Drupal 7 development branch](https://www.drupal.org/node/361042). This version of the Field API was a significantly refactored CCK, made more generic and with an improved API. Probably the biggest win of that refactoring effort is that as of Drupal 7, it will be possible to attach fields to nodes, users and taxonomy terms, and by extension, to any other entity type that wants them.

Since that initial version was committed in February 2009, a lot of effort has gone into streamlining the Field API. [Yves Chedemois](https://www.drupal.org/user/39567) and [Barry Jaspan](https://www.drupal.org/user/46413) took the lead in converting node bodies and node teasers to regular fields instead of treating them as special cases (oh my!), [Nat Catchpole](https://www.drupal.org/user/35733) focused on improving performance of the Field API, and various people in the community have helped with a steady stream of incremental improvements, including improving the field validation and error reporting to decouple it from the Form API.

### Future work

Despite some of the early awesomeness of the Field API, a lot of work is left to be done. While there is more to streamline, it feels like the Field API has arrived at that "good state" where it feels right to start building on top of it. It is that feeling that triggered me to write this post, and to invite people to participate. And with less than three months away before code freeze, it is time to get more people involved as we build on top of the foundations that are now in place. The most important items that we still need to work on include:

#### Field UI

The only thing we have in core at the time of this writing is the Field API. The Field API is exactly that: a programming interface. I'd love to see a Field UI in core to enable end users to add fields to content types, extend user profiles, and more. Unfortunately, it is not just a straight port of the CCK UI as the Field API has a number of important new features. The CCK UI in Drupal 6 is pretty dull, so hopefully some good UI suggestions will emerge as part of the [D7UX effort](http://d7ux.org), or maybe by leveraging the [form builder module](https://www.lullabot.com/blog/drupals-form-building-future)? Having a good UI in core is a strategic necessity because it enables more people to test, benchmark and experiment with what we have built so far – it lowers the barriers for more developers to get involved and could speed up our progress significantly.

#### User profiles

I'd love to see us rewrite the profile module to take advantage of the Field API. We demonstrated that it is possible to attach fields to users but that doesn't necessarily give you the functionality that comes with profile module; we need to be able to attach fields to the registration form, support a number of different views, and provide an upgrade path from the old profile module to a new, Field API aware profile module. Our goal, of course, is to leverage the new Field API so we can bring the power of dozens of CCK field types to user profiles.

#### Performance

We need more effort in optimizing performance. The Field API introduces additional abstractions and generalizations and, as is often the case, increased power and flexibility has a performance cost. As bigger and bigger sites adopt Drupal, performance is not something we can compromise on. We should investigate caching strategies, and explore how field data is stored in the local SQL database. One promising approach suggested by [David Strauss](https://www.drupal.org/user/93254) is to implement [materialized views](https://en.wikipedia.org/wiki/Materialized_view) at the application level instead of relying on database support; this approach has the additional advantage of potentially speeding up Drupal sub-systems other than the Field API. Another interesting solution may be the [per-bundle storage model](https://www.drupal.org/project/pbs) prototyped by [Barry Jaspan](https://www.drupal.org/user/46413); instead of the current per-field-only storage approach, this solution stores data per-bundle to reduce the number of table joins.

#### More field types in core

I'd like to see us add a few more field types to core; especially ones that enable basic file and image handling. And date fields, of course. Users expect this kind of functionality out of the box.

#### Other improvements

Other than the things mentioned above, there are lots of other things that could leverage the Field API: taxonomy terms as fields so we can categorize users, terms and vocabularies as field-able entities, translatable fields, [extending RDFa support to the Field API](https://www.drupal.org/project/issues/search/drupal?issue_tags=RDF) and more. All of these are great, but in the overall scheme of things, probably less important than the other items. Let's try to prioritize and focus our efforts.

### Summary

A lot of good progress has been made already, but a lot of work is left to do and we must accelerate our efforts. Now that we have the foundation in place, we can actually start to accomplish some of this work in parallel. We need more people to step up and address some of these big to-do list items. If you want to become a recognized Drupal expert, adding your mark on the Field API would certainly buy you street cred. If you want to help, a good starting point would be the [Field API documentation](https://api.drupal.org/api/group/field/7) and the [Fields in core issues](https://www.drupal.org/project/issues/search/drupal?version%5B0%5D=7.x&issue_tags=Fields%20in%20Core).

*See you in the issue queue?*
