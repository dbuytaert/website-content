---
url: 'https://dri.es/cmis'
title: CMIS
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2008-09-19T10:29:32-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
published: true
id: 508
---

# CMIS

In the spring of 2007, I first heard rumors about IBM and Microsoft working together on a specification that could change the content management landscape. Last week, EMC, IBM and Microsoft (with support from Oracle, SAP, Alfresco and OpenText) [announced that they will be collaborating on CMIS](https://www.emc.com/about/news/press/2008/091008-smr-content-management-interoperability-services.htm), a standard to enable interoperability among content management systems. CMIS stands for [Content Management Interoperability Services](https://community.emc.com/docs/DOC-1605) and promises improved content unification, better content aggregation and mashups, cross-silo federation, and better integration with desktop publishing.

Various people blogged about CMIS, including [John Newton](http://newton.typepad.com/content/2008/09/alfresco-releases-first-cmis-implementation.html) (CTO Alfresco), [Craig Randall](http://craigrandall.net/archives/2008/09/cmis/) (software architect for EMC), [Kas Thomas](http://www.cmswatch.com/Trends/1361-CMIS:%C2%A0the-new-Lingua-Franca-of-ECM?) (analyst for CMSWatch), [Brian Huff](http://bexhuff.com/2008/09/ecm-standards-war-bye-bye-jsr170-hello-cmis), [Andrew Chapman](http://nevertalkwhenyoucannod.com/2008/09/10/content-management-interoperability-services-cmis-ndash-another-sharepoint-desilofication-solution.aspx) (Senior Director EMC) and more. If you want to learn more, you can also check <https://community.emc.com/community/labs/cmis> for video presentations and additional technical materials.

It will probably take years before this becomes an actual standard and before it gets widely adopted, but it is interesting for at least two reasons:

1. CMIS can use Atom in its REST model. This makes me want to push even harder for adding Atom as one of the default output formats for Drupal nodes (see also [refactor node rendering](https://www.drupal.org/node/134478) and [pluggable renders for JSON, XML, etc](https://www.drupal.org/node/145551)). Looks like Drupal was already heading in similar directions, so we might as well keep an eye on CMIS.
2. The specification solves a real problem and the big boys are backing it. If EMC, IBM and Microsoft put code behind their words, CMIS might become part of Microsoft Office, SharePoint, Documentum, FileNet, etc. I'd love to see Microsoft Office users to be able to save documents into Drupal. Pushing for standards is always a good thing.
