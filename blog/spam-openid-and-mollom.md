---
title: 'Spam, OpenID and Mollom'
date: '2008-04-03T08:57:55-04:00'
author: Dries
tags:
  - Drupal
  - 'The future'
  - Mollom
published: true
type: blog
url: /spam-openid-and-mollom
id: 421
---

There is an [interesting discussion about spam and OpenID going on at ](https://ma.tt/2008/04/openid-and-spam/)[Matt Mullenweg's blog](http://ma.tt). The discussion was triggered by the policy decision of social bookmarking site [Magnolia](https://ma.gnolia.com/) to restrict signups to OpenID users. According to the site, [75% of new accounts were being created at Magnolia by spammers](https://jakandjil.it/blog/2008/01/31/a-dirty-shame/) using automated tools (our friends the 'spambots'). They say that by restricting access to OpenID users, the rate of spam-account creation decreased. In the discussion, there is a lot of talk about whether [OpenID](http://openid.net) should be used to fight spam, and whether it could be an effective spam-fighting tool in the long term.

Here are my thoughts. Spammers can create OpenIDs too, and a single sign-on system might be many a spammer's wet dream. It gives them easy access to millions of sites in one fell swoop.

Now, OpenID by itself can't prevent spam. All it does is provide a globally unique identifier for any given user on the planet. This is where a tool like [Mollom](https://mollom.com) comes in. At Mollom we're already maintaining an internal reputation for each OpenID account we encounter while assessing submitted content. Combine an identity system (OpenID) with a reputation system (Mollom) and it becomes a lot easier to separate spam users from non-spam users. [Simon Willison](http://simonwillison.net) said it best: ["a trust system requires identity first"](https://simonwillison.net/2007/Jan/10/account/). A globally unique identifier combined with reputation tools give us a powerful weapon to fight website spam. [OpenID's attribute exchange](https://openid.net/specs/openid-attribute-exchange-1_0-08.html) might become Mollom's best friend ...

Similarly, [Tim Berners-Lee](https://en.wikipedia.org/wiki/Tim_Berners-Lee) is experimenting with [combining FOAF ("friend of a friend") and OpenID to fight spam](http://dig.csail.mit.edu/breadcrumbs/node/206): you can only comment on Tim's blog if you are no more than a certain number of degrees of friendship away from him. Of course, it is a [widely accepted theory](https://en.wikipedia.org/wiki/Six_degrees_of_separation) that we are only six degrees away from everyone in the world so I do wonder how effective this would really be in the long run.

It is still early days in these debates and experiments, but for now, [Mollom](https://mollom.com) can already protect your login and submission forms with an image or audio CAPTCHA.

Either way, it is an interesting discussion that makes you wonder. Where will OpenID be in 3 years? Where do you think the website spam problem will be in 3 years? How will this affect online communities?

I have my own thoughts and predictions and it was one of the principal reasons for co-founding Mollom ...
