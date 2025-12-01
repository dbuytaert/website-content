---
title: 'Mollom as a reputation service'
date: '2008-05-23T04:00:20-04:00'
author: Dries
tags:
  - Drupal
  - Mollom
published: true
type: blog
url: /mollom-as-a-reputation-service
id: 449
---

A while ago I wrote about [spam, OpenID and Mollom](https://dri.es/spam-openid-and-mollom). I mentioned that at [Mollom](https://mollom.com) we are maintaining an internal reputation for OpenID identifier that we encounter while assessing submitted content. In addition to that, we could also asses the reputation of the OpenID identify provider (IdP), which is useful in its own right.

It is still early days, but I believe that any identify system (i.e. OpenID) needs a reputation component (i.e. Mollom). I also believe that any reputation system needs to be able to establish an identity first.

Mollom's reputation system tries to predict future behavior by looking at past behavior. To do this, Mollom keeps track of past behavior, and updates the behavior as it receives more data about the user. At the same time, Mollom forgets. In other words, one must consistently behave well to maintain a good reputation.

At Mollom, we plan to open up our reputation system through an API (i.e. `mollom.getReputationIdentity('http://john.myopenid.com'))` or `mollom.getReputationProvider('http://myopenid.com')`), but before we do, I'd like to solicit some feedback and invite people to participate.

Nothing drives API design better than concrete use cases and experiments in the field. How would you like to consume reputation information? What format should we use so reputation information from different sources can be combined? How can your application help us build and maintain reputation profiles? What Drupal modules can take advantage of this? What Drupal modules can help build reputation? How do we prevent abuse?

I don't expect that we can answer these questions overnight, but if you want to collaborate or prototype a few ideas, let us know. *Should be fun!*
