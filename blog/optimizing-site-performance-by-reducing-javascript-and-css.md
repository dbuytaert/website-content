---
title: 'Optimizing site performance by reducing JavaScript and CSS'
date: '2019-02-13T21:04:05-05:00'
author: Dries
tags:
  - Performance
  - Accessibility
  - Drupal
  - 'My site'
published: true
type: blog
url: /optimizing-site-performance-by-reducing-javascript-and-css
id: 4756
---

I've been thinking about the performance of my site and how it affects the user experience. There are real, [ethical concerns](https://timkadlec.com/remembers/2019-01-09-the-ethics-of-performance/) to poor web performance. These include accessibility, inclusion, waste and environmental concerns.

A faster site is more accessible, and therefore more inclusive for people visiting from a mobile device, or from [areas in the world with slow or expensive internet](https://whatdoesmysitecost.com).

For those reasons, I decided to see if I could improve the performance of my site. I used the excellent <https://webpagetest.org> to benchmark a simple blog post <https://dri.es/relentlessly-eliminating-barriers-to-growth>.

<div class="large">
  [image blog/webpagetest-no-images-february-2019-before]
</div>

The image above shows that it took a browser 0.722 seconds to download and render the page (see blue vertical line):

- The first 210 milliseconds are used to set up the connection, which includes the DNS lookup, TCP handshake and the SSL negotiation.
- The next 260 milliseconds (from 0.21 seconds to 0.47 seconds) are spent downloading the rendered HTML file, two CSS files and one JavaScript file.
- After everything is downloaded, the final 330 milliseconds (from 0.475 seconds to 0.8 seconds) are used to layout the page and execute the JavaScript code.

By most standards, 0.722 seconds is pretty fast. In fact, according to [HTTP Archive](https://httparchive.org/), it takes more than 2.4 seconds to download and render the average web page on a laptop or desktop computer.

Regardless, I noticed that the length of the horizontal green bars and the horizontal yellow bar was relatively long compared to that of the blue bar. In other words, a lot of time is spent downloading JavaScript (yellow horizontal bar) and CSS (two green horizontal bars) instead of the HTML, including the actual content of the blog post (blue bar).

To fix, I did two things:

1. **Use vanilla JavaScript**. I replaced my jQuery-based JavaScript with vanilla JavaScript. Without impacting the functionality of my site, the amount of JavaScript went from almost 45 KB to 699 bytes, good for a savings of over 6,000 percent.
2. **Conditionally include CSS**. For example, I use [Prism.js](https://prismjs.com/) for [syntax highlighting code snippets in blog posts](https://dri.es/how-to-use-drupal-8-off-canvas-dialog-in-your-modules). `prism.css` was downloaded for every page request, even when there were no code snippets to highlight. Using Drupal's render system, it's easy to conditionally include CSS. By taking advantage of that, I was able to reduce the amount of CSS downloaded by 47 percent – from 4.7 KB to 2.5 KB.

According to the January 1st, 2019 run of [HTTP Archive](https://httparchive.org/), the median page requires 396 KB of JavaScript and 60 KB of CSS. I'm proud that my site is well under these medians.

<table>
  <thead>
   <tr>
    <th>File type</th>
    <th>Dri.es before</th>
    <th>Dri.es after</th>
    <th>World-wide median</th>
  </tr>
 </thead>
  <tbody>
   <tr>
    <td>JavaScript</td>
    <td>45 KB</td>
    <td>669 bytes</td>
    <td>396 KB</td>
  </tr>
   <tr>
    <td>CSS</td>
    <td>4.7 KB</td>
    <td>2.5 KB</td>
    <td>60 KB</td>
  </tr>
 </tbody>
</table>

Because the new JavaScript and CSS files are significantly smaller, it takes the browser less time to download, parse and render them. As a result, the same blog post is now available in 0.465 seconds instead of 0.722 seconds, or 35% faster.

After a new <https://webpagetest.org> test run, you can clearly see that the bars for the CSS and JavaScript files became visually shorter:

<div class="large">
  [image blog/webpagetest-no-images-february-2019-after]
</div>

To optimize the user experience of my site, I want it to be fast. I hope that others will see that bloated websites can come at a great cost, and will consider using tools like <https://webpagetest.org> to make their sites more performant.

I'll keep working on making my website even faster. As a next step, I plan to make pages with images faster by using lazy image loading.
