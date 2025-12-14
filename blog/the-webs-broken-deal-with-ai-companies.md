---
title: "The web's broken deal with AI companies"
date: '2025-07-01T10:40:58-04:00'
author: Dries
summary: "AI companies are breaking the web's economic model by extracting content without compensating creators, but new enforcement tools and content licensing marketplaces could restore fair compensation."
image: blog/cloudflare-vs-crawlers
tags:
  - 'Open Web'
  - 'Artificial Intelligence'
featured: false
published: true
type: blog
url: /the-webs-broken-deal-with-ai-companies
id: 5836
---

[image blog/cloudflare-vs-crawlers lazy=false priority=true]

AI is rewriting the rules of how we work and create. Expert developers can now build faster, non-developers can build software, research is accelerating, and human communication is improving. In the next 10 years, we'll probably see a 1,000x increase in AI demand. That is why [Drupal is investing heavily in AI](https://dri.es/accelerating-ai-innovation-in-drupal).

But at the same time, AI companies are breaking the web's fundamental economic model. This problem demands our attention.

### The AI extraction problem

For 25 years, we built the [Open Web](https://dri.es/tag/open-web) on an implicit agreement: search engines could index our content because they sent users back to our websites. That model helped sustain blogs, news sites, and even open source projects.

AI companies broke that model. They train on our work and answer questions directly in their own interfaces, cutting creators out entirely. Anthropic's crawler reportedly makes [70,000 website requests for every single visitor it sends back](https://blog.cloudflare.com/ai-search-crawl-refer-ratio-on-radar/). That is extraction, not exchange.

This is the [Makers and Takers problem](https://dri.es/balancing-makers-and-takers-to-scale-and-sustain-open-source) all over again.

The damage is real:
- [Chegg](https://www.chegg.com/), an online learning platform, [filed an antitrust lawsuit against Google](https://www.reuters.com/legal/googles-ai-previews-erode-internet-edtech-company-says-lawsuit-2025-02-24/), claiming that AI-powered search answers have crushed their website traffic and revenue.
- [Stack Overflow](https://stackoverflow.com/) has seen a significant drop in daily active users and new questions (about 25-50%), as more developers turn to ChatGPT for faster answers.
- I recently spoke with a recipe blogger who is a solo entrepreneur. With fewer visitors, they're earning less from advertising. They poured their heart, craft, and sweat into creating a high-quality recipe website, but now they believe their small business won't survive.

None of this should surprise us. According to [Similarweb](https://www.similarweb.com/corp/reports/generative-ai-publishers/), since Google launched "AI Overviews", the number of searches that result in no click-throughs has increased from 56% in May 2024 to 69% in May 2025, meaning users get their answers directly on the results page. 

This "zero-click" phenomenon reinforces the shift I described in my 2015 post, ["The Big Reverse of the Web"](https://dri.es/the-big-reverse-of-the-web). Ten years ago, I argued that the web was moving away from sending visitors out to independent sites and instead keeping them on centralized platforms, all in the name of providing a faster and more seamless user experience.

However, the picture isn't entirely negative. Some companies find that visitors from AI tools, while small in volume, convert at much higher rates. At [Acquia](https://www.acquia.com/), the company I co-founded, traffic from AI chatbots makes up less than 1 percent of total visitors but converts at over 6 percent, compared to typical rates of 2 to 3 percent. We are still relatively early in the AI adoption cycle, so time will tell how this trend evolves, how marketers adapt, and what new opportunities it might create.

### Finding a new equilibrium

There is a reason this trend has taken hold: users love it. AI-generated answers provide instant, direct information without extra clicks. It makes traditional search engines look complicated by comparison.

But this improved user experience comes at a long-term cost. When value is extracted without supporting the websites and authors behind it, it threatens the sustainability of the content we all rely on.

I fully support improving the user experience. That should always come first. But it also needs to be balanced with fair support for creators and the Open Web.

We should design systems that share value more fairly among users, AI companies, and creators. We need a new equilibrium that sustains creative work, preserves the Open Web, and still delivers the seamless experiences users expect.

Some might worry it is already too late, since large AI companies have massive scraped datasets and can generate [synthetic data](https://en.wikipedia.org/wiki/Synthetic_data) to fill gaps. But I'm not so sure. The web will keep evolving for decades, and no model can stay truly relevant without fresh, high-quality content.

### From voluntary rules to enforcement

We have [`robots.txt`](https://en.wikipedia.org/wiki/Robots.txt), a simple text file that tells crawlers which parts of a website they can access. But it's purely voluntary. [Creative Commons](https://creativecommons.org) launched [CC Signals](https://creativecommons.org/2025/06/25/introducing-cc-signals-a-new-social-contract-for-the-age-of-ai/) last week, allowing content creators to signal how AI can reuse their work. But both `robots.txt` and CC Signals are "social contracts" that are hard to enforce.

Today, Cloudflare announced [they will default to blocking AI crawlers from accessing content](https://blog.cloudflare.com/content-independence-day-no-ai-crawl-without-compensation/). This change lets website owners decide whether to allow access and whether to negotiate compensation. [Cloudflare](https://www.cloudflare.com/) handles 20% of all web traffic. When an AI crawler tries to access a website protected by Cloudflare, it must pass through Cloudflare's servers first. This allows Cloudflare to detect crawlers that ignore `robots.txt` directives and block them.

This marks a shift from purely voluntary signals to actual technical enforcement. Large sites could already afford their own infrastructure to detect and block crawlers or negotiate licensing deals directly. For example, [Reddit signed a $60 million annual deal with Google](https://www.reuters.com/technology/reddit-ai-content-licensing-deal-with-google-sources-say-2024-02-22/) to license its content for AI training.

However, most content creators, like you and I, can do neither.

Cloudflare's actions establish a crucial principle: AI training data has a price, and creators deserve to share in the value AI generates from their work.

### The missing piece: content licensing marketplaces

Accessible enforcement infrastructure is step one, and Cloudflare now provides that. Step two would be a content licensing marketplace that helps broker deals between AI companies and content creators at any scale. This would move us from simply blocking to creating a fair economic exchange.

To the best of my knowledge, such marketplaces do not exist yet, but the building blocks are starting to emerge. Matthew Prince, CEO of Cloudflare, has hinted that Cloudflare may be working on building such a marketplace, and I think it is a great idea.

I don't know what that will look like, but I imagine something like [Shutterstock](https://www.shutterstock.com) for AI training data, combined with programmatic pricing like [Google Ads](https://ads.google.com). On Shutterstock, photographers upload images, set licensing terms, and earn money when companies license their photos. Google Ads automatically prices and places millions of ads without manual negotiations. A future content licensing marketplace could work in a similar way: creators would set licensing terms (like they do on Shutterstock), while automated systems manage pricing and transactions (as Google Ads does).

Today, only large platforms like Reddit can negotiate direct licensing deals with AI companies. A marketplace with programmatic pricing would make licensing accessible to creators of all sizes. Instead of relying on manual negotiations or being scraped for free, creators could opt into fair, programmatic licensing programs.

This would transform the dynamic from adversarial blocking to collaborative value creation. Creators get compensated. AI companies get legal, high-quality training data. Users benefit from better AI tools built on ethically sourced content.

### Making the Open Web sustainable

We built the [Open Web](https://dri.es/tag/open-web) to democratize access to knowledge and online publishing. AI advances this mission of democratizing knowledge. But we also need to ensure the people who write, record, code, and share that knowledge aren't left behind.

The issue is not that AI exists. The problem is that we have not built economic systems to support the people and organizations that AI relies on. This affects independent bloggers, large media companies, and open source maintainers whose code and documentation train coding assistants.

Call me naive, but I believe AI companies want to work with content creators to solve this. Their challenge is that no scalable system exists to identify, contact, and pay millions of content creators.

Content creators lack tools to manage and monetize their rights. AI companies lack systems to discover and license content at scale. Cloudflare's move is a first step. The next step is building content licensing marketplaces that connect creators directly with AI companies.

The Open Web needs economic systems that sustain the people who create its content. There is a unique opportunity here: if content creators and AI companies build these systems together, we could create a stronger, more fair, and more resilient Web than we have had in 25 years. The jury is out on that, but one can dream.

*Disclaimer: [Acquia](https://www.acquia.com/), my company, has a commercial relationship with [Cloudflare](https://www.cloudflare.com/), but this perspective reflects my long-standing views on sustainable web economics, not any recent briefings or partnerships.*
