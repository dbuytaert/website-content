---
title: 'My first Web3 webpage'
date: '2022-02-24T04:19:24-05:00'
author: Dries
summary: "How I built my first Web3 website, the Web3 services I used, and what I think about Web3's potential."
image: blog/web3-exploration
tags:
  - Blockchain
  - 'My site'
  - Web3
featured: true
published: true
type: blog
url: /my-first-web3-webpage
id: 5301
---

[image blog/web3-exploration schema=false]

Today, I'm going to publish my first webpage using Web3 technologies. I will upload a page to IPFS (InterPlanetary File System), make it available at `dries.eth` using ENS (Ethereum Name Service), and visit it with a Web3-enabled browser. If you don't know what that means, buckle up for a crash course.

### Step 1: Buy an ENS domain name

Last year, [I minted `buytaert.eth`](https://etherscan.io/tx/0x86dc98df818e3e135be63bfda35b5e5e3a8a467435c54f9d6707f6c0be2064ad), and more recently, [I purchased `dries.eth`](https://etherscan.io/tx/0xf60512dae73bd0e37b622ef60bb1bded61dbe72dbe96c1e89e7f7b2d99b14d63). Both are *ENS domain names*.

[ENS](https://ens.domains/), which stands for *Ethereum Name Service*, is an Open Source blockchain-based naming protocol. You can think of ENS as DNS for Web3. Where DNS maps domain names to IP addresses, ENS maps domain names to Ethereum addresses. And an Ethereum address can point to a cryptocurrency wallet, a content hash, and more.

ENS isn't just a service for Ethereum; it's a general purpose Web3 service built *on* Ethereum using [smart contracts](https://ethereum.org/en/smart-contracts/). Because ENS is built on the blockchain, it is more resistant to censorship than DNS.

Today, the primary use case for having your own ENS domain is to make receiving cryptocurrencies easier. If you wanted to send me some Ether, you have to send it to `0xbAD65DE65AE2c23f5eA30d12fC8c2f883cbe671f`, the address of my Ethereum wallet. Because I own `dries.eth`, you can send it `dries.eth` instead. Much easier to remember!

It's pretty amazing that `dries.eth` can collect cryptocurrencies permissionless from anyone anywhere in the world without a single intermediary. However, that is not the topic of today's blog post. In this blog post, I want to show how `dries.eth` can be used to host a fully decentralized Web3 webpage.

If you want to buy an `.eth` domain, you can do so at the [ENS Domains website](https://ens.domains/). Because an `.eth` domain is an NFT (Non-Fungible Token), you can also buy and sell domain names at NFT marketplaces like [OpenSea](http://opensea.io/).

When ENS launched in May 2017, it only supported the ENS-native TLD `.eth`. As of August 2021, ENS added support for the full DNS namespace. So if you own `example.com` on DNS, you can use the [ENS Domains website](https://ens.domains/) to set ENS records for `example.com`.

### Step 2: Upload a HTML file to IPFS

[IPFS](https://ipfs.io/), short for *InterPlanetary File System*, is an Open Source protocol and peer-to-peer network for storing and sharing data.

Today, most webpages are stored on a single server, hosted in a single data center. These sites are not very resilient to a single point of failure, denial of service attacks, or government censorship.

More advanced websites replicate their webpages using [CDNs](https://en.wikipedia.org/wiki/Content_delivery_network) and other caching systems. My site uses multiple Kubernetes web nodes, Varnish and Cloudflare, but that is because [my company](https://dri.es/acquia-my-drupal-startup) helps run some of the largest websites in the world, not because my website requires it. All these technologies can be used to improve a website's resiliency.

With IPFS, your webpage can be replicated across hundreds of "IPFS nodes" around the world. Everyone in the world can run an IPFS node. The nodes create a single, global network, and each file in the network gets a unique, global identifier.

In theory, IPFS is *more resilient* than traditional website hosting. Because IPFS nodes are run by different people and organizations around the world, and content is replicated across them, the hosted content is more resistant to a single point of failure, denial of service attacks, or government censorship. The flip-side is that it is also more difficult to moderate misinformation.

I wrote "in theory" because content uploaded to IPFS only stays available as long as one node, somewhere in the world, chooses to host it. And by default, IPFS does *not* include a built-in mechanism to incentivize other nodes in the network to replicate data. Each IPFS node tends to host its own data. Other nodes can replicate data cooperatively, or as a service.

This is where [Filecoin](https://filecoin.io/) comes in. Like IPFS, Filecoin is an Open Source protocol. IPFS itself is not blockchain-based, but Filecoin is. Filecoin extends IPFS with a public marketplace for storing and replicating data. Miners can earn [Filecoin](https://www.coinbase.com/price/filecoin) (a cryptocurrency token) in exchange for storing and replicating IPFS data. Because Filecoin is blockchain-based, the marketplace is not owned by a single intermediary. Storage deals are brokered programmatically by nodes on the network.

Long story short, to host my webpage on IPFS, I need at least one IPFS node willing to host my content. There are two solutions for this: (1) I can run my own IPFS node or (2) I can pay a third-party IPFS service to host my content.

#### Running my own IPFS node

In the spirit of helping to build a decentralized web, running your own IPFS node should be the preferred option. Below you can see my local IPFS node hosting my `index.html` file:

<div class="large">
  [image blog/local-ipfs-node-1 resize=false]
  [image blog/local-ipfs-node-2 resize=false]
</div>

#### Replicating my webpage

Because my local IPFS node runs on my laptop, my webpage is only available when my laptop is connected to the internet.

As explained, I can use Filecoin to pay other nodes on the network to replicate my content. However, I came up with a better solution: [one of my best friends](https://www.linkedin.com/in/sponnet/).

I asked him to "pin" my file on some of his IPFS nodes that are permanently connected to the internet. This way my webpage remains available even when my laptop disconnects from the internet.

<div class="large">
  [image blog/local-ipfs-node-3 resize=false]
</div>

<p class="pullquote">With a few friends pinning each other's websites on IPFS, you don't need to pay for web hosting anymore!</p>

#### Third-party IPFS and pinning services

If you don't want to run your own IPFS service, or you don't have friends who can replicate your data, you can use a third-party IPFS and pinning service.

I found a dozen pinning services, and tried the following:

- [Infura](https://infura.io/)
- [Fleek](https://fleek.co/)
- [Pinata](https://www.pinata.cloud/)

[Infura](https://infura.io/) makes it easy to upload files using their command line tool:

```shell
$ ipfs-upload-client --id xxx --secret yyy ./index.html
```

`xxx` is the Infura Project ID and `yyy` the Infura Project Secret Key.

[Fleek](%E2%80%8B%E2%80%8Bhttps://fleek.co/) and [Pinata](https://www.pinata.cloud/) allow you to upload files from your web browser:

<div class="large">
  [image blog/fleek-upload-form resize=false]
  [image blog/pinata-replication resize=false]
</div>

If you're looking for Filecoin-based solutions, [Web3.storage](https://Web3.storage/) comes recommended.

### Step 3: Visit your Web3 webpage

After uploading a file to IPFS, you get the "hash" (a unique ID or address) of the file. The hash of my `index.html` file is:

`bafybeibbkhmln7o4ud6an4qk6bukcpri7nhiwv6pz6ygslgtsrey2c3o3q`

Content hosted on IPFS can be accessed using an IPFS-compatible browser like [Brave](https://brave.com/). Firefox, Safari and Chrome don't currently support IPFS natively, but various IPFS browser extensions exist.

Using Brave, you can visit my webpage at <ipfs://bafybeibbkhmln7o4ud6an4qk6bukcpri7nhiwv6pz6ygslgtsrey2c3o3q> (note the `ipfs://` schema).

[image blog/brave-with-ipfs resize=false]

### Step 4: Map your webpage to your domain name

Being able to visit your IPFS-hosted website is pretty neat, but you're probably not going to ask other people to check out your new webpage at ipfs://bafybeibbkhmln7o4ud6an4qk6bukcpri7nhiwv6pz6ygslgtsrey2c3o3q. Using a 60-character hexadecimal hash isn't exactly ideal.

This is where ENS comes in. I just had to set the *Content Resolver* record of `dries.eth` to the IPFS hash associated with my webpage.

<div class="large">
  [image blog/ens-content-resolver resize=false]
</div>

Updating an ENS record permanently updates the state of the Ethereum blockchain. This means you have to pay a "gas fee", or a network transaction fee. As you can see on [Etherscan](https://etherscan.io), it cost me [0.004369 Ether](https://etherscan.io/tx/0x5d72594efe7b3cca99304ea9c01f3cc2ed2ed21f8f2915932b5bb53abce5bc77) ($11.69 at the time) to update my ENS record.

You can now use an ENS and IPFS compatible browser to visit <https://dries.eth>. Voila, a *truly* decentralized website!

[image blog/google-chrome-with-metamask resize=false]

### Are ENS and IPFS the future of the web?

There are various big shortcomings:

- **It only works with static sites.** Most organizations use dynamic websites such as those rendered by [Drupal](https://www.drupal.org/) or [WordPress](https://wordpress.org/). Of course, you can export simple Drupal sites (like this blog) to static HTML and upload those files to IPFS. But not all sites lend themselves to becoming static sites.
- **It is too costly for many.** Every time you make changes to your website, and you redeploy to IPFS, you generate a new hash. A new hash means updating your ENS record, and updating your ENS record means paying gas fees. This becomes expensive when you have to update your site frequently.
- **It is too slow for some.** Updating my ENS record was manual, requires approval of the transaction, and takes some time to settle on the blockchain. Not acceptable for news websites that need to get information out in real-time.
- **Lack of browser support.** Mainstream browsers still don't support ENS out-of-the-box. Until they do, Web3 feels like a parallel universe.

I'm sure these shortcomings will be addressed in the years ahead. Some might already have solutions.

Shortcomings aside, I believe IPFS and ENS hold promise:

- I prefer using the IPFS API over Amazon's proprietary S3 API. It makes my web applications more portable. Open Source protocols are preferred.
- The idea that these services are both permissionless and programmable is mind-blowing. For example, it makes me wonder if I could create a [smart contract](https://ethereum.org/en/smart-contracts/) that automatically pays miners around the world to keep my blog and photo albums online for the next 250+ years. I'd *love* to explore that in a future blog post.
- ENS feels like a really useful building block for resolving and verifying various things. A global key-value store has many potential use cases.

### What does Web3 mean for developers?

If you are a developer, think of Web3 as a growing collection of new "web services".

IPFS and ENS are two such web services. Today, they mainly provide improved resiliency and censorship protection. If resiliency and censorship protection are important for your website, use them. If they are not, you don't have to use them. As the owner and developer of <https://dri.es>, I don't care about censorship protection. For that reason, I'm happy to keep using traditional hosting technologies. But I do recognize that IPFS and ENS could become more interesting in the future.

<p class="pullquote">In its current state, IPFS and ENS offer limited value to most website owners, but tremendous value to a very narrow subset of all website owners. That could change in the future.</p>

### What is the promise of Web3?

I do think it is important to watch the Web3 space. New and powerful Web3 services will emerge. The internet's desire to eliminate intermediates has raged on for 20+ years. It is an unstoppable trend. With Web3, more intermediaries face risk of disintermediation and decentralization.

That includes organizations whose business model depends on proprietary databases and ledgers; financial institutions, central banks, certain non-profits, social communities. Many of these could turn into truly decentralized web services.

For example, many commerce websites offer loans and loan repayment programs using intermediaries like PayPal or Square. In time, some of these intermediaries could be replaced by permissionless, distributed web services that charge less interest and/or smaller transaction fees. Imagine the day it becomes really easy for commerce websites to offer loan repayment programs directly to their customers without an intermediary. When profit margins stand to benefit, technology solutions gets adopted quickly.

The blockchain will also enable us to solve coordination and ownership problems in new ways. Everyone who creates content on the web (images, music, videos, blog posts) could benefit from that. The ability for others to use your content, and for value to flow back to you programmatically is quite exciting.

Most of all, I'm hopeful that these decentralized services will help us advance how we govern public goods, [how we sustain Open Source projects](https://dri.es/balancing-makers-and-takers-to-scale-and-sustain-open-source), and how we can meaningfully shift power back from large organizations to individuals and communities. But that is the topic for a future blog post.

**February, 2024 update:** Two years have passed since I last engaged with my Web3 site. I decided to review its current state, expand on some points in this blog post, and explore Web3's progress in the context of website hosting. Read my update at [Two years later: is my Web3 website still standing?](https://dri.es/two-years-later-is-my-web3-website-still-standing).
