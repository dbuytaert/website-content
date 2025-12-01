---
title: 'Why content management systems can outperform static site generators'
date: '2023-03-20T14:24:38-04:00'
author: Dries
summary: 'Why I choose Drupal over static site generators for my website.'
image: blog/static-site-generators-are-fast-marketing
tags:
  - Drupal
  - 'My site'
  - Performance
featured: true
published: true
type: blog
url: /why-content-management-systems-can-outperform-static-site-generators
id: 5436
---

One or two times a month I get the following question: <q>Why don't you just use a Static Site Generator (SSG) for your blog?</q>

Well, I'm not gonna lie, being the founder and project lead of Drupal definitely plays a role in why I use Drupal for my website. Me not using Drupal would be like Coca-Cola's CEO drinking Pepsi, a baker settling for supermarket bread, or a cabinet builder furnishing their home entirely with IKEA. People would be confused.

Of course, if I wanted to use a static site, I could. Drupal is frequently used as the content repository for [Gatsby.js](https://www.drupal.org/project/gatsby), [Next.js](https://next-drupal.org/), and many other frameworks.

The main reason I don't use a SSG is that I don't love their publishing workflow. It's slow. With Drupal, I can make edits, hit save, and immediately see the result. With a static site generator it becomes more complex. I have to commit Markdown to Git, rebuild my site, and push updates to a web server. I simply prefer the user-friendly authoring of Drupal.

<div class="large">
  [image blog/static-site-generators-are-fast-marketing resize=false]
</div>

Proponents of static sites will be quick to point out that static sites are "much faster". Personally, I find that misleading. My Drupal-powered site, <https://dri.es/>, is faster than most static sites, including the official websites of leading static site generators.

<table>
  <tr>
  <th>Technology</th>
  <th>URL tested</th>
  <th>Page load time</th>
</tr>
  <tr>
  <td>Drupal</td>
  <td>
   <a href="https://dri.es/">https://dri.es/</a>
 </td>
  <td>0.3 seconds</td>
</tr>
  <tr>
  <td>Gatsby.js</td>
  <td>
   <a href="https://www.gatsbyjs.com/">https://www.gatsbyjs.com/</a>
 </td>
  <td>2.8 seconds</td>
</tr>
  <tr>
  <td>Next.js</td>
  <td>
   <a href="https://nextjs.org/">https://nextjs.org/</a>
 </td>
  <td>1.8 seconds</td>
</tr>
  <tr>
  <td>Jekyll</td>
  <td>
   <a href="https://jekyllrb.com/">https://jekyllrb.com/</a>
 </td>
  <td>0.8 seconds</td>
</tr>
  <tr>
  <td>Elevently</td>
  <td>
   <a href="https://www.11ty.dev/">https://www.11ty.dev/</a>
 </td>
  <td>0.5 seconds</td>
</tr>
  <tr>
  <td>Docusaurus</td>
  <td>
   <a href="https://docusaurus.io/">https://docusaurus.io/</a>
 </td>
  <td>1.8 seconds</td>
</tr>
  <tr>
  <td>Svelte Kit</td>
  <td>
   <a href="https://kit.svelte.dev/">https://kit.svelte.dev/</a>
 </td>
  <td>1.1 seconds</td>
</tr>
</table>

In practice, most sites serve their content from a cache. As a result, we're mainly measuring (1) the caching mechanism, (2) last mile network performance and (3) client-side rendering. Of these three, client-side rendering impacts performance the most.

My site is the fastest because its HTML/CSS/JavaScript is the simplest and fastest to render. I don't use external web fonts, track visitors, or use a lot of JavaScript. Drupal also optimizes performance with lazy loading of images, CSS/JavaScript aggregation, and more.

In other words, the performance of a website depends more on the HTML, CSS, JavaScript code and assets (images, video, fonts) than the underlying technology used.

The way an asset is cached can also affect its performance. Using a reverse proxy cache, such as Varnish, is faster than caching through the filesystem. And using a global CDN yields even faster results. A CMS that uses a CDN for caching can provide better performance than a SSG that only stores assets on a filesystem.

To be clear, I'm not against SSGs. I can understand the use cases for them, and there are plenty of situations where they are a great choice.

In general, I believe that any asset that can be a static asset, should be a static asset. But I also believe that any dynamically generated asset that is cached effectively has become a static asset. A page that is created dynamically by a CMS and is cached efficiently is a static asset. Both a CMS and a SSG can generate static assets.

In short, I simply prefer the authoring experience of a CMS, and I keep my site fast by keeping the generated HTML code lightweight and well-cached.

What really tips the scale for me is that I enjoy having a server-side requests handler. Now, I know that this might sound like the nerdiest closing statement ever, but trust me: server-side request handlers bring the fun. Over the years they have enabled me to do [fun and interesting things on my websites](https://dri.es/posting-my-phone-battery-status-to-my-site). I'm not stopping the fun anytime soon!
