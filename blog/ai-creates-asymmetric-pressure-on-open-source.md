---
url: 'https://dri.es/ai-creates-asymmetric-pressure-on-open-source'
title: 'AI creates asymmetric pressure on Open Source'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2026-01-29T19:58:44-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'How Open Source communities can adapt to AI-generated contributions without overwhelming Open Source maintainers'
tags:
  - Drupal
  - 'Artificial Intelligence'
  - 'Open Source'
image: blog/asymmetric-ai-pressure
discussions:
  - { platform: Drupal.org, url: 'https://www.drupal.org/project/drupal/issues/3570498' }
  - { platform: LinkedIn, url: 'https://www.linkedin.com/posts/buytaert_drupal-curl-opensource-share-7422815639985324032-ShyE' }
published: true
featured: true
id: 6081
---

# AI creates asymmetric pressure on Open Source

[image blog/asymmetric-ai-pressure priority=high schema=false]

AI makes it cheaper to contribute to Open Source, but it's not making life easier for maintainers. More contributions are flowing in, but the burden of evaluating them still falls on the same small group of people. That asymmetric pressure risks breaking maintainers.

### The curl story

Daniel Stenberg, who maintains [curl](https://curl.se/), just [ended the curl project's bug bounty program](https://daniel.haxx.se/blog/2026/01/26/the-end-of-the-curl-bug-bounty/). The program had worked well for years. But in 2025, fewer than one in twenty submissions turned out to be real bugs.

In a post called ["Death by a thousand slops"](https://daniel.haxx.se/blog/2025/07/14/death-by-a-thousand-slops/), Stenberg described the toll on curl's seven-person security team: each report engaged three to four people, sometimes for hours, only to find nothing real. He wrote about the "emotional toll" of "mind-numbing stupidities".

Stenberg's response was pragmatic. He didn't ban AI. He ended the bug bounty. That alone removed most of the incentive to flood the project with low-quality reports.

Drupal doesn't have a bug bounty, but it still has incentives: contribution credit, reputation, and visibility all matter. Those incentives can attract low-quality contributions too, and the cost of sorting them out often lands on maintainers.

### Caught between two truths

We've seen some AI slop in Drupal, though not at the scale curl experienced. But our maintainers are stretched thin, and they see what is happening to other projects.

That tension shows up in conversations about AI in Drupal Core and can lead to indecision. For example, people hesitate around [AGENTS.md files](https://www.drupal.org/project/drupal/issues/3568936) and [adaptable modules](https://www.drupal.org/project/drupalorg/issues/3563839) because they worry about inviting more contributions without adding more capacity to evaluate them.

This is AI-driven asymmetric pressure in our community. I understand the hesitation. When we get this wrong, maintainers pay the price. They've earned the right to be skeptical.

Many also have concerns about AI itself: its environmental cost, its impact on their craft, and the unresolved legal and ethical questions around how it was trained. Others worry about security vulnerabilities slipping through. And for some, it's simply demoralizing to watch something they built with care become a target for high-volume, low-quality contributions. These concerns are legitimate and deserve to be heard.

As a result, I feel caught between two truths. 

On one side, maintainers hold everything together. If they burn out or leave, Drupal is in serious trouble. We can't ask them to absorb more work without first creating relief. 

On the other side, the people who depend on Drupal are watching other platforms accelerate. If we move too slowly, they'll look elsewhere. 

Both are true. Protecting maintainers and accelerating innovation shouldn't be opposites, but right now they feel that way. As Drupal's project lead, my job is to help us find a path that honors both.

I should be honest about where I stand. I've been [writing software with AI tools](https://dri.es/claude-code-meets-drupal) for over a year now. I've had real successes. I've also seen some of our most experienced contributors become dramatically more productive, doing things they simply couldn't do before. That view comes from experience, not hype.

But having a perspective is not the same as having all the answers. And leadership doesn't mean dragging people where they don't want to go. It means pointing a direction with care, staying open to different viewpoints, and not abandoning the people who hold the project together.

### We've sort of been here before

New technology has a way of lowering barriers, and lower barriers always come with tradeoffs. I saw this early in my career. I was writing low-level C for embedded systems by day, and after work I'd come home and work on websites with Drupal and PHP. It was thrilling, and a stark contrast to my day job. You could build in an evening what took days in C.

I remember that excitement. The early web coming alive. I hadn't felt the same excitement in 25 years, until AI.

PHP brought in hobbyists and self-taught developers, people learning as they went. Many of them built careers here. But it also meant that a lot of early PHP code had serious security problems. The language got blamed, and many experts dismissed it entirely. Some still do.

The answer wasn't rejecting PHP for enabling low-quality code. The answer was frameworks, better security practices, and shared standards.

AI is a different technology, but I see the same patterns. It lowers barriers and will bring in new contributors who aren't experts yet. And like scripting languages, AI is here to stay. The question isn't whether AI is coming to Open Source. It's how we make it work.

### AI in the right hands

The curl story doesn't end there. In October 2025, a researcher named Joshua Rogers used AI-powered code analysis tools to [submit hundreds of potential issues](https://daniel.haxx.se/blog/2025/10/10/a-new-breed-of-analyzers/). Stenberg was "amazed by the quality and insights". He and a fellow maintainer merged about 50 fixes from the initial batch alone.

Earlier this week, a security startup called AISLE [announced they had used AI to find 12 zero-days](https://www.lesswrong.com/posts/7aJwgbMEiKq5egQbd/ai-found-12-of-12-openssl-zero-days-while-curl-cancelled-its) in the latest OpenSSL security release. OpenSSL is one of the most scrutinized codebases on the planet. It encrypts most of the internet. Some of the bugs AISLE found had been hiding for over 25 years. They also reported over 30 valid security issues to curl.

The difference between this and the slop flooding Stenberg's inbox wasn't the use of AI. It was expertise and intent. Rogers and AISLE used AI to amplify deep knowledge. The low-quality reports used AI to replace expertise that wasn't there, chasing volume instead of insight.

AI created new burden for maintainers. But used well, it may also be part of the relief.

### Earn trust through results

I reached out to Daniel Stenberg this week to compare notes. He's navigating the same tensions inside the curl project, with maintainers who are skeptical, if not outright negative, toward AI.

His approach is simple. Rather than pushing tools on his team, he tests them on himself. He uses AI review tools on his own pull requests to understand their strengths and limits, and to show where they actually help. The goal is to find useful applications without forcing anyone else to adopt them.

The curl team does use AI-powered analyzers today because, as Stenberg puts it, "they have proven to find things no other analyzers do". The tools earned their place.

That is a model I'd like us to try in Drupal. Experiments should stay with willing contributors, and the burden of proof should remain with the experimenters. Nothing should become a new expectation for maintainers until it has demonstrated real, repeatable value.

That does not mean we should wait. If we want evidence instead of opinions, we have to create it. Contributors should experiment on their own work first. When something helps, show it. When something doesn't, share that too. We need honest results, not just positive ones. Maintainers don't have to adopt anything, but when someone shows up with real results, it's worth a look.

Not all low-quality contributions come from bad faith. Many contributors are learning, experimenting, and trying to help. They want what is best for Drupal. A welcoming environment means building the guidelines and culture to help them succeed, with or without AI, not making them afraid to try.

I believe AI tools are part of how we create relief. I also know that is a hard sell to someone already stretched thin, or dealing with AI slop, or wrestling with what AI means for their craft. The people we most want to help are often the most skeptical, and they have good reason to be.

I'm going to do my part. I'll seek out contributors who are experimenting with AI tools and share what they're learning, what works, what doesn't, and what surprises them. I'll try some of these tools myself before asking anyone else to. And I'll keep writing about what I find, including the failures.

If you're experimenting with AI tools, I'd love to hear about it. I've opened [an issue on Drupal.org](https://www.drupal.org/project/drupal/issues/3570498) to collect real-world experiences from contributors. Share what you're learning in the issue, or write about it on your own blog and link it there. I'll report back on what we learn on my blog or at DrupalCon.

### Protect your maintainers

This isn't just Drupal's challenge. Every large Open Source project is navigating the same tension between enthusiasm for AI and real concern about its impact.

But wherever this goes, one principle should guide us: protect your maintainers. They're a rare asset, hard to replace and easy to lose. Any path forward that burns them out isn't a path forward at all.

I believe Drupal will be stronger with AI tools, not weaker. I believe we can reduce maintainer burden rather than add to it. But getting there will take experimentation, honest results, and collaboration. That is the direction I want to point us in. Let's keep an open mind and let evidence and adoption speak for themselves.

*Thanks to [phenaproxima](https://www.drupal.org/u/phenaproxima), [Tim Lehnen](https://www.drupal.org/u/hestenet), [Gábor Hojtsy](https://www.drupal.org/u/g%C3%A1bor-hojtsy), [Scott Falconer](https://www.drupal.org/u/scott-falconer), [Théodore Biadala](https://www.drupal.org/u/nod_), [Jürgen Haas](https://www.drupal.org/u/jurgenhaas) and [Alex Bronstein](https://www.drupal.org/u/effulgentsia) for reviewing my draft.*

PS: Follow the discussion on [Drupal.org](https://www.drupal.org/project/drupal/issues/3570498) or [LinkedIn](https://www.linkedin.com/posts/buytaert_drupal-curl-opensource-share-7422815639985324032-ShyE).
