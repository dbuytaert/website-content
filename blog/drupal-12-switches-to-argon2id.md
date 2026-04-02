---
url: 'https://dri.es/drupal-12-switches-to-argon2id'
title: 'Drupal 12 switches to Argon2id'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2026-03-30T05:15:35-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
  - Security
discussions:
  - { platform: LinkedIn, url: 'https://www.linkedin.com/posts/buytaert_drupal-12-switches-to-argon2id-activity-7444322345546305538--Lua/' }
published: true
featured: false
id: 6151
---

# Drupal 12 switches to Argon2id

Drupal 12 will [hash passwords with Argon2id by default](https://www.drupal.org/project/drupal/issues/3530186). It moves every Drupal site to what is now best practice for password storage, recommended by [OWASP](https://cheatsheetseries.owasp.org/cheatsheets/Password_Storage_Cheat_Sheet.html) and aligned with [NIST guidance](https://pages.nist.gov/800-63-4/sp800-63b.html).

Drupal is often used for security-sensitive and large-scale sites, so these kinds of changes matter.

Early versions of Drupal stored passwords as simple MD5 hashes, which is extremely weak by today's standards. Drupal 7 introduced a modified version of the [phpass library](https://www.openwall.com/phpass/) using [SHA-512](https://en.wikipedia.org/wiki/SHA-2) with multiple iterations and a salt, and [Drupal 10 switched to bcrypt](https://www.drupal.org/node/3322420). Each jump was a response to attackers getting faster hardware, and this change continues that pattern.

When I first looked at this change, I wanted to understand what [Argon2id](https://en.wikipedia.org/wiki/Argon2) actually does differently from [bcrypt](https://en.wikipedia.org/wiki/Bcrypt).

Its key advantage is that it is "memory hard". Each Argon2id hash requires far more memory to compute than a bcrypt hash, and the amount is configurable.

Modern GPUs can run many bcrypt computations in parallel because each one uses very little RAM. GPUs have a lot of total memory, but it is shared across thousands of parallel computations. As a result, Argon2id limits how many hash computations can run in parallel, making it harder and more expensive to scale attacks.

The best security upgrades are the ones nobody has to think about. Once a site upgrades to Drupal 12, existing passwords will automatically be rehashed to Argon2id the next time each user logs in. And in the unlikely event that Argon2id is not available in a particular PHP installation, Drupal will fall back to bcrypt for compatibility.

Many site owners never think about password hashing, so Drupal's defaults become their security policy. The people who benefit most from this change may never know it happened. It's why being "secure by default" matters so much.

Thanks to everyone who helped make this happen.

PS: Follow the discussion on [LinkedIn](https://www.linkedin.com/posts/buytaert_drupal-12-switches-to-argon2id-activity-7444322345546305538--Lua/).
