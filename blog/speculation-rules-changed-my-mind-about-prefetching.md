---
url: 'https://dri.es/speculation-rules-changed-my-mind-about-prefetching'
title: 'Speculation Rules changed my mind about prefetching'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2026-06-05T10:37:35-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - 'My site'
  - 'Web performance'
discussions:
  - { platform: LinkedIn, url: 'https://www.linkedin.com/feed/update/urn:li:share:7468677251128197120/' }
published: true
featured: false
id: 6211
---

# Speculation Rules changed my mind about prefetching

For years, prefetching made me uneasy. It can make websites feel faster, but it also asks visitors to spend bandwidth, CPU, memory, and battery on pages they may never open. That always felt a little wasteful, and maybe even a little disrespectful.

That unease also comes from a deeper belief: prefetching should not be a substitute for a fast site. Too many sites are weighed down by unnecessary JavaScript, tracking scripts, third-party widgets, heavy fonts, and oversized assets. Prefetching should not be used to hide that bloat. Before considering prefetching, make your site light and fast.

A couple months ago, while [updating my HTTP header analyzer](https://dri.es/introducing-headers-dev), I added support for the `Speculation-Rules` HTTP header. Learning about the [Speculation Rules API](https://developer.mozilla.org/en-US/docs/Web/API/Speculation_Rules_API) inspired me to try it on my own blog.

The idea is simple: a page can give the browser a small JSON rule set that says which links are safe to prefetch, and when. Those rules can live directly in the HTML using `<script type="speculationrules">`, or in an external file referenced by the `Speculation-Rules` HTTP header.

For my blog, I added the rules directly to the HTML of every anonymous page request:

```html
<script type="speculationrules">
{
  "prefetch": [{
    "where": {
      "and": [
        { "href_matches": "/*" },
        { "not": { "href_matches": "/search*" } }
      ]
    },
    "eagerness": "conservative"
  }]
}
</script>
```

The rule tells browsers that any same-origin link is safe to prefetch, except for paths under `/search*`.

The `eagerness: conservative` setting fires the prefetch on `pointerdown` or `touchstart`, meaning the browser only starts prefetching once the user begins to click or tap a link. There are more aggressive options, such as prefetching when a link becomes visible or when a user hovers over it. 

Some of you might point out that browsers have supported prefetching for years through the older [`<link rel="prefetch">`](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/rel/prefetch) tag. That is true, but I've never loved it.

Traditional prefetching is great when the next page is highly predictable, like the next step in a checkout flow or setup wizard. 

On many websites, including my blog, it's anyone's guess what a visitor will click next. Sometimes you can make a smarter guess, but it is still a guess.

And when you guess wrong, visitors spend bandwidth, battery, and compute on pages they never visit. Multiply that across millions of sites and visitors, and those speculative requests add up.

So why implement Speculation Rules? My site was already [fast without being static](https://dri.es/why-content-management-systems-can-outperform-static-site-generators). With `eagerness: conservative`, the browser waits until the user has already started an action. At that point, the navigation is no longer a vague prediction. It is very likely to happen.

Speculation Rules also respect Battery Saver and Data Saver modes. If a device is low on battery, memory constrained, or trying to conserve data, the prefetching is skipped.

So is prefetching still worth it when the user has already started to click? I think so. With `eagerness: conservative`, the browser only gets a small head start but something is better than nothing.

Browsers already do some speculative loading on their own without Speculation Rules, but only for high-confidence destinations, like the address bar suggestion you are typing toward. 

But they will not prefetch arbitrary links on a page, and for good reason. Prefetching `/logout`, for example, would sign the visitor out, even if they change their mind and never complete the click or hit `Enter`.

That is why Speculation Rules can be useful. You can tell the browser which paths are safe and which to leave alone. 
	
In short, Speculation Rules changed my mind because they make prefetching feel more responsible: don't prefetch too much, don't prefetch too early, and only give the browser a safe hint when the user's intent is clear.

PS: Follow the discussion on [LinkedIn](https://www.linkedin.com/feed/update/urn:li:share:7468677251128197120/).
