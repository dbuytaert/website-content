---
title: 'Drupal upgrades: tools and workflow'
date: '2024-06-10T03:19:07-04:00'
author: Dries
tags:
  - Drupal
published: true
type: note
url: /drupal-upgrades-tools-and-workflow
id: 5631
---

When a new major version of Drupal is released, custom code often requires updates to align with API changes, including the removal of deprecated APIs.

Because I keep forgetting certain aspects of this workflow, I decided to document it for future reference.

### Tools overview

<table>
  <thead>
   <tr>
    <th>Tool</th>
    <th>Interface</th>
    <th>Functionality</th>
    <th>Target Audience</th>
  </tr>
 </thead>
  <tbody>
   <tr>
    <td>
      <a href="https://www.drupal.org/project/upgrade_status">Upgrade Status module</a>
   </td>
    <td>UI in Drupal</td>
    <td>Identifies deprecated code, hosting environment compatibility, and more</td>
    <td>Site administrators and developers</td>
  </tr>
   <tr>
    <td>
      <a href="https://github.com/mglaman/drupal-check">Drupal Check</a>
   </td>
    <td>Command-line</td>
    <td>Identifies deprecated code</td>
    <td>Developers, especially during coding and continuous integration (CI)</td>
  </tr>
 </tbody>
</table>

### Upgrade Status module

The [Upgrade Status module](https://www.drupal.org/project/upgrade_status) assesses a Drupal site's readiness for major version upgrades by checking for deprecated code and other compatibility issues.

[image drupal/drupal-upgrade-status-2024]

1. Install the Upgrade Status module like you would install any other Drupal module:
   
    ```shell
    $ ddev composer require –dev drupal/upgrade_status
    ```
   
   Here, `ddev` is the tool I prefer for managing my local development environment. `composer` is a dependency manager for PHP, commonly used to install Drupal modules. The `–dev` option specifies that the module should be installed as a development requirement, meaning it is necessary for development environments but not installed on production environments.
2. Enable the Upgrade Status module:
   
    ```shell
    $ ddev drush pm-enable upgrade_status
    ```
   
   `drush` stands for "Drupal shell" and is a command-line utility for managing Drupal sites. The command `pm:enable` (where `pm` stands for "package manager") is used to enable a module in Drupal.
3. After enabling the module, you can access its features by navigating to the **Admin &gt; Reports &gt; Upgrade status** page at `/admin/reports/upgrade-status`.

### Upgrading PHP and MySQL using DDEV

The Upgrade Status module might recommend updating PHP and MySQL, per [Drupal's system requirements](https://www.drupal.org/docs/getting-started/system-requirements).

To update the PHP version of DDEV, use the following command:

```shell
$ ddev config –-php-version 8.3
```

To upgrade the MySQL version of DDEV and migrate your database content, use the following command:

```shell
$ ddev debug migrate-database mariadb:10.11
```

After updating these settings, I restart DDEV and [run my PHPUnit tests](https://dri.es/phpunit-tests-for-drupal). Although these tests are integrated into [my CI/CD workflow](https://dri.es/my-drupal-deployment-workflow), I also run them locally on my development machine using DDEV for immediate feedback.

### Drupal Check

[Drupal Check](https://github.com/mglaman/drupal-check) is a command-line tool that scans Drupal projects for deprecated code and compatibility issues.

I always run `drupal-check` *before* updating my Drupal site's code and third-party dependencies. This helps ensure there are no compatibility issues with the current codebase before upgrading. I also run `drupal-check` *after* the update to identify any new issues introduced by the updated code.

[image drupal/drupal-check-2024]

1. Installation:
   
    ```shell
    $ ddev composer require –dev mglaman/drupal-check
    ```
2. Run Drupal Check from the root of your Drupal installation:
   
    ```shell
    $ ./vendor/bin/drupal-check –-memory-limit 500M docroot/modules/custom
    ```
   
   I usually have to increase the memory limit, hence the `--memory-limit 500M`.

### Using PHPStan directly

In the future, I'd like to evaluate whether using PHPStan directly is simpler. This is a TODO for myself. Drupal Check is essentially a wrapper around PHPStan, offering default configuration such as automatically running at level 2. To achieve the same result with PHPStan, I should be able to simply run:

```shell
$ php vendor/bin/phpstan analyze -l 2 docroot/modules/custom
```
