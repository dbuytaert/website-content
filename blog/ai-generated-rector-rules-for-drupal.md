---
url: 'https://dri.es/ai-generated-rector-rules-for-drupal'
title: 'AI-generated Rector rules for Drupal'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2026-05-06T14:41:48-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
  - 'Artificial Intelligence'
discussions:
  - { platform: LinkedIn, url: 'https://www.linkedin.com/posts/buytaert_keeping-up-with-drupal-core-releases-has-share-7457865465676075008-qAqT/' }
published: true
featured: false
id: 6176
---

# AI-generated Rector rules for Drupal

Keeping up with major Drupal Core releases takes real effort. Each release deprecates APIs and introduces new coding patterns, forcing module developers to update their code. 

That is how most software evolves: old patterns are gradually replaced by better ones.

Tools like [Drupal Rector](https://github.com/palantirnet/drupal-rector) help automate parts of that work, but still rely on hand-written rules. Historically, that hasn't scaled well. Writing Rector rules is often more tedious than difficult: reading change records, understanding edge cases, finding real-world usage patterns, and testing rules.

So I asked a different question: what if we didn't have to write Rector rules at all?

If AI can generate Rector rules automatically, Drupal Core can keep evolving without every API change turning into manual migration work.

That idea led me to extend [Drupal Digests](https://github.com/dbuytaert/drupal-digests), the tool I built to [follow key Drupal developments](https://dri.es/a-better-way-to-follow-drupal-development). In addition to generating summaries, it now also analyzes Drupal Core commits and generates [Rector](https://getrector.com) rules automatically.

When a Drupal Core commit deprecates an API or introduces a new pattern, the tool reads the related issue, analyzes the discussion around it, reviews the code changes, and generates a corresponding Rector rule.

The system has only been running for a few weeks, yet it has already generated [over 175 Rector rules](https://github.com/dbuytaert/drupal-digests/tree/main/rector/rules), with new rules continuously added as the pipeline processes more Drupal Core issues.

AI-generated code is far from perfect. Some rules will have bugs, and others will miss edge cases. But that is exactly why I wanted to publish them now: the more people test them on real projects, the faster they will improve.

Special thanks to [Björn Brala](https://www.drupal.org/u/bbrala), co-maintainer of Drupal Rector, who discovered I was working on this and quickly jumped in to help test and validate some of the generated rules. That kind of feedback is incredibly valuable.

You can try them as follows:

```
git clone https://github.com/dbuytaert/drupal-digests.git
composer require --dev rector/rector
vendor/bin/rector process web/modules/custom \
  --config drupal-digests/rector/all.php --dry-run
```

### Example

Take Drupal's modernization of the [`$entity->original` property](https://www.drupal.org/node/3571065), which exposed the unchanged copy of an entity. Drupal 11.2 deprecated the property in favor of explicit `$entity->getOriginal()` and `$entity->setOriginal()` methods. The old property will be removed in Drupal 12 so various module maintainers have to update their code.

Drupal Digests generated a [Rector rule](https://github.com/dbuytaert/drupal-digests/blob/main/rector/rules/replace-deprecated-entity-original-magic-property-with-3571065.php) that rewrites read access to `getOriginal()` and write assignment to `setOriginal()`.

**Before:**

```php
$entity->original->field->value;
$entity->original = $unchanged;
```

**After:**

```php
$entity->getOriginal()->field->value;
$entity->setOriginal($unchanged);
```

AI-generated upgrade rules will not eliminate all upgrade work anytime soon. But even partial automation can reduce a surprising amount of repetitive work while helping Drupal evolve faster.

PS: Follow the discussion on [LinkedIn](https://www.linkedin.com/posts/buytaert_keeping-up-with-drupal-core-releases-has-share-7457865465676075008-qAqT/).
