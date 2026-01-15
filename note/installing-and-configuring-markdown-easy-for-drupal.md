---
title: 'Installing and configuring Markdown Easy for Drupal'
date: '2025-08-20T03:29:25-04:00'
author: Dries
tags:
  - Drupal
  - Markdown
featured: false
published: true
type: note
url: /installing-and-configuring-markdown-easy-for-drupal
id: 5866
---

I recently installed [Markdown Easy](https://www.drupal.org/project/markdown_easy) for [Drupal](https://www.drupal.org/) and then upgraded from version 1.0 to 2.0. 

I decided to document my steps in a [public note](https://dri.es/if-a-note-can-be-public-it-should-be) in case they help others.

On my local machine, I run Drupal with [DDEV](https://ddev.com). It sets up pre-configured Docker containers for the web server, database, and other required Drupal services. DDEV also installs [Composer](https://getcomposer.org/) and [Drush](https://www.drush.org/), which we will use in the steps below.

First, I installed version 2.0 of *Markdown Easy* using Composer:
```bash
ddev composer require drupal/markdown_easy
```

If you are upgrading from version 1.0, you will need to run the database updates so Drupal can apply any changes required by the new version. You can do this using Drush:
```bash
ddev drush updatedb
```

As explained in [*Switching to Markdown after 20 years of HTML*](https://dri.es/switching-to-markdown-after-20-years-of-html), I want to use HTML and Markdown interchangeably. By default, *Markdown Easy* strips all HTML. This default approach is the safest option for most sites, but it also means you can't freely mix HTML tags and Markdown.


To change that behavior, I needed to adjust two configuration settings. These settings are not exposed anywhere in Drupal's admin interface, which is intentional. *Markdown Easy* keeps its configuration surface small to stay true to its "easy" name, and it leads with a secure-by-default philosophy. If you choose to relax those defaults, you can do so using Drush.

```bash
ddev drush config:set markdown_easy.settings skip_html_input_stripping 1

ddev drush config:set markdown_easy.settings skip_filter_enforcement 1
```

The `skip_html_input_stripping` setting turns off input stripping in the [CommonMark](https://commonmark.thephpleague.com/) Markdown parser, which means your HTML tags remain untouched while Markdown is processed.

The `skip_filter_enforcement` setting lets you turn off input stripping in Drupal itself. It allows you to disable the *"Limit allowed HTML tags"* filter without warnings from *Markdown Easy*.

You can enable just the first setting if you want Markdown to allow HTML but still let Drupal filter certain tags using the *"Limit allowed HTML tags"* filter. Or you can enable both if you want full control over your HTML with no stripping at either stage.

Just know that disabling HTML input stripping and disabling HTML filter enforcement can have security implications. Only disable these features if you trust your content creators and understand the risks.

Next, I verified my settings:

```bash
ddev drush config:get markdown_easy.settings
```

You should see:
```bash
skip_html_input_stripping: true
skip_filter_enforcement: true
```

Finally, clear the cache:
```bash
ddev drush cache-rebuild
```

Next, I updated my existing Markdown text format. I went to `/admin/config/content/formats/` and made the following changes:
- Set the Markdown flavor to *Smorgasbord*.
- Disabled the *"Limit allowed HTML tags and correct faulty HTML"* filter.
- Disabled the *"Convert line breaks into HTML"* filter.

That's it!
