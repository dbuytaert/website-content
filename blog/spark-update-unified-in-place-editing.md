---
title: 'Spark update: unified in-place editing'
date: '2013-01-07T15:48:30-05:00'
author: Dries
tags:
  - Drupal
  - Acquia
  - Usability
  - 'Spark distribution'
published: true
type: blog
url: /spark-update-unified-in-place-editing
id: 2861
---

A major focus of usability efforts in Drupal core has been around making it easier to edit things on your site. In Drupal 7, we introduced the *Contextual links* and *Overlay modules* to make it simpler for content authors and site builders to jump directly to the parts of the administration that relate to the things they see directly on the page, such as blocks or menus. Drupal 8 has now upped the ante with the new [in-place editing feature](https://www.drupal.org/node/1824500), which allows for direct modification of content on your site, within the context of the page it is displayed on.

The next logical step is to take in-place editing to the next level by unifying contextual editing paradigms: combining the concept of "edit mode" with the ability to contextually edit more than just fields on content, in order to allow for contextual editing of everything on the page, in a mobile-first way.

Specifically, we need to address the following challenges:

- **Conflicting patterns confuse users**: There are contextual gears to edit content, local tabs to edit content, and "Edit mode" to edit content. These patterns need to be streamlined.
- **Tasks are not intuitive enough**: Seemingly simple tasks can often result in "pogo-sticking" around in the admin backend trying to locate where to change a given setting.
- **Unnecessary information slows users down**: Drupal forms tend to be long and full of advanced/confusing options, which can overwhelm users trying to complete simple tasks.
- **Interactions don't work with smaller devices**: With Drupal 8's Mobile Initiative, it is critical that these tools be as easy to use on the desktop as they are on a smartphone or tablet.

Here is a video showing what we'd like to propose for solving these problems in Drupal 8 core:

[video evBpwxWPzPk]

We've now performed several rounds of internal usability testing on this functionality, and it has tested really well so far, with a high emotional value: in general, people can't believe this is Drupal. :-) Check out the prototype yourself at <https://projects.invisionapp.com/share/U2A4IAGX>.

I'm very excited about these changes, and feel that if we can get this into Drupal 8 it could be game-changing. But what do you think? If you like it, we'd love help with implementation and reviews in the core issue at <https://www.drupal.org/node/1882482>.
