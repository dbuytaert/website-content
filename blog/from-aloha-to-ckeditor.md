---
title: 'From Aloha to CKEditor'
date: '2013-01-02T15:25:45-05:00'
author: Dries
tags:
  - Drupal
  - 'Spark distribution'
published: true
type: blog
url: /from-aloha-to-ckeditor
id: 2856
---

In the summer, I announced that [we would adopt Aloha Editor as part of Drupal 8](https://dri.es/spark-update-wysiwyg-editing-for-drupal). The primary reason was that Aloha was the only WYSIWYG editor that supported in-place ("true" WYSIWYG) editing; something we need to accomplish [our vision for in-place editing](https://dri.es/spark-update-in-line-editing-in-drupal). The Aloha Editor developers have been excellent in their attention to Drupal's needs. However, due to the nature of their editor being based around the concept of "true" WYSIWYG, we've run into some issues (which the Aloha Editor folks are actively working on) surrounding the user experience and accessibility of Aloha Editor when using it on the back-end.

Since that announcement, [CKEditor has caught up](https://ckeditor.com/blog/CKEditor-4-Launched-Inline-Editing-New-Skin-and-More/), and now offers feature parity to Aloha Editor when it comes to our needs. Frederico Knabben, creator of CKEditor, has reached out to offer whatever support he can to make CKEditor and Drupal work together better. They already prototyped a convincing alternative to Aloha Editor's killer "Blocks" system (which is an excellent match for Drupal's need to manage content within text content in a structured manner). In addition to that, we found that CKEditor is more mature in terms of APIs, documentation, and ecosystem around the project. Hence, after [days of research](https://docs.google.com/a/acquia.com/document/d/164Bm2KPAPelQj2fKauWlajDDuusYh4XSluZNlunlaI4/edit) and [weeks of further discussion](https://www.drupal.org/node/1260052), the consensus is that CKEditor is now our best choice.

Therefore, we are going to switch from Aloha to CKEditor for Drupal 8 core. By making this switch, we will not only have a more mature WYSIWYG editor, but we also free up resources to work on other parts of Drupal's authoring experience. The CKEditor team has committed to fix the [8 functional gaps](https://www.drupal.org/node/1260052#comment-6859824) that we've identified in their two [next](https://dev.ckeditor.com/milestone/CKEditor%204.0.1) [upcoming](https://dev.ckeditor.com/milestone/CKEditor%204.1) releases.

Last-minute decisions like this are never easy. But we make them in order to do what is best for Drupal. I'd like to thank both the Aloha Editor team and the CKEditor team for helping us evaluate both editors and working with the Drupal community on closing functional gaps. But don't take your eyes off Aloha Editor; it's an editor that continues to hold a lot of promise for the future of the web.
