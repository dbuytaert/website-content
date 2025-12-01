---
title: 'Two years later: is my Web3 website still standing?'
date: '2024-02-29T10:06:36-05:00'
author: Dries
summary: "After two years of neglecting my Web3 site, does it still work? Plus, insights into Web3's progress for website hosting."
image: blog/web3-exploration
tags:
  - Web3
  - Blockchain
  - 'My site'
  - Drupal
featured: true
published: true
type: blog
url: /two-years-later-is-my-web3-website-still-standing
id: 5576
---

[image blog/web3-exploration schema=false]

Two years ago, [I launched a simple Web3 website](https://dri.es/my-first-web3-webpage) using [IPFS](https://ipfs.io/) (InterPlanetary File System) and [ENS](https://ens.domains/) (Ethereum Name Service). Back then, Web3 tools were getting a lot of media attention and I wanted to try it out.

Since I set up my Web3 website two years ago, I basically forgot about it. I didn't update it or pay attention to it for two years. But now that we hit the two-year mark, I'm curious: is my Web3 website still online?

At that time, I also stated that Web3 was not fit for hosting modern web applications, except for a small niche: static sites requiring high resilience and infrequent content updates.

I was also curious to explore the evolution of Web3 technologies to see if they became more applicable for website hosting.

### My original Web3 experiment

In my original blog post, I documented the process of setting up what could be called the "Hello World" of Web3 hosting. I stored an HTML file on IPFS, ensured its availability using "pinning services", and made it accessible using an ENS domain.

For those with a basic understanding of Web3, here is a summary of the steps I took to launch my first Web3 website two years ago:

1. **Purchased an ENS domain name:** I used a crypto wallet with Ethereum to acquire `dries.eth` through the [Ethereum Name Service](https://ens.domains/), a decentralized alternative to the traditional DNS (Domain Name System).
2. **Uploaded an HTML File to IPFS:** I uploaded a static HTML page to the [InterPlanetary File System](https://ipfs.io/) (IPFS), which involved running my own IPFS node and utilizing various pinning services like [Infura](https://infura.io/), [Fleek](https://fleek.co/), and [Pinata](https://pinata.cloud/). These pinning services ensure that the content remains available online even when my own IPFS node is offline.
3. **Accessed the website:** I confirmed that my website was accessible through IPFS-compatible browsers.
4. **Mapped my webpage to my domain name:** As the last step, I linked my IPFS-hosted site to my ENS domain `dries.eth`, making the web page accessible under an easy domain name.

If the four steps above are confusing to you, I recommend reading [my original post](https://dri.es/my-first-web3-webpage). It is over 2,000 words, complete with screenshots and detailed explanations of the steps above.

### Checking the pulse of various Web3 services

As the first step in my check-up, I wanted to verify if the various services I referenced in my original blog post are still operational.

The results, displayed in the table below, are really encouraging: Ethereum, ENS, IPFS, Filecoin, Infura, Fleek, Pinata, and web3.storage are all operational.

The two main technologies – ENS and IPFS – are both actively maintained and developed. This indicates that Web3 technology has built a robust foundation.

<table>
  <tr>
  <th>Service</th>
  <th>Description</th>
  <th>Still around in February 2024)</th>
</tr>
  <tr>
  <td>
   <a href="https://ens.domains/">ENS</a>
 </td>
  <td>A blockchain-based naming protocol offering DNS for Web3, mapping domain names to Ethereum addresses.</td>
  <td>Yes</td>
</tr>
  <tr>
  <td>
   <a href="https://ipfs.io/">IPFS</a>
 </td>
  <td>A peer-to-peer protocol for storing and sharing data in a distributed file system.</td>
  <td>Yes</td>
</tr>
  <tr>
  <td>
   <a href="https://filecoin.io/">Filecoin</a>
 </td>
  <td>A blockchain-based storage network and cryptocurrency that incentivizes data storage and replication.</td>
  <td>Yes</td>
</tr>
  <tr>
  <td>
   <a href="https://infura.io/">Infura</a>
 </td>
  <td>Provides tools and infrastructure to manage content on IPFS and other tools for developers to connect their applications to blockchain networks and deploy smart contracts.</td>
  <td>Yes</td>
</tr>
  <tr>
  <td>
   <a href="https://fleek.co/">Fleek</a>
 </td>
  <td>A platform for building websites using IPFS and ENS.</td>
  <td>Yes</td>
</tr>
  <tr>
  <td>
   <a href="https://pinata.cloud/">Pinata</a>
 </td>
  <td>Provides tools and infrastructure to manage content on IPFS, and more recently <a href="https://www.farcaster.xyz/">Farcaster</a> applications.</td>
  <td>Yes</td>
</tr>
  <tr>
  <td>
   <a href="https://web3.storage/">web3.storage</a>
 </td>
  <td>Provides tools and infrastructure to manage content on IPFS with support for Filecoin.</td>
  <td>Yes</td>
</tr>
</table>

### Is my Web3 website still up?

Seeing all these Web3 services operational is encouraging, but the ultimate test is to check if my Web3 webpage, `dries.eth`, remained live. It's one thing for these services to work, but another for my site to function properly. Here is what I found in a detailed examination:

1. **Domain ownership verification:** A quick check on [etherscan.io](https://etherscan.io/name-lookup-search?id=dries.eth) confirmed that `dries.eth` is still registered to me. Relief!
2. **ENS registrar access:** Using my crypto wallet, I could easily log into the ENS registrar and manage my domains. I even successfully renewed `dries.eth` as a test.
3. **IPFS content availability:** My webpage is still available on IPFS, thanks to having pinned it two years ago. Logging into [Fleek](https://fleek.co/) and [Pinata](https://pinata.cloud/), I found my content on their admin dashboards.
4. **Web3 and ENS gateway access:** I can visit `dries.eth` using a Web3 browser, and also via an IPFS-compatible ENS gateway like <https://dries.eth.limo/> – a privacy-centric service, new since my initial blog post.

The verdict? Not only are these Web3 services still operational, but my webpage also continues to work!

This is particularly noteworthy given that I haven't logged in to these services, didn't perform any maintenance, or didn't pay any hosting fees for two years (the pinning services I'm using have a free tier).

### Visit my Web3 page yourself

For anyone interested in visiting my Web3 page (perhaps your first Web3 visit?), there are several methods to choose from, each with a different level of Web3-ness.

- **Use a Web3-enabled browser:** Browsers such as [Brave](https://brave.com/) and [Opera](https://www.opera.com/), offer built-in ENS and IPFS support. They can resolve ENS addresses and interpret IPFS addresses, making it as easy to navigate IPFS content as if it is traditional web content via HTTP or HTTPS.
- **Install a Web3 browser extension:** If your favorite browser does not support Web3 out of the box, adding a browser extension like [MetaMask](https://metamask.io/) can help you access Web3 applications. MetaMask works with Chrome, Firefox, and Edge. It enables you to use `.eth` domains for doing Ethereum transactions or for accessing content on IPFS.
- **Access through an ENS gateway:** For those looking for the simplest way to access Web3 content without installing anything new, using an ENS gateway, such as [eth.limo](https://eth.limo/), is the easiest method. This gateway maps ENS domains to DNS, offering direct navigation to Web3 sites like mine at <https://dries.eth.limo/>. It serves as a simple bridge between Web2 (the conventional web) and Web3.

### Streamlining content updates with IPNS

In [my original post](https://dri.es/my-first-web3-webpage), I highlighted various challenges, such as the limitations for hosting dynamic applications, the cost of updates, and the slow speed of these updates. Although these issues still exist, my initial analysis was conducted with an incomplete understanding of the available technology. I want to delve deeper into these limitations, and refine my previous statements.

Some of these challenges stem from the fact that IPFS operates as a "content-addressed network". Unlike traditional systems that use URLs or file paths to locate content, IPFS uses a unique hash of the content itself. This hash is used to locate and verify the content, but also to facilitate decentralized storage.

While the principle of addressing content by a hash is super interesting, it also introduces some complications: whenever content is updated, its hash changes, making it tricky to link to the updated content. Specifically, every time I updated my Web3 site's content, I had to update my ENS record, and pay a translation fee on the Ethereum network.

At the time, I wasn't familiar with the [InterPlanetary Name System](https://docs.ipfs.tech/concepts/ipns/) (IPNS). IPNS, not to be confused with IPFS, addresses this challenge by assigning a mutable name to content on IPFS. You can think of IPNS as providing an "alias" or "redirect" for IPFS addresses: the IPNS address always stays the same and points to the latest IPFS address. It effectively eliminates the necessity of updating ENS records with each content change, cutting down on expenses and making the update process more automated and efficient.

To leverage IPNS, you have to take the following steps:

1. Upload your HTML file to IPFS and receive an IPFS hash.
2. Publish this hash to IPNS, creating an IPNS hash that directs to the latest IPFS hash.
3. Link your ENS domain to this IPNS hash. Since the IPNS hash remains constant, you only need to update your ENS record once.

Without IPNS, updating content involved:

1. Update the HTML file.
2. Upload the revised file to IPFS, generating a new IPFS hash.
3. Update the ENS record with the new IPFS hash, which costs some Ether and can take a few minutes.

With IPNS, updating content involves:

1. Update the HTML file.
2. Upload the revised file to IPFS, generating a new IPFS hash.
3. Update the IPNS record to reference this new hash, which is free and almost instant.

Although IPNS is a faster and more cost-effective approach compared to the original method, it still carries a level of complexity. There is also a minor runtime delay due to the extra redirection step. However, I believe this tradeoff is worth it.

### Updating my Web3 site to use IPNS

With this newfound knowledge, I decided to use IPNS for my own site. I generated an IPNS hash using both the IPFS desktop application (see screenshot) and IPFS' command line tools:

```shell
$ ipfs name publish /ipfs/bafybeibbkhmln7o4ud6an4qk6bukcpri7nhiwv6pz6ygslgtsrey2c3o3q
> Published to k51qzi5uqu5dgy8mzjtcqvgr388xjc58fwprededbb1fisq1kvl34sy4h2qu1a: /ipfs/bafybeibbkhmln7o4ud6an4qk6bukcpri7nhiwv6pz6ygslgtsrey2c3o3q
```

[image blog/publish-to-ipns-from-ipfs-desktop resize=false schema=false]

After generating the IPNS hash, I was able to visit my site in Brave using the IPFS protocol at `ipfs://bafybeibbkhmln7o4ud6an4qk6bukcpri7nhiwv6pz6ygslgtsrey2c3o3q`, or via the IPNS protocol at `ipns://k51qzi5uqu5dgy8mzjtcqvgr388xjc58fwprededbb1fisq1kvl34sy4h2qu1a`.

[image blog/brave-ipns resize=false schema=false]

Next, I updated the ENS record for `dries.eth` to link to my IPNS hash. This change cost me 0.0011 ETH (currently $4.08 USD), as shown in the [Etherscan transaction](https://etherscan.io/tx/0xfc8be3add432e7440478897726eced850087cb8a1f79dcdeb926e575c31e3f8c). Once the transaction was processed, `dries.eth` began directing to the new IPNS address.

[image blog/ipns-record-on-ethereum-name-service resize=false schema=false]

### Rolling back my IPNS record in ENS

Unfortunately, my excitement was short-lived. A day later, `dries.eth` stopped working. IPNS records, it turns out, need to be kept alive – a lesson learned the hard way.

While IPFS content can be persisted through "pinning", IPNS records require periodic "republishing" to remain active. Essentially, the network's Distributed Hash Table (DHT) may drop IPNS records after a certain amount of time, typically 24 hours. To prevent an IPNS record from being dropped, the owner must "republish" it before the DHT forgets it.

I found out that the pinning services I use – [Dolphin](https://dolphin.io), [Fleek](https://fleek.co) and [Pinata](https://pinata.cloud) – don't support IPNS republishing. Looking into it further, it turns out few IPFS providers do.

During my research, I discovered [Filebase](https://filebase.com), a small Boston-based company with fewer than five employees that I hadn't come across before. Interestingly, they provide both IPFS pinning and IPNS republishing. However, to pin my existing HTML file and republish its IPNS hash, I had to subscribe to their service at a cost of $20 per month.

Faced with the challenge of keeping my IPNS hash active, I found myself at a crossroads: either fork out $20 a month for a service like Filebase that handles IPNS republishing for me, or take on the responsibility of running my own IPFS node.

Of course, the whole point of decentralized storage is that people run their own nodes. However, considering the scope of my project – a single HTML file – the effort of running a dedicated node seemed disproportionate. I'm also running my IPFS node on my personal laptop, which is not always online. Maybe one day I'll try setting up a dedicated IPFS node on a Raspberry Pi or similar setup.

Ultimately, I decided to switch my ENS record back to the original IPFS link. This change, documented in the [Etherscan transaction](https://etherscan.io/tx/0xb2d68b8244daa4412c8a04d13c66c8705cdeb2233c8f219486c14225ac90440a), cost me 0.002 ETH (currently $6.88 USD).

Although IPNS works, or can work, it just didn't work for me. Despite the setback, the whole experience was a great learning journey.

### Web3 remains too complex for most people

Over the past two years, Web3 hosting hasn't disrupted the mainstream website hosting market. Despite the allure of Web3, mainstream website hosting is simple, reliable, and meets the needs of nearly all users.

Despite a significant upgrade of the Ethereum network that [reduced energy consumption by over 99%](https://ethereum.org/en/energy-consumption/) through its transition to a Proof of Stake (PoS) consensus mechanism, environmental considerations, especially the carbon footprint associated with blockchain technologies, continue to create further challenges for the widespread adoption of Web3 technologies. (Note: ENS operates on the blockchain but IPFS does not.)

As I went through the check-up, I discovered islands of innovation and progress. Wallets and ENS domains got easier to use. However, the overall process of creating a basic website with IPFS and ENS remains relatively complex compared to the simplicity of Web2 hosting.

### The need for a SQL-compatible Web3 database

Modern web applications like those built with [Drupal](https://www.drupal.org/) and [WordPress](https://wordpress.org/) rely on a technology stack that includes a file system, a domain name system (e.g. DNS), a database (e.g. MariaDB or MySQL), and a server-side runtime environment (e.g. PHP).

While IPFS and ENS offer decentralized alternatives for the first two, the equivalents for databases and runtime environments are less mature. This limits the types of applications that can easily move from Web2 to Web3.

A major breakthrough would be the development of a decentralized database that is compatible with SQL, but currently, this does not seem to exist. The complexity of ensuring data integrity and confidentiality across multiple nodes without a central authority, along with meeting the throughput demands of modern web applications, may be too complex to solve.

After all, blockchains, as decentralized databases, have been in development for over a decade, yet lack support for the SQL language and fall short in speed and efficiency required for dynamic websites.

### The need for a distributed runtime

Another critical component for modern websites is the runtime environment, which executes the server-side logic of web applications. Traditionally, this has been the domain of PHP, Python, Node.js, Java, etc.

[WebAssembly](https://en.wikipedia.org/wiki/WebAssembly) (WASM) could emerge as a potential solution. It could make for an interesting decentralized solution as WASM binaries can be hosted on IPFS.

However, when WASM runs on the client-side – i.e. in the browser – it can't deliver the full capabilities of a server-side environment. This limitation makes it challenging to fully replicate traditional web applications.

So for now, Web3's applications are quite limited. While it's possible to host static websites on IPFS, dynamic applications requiring database interactions and server-side processing are difficult to transition to Web3.

### Bridging the gap between Web2 and Web3

In the short term, the most likely path forward is blending decentralized and traditional technologies. For example, a website could store its static files on IPFS while relying on traditional Web2 solutions for its dynamic features.

Looking to the future, initiatives like [OrbitDB's peer-to-peer database](https://orbitdb.org/), which integrates with IPFS, show promise. However, OrbitDB lacks compatibility with SQL, meaning applications would need to be redesigned rather than simply transferred.

### Web3 site hosting remains niche

Even the task of hosting static websites, which don't need a database or server-side processing, is relatively niche within the Web3 ecosystem.

As I wrote in [my original post](https://dri.es/my-first-web3-webpage): <q>In its current state, IPFS and ENS offer limited value to most website owners, but tremendous value to a very narrow subset of all website owners.</q>. This observation remains accurate today.

IPFS and ENS stand out for their strengths in censorship resistance and reliability. However, for the majority of users, the convenience and adequacy of Web2 for hosting static sites often outweigh these benefits.

The key to broader acceptance of new technologies, like Web3, hinges on either discovering new mass-market use cases or significantly enhancing the user experience for existing ones. Web3 has not found a universal application or surpassed Web2 in user experience.

The popularity of SaaS platforms underscores this point. They dominate not because they're the most resilient or robust options, but because they're the most convenient. Despite the benefits of resilience and autonomy offered by Web3, most individuals opt for less resilient but more convenient SaaS solutions.

### Conclusion

Despite the billions invested in Web3 and notable progress, its use for website hosting still has significant limitations.

The main challenge for the Web3 community is to either develop new, broadly appealing applications or significantly improve the usability of existing technologies.

Website hosting falls into the category of existing use cases.

Unfortunately, Web3 remains mostly limited to static websites, as it does not yet offer robust alternatives to SQL databases and server-side runtime.

Even within the limited scope of static websites, improvements to the user experience have been marginal, focused on individual parts of the technology stack. The overall end-to-end experience remains complex.

Nonetheless, the fact that my Web3 page is still up and running after two years is encouraging, showing the robustness of the underlying technology, even if its current use remains limited. I've grown quite fond of IPFS, and I hope to do more useful experiments with it in the future.

All things considered, I don't see Web3 taking the website hosting world by storm any time soon. That said, over time, Web3 could become significantly more attractive and functional. All in all, keeping an eye on this space is definitely fun and worthwhile.
