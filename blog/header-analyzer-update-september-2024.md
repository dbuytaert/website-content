---
title: 'HTTP Header Analyzer update - September 2024'
date: '2024-09-09T03:02:43-04:00'
author: Dries
tags:
  - 'HTTP headers'
published: true
type: blog
url: /header-analyzer-update-september-2024
id: 5681
---

My [HTTP Header Analyzer](https://dri.es/headers) continues to be [used a lot](https://dri.es/the-little-http-header-analyzer-that-could). Last week, I received a bug report, so I decided to look into it over the weekend. One thing led to another, and I ended up making a slew of improvements:

1. Clarified the explanations for various Cloudflare headers, including `CF-Edge-Cache`, `CF-APO-Via`, `CF-BGJ`, `CF-Polish`, `CF-Mitigated`, `CF-Ray`, `CF-Request-ID`, `CF-Connecting-IP`, and `CF-IPCountry`.
2. Added support for new headers: `X-Logged-In`, `X-Hacker`, `X-Vimeo-Device`, and `Origin-Agent-Cluster`.
3. Improved checks and explanations for cache-related headers, including `X-Cache`, `X-Cache-Status`, and `X-Varnish`.
4. Expanded the validation and explanation for the `X-Content-Type-Options` header.
5. Marked `X-Content-Security-Policy` as a deprecated version of the `Content-Security-Policy` header and provided a more comprehensive breakdown of Content Security Policy (CSP) directives.
6. Improved the validation for CORS-related headers: `Access-Control-Expose-Headers` and `Access-Control-Max-Age`.
7. Expanded the explanation of the `Cross-Origin-Resource-Policy` header, covering its possible values.
8. Added support for the `Timing-Allow-Origin` header.
9. Clarified the `X-Runtime` header, which provides timing information for server response generation.
10. Expanded the explanations for TLS and certificate-related headers: `Strict-Transport-Security`, `Expect-Staple`, and `Expect-CT`.
11. Added an explanation for the `Host-Header` header.
12. Improved details for `X-Forwarded-For`.
13. Refined the explanations for `Cache-Control` directives like `Public`, `Private`, and `No-Cache`.
14. Expanded the explanation for the `Vary` header and its impact on caching behavior.
15. Added an explanation for the `Retry-After` header.
16. Updated the explanation for the legacy `X-XSS-Protection` header.
17. Added an explanation for the Akamai-specific `Akamai-Age-MS` header.

HTTP headers are crucial for web application functionality and security. While some are commonly used, there are many lesser-known headers that protect against security vulnerabilities, enforces stronger security policies, and improves performance.

To explore these headers further, you can try the latest [HTTP Header Analyzer](https://dri.es/headers). It is pretty simple to use: enter a URL, and the tool will analyze the headers sent by your website. It then explains these headers, provides a score, and suggests possible improvements.
