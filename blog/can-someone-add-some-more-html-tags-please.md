---
title: 'Can someone add some more HTML tags, please?'
date: '2021-01-06T04:39:12-05:00'
author: Dries
image: blog/wikipedia-timbl-markup
tags:
  - 'Semantic web'
featured: true
published: true
type: blog
url: /can-someone-add-some-more-html-tags-please
id: 5126
---

Every day, millions of new web pages are added to the internet. Most of them are unstructured, uncategorized, and nearly impossible for software to understand. It irks me.

Look no further than [Sir Tim Berners-Lee's Wikipedia page](https://en.wikipedia.org/wiki/Tim_Berners-Lee):

<div class="side-by-side">
  [image blog/wikipedia-timbl-markup resize=false]
  [image blog/wikipedia-timbl-page resize=false]
</div>

At first glance, there is [no rhyme or reason to Wikipedia's markup](http://blog.spencermounta.in/2019/wikipedias-in-trouble/index.html). (Wikipedia also has [custom markup for hieroglyphs](https://en.wikipedia.org/wiki/Help:WikiHiero_syntax), which admittedly *is* pretty cool.)

The problem? Wikipedia is the world's largest source of knowledge. It's a top 10 website in the world. Yet, Wikipedia's markup language is [nearly impossible to parse](http://blog.spencermounta.in/2019/wikipedias-in-trouble/index.html), Tim Berners-Lee's Wikipedia page has [almost 100 HTML validation errors](https://validator.w3.org/nu/?doc=https%3A%2F%2Fen.wikipedia.org%2Fwiki%2FTim_Berners-Lee), and the page's generated HTML output is not very semantic. It's hard to use or re-use with other software.

I bet it irks Sir Tim Berners-Lee too.

<div class="side-by-side">
  [image blog/wikipedia-timbl-markup resize=false]
  [image blog/wikipedia-timbl-html resize=false]
</div>

It's not just Wikipedia. Every site is still messing around with custom `<div>`s for a table of contents, footnotes, logos, and more. I could think of a dozen new HTML tags that would make web pages, including Wikipedia, easier to write and reuse: `<footnote>`, `<logo>`, `<place>`, and many more.

A good approach would be to take the most successful [Schema.org schemas](https://en.wikipedia.org/wiki/Schema.org), [Microformats](http://microformats.org/) and [Web Components](https://en.wikipedia.org/wiki/Web_Components), and incorporate their functionality into the [official HTML specification](https://html.spec.whatwg.org/).

<p class="pullquote">Adding new semantic markup options to the HTML specification is the surest way to improve the semantic web, improve content reuse, and advance content authoring tools.</p>

Unfortunately, I don't see new tags being introduced. I don't see experiments with [Web Components](https://en.wikipedia.org/wiki/Web_Components) being promoted to official standards. I hope I'm wrong! ([Cunningham's Law](https://meta.wikimedia.org/wiki/Cunningham%27s_Law) states that <q>the best way to get the right answer on the internet is not to ask a question; it's to post the wrong answer</q>. If I'm wrong, I'll update this post.)

If you want to help make the web better, you could literally start with [Sir Tim Berners-Lee's Wikipedia page](https://en.wikipedia.org/wiki/Tim_Berners-Lee), and use it as the basis to spend a decade [pushing for HTML markup improvements](https://github.com/whatwg/html/commits). It could be the [start of a long and successful career](http://1997.webhistory.org/www.lists/www-talk.1993q1/0182.html).
