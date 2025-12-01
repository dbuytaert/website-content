---
title: 'IIS module for Mollom'
date: '2009-08-03T03:10:37-04:00'
author: Dries
tags:
  - Microsoft
  - Mollom
  - 'Mollom plugins'
published: true
type: blog
url: /iis-module-for-mollom
id: 891
---

[Zion Security](http://www.zionsecurity.com), a Belgium-based company specializing in the security analysis of web sites and systems, has used [Mollom's open API](https://www.mollom.com/api) to develop a Microsoft IIS module utilizing [Mollom](https://mollom.com) to detect and prevent comment and posting spam.

This module is unique in that it is a *HTTP module* coded for Microsoft IIS, comparable to an [Apache module](http://modules.apache.org/), and allows Mollom to potentially expand to a number of ASP/IIS based systems.

The [Mollom IIS module](https://www.zionsecurity.com/downloads/products/mollom-httpmodule.aspx) is available as a zipped file for [download here](https://www.zionsecurity.com/protected/HttpModuleMollom.zip) and is listed on our [downloads page](https://www.mollom.com/download). It checks any submitted form for spam using Mollom's spam detection analysis, and like other Mollom plugins, requires you to obtain a set of registration keys from [mollom.com](https://mollom.com) before it can be actively used to protect your ASP-based forms.

Because it is written as a module at the webserver layer, it may be possible to use Mollom's spam-detection and CAPTCHA challenge ability with existing web applications running on IIS (think SharePoint or DotNetNuke). It's an interesting approach and one we haven't really considered ourselves. It will be interesting to see how this develops, and if it sticks.
