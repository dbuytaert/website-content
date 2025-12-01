---
title: 'Setting up a new computer with Homebrew'
date: '2024-08-26T10:29:51-04:00'
author: Dries
tags:
  - 'Software development'
published: true
type: note
url: /setting-up-a-new-computer-with-homebrew
id: 5676
---

Setting up a new computer can be a lot of work, but I've made it much simpler with [Homebrew](https://brew.sh/), a popular package manager.

### Creating a list of installed software

As a general rule, I prefer to install all software on my Mac using [Homebrew](https://brew.sh/). I always try Homebrew first and only resort to downloading software directly from websites if it is not available through Homebrew.

Homebrew manages both *formulae* and *casks*. Casks are typically GUI applications, while formulae are command-line tools or libraries. To keep these two types of packages organized and avoid potential conflicts, I save them in separate lists.

First, I generate a list of all manually installed formulae on my old computer:

```shell
$ brew leaves > brews.txt
```

The `brew leaves` command displays only the formulae you installed directly using Homebrew. It excludes any formulae that were installed automatically as dependencies. To view all installed formulae, including dependencies, you can use the `brew list` command.

Next, I generate a separate list for installed casks:

```shell
$ brew list --cask > casks.txt
```

This keeps the formulae (`brews.txt`) and casks (`casks.txt`) in distinct files, avoiding any ambiguity.

### Reviewing your packages

It is a good idea to check if you still need all packages on your new computer. I review my formulae and casks as follows:

For formulae:

```shell
$ cat brews.txt | xargs brew desc --formula --eval-all
```

For casks:

```shell
$ cat casks.txt | xargs brew desc --cask --eval-all
```

These commands provide a short description for each package in your lists.

### Installing your packages on a new machine

Transfer your `brews.txt` and `casks.txt` files to the new computer, install Homebrew, and run:

To install formulae:

```shell
$ xargs brew install --formula 
```

To install casks:

```shell
$ xargs brew install --cask 
```
