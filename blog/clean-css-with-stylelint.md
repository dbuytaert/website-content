---
url: 'https://dri.es/clean-css-with-stylelint'
title: 'Clean CSS with Stylelint'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2017-12-20T10:29:49-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'Finding bugs, inefficiencies and stylistic inconsistencies in your CSS with Stylint'
tags:
  - 'My site'
  - CSS
published: true
id: 4106
---

# Clean CSS with Stylelint

Last night I was working on the [album functionality](https://dri.es/photos) for this website. CSS is not my strong suit, so I wanted to get some help from a *CSS linter*. A CSS lint tool parses your CSS code and flags signs of inefficiency, stylistic inconsistencies, and patterns that may be erroneous.

I tried [Stylelint](https://stylelint.io), an open source CSS linter written in JavaScript that is maintained as an [npm package](https://www.npmjs.com). It was quick and easy to install on my local development environment:

```shell
$ npm install -g stylelint stylelint-config-standard stylelint-no-browser-hacks
```

The `-g` attribute instructs npm to install the packages globally, the `stylelint-config-standard` is a standard configuration file (more about that in a second), and the `stylelint-no-browser-hacks` is an optional Stylelint plugin.

Stylelint has over 150 rules to catch invalid CSS syntax, duplicates, etc. What is interesting about Stylelint is that it is completely unopinionated; all the rules are disabled by default. Configuring [all 150+ rules](https://stylelint.io/user-guide/rules/) would be very time-consuming. Fortunately you can use the example `stylelint-config-standard` configuration file as a starting point. This configuration file is maintained as a separate npm package. Instead of having to configure all 150+ rules, you can start with the `stylelint-config-standard` configuration file and overwrite the standard configuration with your own configuration file. In my case, I created a configuration file called `stylelint.js` in my Drupal directory.

```json
"use strict"

module.exports = {
  "extends": "stylelint-config-standard",
  "plugins": [
    "stylelint-no-browser-hacks/lib"
  ],
  "rules": {
    "block-closing-brace-newline-after": "always",
    "color-no-invalid-hex": true,
    "indentation": 2,
    "property-no-unknown": true,
    "plugin/no-browser-hacks": [true, {
      "browsers": [
        "last 2 versions",
        "ie >=8"
      ]
    }],
    "max-empty-lines": 1,
    "value-keyword-case": "lower",
    "at-rule-empty-line-before": null,
    "rule-empty-line-before": null,
  },
}
```

As you can see, the configuration file is a JSON file. I've extended `stylelint-config-standard` and overwrote the `indentation` rule to be 2 spaces instead of tabs, for example.

To check your CSS file, you can run Stylelint from the command line:

```shell
$ stylelint --config stylelint.js --config-basedir /usr/local/lib/node_modules/ css/album.css
```

In my case it found a couple of problems that were easy to fix:

[image blog/stylelint-album-css resize=false]

For fun, I googled "Stylelint Drupal" and found that [Alex Pott](https://www.drupal.org/u/alexpott) has proposed [adding a Stylelint configuration file to Drupal core](https://www.drupal.org/project/drupal/issues/2865971). *Seems useful to me!*
