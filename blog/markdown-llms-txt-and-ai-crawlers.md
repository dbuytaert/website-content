---
url: 'https://dri.es/markdown-llms-txt-and-ai-crawlers'
title: 'Markdown, llms.txt and AI crawlers'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2026-03-05T10:18:15-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - 'My site'
  - Markdown
image: blog/machines-reading-web-content
discussions:
  - { platform: LinkedIn, url: 'https://www.linkedin.com/posts/buytaert_i-made-every-page-on-my-site-available-as-share-7435421394915454978-nUV3/' }
published: true
featured: false
id: 6121
---

# Markdown, llms.txt and AI crawlers

[image blog/machines-reading-web-content priority=true schema=false]

In January, I made [every page on my site available as Markdown](https://dri.es/the-third-audience). Immediately AI crawlers quickly found the Markdown versions. I was excited, but excitement isn't data. Now that the dust has settled, I pulled a month of Cloudflare logs and analyzed them.

I compared how much AI bots crawl my site to how often AI answer engines link back. For every citation they sent, their crawlers had fetched 1,241 pages. That is a lot of reading for very little traffic in return. It is [the deal AI is offering creators](https://dri.es/the-webs-broken-deal-with-ai-companies) right now, and it is not a good one.

People also asked whether serving Markdown reduced my bot traffic since the files are smaller. It does not. Bots fetch both versions, and my crawler traffic increased by about 7%. Offering a lighter format does not replace the heavier one. It simply gives bots more to crawl.

As the table below shows, several AI companies crawl my site. Some fetch thousands of pages each month, but very few request the Markdown versions.

<div class="large">
  <table>
  <thead>
  <tr><th>Bot</th><th>Vendor</th><th style="text-align: right">Total</th><th style="text-align: right">HTML files</th><th style="text-align: right">.md files</th><th style="text-align: right">Content Neg</th><th style="text-align: right">% .md</th></tr>
</thead>
  <tbody>
  <tr><td>Amazonbot</td><td>Amazon</td><td style="text-align: right">16,872</td><td style="text-align: right">15,032</td><td style="text-align: right">1,840</td><td style="text-align: right">0</td><td style="text-align: right">10.9%</td></tr>
  <tr><td>ChatGPT-User</td><td>OpenAI</td><td style="text-align: right">13,864</td><td style="text-align: right">13,856</td><td style="text-align: right">8</td><td style="text-align: right">0</td><td style="text-align: right">0.1%</td></tr>
  <tr><td>Meta AI</td><td>Meta</td><td style="text-align: right">9,011</td><td style="text-align: right">8,526</td><td style="text-align: right">485</td><td style="text-align: right">0</td><td style="text-align: right">5.4%</td></tr>
  <tr><td>ClaudeBot</td><td>Anthropic</td><td style="text-align: right">7,144</td><td style="text-align: right">6,995</td><td style="text-align: right">149</td><td style="text-align: right">0</td><td style="text-align: right">2.1%</td></tr>
  <tr><td>OAI-SearchBot</td><td>OpenAI</td><td style="text-align: right">5,722</td><td style="text-align: right">4,422</td><td style="text-align: right">1,300</td><td style="text-align: right">0</td><td style="text-align: right">22.7%</td></tr>
  <tr><td>GPTBot</td><td>OpenAI</td><td style="text-align: right">3,385</td><td style="text-align: right">2,208</td><td style="text-align: right">1,177</td><td style="text-align: right">0</td><td style="text-align: right">34.8%</td></tr>
  <tr><td>Bytespider</td><td>ByteDance</td><td style="text-align: right">1,190</td><td style="text-align: right">1,190</td><td style="text-align: right">0</td><td style="text-align: right">0</td><td style="text-align: right">0.0%</td></tr>
  <tr><td>CCBot</td><td>CommonCrawl</td><td style="text-align: right">530</td><td style="text-align: right">530</td><td style="text-align: right">0</td><td style="text-align: right">0</td><td style="text-align: right">0.0%</td></tr>
  <tr><td>PerplexityBot</td><td>Perplexity</td><td style="text-align: right">467</td><td style="text-align: right">466</td><td style="text-align: right">1</td><td style="text-align: right">0</td><td style="text-align: right">0.2%</td></tr>
  <tr><td>Claude-User</td><td>Anthropic</td><td style="text-align: right">94</td><td style="text-align: right">87</td><td style="text-align: right">7</td><td style="text-align: right">0</td><td style="text-align: right">7.4%</td></tr>
</tbody>
</table>
</div>

Interestingly, OpenAI runs three bots with different roles. `OAI-SearchBot` indexes content for search, `GPTBot` crawls for training data, and `ChatGPT-User` fetches pages in real time during live ChatGPT sessions.

When I added Markdown support to my site, [I exposed it in two ways](https://dri.es/the-third-audience). The first is through dedicated Markdown URLs: append `.md` to any page and you get the Markdown version. The second is through content negotiation, where the original URL returns Markdown instead of HTML when the request includes an `Accept: text/markdown` header.

No AI crawler uses content negotiation. Not one. They only discover the Markdown pages through the dedicated URLs, and only via the auto-discovery link.  To be fair, the auto-discovery link points to the `.md` version.

<div class="large">
  <table>
  <thead>
  <tr><th>Bot</th><th style="text-align: right">robots.txt</th><th style="text-align: right">sitemap.xml</th><th style="text-align: right">llms.txt</th><th style="text-align: right">.md files</th></tr>
</thead>
  <tbody>
  <tr><td>Amazonbot</td><td style="text-align: right">182</td><td style="text-align: right">-</td><td style="text-align: right">-</td><td style="text-align: right">1,840</td></tr>
  <tr><td>ChatGPT-User</td><td style="text-align: right">-</td><td style="text-align: right">-</td><td style="text-align: right">-</td><td style="text-align: right">8</td></tr>
  <tr><td>Meta AI</td><td style="text-align: right">-</td><td style="text-align: right">75</td><td style="text-align: right">-</td><td style="text-align: right">485</td></tr>
  <tr><td>ClaudeBot</td><td style="text-align: right">496</td><td style="text-align: right">115</td><td style="text-align: right">-</td><td style="text-align: right">149</td></tr>
  <tr><td>OAI-SearchBot</td><td style="text-align: right">653</td><td style="text-align: right">-</td><td style="text-align: right">-</td><td style="text-align: right">1,300</td></tr>
  <tr><td>GPTBot</td><td style="text-align: right">-</td><td style="text-align: right">4</td><td style="text-align: right">-</td><td style="text-align: right">1,177</td></tr>
  <tr><td>Bytespider</td><td style="text-align: right">259</td><td style="text-align: right">-</td><td style="text-align: right">-</td><td style="text-align: right">-</td></tr>
  <tr><td>CCBot</td><td style="text-align: right">8</td><td style="text-align: right">-</td><td style="text-align: right">-</td><td style="text-align: right">-</td></tr>
  <tr><td>PerplexityBot</td><td style="text-align: right">142</td><td style="text-align: right">-</td><td style="text-align: right">-</td><td style="text-align: right">1</td></tr>
  <tr><td>Claude-User</td><td style="text-align: right">87</td><td style="text-align: right">-</td><td style="text-align: right">-</td><td style="text-align: right">7</td></tr>
</tbody>
</table>
</div>

And then my favorite: [llms.txt](https://llmstxt.org/), a proposed standard where sites describe their content for AI systems. My site received 52 requests for it last month. Every one came from SEO audit tools. Not a single request came from an AI answer engine or crawler.  (I don't use or pay for SEO tools but apparently that doesn't stop them from auditing my site.)

For fun, we also looked across [Acquia](https://www.acquia.com/)'s entire hosting fleet and found about 5,000 `llms.txt` requests out of 400 million total (0.001%), nearly all from SEO tools. `llms.txt` is a solution looking for a problem. The bots it was designed for don't look for it.

So should you add Markdown support to your site? Probably not. There is no clear benefit today. It does not reduce crawl traffic, and I can't demonstrate that it improves how AI systems use your content.

We do know that AI systems love Markdown, and they fetch it when it is available. At best, it may become more useful over time.

If it is easy to add and you enjoy experimenting, go ahead. If it takes real effort, spend that effort on your content instead. What still works is what has always worked: clear writing, authoritative content, and timely publishing.

PS: Follow the discussion on [LinkedIn](https://www.linkedin.com/posts/buytaert_i-made-every-page-on-my-site-available-as-share-7435421394915454978-nUV3/).
