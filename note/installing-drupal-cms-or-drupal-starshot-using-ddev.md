---
title: 'Installing Drupal CMS (or Drupal Starshot) using DDEV'
date: '2024-11-15T05:21:38-05:00'
author: Dries
tags:
  - Drupal
  - 'Drupal Starshot'
published: true
type: note
url: /installing-drupal-cms-or-drupal-starshot-using-ddev
id: 5716
---

### Installation instructions for end users and testers

We will use [DDEV](https://ddev.com/) to setup and run [Drupal](https://www.drupal.org/) on your computer. DDEV handles all the complex configuration by providing pre-configured Docker containers for your web server, database, and other services.

To install DDEV, you can use [Homebrew](https://brew.sh/) (or choose an [alternative installation method](https://ddev.readthedocs.io/en/stable/users/install/ddev-installation/)):

```shell
$ brew install ddev/ddev/ddev
```

Next, download a [pre-packaged zip-file](https://www.drupal.org/project/cms/releases). Unzip it, navigate to the new directory and simply run:

```shell
$ ddev launch
```

That's it! DDEV will automatically configure everything and open your new Drupal site in your default browser.

### Installation instructions for contributors

If you plan to contribute to Drupal CMS development, set up your environment using Git to create merge requests and submit contributions to the project. If you're not contributing, this approach isn't recommended. Instead, follow the instructions provided above.

First, clone the [Drupal CMS Git repository](https://git.drupalcode.org/project/drupal_cms.git):

```shell
$ git clone https://git.drupalcode.org/project/drupal_cms.git
```

This command fetches the latest version of [Drupal CMS](https://www.drupal.org/project/drupal_cms) from the official Git repository and saves it in the `drupal_cms` directory.

Drupal CMS comes pre-configured for DDEV with all the necessary settings in `.ddev/config.yaml`, so you don't need to configure anything.

So, let's just fire up our engines:

```shell
$ ddev start
```

The first time you start DDEV, it will setup Docker containers for the web server and database. It will also use [Composer](https://getcomposer.org/) to download the necessary Drupal files and dependencies.

The final step is configuring Drupal itself. This includes things like setting your site name, database credentials, etc. You can do this in one of two ways:

**Option 1: Configure Drupal via the command line**
```shell
$ ddev drush site:install
```
This method is the easiest and the fastest, as things like the database credentials are automatically setup. The downside is that, at the time of this writing, you can't choose which Recipes to enable during installation.

**Option 2: Configure Drupal via the web installer**

You can also use the web-based installer to configure Drupal, which allows you to enable individual Recipes. You'll need your site's URL and database credentials. Run this command to get both:
```shell
$ ddev describe
```
Navigate to your site and step through the installer.

Once everything is installed and configured, you can access your new Drupal CMS site. You can simply use:

```shell
$ ddev launch
```

This command opens your site's homepage in your default browser – no need to remember the specific URL that DDEV created for your local development site.

To build or manage a Drupal site, you'll need to log in. By default, Drupal creates a main administrator account. It's a good idea to update the username and password for this account. To do so, run the following command:

```shell
$ ddev drush uli
```

This command generates a one-time login link that takes you directly to the Drupal page where you can update your Drupal account's username and password.

That's it! Happy Drupal-ing!
