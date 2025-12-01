---
title: 'Suggestions for Drupal core'
date: '2007-03-16T05:24:40-04:00'
author: Dries
tags:
  - Drupal
published: true
type: blog
url: /suggestions-for-drupal-core
id: 232
---

From yesterday on until March 24, Google is accepting student applications for the [Google Summer of Code 2007](https://developers.google.com/open-source/gsoc/?csw=1). Google pays each successful student 4,500 USD for his work on Drupal during the summer, and we try to assign each student two top-class Drupal mentors to work with.

I'm particular interested in students that want to work on Drupal core, Drupal's main distribution, so I decided to share five ideas that I think are particularly core-worthy:

1. **Improved file handling.** Make it possible to mix database and file system storage on a per post basis, further abstract the storage model so we can support distributed storage solutions (like Amazon S3), apply node-level permissions to a node's files through a light-weight `file.php` layer. Do **not** implement files as nodes.
2. **Hierarchical page structuring.** Remove the "book page" node type, and turn the book module into a module that is specialized at creating *hierarchical content trees*. The module should automatically extract a menu from the node hierarchy, set the correct breadcrumbs, help you define a hierarchical URL structure with clean URLs, etc. This module will be the *de facto* standard to structure pages and to create hierarchical navigation schemes in Drupal.
3. **Lightweight image/asset management.** Make it easier to embed images in posts: write a lightweight asset manager to make it easy to re-use previously uploaded images, and provide a lightweight WYSIWYG solution to drag-and-drop (position) images into posts. More advanced WYSIWYG editors should be able to overwrite the one in core, and more advanced document management solutions should be able to overwrite or extend the basic asset management solution in core.
4. **Streamlined installation procedure.** Remove the Drupal welcome page, and replace it by additional installation steps in the installer. The additional installation steps should query the user for basic site settings (i.e. site name, site slogan), and should provide a dedicated and simpler user interface to create the administrative user account. I'd also like to ship core with an optional install profile optimized at jump starting your installation – for example, one that sets up a working contact form and creates a dummy about page with a clean and human-readable URL.
5. **Improved data models.** If you look around, it's quite obvious that websites are becoming a selection of independent components: OpenID, Amazon S3, etc. If we have well-defined data models in Drupal core, integration with web services (like those build with Adobe's Flex) will become easier. As a first step, we need a *data API* that we leverage internally, so we can get better at distributed search, import/export functionality, user profiles, custom content types, internationalization, and basic scaffolding. Start with Drupal's *form API* and massage it into the beginning of a *data API*. It's crucial for Drupal's future, but the work might not be for the faint hearted.

Keep in mind that each of these ideas need to be fleshed out more before they can be considered to be a solid Google Summer of Code proposal. Also note that this is not an exhaustive list of ideas, so feel free to submit additional ideas for consideration.
