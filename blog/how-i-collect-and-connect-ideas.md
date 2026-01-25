---
url: 'https://dri.es/how-i-collect-and-connect-ideas'
title: 'How I collect and connect ideas'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2025-06-24T04:04:20-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'How I use Obsidian to build a knowledge base that helps me think better, connect ideas in writing, and pursue projects.'
tags:
  - Writing
  - Markdown
image: miscellaneous-2023/champagne-tunnel
published: true
featured: false
id: 5831
---

# How I collect and connect ideas

[image miscellaneous-2023/champagne-tunnel caption=false]

In my post about [digital gardening and public notes](https://dri.es/if-a-note-can-be-public-it-should-be), I shared a principle I follow: "If a note can be public, it should be". I also mentioned using [Obsidian](https://obsidian.md) for note-taking. Since then, various people have asked about my Obsidian setup.

I use Obsidian to collect ideas over time rather than to manage daily tasks or journal. My setup works like a [Commonplace book](https://en.wikipedia.org/wiki/Commonplace_book), where you save quotes, thoughts, and notes to return to later. It is also similar to a [Zettelkasten](https://en.wikipedia.org/wiki/Zettelkasten), where small, linked notes build deeper understanding.

What makes such note-taking systems valuable is how they help ideas grow and connect. When notes accumulate over time, connections start to emerge. Ideas compound slowly. What starts as scattered thoughts or quotes becomes the foundation for blog posts or projects.

### Why plain text matters

One of the things I appreciate most about [Obsidian](https://obsidian.md) is that it stores notes as plain text [Markdown](https://en.wikipedia.org/wiki/Markdown) files on my local filesystem.

Plain text files give you full control. I sync them with iCloud, back them up myself, and track changes using Git. You can search them with command-line tools, write scripts to process them outside of Obsidian, or edit them in other applications. Your notes stay portable and usable any way you want.

Plus, plain text files have long-term benefits. Note-taking apps come and go, companies fold, subscription models shift. But plain text files remain accessible. If you want your notes to last for decades, they need to be in a format that stays readable, editable, and portable as technology changes. A Markdown file you write today will open just fine in 2050.

All this follows what Obsidian CEO [Steph Ango](https://stephango.com/) calls the ["files over apps" philosophy](https://stephango.com/file-over-app): your files should outlast the tools that create them.  Don't lock your thinking into formats you might not be able to access later.

### My tools

Before I dive into how I use Obsidian, it is worth mentioning that I use different tools for different types of thinking. Some people use Obsidian for everything – task management, journaling, notes – but I prefer to separate those.

For daily task management and meeting notes, I rely on my [reMarkable Pro](https://remarkable.com). A study titled *[The Pen Is Mightier Than the Keyboard](https://journals.sagepub.com/doi/abs/10.1177/0956797614524581)* by Mueller and Oppenheimer found that students who took handwritten notes retained concepts better than those who typed them. Handwriting meeting notes engages deeper cognitive processing than typing, which can improve understanding and memory. 

For daily journaling and event tracking, I use a custom iOS app I built myself. I might share more about that another time.

Obsidian is where I grow long-term ideas. It is for collecting insights, connecting thoughts, and building a knowledge base that compounds over time.

### How I capture ideas

In Obsidian, I organize my notes around topic pages. Examples are "Coordination challenges in Open Source", "Solar-powered websites", "Open Source startup lessons", or "How to be a good dad".

I have hundreds of these topic pages. I create a new one whenever an idea feels worth tracking. 

Each topic page grows slowly over time. I add short summaries, interesting links, relevant quotes, and my own thoughts whenever something relevant comes up.  The idea is to build a thoughtful collection of notes that deepens and matures over time.

Some notes stay short and focused. Others grow rich with quotes, links, and personal reflections. As notes evolve, I sometimes split them into more specific topics or consolidate overlapping ones.

I do not schedule formal reviews. Instead, notes come back to me when I search, clip a new idea, or revisit a related topic. A recent thought often leads me to something I saved months or years ago, and may prompt me to reorganize related notes.

Obsidian's core features help these connections deepen. I use [tags](https://help.obsidian.md/tags), [backlinks](https://help.obsidian.md/backlinks) and [graph view](https://help.obsidian.md/plugins/graph), to connect notes and reveal patterns between notes.

### How I use notes

The biggest challenge with note-taking is not capturing ideas, but actually using them. Most notes get saved and then forgotten. 

Some of my blog posts grow directly from these accumulated notes. [Makers and Takers](https://dri.es/balancing-makers-and-takers-to-scale-and-sustain-open-source), one of my most-read blog posts, pre-dates Obsidian and did not come from this system. But if I write a follow-up, it will. I have a "Makers and Takers" note where relevant quotes and ideas are slowly accumulating.

As my collection of notes grows, certain notes keep bubbling up while others fade into the background. The ones that resurface again and again often signal ideas worth writing about or projects worth pursuing.

What I like about this process is that it turns note-taking into more than just storage. As I've said many times, writing is how I think. Writing pushes me to think, and it is the process I rely on to flesh out ideas. I do not treat my notes as final conclusions, but as ongoing conversations with myself. Sometimes two notes written months apart suddenly connect in a way I had not noticed before. 

### My plugin setup

Obsidian has a large plugin ecosystem that reminds me of [Drupal](https://www.drupal.org)'s.  I mostly stick with core plugins, but use the following community ones:

* **[Dataview](https://github.com/blacksmithgu/obsidian-dataview)** – Think of it as SQL queries for your notes. I use it to generate dynamic lists like `TABLE FROM #chess AND #opening AND #black` to see all my notes on chess openings for Black. It turns your notes into a queryable database.

* **[Kanban](https://github.com/mgmeyers/obsidian-kanban)** – Visual project boards for tracking progress on long-term ideas. I maintain Kanban boards for [Acquia](https://acquia.com), [Drupal](https://drupal.org), improvements to [dri.es](https://dri.es), and more. Unlike daily task management, these boards capture ideas that evolve over months or years.

* **[Linter](https://github.com/platers/obsidian-linter)** – Automatically formats my notes: standardizes headings, cleans up spacing, and more. It runs on save, keeping my Markdown clean.

* **[Encrypt](https://github.com/meld-cp/obsidian-encrypt)** – Encrypts specific notes with password protection. Useful for sensitive information that I want in my knowledge base but need to keep secure.

* **[Pandoc](https://github.com/OliverBalfour/obsidian-pandoc)** – Exports notes to Word documents, PDFs, HTML, and other formats using [Pandoc](https://pandoc.org).

* **[Copilot](https://github.com/logancyang/obsidian-copilot)** – I'm still testing this, but the idea of chatting with your own knowledge base is compelling. You can also ask AI to help organize notes more effectively.

### The Obsidian Web Clipper

The tool I'd actually recommend most isn't a traditional Obsidian plugin: it's the official [Obsidian Web Clipper](https://obsidian.md/clipper) browser extension.  I have it installed on my desktop and phone.

When I find something interesting online, I highlight it and clip it directly into Obsidian. This removes friction from the process.

I usually save just a quote or a short section of an article, not the whole article. Some days I save several clips. Other days, I save none at all.

### Why this works

For me, Obsidian is not just a note-taking tool. It is a thinking environment. It gives me a place to collect ideas, let them mature, and return to them when the time is right. I do not aim for perfect organization. I aim for a system that feels natural and helps me notice connections I would otherwise miss.
