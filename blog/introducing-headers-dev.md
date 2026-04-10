---
url: 'https://dri.es/introducing-headers-dev'
title: 'Introducing headers.dev'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2026-04-07T05:44:37-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - 'HTTP headers'
published: true
featured: false
id: 6161
---

# Introducing headers.dev

My [HTTP Header Analyzer](https://headers.dev) started as [a small tool on my blog](https://dri.es/the-little-http-header-analyzer-that-could) six years ago. It makes HTTP headers visible and explains what they do. You give it a URL, it fetches the response headers, and it breaks down what is present, what is missing, and what is possibly misconfigured.

It has been used more than 5 million times, despite being buried at `https://dri.es/headers`. So last week I finally registered [headers.dev](https://headers.dev) and gave it a proper home.

While I was at it, I also audited the analyzer against [OWASP's recommendations for HTTP headers](https://owasp.org/www-project-secure-headers/). I found a few gaps worth fixing. A site could have a Content Security Policy that included `unsafe-inline` and `unsafe-eval`, and the analyzer would describe each directive without mentioning that those two keywords effectively disable XSS protection. Or you could set HSTS with `preload` but forget `includeSubDomains`, which means your preload submission gets silently rejected. These are the kinds of issues a human reviewer might miss but an automated tool should catch. I fixed those and more, so if you've used the analyzer before, your scores might look different now.

The analyzer also learned about dozens of new headers. `Speculation-Rules`, for example, tells browsers to prerender pages a user is likely to visit next. `Cache-Status` replaces the patchwork of vendor-specific `X-Cache` headers with a single structured format that can describe multiple cache layers in one value. And `Reporting-Endpoints` is the modern replacement for `Report-To`, using a simpler key-value syntax for telling browsers where to send security violation reports.

Try it at [headers.dev](https://headers.dev). It now explains over 150 headers and catches misconfigurations that it used to miss. The [Open Web](https://dri.es/tag/open-web) is better when more people check their HTTP headers.
