---
url: 'https://dri.es/soft-launching-your-new-drupal-theme'
title: 'Soft-launching your new Drupal theme'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2018-12-30T11:22:51-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'Learn how to implement a theme preview feature in Drupal.'
tags:
  - Drupal
  - 'My site'
published: true
id: 4696
---

# Soft-launching your new Drupal theme

Have you ever wanted to preview your new Drupal theme in a production environment without making it the default yet?

I did when I was working on [my redesign of dri.es earlier in the year](https://dri.es/a-fresh-look-for-dri-es). I wanted the ability to add `?preview` to the end of any URL on [dri.es](https://dri.es) and have that URL render in my upcoming theme.

It allowed me to easily preview my new design with a few friends and ask for their feedback. I would send them a quick message like this: <q>Hi Matt, check out an early preview of my site's upcoming redesign: `https://dri.es?preview`. Please let me know what you think!</q>.

Because I use [Drupal](https://www.drupal.org) for my site, I created a custom Drupal 8 module to add this functionality.

Like all Drupal modules, my module has a `*.info.yml` file. The purpose of the `*.info.yml` file is to let Drupal know about the existence of my module and to share some basic information about the module. My theme preview module is called *Previewer* so it has a `*.info.yml` file called `previewer.info.yml`:

```json
name: Previewer
description: Allows previewing of a theme by appending '?preview' to URLs.
package: Custom
type: module
core: 8.x
```

The module has only one PHP class, `Previewer`, that implements Drupal's `ThemeNegotiatorInterface` interface:

```php
<?php

namespace Drupal\previewer\Theme;

use Drupal\Core\Routing\RouteMatchInterface;
use Drupal\Core\Theme\ThemeNegotiatorInterface;

class Previewer implements ThemeNegotiatorInterface {

  /**
  * The function applies() determines if it wants to set the 
  * active theme. If the ?preview query string is part of the
  * URL, return TRUE to denote that Previewer wants to set
  * the theme. determineActiveTheme() will be called to
  * ask for the theme's name.
  */
  public function applies(RouteMatchInterface $route_match) {
  if (isset($_GET['preview'])) {
   return TRUE;
  }
  return FALSE;
  }

  /**
  * The function determineActiveTheme() is responsible
  * for returning the name of the theme that is to be used.
  */
  public function determineActiveTheme(RouteMatchInterface $route_match) {
  return 'dries'; // Yes, the name of my theme is 'dries'.
  }
}

?>
```

The function `applies()` checks if `?preview` is set as part of the current URL. If so, `applies()` returns `TRUE` to tell Drupal that it would like to specify what theme to use. If `Previewer` is allowed to specify the theme, its `determineActiveTheme()` function will be called. `determineActiveTheme()` returns the name of the theme. Drupal uses the specified theme to render the current page request.

For this to work, we have to tell Drupal about our theme negotiator class `Previewer`. This is done by registering it a service in `previewer.services.yml`:

```json
services:
  theme.negotiator.previewer:
  class: Drupal\previewer\Theme\Previewer
  tags:
   - { name: theme_negotiator, priority: 10 }

```

`previewer.services.yml` tells Drupal to call our class `Drupal\previewer\Theme\Previewer` when it has to decide what theme to load.

A *service* is a common concept in Drupal (inherited from Symfony). Many of Drupal's features are separated into a service. Each service does just one job. Structuring your application around a set of independent and reusable service classes is an object-oriented programming best-practice. To some it might feel unnecessarily complex, but it actually promotes reusable, configurable and decoupled code.

Note that Drupal 8 adheres to [PSR-4 namespaces and autoloading](https://www.drupal.org/node/2156625). This means that files must be named in specific ways and placed in specific directories in order to be recognized and loaded. Here is what my directory structure looks like:

```shell
$ tree previewer
previewer
├── previewer.info.yml
├── previewer.services.yml
└── src
  └── Theme
    └── Previewer.php
```

And that's it!
