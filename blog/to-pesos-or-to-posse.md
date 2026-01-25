---
url: 'https://dri.es/to-pesos-or-to-posse'
title: 'To PESOS or to POSSE?'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2018-02-06T04:43:38-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'Comparing two different approaches that help you take control back over your own data on the web.'
tags:
  - 'Open Web'
  - POSSE
  - 'My site'
  - 'Social media'
image: blog/pesos-vs-posse
published: true
featured: true
id: 4146
---

# To PESOS or to POSSE?

Yesterday I shared that [I uninstalled the Facebook application from my phone](https://dri.es/taking-control-of-my-data-and-social-media). My friend Simon Surtees was quick to text me: <q>I for one am pleased you have left Facebook. Less Cayman Island pictures!</q>. Not too fast Simon. I never said that I left Facebook or that I'd stop posting on Facebook. Plus, I'll have more Cayman Islands pictures to share soon. :)

As a majority of my friends and family communicate on Facebook and Twitter, I still want to share updates on social media. However, I believe I can do it in a more thoughtful manner that allows me to take back control over my own data. There are a couple of ways I could go about that:

- I could share my status updates and photos on a service like Facebook or Twitter and then automatically download and publish them to my website.
- I could publish my status updates and photos on my website first, and then programmatically share them on Facebook, Twitter, etc.

The [IndieWeb movement](https://indieweb.org) has provided two clever names for these models:

1. **PESOS** or [Publish Elsewhere, Syndicate (to your) Own Site](https://indieweb.org/PESOS) is a model where publishing begins on third party services, such as Facebook, and then copies can be syndicated to your own site.
2. **POSSE** or [Publish (on your) Own Site, Syndicate Elsewhere](https://indieweb.org/POSSE) is a publishing model that begins with posting content on your own site first, then syndicating out copies to third party services.

[image blog/pesos-vs-posse resize=false]

Here is the potential impact of each approach:

<table>
  <thead>
   <tr>
    <th>
   </th>
    <th>PESOS</th>
    <th>POSSE</th>
  </tr>
 </thead>
  <tr>
   <td>
    <em>Dependence</em>
  </td>
   <td>A 3rd party is a required intermediary within the PESOS approach. When the 3rd party platform is down or disappears completely, publishers lose their ability to post new content or retrieve old content.</td>
   <td>No dependence, as the 3rd party service is an optional endpoint, not a required intermediary.</td>
 </tr>
  <tr>
   <td>
    <em>Canonical</em>
  </td>
   <td>Non-canonical: the data on the 3rd party is the original and copies on your domain may have to cite 3rd party URLs.</td>
   <td>Canonical: you have full control over URLs and host the original data. The 3rd party could cite the original URL.</td>
 </tr>
  <tr>
   <td>
    <em>Quality</em>
  </td>
   <td>Pulling data from 3rd parties services could reduce its quality. For example, images could be degraded or downsized.</td>
   <td>Full control over the quality of assets on your own site.</td>
 </tr>
  <tr>
   <td>
    <em>Ease of use, implementation and maintenance</em>
  </td>
   <td>3rd party platforms make it really easy for users to publish content and you can still benefit from that. For example, you can easily upload images from your phone. The complexity inherent to the PESOS approach includes developing an infrastructure to curate archival copies to your own domain.</td>
   <td>The POSSE strategy can be significantly more work for the site owner, especially if you want comparable ease of use to 3rd party platforms. A higher level of technical expertise and time investment is likely required.</td>
 </tr>
</table>

The goal of this analysis was to understand the pros and cons of how I can own my own content on <https://dri.es>. While PESOS would be much easier to implement, I decided to go with POSSE. My next step is to figure out my "POSSE plan"; how to quickly and easily share status updates on my Drupal site, how to syndicate them to 3rd party services, how to re-organize [my mailing list](https://dri.es/subscribe) and [my RSS feed](https://dri.es/rss.xml), and more.
