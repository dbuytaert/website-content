---
title: 'PHPUnit tests for Drupal'
date: '2022-10-31T09:15:23-04:00'
author: Dries
tags:
  - Drupal
  - Testing
published: true
type: note
url: /phpunit-tests-for-drupal
id: 5376
---

Writing tests can be hard, but the key is to get started and take that first step. When I start a new Drupal module, I begin with a simple test and make sure it passes. Once I have one simple test passing, it becomes easy to add more.

This page documents how I use [PHPUnit](https://phpunit.de/) with Drupal. Since I sometimes take breaks from working on my Drupal site, I've documented the process of installing, configuring, running and debugging tests as a quick reference. I often return to this guide to refresh my memory.

### The most basic PHPUnit test for Drupal

The most basic [PHPUnit](https://phpunit.de/) test for Drupal looks something like this:

```php
<?php
namespace Drupal\Tests\my_module\Functional;

use Drupal\Tests\BrowserTestBase;

class MyModuleTest extends BrowserTestBase {

  /**
  * Modules to enable.
  *
  * @var array<string>
  */
  protected static $modules = ['my_module'];

  /**
  * Theme to enable. This field is mandatory.
  *
  * @var string
  */
  protected $defaultTheme = 'stark';

  /**
  * The simplest assert possible.
  */
  public function testOne() {
   $this->assertTrue(TRUE);
  }
}

```

The test lives in `docroot/modules/custom/my_module/tests/src/Functional/MyModuleTest.php`.

### Installing PHPUnit for Drupal

Drupal does *not* ship with PHPUnit out-of-the-box, so it needs to be installed.

The best way to install PHPUnit on a Drupal site is by installing the 1 package. It can be installed using [Composer](https://getcomposer.org/):

```shell
$ composer require drupal/core-dev --dev --update-with-all-dependencies
```

The command above will download and install PHPUnit, along with other development dependencies that are considered a best-practice for Drupal development (e.g. [PHPStan](https://phpstan.org/)).

### Configuring PHPUnit for Drupal

Once installed, you still have to configure PHPUnit. All you need to do is set two variables in your shell:

- `SIMPLETEST_BASE_URL` should be the URL of your site (e.g. `http://localhost/`).
- `SIMPLETEST_DB` should be your database settings (e.g. `mysql://username:password@localhost/database`).

I use [DDEV](https://ddev.com/) for my local development environment and follow these steps to log into DDEV's web server and configure the PHPUnit testing variables:

```shell
$ ddev ssh
$ export SIMPLETEST_BASE_URL="https://dri.es.ddev.site/"
$ export SIMPLETEST_DB="mysql://db:db@db/db"

```

### Running PHPUnit test for Drupal

To run all PHPUnit tests in the `./docroot/modules/custom` directory, run the following command from your web server's container:

```shell
$ ./vendor/bin/phpunit docroot/modules/custom
```

To run all tests from a specific class, use the following command:

```shell
$ ./vendor/bin/phpunit --filter MyModuleTest
```

To run a single test method from a specific class, use this command:

```shell
$ ./vendor/bin/phpunit --filter MyModuleTest::testOne
```

### Debugging PHPUnit tests in Drupal

When tests fail, the default PHPUnit output can make it hard to debug the problem. A good first step is to enable the `--debug` flag:

```shell
$ ./vendor/bin/phpunit --filter MyModuleTest::testOne --debug
```

This shows all the steps your test goes through, including setup, data preparation, and each assertion. Often, this extra detail is enough to identify the problem.

If you still encounter unclear errors, like a "500 Internal Server Error", inspecting the response from your application can help. You can temporarily modify your test to print the response body or headers by adding this code:

```php
$content = $this->getSession()->getPage()->getContent(); 
var_dump($content);
```

If PHP is configured to display a stack trace (by setting `display_errors = On` and `error_reporting = E_ALL` in `php.ini`), it will also appear in your terminal.
