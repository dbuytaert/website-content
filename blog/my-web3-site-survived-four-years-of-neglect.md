---
url: 'https://dri.es/my-web3-site-survived-four-years-of-neglect'
title: 'My Web3 site survived four years of neglect'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2026-02-23T03:56:44-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: "After four years of neglecting my Web3 site, does it still work? Plus, insights into Web3's progress for website hosting."
tags:
  - Web3
  - 'Digital preservation'
  - Blockchain
image: blog/web3-exploration
discussions:
  - { platform: LinkedIn, url: 'https://www.linkedin.com/posts/buytaert_web3-ipfs-ens-activity-7431632061007810561-_Mll' }
published: true
featured: false
id: 6106
---

# My Web3 site survived four years of neglect

[image blog/web3-exploration schema=false]

Four years ago, [I published my first Web3 webpage](https://dri.es/my-first-web3-webpage) using IPFS and ENS. I uploaded a simple "Hello World" HTML file, pointed `dries.eth` at it, and left it there. [Two years later](https://dri.es/two-years-later-is-my-web3-website-still-standing), I found it still running.

I haven't touched it since. Today, on the experiment's four-year anniversary, I checked again. It's still up at [dries.eth.limo](https://dries.eth.limo/). Four years of total neglect, and the page loads just fine.

When I checked two years ago, every service I used was still operational. I called that "really encouraging". That optimism aged poorly.

Today, half the services have shut down, restricted access, or pivoted entirely:

- [Fleek](https://fleek.co/), a platform I used to pin my content, [shut down its hosting service](https://ipshipyard.com/blog/2026-ipfs-self-hosting-migration/) on January 31, 2026. They pivoted to AI.  

- [Infura](https://infura.io/) was acquired by [MetaMask](https://metamask.io/) and [closed its IPFS service to new users](https://docs.metamask.io/services/reference/ipfs/). 

- [Web3.storage](https://web3.storage) rebranded to [Storacha](https://storacha.network/), and dropped IPFS pinning altogether.  

- [Cloudflare sunset its public IPFS gateways](https://blog.cloudflare.com/cloudflares-public-ipfs-gateways-and-supporting-interplanetary-shipyard/).

- [Scaleway shut down its IPFS pinning service](https://labs.scaleway.com/en/ipfs-pinning/).

Of the original services, [Pinata](https://pinata.cloud/) is still focused on IPFS. I logged in and my "Hello World" HTML file is still there. And [eth.limo](https://eth.limo/), the ENS gateway that lets anyone access `.eth` sites in a normal browser, still works.

## Technically robust, commercially fragile

IPFS content exists only as long as someone chooses to host it. In 2022, my HTML file was pinned on Fleek, Pinata, Infura, and a friend's node. Today, it comes down to Pinata's free tier. My web3 page is hanging by a thread. 

That sounds fragile, and in one sense it is. But the protocol is working as designed. IPFS doesn't promise permanence. It promises that content is addressable, verifiable, and can be kept alive by anyone who cares enough to pin it.

The durability of content on IPFS scales with how much people care about it. No one really cares about my "Hello World" page, so it's not being pinned. If this were dissident journalism or censored speech, people would likely pin it.

If you run an IPFS node and want to help keep my page alive, feel free to pin it: `ipfs pin add bafybeibbkhmln7o4ud6an4qk6bukcpri7nhiwv6pz6ygslgtsrey2c3o3q`.

Of course, I could make it more robust myself by pinning it on additional services or running my own node. Instead, I relied on third parties. With no node of my own, I'm entirely dependent on pinning services and other users to keep it alive.

The real story isn't fragility. It's economics. There may simply not be enough demand for decentralized storage to support a healthy market of providers. Companies keep entering, failing to find a business model, and pivoting away.

Traditional hosting is cheap, reliable, and familiar. The people who need censorship resistance are a narrow group, and everyone else has little reason to switch, myself included. And to be fair, replacing everyday web hosting was probably never IPFS's goal.

I still love IPFS as a protocol and the ideas behind it. But it feels like the ecosystem around it is commercially thin, and getting thinner.

I've written before about the idea of a [RAID for web content](https://dri.es/a-raid-for-web-content). Rather than relying on a single system, the goal is redundancy across multiple layers. I'd like to experiment more with IPFS and make it one of those layers.

## Browser support got worse, not better

In 2022, mainstream browsers didn't support ENS or IPFS natively, except for [Brave](https://brave.com/). Brave included a built-in IPFS node that could resolve `ipfs://` and `ipns://` addresses directly.

In August 2024, Brave [removed that integration](https://brave.com/blog/ipfs-support/). Fewer than 0.1% of users had ever used it, and the support costs were too high.

Chrome, Firefox, and Safari still don't support ENS or IPFS natively. A [Firefox issue for adding IPFS support](https://bugzilla.mozilla.org/show_bug.cgi?id=1354807) has been open since 2017, with no plans to implement it. The IPFS community continues pushing for [browser standards work](https://discuss.ipfs.tech/t/browsers-standards-work-2026-call-for-community-input/19917), but native protocol support seems like a long way off.

Today, the easiest way to visit a `.eth` site is still through a gateway like [eth.limo](https://eth.limo/). You append `.limo` to the ENS name and visit it in any browser. It works, but it's a centralized bridge to a decentralized system, which is a little ironic.

## Gas fees dropped 99%

Not everything got worse. In [my original post](https://dri.es/my-first-web3-webpage), I called out the cost of updating an ENS record as a major barrier. When content changes on IPFS, its hash changes too. To keep `dries.eth` pointing to the latest version, that new address has to be written to Ethereum, which costs gas.

Updating my content on Ethereum cost me $11.69 in 2022 and $4.08 in 2024. If I wanted to update it today, it would cost roughly one cent.

Average Ethereum gas prices now sit around 0.03 to 0.05 Gwei, compared to 30 to 50 Gwei when I first set this up. That is roughly a thousand times cheaper.

Two things drove this. 

First, Ethereum roughly doubled the computation it can process per block over 2025. Validators gradually raised the gas limit, and the [Fusaka upgrade](https://ethereum.org/roadmap/fusaka/) in December formally pushed it from 30 million to 60 million.

Second, many applications migrated to Layer 2 networks. These are separate blockchains that batch up transactions and settle them back to Ethereum in bulk. As traffic moved off the main chain, congestion and fees dropped further.

The impact on ENS is dramatic. Just this month, ENS Labs [cancelled its planned Layer 2 blockchain called "Namechain"](https://www.theblock.co/post/388932/ens-labs-scraps-namechain-l2-shifts-ensv2-fully-ethereum-mainnet) because Ethereum's main network got so inexpensive that the Layer 2 became unnecessary. Nick Johnson, ENS co-founder and lead developer, noted that subsidizing 100% of all ENS transactions at current gas prices would cost about $10,000 per year.

## A mixed scorecard

Four years in, the technology is better than ever but the market around it is worse. The IPFS protocol seems sound. ENS records are permanent. Gas fees have nearly vanished. But the commercial ecosystem for decentralized hosting has steadily thinned.

I wrote in 2022 that "IPFS and ENS offer limited value to most website owners, but tremendous value to a very narrow subset". Four years later, that assessment holds true. 

AI also absorbed most of the tech industry's attention and capital. Web3 funding dropped sharply. Fleek's pivot from IPFS hosting to AI inference feels symbolic.

Will I keep the experiment going? Of course. But it's probably time to add a few more pins and stop relying on free tiers. The protocols don't need my help. The ecosystem apparently does.

PS: Follow the discussion on [LinkedIn](https://www.linkedin.com/posts/buytaert_web3-ipfs-ens-activity-7431632061007810561-_Mll).
