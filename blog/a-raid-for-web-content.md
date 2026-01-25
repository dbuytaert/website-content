---
url: 'https://dri.es/a-raid-for-web-content'
title: 'A RAID for web content'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2025-12-16T07:22:03-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - 'Digital preservation'
published: true
featured: false
id: 5996
---

# A RAID for web content

If you've worked with storage systems, you know [RAID](https://en.wikipedia.org/wiki/RAID): redundant arrays of independent disks. RAID doesn't try to make individual disks more reliable. It accepts that disks fail and designs around it.

I recently [open-sourced my blog content](/blog/i-open-sourced-my-blog-content) by automatically exporting it as Markdown to GitHub. GitHub might outlive me, but it probably won't be around in 100 years either.  No one really knows.

That raises a simple question: where should content live if you want it to last decades, maybe centuries?

I don't have the answer, but I know it matters well beyond my blog. We are the first generation to create digital content, and we are not very good at preserving what we create. Studies of link rot consistently show that large portions of the web disappear within just a few years.

Every time you publish something online, you're trusting a stack: the file format, the storage medium, the content management system, the organization running the service, the economic model keeping them running. When any layer fails, your content is gone.

So my plan is to slowly build a "digital preservation RAID" across several platforms: [GitHub](https://github.com), the [Internet Archive](https://archive.org), [IPFS](https://ipfs.tech/), and blockchain-based storage like [Filecoin](https://filecoin.io/) or [Arweave](https://www.arweave.org/). If one disappears, the others might remain.

Each option has different trade-offs and failure modes. GitHub has corporate risk because Microsoft owns it, and one day their priorities might change. The Internet Archive depends on non-profit funding and has faced [costly legal battles](https://www.rollingstone.com/music/music-features/internet-archive-major-label-music-lawsuit-1235105273/). IPFS requires someone to actively "pin" your content – if no one cares enough to host it, it disappears. Blockchain-based solutions let you pay once for permanent storage, but the economic models are unproven and I'm not a fan of their climate impact.

If I had to bet on a single option, it would be the Internet Archive. They've been doing some pretty heroic work the past 25 years. GitHub feels durable but archiving old blog posts will never be Microsoft's priority. IPFS, Filecoin, and Arweave are fascinating technical experiments, but I wouldn't rely on them alone.

But the point is _not_ to pick a winner. It is to accept failure as inevitable and design around it, and to keep doing that as the world changes and better preservation tools emerge.

The cost of loss isn't just data. It is the ability to learn from what came before. That feels like a responsibility worth exploring.
