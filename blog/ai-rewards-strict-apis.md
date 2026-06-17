---
url: 'https://dri.es/ai-rewards-strict-apis'
title: 'AI rewards strict APIs'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2026-04-28T09:00:35-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: "AI agents don't struggle with complexity. They struggle with ambiguity. Strict APIs are now an important advantage."
tags:
  - Drupal
  - 'Artificial Intelligence'
  - WordPress
image: blog/drupal-ai-advantage
discussions:
  - { platform: LinkedIn, url: 'https://www.linkedin.com/feed/update/urn:li:share:7454880720868708352/' }
published: true
featured: false
id: 6171
---

# AI rewards strict APIs

Every framework's API surface sits on a spectrum, from strict (typed interfaces, schemas, service containers) to loose (string keys, naming conventions, untyped hooks). Strict APIs cost more upfront: more boilerplate, more to learn before writing code. Loose APIs shift that cost later: more ambiguity, more reliance on naming conventions, and more bugs that are harder to detect and fix.

AI changes who pays. Boilerplate and learning curves don't slow agents down. What slows them down is missing feedback: code that runs but does the wrong thing, errors that don't point to the cause, conventions that have to be guessed. Magic-name binding, untyped hooks, unvalidated configuration, and conventions the code doesn't enforce produce exactly those failure modes.

### Magic strings break the loop

For example, both Drupal and WordPress have long used magic-string hooks. In Drupal, you write a function like `mymodule_user_login`. WordPress uses a related pattern: a string action name passed to `add_action()`. In both cases, the binding is a string the language can't validate.

Get the name wrong and the system silently skips your code: no error, no warning, nothing in the logs. The function just sits there, unloved.

The signature is a convention, not a contract: the documentation says the `user_login` hook receives a `$user` object, but nothing enforces it. To your IDE or a static analyzer like PHPStan, it's just a function. They don't know it's wired into the platform's login flow, so they can't warn you when it's wrong.

A typed alternative makes the binding explicit. With a PHP attribute like `#[Hook('user_login')]` on a registered service, the class must exist, the method signature is type-checked, and the container wires the dependencies. IDEs, static analyzers, and AI coding agents can follow the chain from the attribute to the implementation.

For AI agents, this keeps the feedback loop tight instead of turning it into trial and error. That means they can move faster, spend less time debugging, and use fewer tokens. 

At DrupalCon Chicago this March, AI coding tools migrated a [Lovable-generated site into Drupal](https://dri.es/state-of-drupal-presentation-march-2026) in hours. The strict APIs kept the agent on track.

### A bet made before AI existed

This didn't start with AI. Drupal 8, which we shipped in 2015, introduced Symfony's routing, services, and event dispatcher, replacing large parts of the procedural hook system. Since then, we've kept reducing magic hooks. The attribute-based approach (`#[Hook('user_login')]`) landed in Drupal 11.1 and helps remove more of the remaining procedural-only paths.

Hooks aren't the only place Drupal has been getting stricter. Drupal stores a lot of configuration in YAML, which was one of the loosest parts of the system. A [multi-year validation effort](https://wimleers.com/validation-first) has been tightening that.

When an agent generates a content type definition or editor configuration, validation catches missing keys, invalid values, and broken references before anything is saved. The agent gets a precise error pointing to the exact field, instead of a runtime failure. That tight feedback loop is what makes Drupal a strong CMS for AI-assisted development.

Drupal made this bet early, and it was painful. The Drupal 7 to Drupal 8 transition broke backward compatibility and took years to recover from. But it left the platform much stricter. More than ten years in, [we're still making Drupal stricter](https://dbuytaert.github.io/drupal-core-metrics/).

Meanwhile, WordPress made a different bet, prioritizing backward compatibility over stricter APIs. That kept the platform stable for a long time. It also kept the looseness. 

Those trade-offs now determine how efficiently AI agents can work with each platform.

### What was style is now speed

What used to be a stylistic choice is now a speed and cost problem. Loose APIs mean more debugging and guesswork. Strict APIs mean faster, more precise feedback. This was always true for humans. It's now also true for AI agents. But today that cost shows up in tokens.

PS: Follow the discussion on [LinkedIn](https://www.linkedin.com/feed/update/urn:li:share:7454880720868708352/).
