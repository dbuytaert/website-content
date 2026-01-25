---
url: 'https://dri.es/switching-to-markdown-after-20-years-of-html'
title: 'Switching to Markdown after 20 years of HTML'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2025-08-20T07:33:13-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
  - 'My site'
  - Writing
  - Markdown
published: true
featured: false
id: 5871
---

# Switching to Markdown after 20 years of HTML

After nearly two decades and over 1,600 blog posts written in raw HTML, I've made a change that feels long overdue: I've switched to [Markdown](https://en.wikipedia.org/wiki/Markdown).

Don't worry, I'm not moving away from [Drupal](https://www.drupal.org/). I'm just moving from a "HTML text format" to a "Markdown format". My last five posts have all been written in Markdown.

I've actually written in Markdown for years. I started with [Bear](https://bear.app/) for note-taking, and for the past four years [Obsidian](https://obsidian.md) has been my go-to tool. Until recently, though, I've always published my blog posts in HTML.

For almost 20 years, I wrote every blog post in raw HTML, typing out every tag by hand. For longer posts, it could take me 45 minutes wrapping everything in `<p>` tags, adding links, and closing HTML tags like it was still 2001. It was tedious, but also a little meditative. I stuck with it, partly out of pride and partly out of habit.

### Getting Markdown working in Drupal

So when I decided to make the switch, I had to figure out how to get Markdown working in [Drupal](https://www.drupal.org/). Drupal has multiple great Markdown modules to choose from but I picked [Markdown Easy](https://www.drupal.org/project/markdown_easy) because it's lightweight, fully tested, and built on the popular [CommonMark](https://commonmark.org/) library.

I documented my installation and upgrade steps in a [public note](https://dri.es/if-a-note-can-be-public-it-should-be) titled [*Installing and configuring Markdown Easy for Drupal*](https://dri.es/installing-and-configuring-markdown-easy-for-drupal).

I ran into one problem: the module's security-first approach stripped all HTML tags from my posts. This was an issue because I mostly write in Markdown but occasionally mix in HTML for things Markdown doesn't support, like custom styling. One example is creating pull quotes with a custom CSS class:

```markdown
After 20 years of writing in HTML, I switched to *Markdown*.

<p class="pullquote">HTML for 20 years. Markdown from now on.</p>

Now I can publish faster while still using [Drupal](https://drupal.org).
```

### HTML in Markdown by design

Markdown was always meant to work hand in hand with HTML, and Markdown parsers are supposed to leave HTML tags untouched. [John Gruber](https://daringfireball.net/), the creator of Markdown, makes this clear in the [original Markdown specification](https://daringfireball.net/projects/markdown/syntax):

> HTML is a publishing format; Markdown is a writing format. Thus, Markdown's formatting syntax only addresses issues that can be conveyed in plain text. [...] For any markup that is not covered by Markdown's syntax, you simply use HTML itself. There is no need to preface it or delimit it to indicate that you're switching from Markdown to HTML; you just use the tags.

In Markdown Easy 1.x, allowing HTML tags required writing a custom Drupal module with a specific "hook" implementation. This felt like too much work for something that should be a simple configuration option. I've never enjoyed writing and maintaining custom Drupal modules for cases like this.

I reached out to [Mike Anello](https://www.drupal.org/u/ultimike), the maintainer of [Markdown Easy](https://www.drupal.org/project/markdown_easy), to discuss a simpler way to mix HTML and Markdown.

I suggested making it a configuration option and helped test and review the necessary changes. I was happy when that became part of the built-in settings in version 2.0. A few weeks later, Markdown Easy 2.0 was released, and this capability is now available out of the box.

Now that everything is working, I am considering converting my 1,600+ existing posts from HTML to Markdown. Part of me wants everything to be consistent, but another part hesitates to overwrite hundreds of hours of carefully crafted HTML. The obsessive in me debates the archivist. We'll see who wins.

The migration itself would be a fun technical challenge. Plenty of tools exist to convert HTML to Markdown so no need to reinvent the wheel. Maybe I'll test a few converters on some posts to see which handles my particular setup best.

### Extending Markdown with tokens

Like [Deane Barker](https://deanebarker.net/tech/blog/custom-elements-markdown/), I often mix HTML and Markdown with custom "tokens". In my case, they aren't [official web components](https://github.com/WICG/webcomponents), but they serve a similar purpose.

For example, here is a snippet that combines standard Markdown with a token that embeds an image:

```markdown
Nothing beats starting the day with [coffee](https://dri.es/tag/coffee) and this view:

［image beach-sunrise.jpg lazy=true schema=true caption=false］
```

These tokens get processed by my custom Drupal module and transformed into full HTML.  That basic image token? It becomes a responsive picture element complete with lazy loading, `alt`-text from my database, [Schema.org](https://schema.org/) support, and optional caption. I use similar tokens for videos and other dynamic content.

The real power of tokens is future proofing. When responsive images became a web standard, I could update my image token processor once and instantly upgrade all my blog posts. No need to edit old content. Same when lazy loading became standard, or when new image formats arrive. One code change updates all 10,000 images or so that I've ever posted.

My tokens has evolved over 15 years and deserves its own blog post. Down the road, I might turn some of them into web components [like Deane describes](https://deanebarker.net/tech/blog/custom-elements-markdown/).

### Closing thoughts

In the end, this was not a syntax decision: it was a workflow decision. I want less friction between an idea and publishing it. Five Markdown posts in, publishing is faster, cleaner, and more enjoyable, while still giving me the flexibility I need. 

Those 45 minutes I used to spend on HTML tags? I now spend on things that matter more, or on writing another blog post.
