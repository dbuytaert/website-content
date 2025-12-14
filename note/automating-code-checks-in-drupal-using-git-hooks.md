---
title: 'Automating code checks in Drupal using Git Hooks'
date: '2023-12-07T09:28:35-05:00'
author: Dries
tags:
  - Drupal
  - Automation
featured: false
published: true
type: note
url: /automating-code-checks-in-drupal-using-git-hooks
id: 5526
---

I finally set up some Github pre-commit hooks on my local [Drupal](http://www.drupal.org/) development environment.

Pre-commit hooks in Git can streamline your workflow by automating checks and tasks for every commit. The official documentation can be found at <https://git-scm.com/docs/githooks>.

If you, like me, often forget to run your code linter and static code analyzer, pre-commit hooks offer a great solution. They automate these tasks with every commit.

To set up a pre-commit hook, edit the file `.git/hooks/pre-commit` in your Drupal directory. Git specifically looks for a file named `pre-commit` in the `.git/hooks` directory so the name has to be exact.

Here is my current script:

```shell
#!/bin/sh

# Execute PHP Code Beautifier and Fixer
./vendor/bin/phpcbf
if [ $? -ne 0 ]; then
 echo "Failed command: ./vendor/bin/phpcbf"
 exit 1
fi

# Execute PHPStan for static code analysis
./vendor/bin/phpstan analyse –memory-limit=256M
if [ $? -ne 0 ]; then
 echo "Failed command: ./vendor/bin/phpstan analyse –memory-limit=256M"
 exit 1
fi

```

The script runs 1 (PHP Code Beautifier and Fixer) for code formatting and 1 (a static analysis tool for PHP) for identifying bugs. Should these tools find any issues, the commit is blocked.

### Installing `phpcbf` and `phpstan`

Drupal does *not* ship with `phpcbf` or `phpstan` out-of-the-box, so these tools need to be installed. They can be installed individually using [Composer](https://getcomposer.org/):

```shell
$ composer require –dev squizlabs/php_codesniffer phpstan/phpstan
```

However, my recommended way to install these tools for Drupal is by installing the 1 package. This package bundles a number of Drupal development tools and best practices, including `phpcbf` and `phpstan`.

```shell
$ composer require drupal/core-dev –dev –update-with-all-dependencies
```
