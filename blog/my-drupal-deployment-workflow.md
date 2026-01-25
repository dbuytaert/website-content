---
url: 'https://dri.es/my-drupal-deployment-workflow'
title: 'My Drupal deployment workflow'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2022-08-01T14:28:03-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'In 20+ years of working on Drupal, this is my best Drupal development and deployment workflow.'
tags:
  - Drupal
  - 'Acquia Cloud'
  - 'My site'
image: acquia/acquia-code-studio-automated-updates
published: true
id: 5356
---

# My Drupal deployment workflow

I wanted to outline the development and deployment workflow I use on [dri.es](https://dri.es/), my personal website.

My site uses [Drupal](https://www.drupal.org/) (obviously) and runs on [Acquia Cloud](https://www.acquia.com/products/drupal-cloud/cloud-platform) (of course), but a lot of this is a best practice for any web application.

I manage my website's code and configuration in [Git](https://en.wikipedia.org/wiki/Git). Each time I commit a change to my Git repository, I go through the following steps:

1. I create a staging environment to test my code before deploying it to production. It's a complete staging environment: not just PHP, MySQL and Nginx, but also Varnish, Memcache, etc.
2. I check out my Git repository. My Git repository hosts my custom files only. It's a best practice not to commit Drupal core or third-party Drupal modules to your Git repository.
3. I run [PHP Code Sniffer](https://github.com/squizlabs/PHP_CodeSniffer) to make sure my code conforms to my coding style rules. I specify my coding style rules in `phpcs.xml` and use `phpcs` to make sure my code adheres to them. If not, `phpcbf` tries to fix my code automatically. I like my code tidy.
4. I run [PHPStan](https://phpstan.org/), a static code analysis tool for PHP, that scans my code base for bugs. It will find dead code, type casting problems, incorrect function arguments, missing type hints, unknown function calls, and much more. PHPStan is a fantastic tool.
5. I run [PHP Unit](https://phpunit.de/), a PHP testing framework, to make sure my unit tests pass.
6. I run [phpcs-security-audit](https://github.com/FloeDesignTechnologies/phpcs-security-audit), a static code analysis tool for PHP. It scans my PHP code for security vulnerabilities and security weaknesses.
7. I run [ESLint](https://eslint.org/), a static code analysis tool for JavaScript. It scans my JavaScript code for security vulnerabilities and weaknesses.
8. I run [nodejs-scan](https://github.com/ajinabraham/njsscan) to find insecure code patterns in my Node.js applications. I don't use Node.js at the moment though.
9. I also run [Semgrep](https://semgrep.dev/), a static code analysis tool for a variety of programming languages.
10. I run [Rector](https://www.drupal.org/project/rector) to make sure I don't use [deprecated Drupal code](https://www.drupal.org/list-changes/drupal). When I do, Rector will try to programmatically update any deprecated code that it finds.
11. As my Git repository only has custom files, I use [Composer](https://getcomposer.org/) to download and install the latest version of Drupal and all third-party modules and components.
12. I run `drush pm:security`. [Drush](https://www.drush.org/) is a Drupal-specific tool, and the `pm:security` option verifies that I have [no insecure dependencies installed](https://github.com/drupal-composer/drupal-security-advisories).

This all might sound like a lot of work to set up, and it can be. For Acquia customers and partners, [Acquia Code Studio](https://youtu.be/f8llAAcj4U8) automates all the steps above. Acquia Code Studio is a fully managed CI/CD based on [Gitlab](https://gitlab.com/), with specific steps optimized for Drupal. In 20+ years of working on Drupal, it's my best [webops](https://en.wikipedia.org/wiki/Web_operations) workflow yet. It couldn't be easier.

<div class="large">
  [image acquia/acquia-code-studio-automated-tests resize=false]
</div>

Acquia Code Studio also takes care of automating dependency updates. Code Studio regularly checks if Drupal or any of its dependencies have a new release available. If there is a new release, it will run all the steps above. When *all* of the above tools pass, Acquia Code Studio can deploy new code to production with one click of a button.

<div class="large">
  [image acquia/acquia-code-studio-automated-updates resize=false]
</div>

I love it!
