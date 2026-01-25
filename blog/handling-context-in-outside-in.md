---
url: 'https://dri.es/handling-context-in-outside-in'
title: 'Handling context in "outside-in"'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2016-05-02T05:28:16-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
  - Usability
  - Outside-in
published: true
id: 3661
---

# Handling context in "outside-in"

In a recent post we talked about how introducing [outside-in experiences](https://dri.es/turning-drupal-outside-in) could improve the Drupal site-building experience by letting you immediately edit simple configuration without leaving the page. In a follow-up blog post, we provided [concrete examples](https://dri.es/examples-of-how-to-make-drupal-outside-in) of how we can apply outside-in to Drupal.

The feedback was overwhelmingly positive. However, there were also some really important questions raised. The most common concern was the idea that the mockups ignored "context".

When we showed [how to place a block "outside-in"](https://dri.es/examples-of-how-to-make-drupal-outside-in), we placed it on a single page. However, in Drupal a block can also be made visible for specific pages, types, roles, languages, or any number of other contexts. The flexibility this provides is one place where Drupal shines.

### Why context matters

For the sake of simplicity and focus we intentionally did not address how to handle context in outside-in in the last post. However, incorporating context into "outside-in" thinking is fundamentally important for at least two reasons:

1. **Managing context is essential to site building.** Site builders commonly want to place a block or menu item that will be visible on not just one but several pages or to not all but some users. A key principle of outside-in is previewing as you edit. The challenge is that you want to preview what site visitors will see, not what you see as a site builder or site administrator.
2. **Managing context is a big usability problem on its own.** Even without outside-in patterns, making context simple and usable is an unsolved problem. Modules like Context and Panels have added lots of useful functionality, but all of it happens away from the rendered page.

### The ingredients: user groups and page groups

To begin to incorporate context into outside-in, [Kevin Oleary](https://www.drupal.org/u/tkoleary), with input from [yoroy](https://www.drupal.org/u/yoroy), [Bojhan](https://www.drupal.org/u/bojhan), [Angie Byron](https://www.drupal.org/u/webchick), [Gábor Hojtsy](https://www.drupal.org/u/gabor-hojtsy) and others, has iterated on the block placement examples that we presented in the last post, to incorporate some ideas for how we can make context outside-in. We're excited to share our ideas and we'd love your feedback so we can keep iterating.

To solve the problem, we recommend introducing 3 new concepts:

1. **Page groups:** re-usable collections of URLs, wildcards, content types, etc.
2. **User groups:** reusable collections of roles, user languages, or other user attributes.
3. **Impersonation:** the ability to view the page as a user group.

#### Page groups

Most sites have some concept of a "section" or "type" of page that may or may not equate to a content type. A commerce store for example may have a "kids" section with several product types that share navigation or other blocks. *Page groups* adapts to this by creating reusable "bundles" of content consisting either of a certain type (e.g. all research reports), or of manually curated lists of pages (e.g. a group that includes /home, /contact us, and /about us), or a combination of the two (similar to [Context module](https://www.drupal.org/project/context) but context never provided an in-place UI).

#### User groups

*User groups* would combine multiple user contexts like role, language, location, etc. Example user groups could be "Authenticated users logged in from the United States", or "Anonymous users that signed up to our newsletter". The goal is to combine the massive number of potential contexts into understandable "bundles" that can be used for context and impersonation.

#### Impersonation

As mentioned earlier, a challenge is that you want to preview what site visitors will see, not what you see as a site builder or site administrator. Impersonation allows site builders to switch between different user groups. Switching between different user groups allow a page to be previewed as that type of user.

### Using page groups, user groups and impersonation

Let's take a look at how we use these 3 ingredients in an example. For the purpose of this blog post, we want to focus on two use cases:

1. I'm a site builder working on a life sciences journal with a paywall and I want to place a block called "Download report" next to all entities of type "Research summary" (content type), but only to users with the role "Subscriber" (user role).
2. I want to place a block called "Access reports" on the main page, the "About us" page, and the "Contact us" page (URL based), and all research summary pages, but only to users who are anonymous users.

Things can get more complex but these two use cases are a good starting point and realistic examples of what people do with Drupal.

#### Step #1: place a block for anonymous users

Let's assume the user is a content editor, and the user groups "Anonymous" and "Subscriber" as well as the page groups "Subscriber pages" and "Public pages" have already been created for her by a site builder. Her first task is to place the "Access reports" block and make it visible only for anonymous users.

[image blog/outside-in-block-placement-anonymous resize=false]

#### Step #2: place a block for subscribers

Our editor's next task is to place the "Download reports" block and make it visible only for subscribers. To do that she is going to want to view the page as a subscriber. Here it's important that this interactions happens smoothly, and with animation, so that changes that occur on the page are not missed.

[image blog/outside-in-block-placement-subscriber resize=false]

#### Step #3: see if you did it right

Once our editor has finished step one and two she will want to go back and make sure that step two did not undo or complicate what was done in step one, for example by making the "Download report" block visible for Anonymous users or vice versa. This is where impersonation comes in.

[image blog/outside-in-impersonate resize=false]

### Summary

The idea of combining a number of contexts into a single object is not new, both context and panels do this. What is new here is that when you bring this to the front-end with impersonation, you can make a change that has broad impact while seeing it exactly as your user will.
