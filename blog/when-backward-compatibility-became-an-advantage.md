---
url: 'https://dri.es/when-backward-compatibility-became-an-advantage'
title: 'When backward compatibility became an advantage'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2026-01-12T12:07:49-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
  - Testing
image: drupal/test-coverage-2026
published: true
featured: false
id: 6046
---

# When backward compatibility became an advantage

Twenty years ago, I argued passionately that [breaking backward compatibility](https://dri.es/backward-compatibility) was one of Drupal's core values:

> The only viable long-term strategy is to focus exclusively on getting the technology right. The only way to stay competitive is to have the best product. [...] If you start dragging baggage along, your product will, eventually, be replaced by something that offers the same functionality but without the baggage. 

I warned that preserving backward compatibility would be the beginning of the end: 

> I fear that this will be the end of Drupal as we have come to know it. Probably not immediately, maybe not even for several years, but eventually Drupal will be surpassed by technology that can respond more quickly to change. 

Twenty years later, I have to admit I was wrong.

So what changed? 

In 2006, [Drupal](https://www.drupal.org/) had almost no automated tests. We couldn't commit to backward compatibility because we had no way to know when we broke it. Two years later in 2008, [we embraced test-driven development](https://dri.es/embracing-test-driven-development). 

<div class="large">
[image drupal/test-coverage-2026 resize=false schema=false]
</div>

By 2013, we had built up some test coverage, and with that foundation we [adopted semantic versioning](https://www.drupal.org/node/2135189) and committed to backward compatibility. It transformed [how we innovate in Drupal](https://dri.es/the-transformation-of-drupal-8-for-continuous-innovation). We can mark old code for removal and clear it out every two years with each major release. The baggage I feared never really accumulated.

Today, according to the [Drupal Core Metrics dashboard](https://dbuytaert.github.io/drupal-core-metrics/), Drupal Core has more than twice as much test code as production code. I didn't fully appreciate how much that would change things. You can't promise backward compatibility at Drupal's scale without extensive automated testing.

Our upgrades are now [the smoothest in the project's history](https://dri.es/making-drupal-upgrades-easy-forever). And best of all, Drupal didn't end. It's still a top choice for organizations that need flexibility, security, and scale.

I recently came across [an interview with Richard Hipp](https://sigmodrecord.org/publications/sigmodRecord/1906/pdfs/06_Profiles_Hipp.pdf), SQLite's creator. SQLite has 90 million lines of tests for 150,000 lines of production code. That is a whopping 600-to-1 ratio. Hipp calls it "aviation-grade testing" and says it's what lets a team of three maintain billions of installations.

I suspect our test coverage will continue to grow over time. But Drupal can't match SQLite's ratio, and it doesn't need to. What matters is that we built the habits and discipline that work for us.

In 2006, I thought backward compatibility would be the end of Drupal. In 2026, I think it might be what keeps us here for another twenty years. 

Thank you to everyone who wrote those tests. 

It does make me wonder: what are we wrong about now? What should we be investing in today that will slowly reshape how we work and become an obvious advantage twenty years from now? And who is already saying it while the rest of us aren't listening?
