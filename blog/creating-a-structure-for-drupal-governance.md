---
url: 'https://dri.es/creating-a-structure-for-drupal-governance'
title: 'Creating a structure for Drupal governance'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2013-03-04T22:57:09-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
  - 'Drupal Association'
  - Governance
published: true
id: 2916
---

# Creating a structure for Drupal governance

Last summer, a number of Drupal community members as well as key figures from other major open source projects met in Portland for the [first-ever Drupal governance sprint](https://dri.es/proposal-from-first-drupal-governance-sprint). The proposal from that sprint recommended the creation of a number of chartered "working groups" to better formalize the existing governance of various aspects of the Drupal project, now that our community is at its current scale. We have now chartered the first of these working groups: the [Community Working Group](https://cgit.drupalcode.org/project/governance.git/blob_plain/refs/heads/master:/charters/community-working-group-charter.html). Thanks very much to everyone who participated in the [vigorous community discussion](https://www.drupal.org/node/1822314) and drafting efforts around this.

However, while the governance proposal coming out of Portland provided some fairly solid direction on the governance of the Drupal project itself, it left some pretty big questions unanswered as it related to the governance of Drupal.org. Drupal.org isn't just some ordinary website. While it was originally a small portal with a few hundred members hosted on a friend's shared server, it is now serving millions of page views to over 2 million unique visitors per month, as well as terabytes of data, and is home to almost a million active members, among them thousands of contributors committing code, reviewing patches, improving documentation, etc. at all hours of the day. The old "do-ocracy" model of getting things done on Drupal.org isn't scaling for our community anymore, and lack of clarity around decision-making has cost us repeatedly, in the form of slow progress on the Drupal.org Drupal 7 upgrade, Drupal Association funding challenges and staff inefficiency, and various community volunteer frustrations.

I've therefore spent time over the past few months talking with a number of members of the Drupal Association, various Drupal.org volunteers, Drupal core/contrib developers, as well as other interested parties, in order to determine how to put into place a structure that clarifies the decision-making processes around Drupal.org. The following is the overall proposal for Drupal.org governance we've come up with, as well as links to more specific draft charters for community review.

### Overview

Note: the finer points of this can be found in <https://dri.es/files/drupal-governance-plan-2013.pdf>.

While "governance" can sometimes sound like a scary word, really it's about coming up with a way to:

- Make decisions fast,
- In as lightweight a way as possible
- Allowing affected parties to have a say,
- With clearly-defined processes and easy to understand decision-making.

Cracking this problem for Drupal.org provides us with less frustration/uncertainty among volunteers, more money and resources funneled into improvements, and better community velocity overall.

Governance mostly comes down to establishing "working groups" around major areas of the project, many of which already have governance in at least an ad-hoc basis. Working groups will consist of a chair, plus 3-5 members who are empowered to make decisions, then a team of N volunteers and/or DA staff to help carry out their tasks/policies. The working groups are only empowered to make decisions as a whole, not on an individual basis.

### Drupal project governance / Drupal.org governance compared

For the Drupal project, we are working towards developing a number of working groups related to various aspects of the community (security, documentation, conflict resolution, Drupal core, etc.), with myself as the final decision-maker:

[image drupal/drupal-project-governance-2013 resize=false]

The working groups might be compared/contrasted this way:

<table>
  <tr>
   <th>Community working group</th>
   <th>Technical working group</th>
   <th>Security team</th>
   <th>Documentation team</th>
   <th>Drupal core X working group</th>
 </tr>
  <tr>
   <td>Guarantee a friendly and welcoming community for the Drupal project by upholding the Drupal Code of Conduct.</td>
   <td>Maintain technical policies, procedures, and standards as required to keep the technical side of our community operating smoothly.</td>
   <td>Maintain technical policies, procedures, and standards as required to keep our projects secure</td>
   <td>Make sure that we have high quality technical documentation for Drupal, including the Drupal handbook and API documentation</td>
   <td>Provide technical leadership and project management for Drupal core development.</td>
 </tr>
</table>

In the case of Drupal.org, however, it makes sense for this final decision-maker to be the Drupal Association, since they are ultimately responsible for the website, purchasing hardware, etc.

[image drupal/drupal-website-governance-2013 resize=false]

The working groups might be compared/contrasted this way:

<table>
  <tr>
   <th>Drupal.org infrastructure working group</th>
   <th>Drupal.org software working group</th>
   <th>Drupal.org content working group</th>
 </tr>
  <tr>
   <td>Responsible for all infrastructure-related needs of the Drupal project, including the servers, Git repositories, mailing lists, DNS management, e-mail management, network, server access and security.</td>
   <td>Responsible for guiding the planning, architecture, development, and maintenance of the Drupal.org websites.</td>
   <td>Responsible for maintaining policies around the major content areas on Drupal.org. They also manage the overall look and feel and voice of the website, including its information architecture and design elements.</td>
 </tr>
</table>

This means that the existing webmasters group members can choose to participate in either the [Drupal.org software working group](https://www.drupal.org/project/webmasters) or [Drupal.org content working group](https://www.drupal.org/project/content), or both.

Needless to say, groups will often have to work together. For example, to answer the question of whether to keep developing project module or move our collaboration tools to Github, we'll have to get the following groups together: (i) the Drupal.org software working group because it affects the features of drupal.org, (ii) the Drupal.org hardware working group because they may need to host new features, (iii) the technical Working Group because it impacts how we collaborate on software development, and (iv) the Drupal Association Board of Directors because they have to write the check.

### Draft charters for review

This is a work in progress. Please help shape the future of Drupal.org governance by reviewing and commenting on the following proposals:

- [Drupal.org Infrastructure Working Group](https://www.drupal.org/node/1929524)
- [Drupal.org Software Working Group](https://www.drupal.org/node/1929526)
- [Drupal.org Content Working Group](https://www.drupal.org/node/1929530)
- [Technical Working Group](https://www.drupal.org/node/1929534)
- [Community Working Group](https://cgit.drupalcode.org/project/governance.git/blob_plain/refs/heads/master:/charters/community-working-group-charter.html) (Already formalized)

Our plan is to allow everyone in the community to provide feedback during the next 3 weeks. Then, around the end of March I will post updated drafts based on community feedback, with the aim to finalize the charters by the mid-April.

### Onward and upward

I'm really excited about the possibilities for Drupal.org in the future with this governance structure. My hope is that this helps address some of the ambiguity and confusion around the current structure, while at the same time not being overly constrictive.

Thanks in advance to everyone for their participation in helping to shape the future of Drupal.org!
