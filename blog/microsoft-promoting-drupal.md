---
url: 'https://dri.es/microsoft-promoting-drupal'
title: 'Microsoft promoting Drupal'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2009-03-18T15:30:00-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
  - Acquia
  - Microsoft
published: true
id: 620
---

# Microsoft promoting Drupal

Microsoft [announced its Web Application Gallery](http://www.prweb.com/releases/2009/03/prweb2246164.htm) at its annual MIX conference today. The exciting news for many of us is that [Drupal](https://www.drupal.org) is one of the first 10 applications to be included as part of the [Web Application Gallery](https://www.microsoft.com/web/gallery). Other open source applications including [Wordpress](http://wordpress.org), [SilverStripe](http://silverstripe.com), and [Gallery](http://galleryproject.org/) also made into the initial group.

The Microsoft [Web Application Gallery](https://www.microsoft.com/web/gallery) follows on from last year's [Web Application Installer](https://dri.es/microsoft-ships-drupal), but it is even better. The Web Application Gallery allows you to browse and discover web applications that install and deploy well on Windows, and offers a simplified download/install experience for these applications and all of [Microsoft's free web products](https://www.microsoft.com/web/) that these applications run on. Just click the 'Install' button on the Web Application Gallery and you'll be guided through the installation process. For people running Windows Vista, 2003 Server, XP or Windows 7, the installer automatically configures IIS6 or IIS7 appropriately for PHP and Drupal, installing the required MySQL database and PHP's mod-rewrite rules and required extensions. Note that Drupal does not support Microsoft SQL, and that Microsoft will not automatically install MySQL at this point – the installer prompts users to download and install Windows binaries for MySQL from mysql.com.

Because we believe this is an opportunity to introduce Drupal to hundreds of thousands of new users, [Acquia](https://www.acquia.com) worked with Microsoft to help package [Acquia Drupal](https://dev.acquia.com/downloads) for the Web Application Gallery. When Microsoft approached us, we were cautious at first, but quickly realized this could be a great opportunity for both Drupal, and the Open Source community at large. We were further encouraged when the Microsoft Web Platform team provided us every resource we needed to get the job done in record time, including dedicating a full-time engineer to work with us. While not perfect in version 1.0 we are encouraged by this new direction.

One interesting aspect of this cooperation is that the actual Drupal code, along with the Web Application Gallery metadata, is all hosted and maintained by Acquia (not by Microsoft). Whenever we roll a new release of Acquia Drupal, the Web Application Gallery will automatically point to the latest version of Acquia Drupal. It is integrated in our testing environment and build loops. In addition, all support for this IIS-friendly Acquia Drupal package can be handled through [Acquia's support forums](http://network.acquia.com/forum).

This kind of arrangement makes things very scalable for Microsoft. Going forward, anyone will be able to submit their ASP.net and PHP applications for inclusion in the Web Application Gallery. If Microsoft chooses to push this hard, and markets these applications to the millions of Windows developers world-wide, it is likely we'll be seeing hundreds of Free and Open Source applications being added to the Web Application Gallery. Microsoft also told us that they are working on an SDK that will allow third-party applications, such as [Plesk](https://www.parallels.com/products/plesk/) and [cPanel](http://www.cpanel.net), to integrate with the Web Application Gallery, enabling their customers to install all the Web Application Gallery software directly on their Windows-based hosting accounts instead of their local desktop.

[image drupal/microsoft-web-application-gallery]
