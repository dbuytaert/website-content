---
title: 'Nostr, love at first sight'
date: '2023-02-15T17:22:33-05:00'
author: Dries
summary: 'My initial impressions on Nostr, a head-to-head comparison of Nostr and Mastodon/ActivityPub, and how Zaps could revolutionize social media.'
image: blog/nostr
tags:
  - 'Social media'
  - 'Open Web'
  - Blockchain
published: true
type: blog
url: /nostr-love-at-first-sight
id: 5421
---

[image blog/nostr priority=true lazy=false]

I recently discovered [Nostr](https://github.com/nostr-protocol/nostr), a decentralized social network that I find exciting and promising.

Technically, Nostr is a protocol, not a social network. However, developers can use the Nostr protocol to create a variety of applications, including social networks.

Nostr has been around a few years, but in December 2022, [Jack Dorsey](https://en.wikipedia.org/wiki/Jack_Dorsey), the co-founder and former CEO of Twitter, announced that he had made [a donation of 14 bitcoins](https://twitter.com/jack/status/1603381913485541376), valued at approximately $250,000. The donation was made to 1, the anonymous founder of Nostr.

Nostr stands for *Notes and Other Stuff Transmitted by Relays*. At its core, it is a system to exchange signed messages. The basic architecture can be explained in three bullets:

- Every Nostr user is identified by a public key.
- Users send and retrieve messages to servers. These servers are called *relays*.
- Messages are called *events*. Users sign events with a private key. Events can be social media posts, private messages [chess moves](https://github.com/jesterui/jesterui), etc.

I reviewed the Nostr protocol and found it to be straightforward to understand. The [basic Nostr protocol](https://github.com/nostr-protocol/nips/blob/master/01.md) seems simple enough to implement in a day. This is a quality I appreciate in protocols. It is why I love RSS, for example.

While the core Nostr protocol is simple, it is very extensible. It is extended using [NIPs](https://github.com/nostr-protocol/nips), which stands for *Nostr Implementation Possibilities*. NIPs can add new fields and features to Nostr messages or events. For example, [NIP-2](https://github.com/nostr-protocol/nips/blob/master/02.md) adds usernames and contact lists (followers), [NIP-8](https://github.com/nostr-protocol/nips/blob/master/08.md) adds mentions, [NIP-36](https://github.com/nostr-protocol/nips/blob/master/36.md) adds support for content warnings, etc.

### Joining the Nostr social network

Despite Nostr being just a few years old, there are a [number of clients](https://github.com/aljazceru/awesome-nostr). I decided on [Damus](https://github.com/damus-io/damus), a Twitter-like Nostr client for iOS. (Nostr's Damus is a clever pun on Nostradamus, the French astrologer.)

You don't need to create a traditional account to sign up. You just use a public and private key. You can use these keys to use the platform anonymously. Unlike with proprietary social networks, you don't need an email address or phone number to register.

If you want, you can choose to verify your identity. Verifying your identity links your public key to a public profile. I verified my identity using [NIP-05](https://github.com/nostr-protocol/nips/blob/master/05.md), though different options exist. The NIP-05 verification process involved creating a static file on my website, available at <https://dri.es/.well-known/nostr.json>. It verifies that I'm the owner of the name `@Dries`, the public key `npub176xpl3dl0agjt7vjeccw6v5grlx8f9mhc75aazwvvqfjvq5al8uszj5asu` and [https://dri.es](https://dri.es/).

### Nostr versus ActivityPub

Recently, Elon Musk became the world's richest troll and many people have left Twitter for [Mastodon](https://en.wikipedia.org/wiki/Mastodon_(social_network)). Mastodon is a decentralized social media platform built on the [ActivityPub protocol](https://en.wikipedia.org/wiki/ActivityPub). I wanted to compare ActivityPub with Nostr, as Nostr offers many of the same promises.

Before I do, I want to stress that I am not an expert in either ActivityPub or Nostr. I have read both specifications, but I have not implemented a client myself. However, I do have a basic understanding of the differences between the two.

I also want to emphasize that both Nostr and ActivityPub are commendable for their efforts in addressing the problems encountered by traditional centralized social media platforms. I'm grateful for both.

ActivityPub has been around for longer, and is more mature, but by comparison, there is a lot more to like about Nostr:

- **Nostr is more decentralized** – Nostr uses a public key to identify users, while ActivityPub utilizes a more conventional user account system. ActivityPub user accounts are based on domain names, which can be controlled by third-party entities. Nostr's identification system is more decentralized, as it does not rely on domain names controlled by outside parties.
- **Nostr is easier to use** – Decentralized networks are notoriously tough to use. To gain mass adoption, the user experience of decentralized social networks needs to match and exceed that of proprietary social networks. Both Nostr and Mastodon have user experience problems that stem from being decentralized applications. That said, I found Nostr easier to use, and I believe it is because the Nostr architecture is simpler. 
   - Migrating to a different Mastodon server can be challenging, as your username is tied to the domain name of the current Mastodon server. However, this is not a problem in Nostr, as users are identified using a unique public key rather than a domain name.
   - Nostr doesn't currently offer the ability to edit or delete messages easily. While there is an API available to delete a message from a relay, it requires contacting each relay that holds a copy of your message to request its deletion, which can be challenging in practice.
- **Nostr makes it easier to select your preferred content policies** – Each Mastodon server or Nostr relay can have its own content policy. For example, you could have a Nostr relay that only lets verified users publish, does not allow content that has anything to do with violence, and conforms the local laws of Belgium. Being able to seamlessly switch servers or relays is very valuable because it allows user to choose a Mastodon server or Nostr relay that they align with. Unfortunately, migrating to a different Mastodon server, to opt into a different content policy, can be a challenging task.
- **Nostr is easier to develop for** – The Nostr protocol is easier to implement than the ActivityPub protocol, and appears more extensible.
- **Nostr has Zaps, which is potentially game-changing** – ActivityPub lacks an equivalent of Zaps, which could make it harder to address funding issues and combat spam. More on that in the next section.

Lastly, both protocols likely suffer from problems unique to decentralized architectures. For example, when you post a link to your site, most clients will try to render a preview card of that link. That preview card can contain an image, the title of the page, and a description. To create preview cards, the page is fetched and its HTML is parsed, looking for [Open Graph tags](https://ogp.me/). Because of the distributed nature of both Nostr and Mastodon this [can cause a site to get hammered with requests](https://odd.blog/2023/01/02/the-mastodon-onslaught-on-your-blog/).

### Zaps

Social networks are overrun with spam and bots. Ads are everywhere. Platform owners profit from content creators, and content creators themselves don't make money. The world needs some breakthrough in this regard, and Nostr's *Zap*-support might offer solutions.

A Zap is essentially a micropayment made using Bitcoin's Lightning network. Although Nostr itself does not use blockchain technology, it enables each message or event to contain a "Zap request" or "Zap invoice" (receipt). In other words, Nostr has optional blockchain integration for micropayment support.

The implementation of this protocol extension can be found in [NIP-57](https://github.com/nostr-protocol/nips/blob/master/57.md), which was finalized last week. As a brand new development, the potential of Zap-support has yet to be fully explored. But it is not hard to see how micropayments could be used to reward content creators, fund relay upkeep, or decrease spam on social media platforms. With micropayments supported at the protocol level, trying out and implementing new solutions has become simpler than ever before.

One potential solution is for receivers to require 200 satoshi (approximately $0.05) to receive a message from someone outside of their network. This would make spamming less economically attractive to marketers. Another option is for relays to charge their users a monthly fee, which could be used to maintain a block-list or content policy.

Personally, I am a big fan of rewarding content creators, financing contributions, and implementing anti-spam techniques. It aligns with my interest in [public good governance and sustainability](https://dri.es/balancing-makers-and-takers-to-scale-and-sustain-open-source).

For the record, I have mixed feelings about blockchains. I've [HODL'd Bitcoin since 2013](https://dri.es/i-bought-some-bitcoin-and-here-is-why) and Ethereum since 2017. On one hand, I appreciate the opportunities and innovation they offer, but on the other hand, I am deeply concerned about their energy consumption and contribution to climate change.

It's worth noting that the Lightning network is much more energy efficient than Bitcoin. Lightning operates on top of the Bitcoin network. The main Bitcoin blockchain, known as a layer 1 blockchain, is very energy inefficient and can only handle fewer than 10 transactions per second. In contrast, the [Lightning Network](https://en.wikipedia.org/wiki/Lightning_Network), known as a layer 2 network, uses a lot less energy and has the potential to handle millions of transactions per second on top of the Bitcoin network.

So, yes, Zap support is an important development to pay attention to. Even though it's brand new, I believe that in five years, we'll look back and agree that Zap support was a game-changer.

### Conclusions

"Notes and Other Stuff, Transmitted by Relays" seems like a promising idea, even at this early stage. It is definitely something to keep an eye on. While for me it was love at first sight, I'm not sure how it will evolve. I am interested in exploring it further, and if time permits, I plan to create some basic integration with my own Drupal site.

<p>
  <a href="https://news.indieweb.org/en" class="u-syndication">Also posted on IndieNews</a>.</p>
