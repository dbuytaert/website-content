---
url: 'https://dri.es/who-sponsors-drupal-development'
title: 'Who sponsors Drupal development? (2015-2016 edition)'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2016-09-06T11:39:05-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: "An in-depth analysis of how Drupal's development was sponsored between July 1, 2015 and June 30, 2016."
tags:
  - Drupal
  - 'Open Source'
  - 'Drupal sponsors'
image: drupal/contributions-top-30-organizations-2016
published: true
id: 3761
---

# Who sponsors Drupal development? (2015-2016 edition)

***Update:** The most recent version of this post is available at [Who sponsors Drupal development? (2018-2019 edition)](https://dri.es/who-sponsors-drupal-development-2019). For a list of all previous versions, see <https://dri.es/tag/drupal-sponsors>.*

There exist millions of Open Source projects today, but many of them aren't sustainable. Scaling Open Source projects in a sustainable manner is difficult. A prime example is [OpenSSL](https://www.openssl.org), which plays a critical role in securing the internet. Despite its importance, the entire OpenSSL development team is relatively small, consisting of 11 people, [10 of whom are volunteers](https://en.wikipedia.org/wiki/OpenSSL#Project_history). In 2014, security researchers discovered [an important security bug](https://en.wikipedia.org/wiki/Heartbleed) that exposed millions of websites. Like OpenSSL, most Open Source projects fail to scale their resources. Notable exceptions are the Linux kernel, Debian, Apache, Drupal, and WordPress, which have foundations, multiple corporate sponsors and many contributors that help these projects scale.

We ([Dries Buytaert](https://dri.es) is the founder and project lead of [Drupal](https://www.drupal.org/) and co-founder and Chief Technology Officer of [Acquia](https://www.acquia.com/) and [Matthew Tift](https://matthewtift.com/) is a Senior Developer at [Lullabot](https://lullabot.com) and Drupal 8 configuration system co-maintainer) believe that the Drupal community has a shared responsibility to build Drupal and that those who get more from Drupal should consider giving more. We examined commit data to help understand who develops Drupal, how much of that work is sponsored, and where that sponsorship comes from. We will illustrate that the Drupal community is far ahead in understanding [how to sustain and scale the project](https://dri.es/scaling-open-source-communities). We will show that the Drupal project is a healthy project with a diverse community of contributors. Nevertheless, in Drupal's spirit of always striving to do better, we will also highlight areas where our community can and should do better.

### Who is working on Drupal?

In the spring of 2015, after [proposing ideas about giving credit](https://dri.es/a-method-for-giving-credit-to-organizations-that-contribute-code-to-open-source) and [discussing various approaches at length](https://www.drupal.org/node/2288727), Drupal.org added the ability for people to [attribute their work](https://www.drupal.org/drupalorg/blog/a-guide-to-issue-credits-and-the-drupal.org-marketplace) to an organization or customer in the Drupal.org issue queues. Maintainers of Drupal themes and modules can award issues credits to people who help resolve issues with code, comments, design, and more.

[image drupal/example-issue-credit-on-drupal-org-2016 resize=false]

Drupal.org's credit system captures all the issue activity on Drupal.org. This is primarily code contributions, but also includes some (but not all) of the work on design, translations, documentation, etc. It is important to note that contributing in the issues on Drupal.org is not the only way to contribute. There are other activities–for instance, sponsoring events, promoting Drupal, providing help and mentoring–important to the long-term health of the Drupal project. These activities are not currently captured by the credit system. Additionally, we acknowledge that parts of Drupal are developed on GitHub and that credits might get lost when those contributions are moved to Drupal.org. For the purposes of this post, however, we looked only at the issue contributions captured by the credit system on Drupal.org.

What we learned is that in the 12-month period from July 1, 2015 to June 30, 2016 there were 32,711 issue credits – both to Drupal core as well as all the contributed themes and modules – attributed to 5,196 different individual contributors and 659 different organizations.

Despite the large number of individual contributors, a relatively small number do the majority of the work. Approximately 51% of the contributors involved got just one credit. The top 30 contributors (or top 0.5% contributors) account for over 21% of the total credits, indicating that these individuals put an incredible amount of time and effort in developing Drupal and its contributed modules:

<small>
  <table>
   <thead>
    <tr>
      <th style="padding: 0.2em;">Rank</th>
      <th style="padding: 0.2em;">Username</th>
      <th style="padding: 0.2em;">Issues</th>
   </tr>
  </thead>
   <tr>
    <td style="padding: 0.2em;">1</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/99340">dawehner</a>
   </td>
    <td style="padding: 0.2em;">560</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">2</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/108450">DamienMcKenna</a>
   </td>
    <td style="padding: 0.2em;">448</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">3</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/157725">alexpott</a>
   </td>
    <td style="padding: 0.2em;">409</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">4</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/214652">Berdir</a>
   </td>
    <td style="padding: 0.2em;">383</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">5</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/99777">Wim Leers</a>
   </td>
    <td style="padding: 0.2em;">382</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">6</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/155601">jhodgdon</a>
   </td>
    <td style="padding: 0.2em;">381</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">7</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/160302">joelpittet</a>
   </td>
    <td style="padding: 0.2em;">294</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">8</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/2833651">heykarthikwithu</a>
   </td>
    <td style="padding: 0.2em;">293</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">9</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/2416470">mglaman</a>
   </td>
    <td style="padding: 0.2em;">292</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">10</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/205582">drunken monkey</a>
   </td>
    <td style="padding: 0.2em;">248</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">11</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/1485048">Sam152</a>
   </td>
    <td style="padding: 0.2em;">237</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">12</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/2393360">borisson_</a>
   </td>
    <td style="padding: 0.2em;">207</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">13</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/1852732">benjy</a>
   </td>
    <td style="padding: 0.2em;">206</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">14</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/3189199">edurenye</a>
   </td>
    <td style="padding: 0.2em;">184</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">15</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/35733">catch</a>
   </td>
    <td style="padding: 0.2em;">180</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">16</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/744628">slashrsm</a>
   </td>
    <td style="padding: 0.2em;">179</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">17</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/205645">phenaproxima</a>
   </td>
    <td style="padding: 0.2em;">177</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">18</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/3149657">mbovan</a>
   </td>
    <td style="padding: 0.2em;">174</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">19</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/241634">tim.plunkett</a>
   </td>
    <td style="padding: 0.2em;">168</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">20</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/1177822">rakesh.gectcr</a>
   </td>
    <td style="padding: 0.2em;">163</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">21</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/2659379">martin107</a>
   </td>
    <td style="padding: 0.2em;">163</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">22</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/266527">dsnopek</a>
   </td>
    <td style="padding: 0.2em;">152</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">23</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/4420">mikeryan</a>
   </td>
    <td style="padding: 0.2em;">150</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">24</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/208732">jhedstrom</a>
   </td>
    <td style="padding: 0.2em;">149</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">25</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/65776">xjm</a>
   </td>
    <td style="padding: 0.2em;">147</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">26</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/314031">hussainweb</a>
   </td>
    <td style="padding: 0.2em;">147</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">27</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/551886">stefan.r</a>
   </td>
    <td style="padding: 0.2em;">146</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">28</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/86106">bojanz</a>
   </td>
    <td style="padding: 0.2em;">145</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">29</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/959536">penyaskito</a>
   </td>
    <td style="padding: 0.2em;">141</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">30</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/395439">larowlan</a>
   </td>
    <td style="padding: 0.2em;">135</td>
  </tr>
 </table>
</small>

### How much of the work is sponsored?

As mentioned above, from July 1, 2015 to June 30, 2016, 659 organizations contributed code to Drupal.org. Drupal is used by more than one million websites. The vast majority of the organizations behind these Drupal websites never participate in the development of Drupal; they use the software as it is and do not feel the need to help drive its development.

Technically, Drupal started out as a 100% volunteer-driven project. But nowadays, the data suggests that the majority of the code on Drupal.org is sponsored by organizations in Drupal's ecosystem. For example, of the 32,711 commit credits we studied, 69% of the credited work is "sponsored".

We then looked at the distribution of how many of the credits are given to volunteers versus given to individuals doing "sponsored work" (i.e. contributing as part of their paid job):

[image drupal/contributions-top-range-2016 resize=false]

Looking at the top 100 contributors, for example, 23% of their credits are the result of contributing as volunteers and 56% of their credits are attributed to a corporate sponsor. The remainder, roughly 21% of the credits, are not attributed. Attribution is optional so this means it could either be volunteer-driven, sponsored, or both.

As can be seen on the graph, the ratio of volunteer versus sponsored don't meaningfully change as we look beyond the top 100–the only thing that changes is that more credits that are not attributed. This might be explained by the fact that occasional contributors might not be aware of or understand the credit system, or could not be bothered with setting up organizational profiles for their employer or customers.

As shown in jamadar's screenshot above, a credit can be marked as volunteer and sponsored at the same time. This could be the case when someone does the minimum required work to satisfy the customer's need, but uses his or her spare time to add extra functionality. We can also look at the amount of code credits that are exclusively volunteer credits. Of the 7,874 credits that marked volunteer, 43% of them (3,376 credits) only had the volunteer box checked and 57% of them (4,498) were also partially sponsored. These 3,376 credits are one of our best metrics to measure volunteer-only contributions. This suggests that only 10% of the 32,711 commit credits we examined were contributed exclusively by volunteers. This number is a stark contrast to the 12,888 credits that were "purely sponsored", and that account for 39% of the total credits. In other words, there were roughly four times as many "purely sponsored" credits as there were "purely volunteer" credits.

When we looked at the 5,196 users, rather than credits, we found somewhat different results. A similar percentage of all users had exclusively volunteer credits: 14% (741 users). But the percentage of users with exclusively sponsored credits is only 50% higher: 21% (1077 users). Thus, when we look at the data this way, we find that users who only do sponsored work tend to contribute quite a bit more than users who only do volunteer work.

None of these methodologies are perfect, but they all point to a conclusion that most of the work on Drupal is sponsored. At the same time, the data shows that volunteer contribution remains very important to Drupal. We believe there is a healthy ratio between sponsored and volunteer contributions.

### Who is sponsoring the work?

Because we established that most of the work on Drupal is sponsored, we know it is important to track and study what organizations contribute to Drupal. Despite 659 different organizations contributing to Drupal, approximately 50% of them got 4 credits or less. The top 30 organizations (roughly top 5%) account for about 29% of the total credits, which suggests that the top 30 companies play a crucial role in the health of the Drupal project. The graph below shows the top 30 organizations and the number of credits they received between July 1, 2015 and June 30, 2016:

[image drupal/contributions-top-30-organizations-2016 resize=false]

While not immediately obvious from the graph above, different types of companies are active in Drupal's ecosystem and we propose the following categorization below to discuss our ecosystem.

<table>
  <thead>
   <tr>
    <th>Category</th>
    <th>Description</th>
  </tr>
 </thead>
  <tr>
   <td>Traditional Drupal businesses</td>
   <td>Small-to-medium-sized professional services companies that make money primarily using Drupal. They typically employ less than 100 employees, and because they specialize in Drupal, many of these professional services companies contribute frequently and are a huge part of our community. Examples are Lullabot (shown on graph) or Chapter Three (shown on graph).</td>
 </tr>
  <tr>
   <td>Digital marketing agencies</td>
   <td>Larger full-service agencies that have marketing led practices using a variety of tools, typically including Drupal, Adobe Experience Manager, Sitecore, WordPress, etc.  They are typically larger, with the larger agencies employing thousands of people.  Examples are Sapient (shown on graph) or AKQA.</td>
 </tr>
  <tr>
   <td>System integrators</td>
   <td>Larger companies that specialize in bringing together different technologies into one solution.  Example system agencies are Accenture, TATA Consultancy Services, Capgemini or CI&amp;T.</td>
 </tr>
  <tr>
   <td>Technology and infrastructure companies</td>
   <td>Examples are Acquia (shown on graph), Lingotek (shown on graph), BlackMesh, RackSpace, Pantheon or Platform.sh.</td>
 </tr>
  <tr>
   <td>End-users</td>
   <td>Examples are Pfizer (shown on graph), Examiner.com (shown on graph) or NBC Universal.</td>
 </tr>
</table>

Most of the top 30 sponsors are traditional Drupal companies. Sapient (120 credits) is the only digital marketing agency showing up in the top 30. No system integrator shows up in the top 30. The first system integrator is CI&amp;T, which ranked 31st with 102 credits. As far as system integrators are concerned CI&amp;T is a smaller player with between 1,000 and 5,000 employees. Other system integrators with credits are Capgemini (43 credits), Globant (26 credits), and TATA Consultancy Services (7 credits). We didn't see any code contributions from Accenture, Wipro or IBM Global Services. We expect these will come as most of them are building out Drupal practices. For example, we know that IBM Global Services already has over 100 people doing Drupal work.

[image drupal/contributions-by-organization-type-2016 resize=false]

When we look beyond the top 30 sponsors, we see that roughly 82% of the code contribution on Drupal.org comes from the traditional Drupal businesses. About 13% of the contributions comes from infrastructure and software companies, though that category is mostly dominated by one company, Acquia. This means that the technology and infrastructure companies, digital marketing agencies, system integrators and end-users are not meaningfully contributing code to Drupal.org today. In an ideal world, the pie chart above would be sliced in equal sized parts.

How can we explain that unbalance? We believe the two biggest reasons are: (1) Drupal's strategic importance and (2) the level of maturity with Drupal and Open Source. Various of the traditional Drupal agencies have been involved with Drupal for 10 years and almost entirely depend on Drupal. Given both their expertise and dependence on Drupal, they are most likely to look after Drupal's development and well-being. These organizations are typically recognized as Drupal experts and sought out by organizations that want to build a Drupal website. Contrast this with most of the digital marketing agencies and system integrators who have the size to work with a diversified portfolio of content management platforms, and are just getting started with Drupal and Open Source. They deliver digital marketing solutions and aren't necessarily sought out for their Drupal expertise. As their Drupal practices grow in size and importance, this could change, and when it does, we expect them to contribute more. Right now many of the digital marketing agencies and system integrators have little or no experience with Open Source so it is important that we motivate them to contribute and then teach them how to contribute.

There are two main business reasons for organizations to contribute: (1) it improves their ability to sell and win deals and (2) it improves their ability to hire. Companies that contribute to Drupal tend to promote their contributions in RFPs and sales pitches to win more deals. Contributing to Drupal also results in being recognized as a great place to work for Drupal experts.

We also should note that many organizations in the Drupal community contribute for reasons that would not seem to be explicitly economically motivated. More than 100 credits were sponsored by colleges or universities, such as the University of Waterloo (45 credits). More than 50 credits came from community groups, such as the Drupal Bangalore Community and the Drupal Ukraine Community. Other nonprofits and government organization that appeared in our data include the Drupal Association (166), National Virtual Library of India (25 credits), Center for Research Libraries (20), and Welsh Government (9 credits).

#### Infrastructure and software companies

Infrastructure and software companies play a different role in our community. These companies are less reliant on professional services (building Drupal websites) and primarily make money from selling subscription based products.

Acquia, Pantheon and Platform.sh are venture-backed Platform-as-a-Service companies born out of the Drupal community. Rackspace and AWS are public companies hosting thousands of Drupal sites each. Lingotek offers cloud-based translation management software for Drupal.

[image drupal/contributions-by-technology-companies-2016 resize=false]

The graph above suggests that Pantheon and Platform.sh have barely contributed code on Drupal.org during the past year. (Platform.sh only became an independent company 6 months ago after they split off from CommerceGuys.) The chart also does not reflect sponsored code contributions on GitHub (such as drush), Drupal event sponsorship, and the wide variety of value that these companies add to Drupal and other Open Source communities.

Consequently, these data show that the Drupal community needs to do a better job of enticing infrastructure and software companies to contribute code to Drupal.org. The Drupal community has a long tradition of encouraging organizations to share code on Drupal.org rather than keep it behind firewalls. While the spirit of the Drupal project cannot be reduced to any single ideology-- not every organization can or will share their code – we would like to see organizations continue to prioritize collaboration over individual ownership. Our aim is not to criticize those who do not contribute, but rather to help foster an environment worthy of contribution.

#### End users

We saw two end-users in the top 30 corporate sponsors: Pfizer (158 credits) and Examiner.com (132 credits). Other notable end-users that are actively giving back are Workday (52 credits), NBC Universal (40 credits), the University of Waterloo (45 credits) and CARD.com (33 credits). The end users that tend to contribute to Drupal use Drupal for a key part of their business and often have an internal team of Drupal developers.

Given that there are hundreds of thousands of Drupal end-users, we would like to see more end-users in the top 30 sponsors. We recognize that a lot of digital agencies don't want, or are not legally allowed, to attribute their customers. We hope that will change as Open Source continues to get more and more adopted.

Given the vast amount of Drupal users, we believe encouraging end-users to contribute could be a big opportunity. Being credited on Drupal.org gives them visibility in the Drupal community and recognizes them as a great place for Open Source developers to work.

### The uneasy alliance with corporate contributions

As mentioned above, when community-driven Open Source projects grow, there becomes a bigger need for organizations to help drive its development. It almost always creates an uneasy alliance between volunteers and corporations.

This theory played out in the Linux community well before it played out in the Drupal community. The Linux project is 25 years old now has seen a steady increase in the number of corporate contributors for roughly 20 years. While Linux companies like Red Hat and SUSE rank highly on the contribution list, so do non-Linux-centric companies such as Samsung, Intel, Oracle and Google. The major theme in this story is that all of these corporate contributors were using Linux as an integral part of their business.

The 659 organizations that contribute to Drupal (which includes corporations), is roughly three times the number of organizations that sponsor development of the Linux kernel. In fairness, Linux has a different ecosystem than Drupal. The Linux business ecosystem has various large organizations (Red Hat, Google, Intel, IBM and SUSE) for whom Linux is very strategic. As a result, many of them employ dozens of full-time Linux contributors and invest millions of dollars in Linux each year.

In the Drupal community, Acquia has had people dedicated full-time to Drupal starting nine years ago when [it hired Gábor Hojtsy](https://dri.es/first-acquia-employees) to contribute to Drupal core full-time. Today, Acquia has about 10 developers contributing to Drupal full-time. They work on core, contributed modules, security, user experience, performance, best practices, and more. Their work has benefited untold numbers of people around the world, most of whom are not Acquia customers.

In response to Acquia's high level of participation in the Drupal project, as well as to the number of Acquia employees that hold leadership positions, some members of the Drupal community have suggested that Acquia wields its influence and power to control the future of Drupal for its own commercial benefit. But neither of us believe that Acquia should contribute less. Instead, we would like to see more companies provide more leadership to Drupal and meaningfully contribute on Drupal.org.

### Who is sponsoring the top 30 contributors?

<small>
  <table>
   <thead>
    <tr>
      <th style="padding: 0.2em;">Rank</th>
      <th style="padding: 0.2em;">Username</th>
      <th style="padding: 0.2em;">Issues</th>
      <th style="padding: 0.2em;">Volunteer</th>
      <th style="padding: 0.2em;">Sponsored</th>
      <th style="padding: 0.2em;">Not specified</th>
      <th style="padding: 0.2em;">Sponsors</th>
   </tr>
  </thead>
   <tr>
    <td style="padding: 0.2em;">1</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/99340">dawehner</a>
   </td>
    <td style="padding: 0.2em;">560</td>
    <td style="padding: 0.2em;">84.1%</td>
    <td style="padding: 0.2em;">77.7%</td>
    <td style="padding: 0.2em;">9.5%</td>
    <td style="padding: 0.2em;">Drupal Association (182), Chapter Three (179), Tag1 Consulting (160), Cando (6), Acquia (4), Comm-press (1)</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">2</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/108450">DamienMcKenna</a>
   </td>
    <td style="padding: 0.2em;">448</td>
    <td style="padding: 0.2em;">6.9%</td>
    <td style="padding: 0.2em;">76.3%</td>
    <td style="padding: 0.2em;">19.4%</td>
    <td style="padding: 0.2em;">Mediacurrent (342)</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">3</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/157725">alexpott</a>
   </td>
    <td style="padding: 0.2em;">409</td>
    <td style="padding: 0.2em;">0.2%</td>
    <td style="padding: 0.2em;">97.8%</td>
    <td style="padding: 0.2em;">2.2%</td>
    <td style="padding: 0.2em;">Chapter Three (400)</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">4</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/214652">Berdir</a>
   </td>
    <td style="padding: 0.2em;">383</td>
    <td style="padding: 0.2em;">0.0%</td>
    <td style="padding: 0.2em;">95.3%</td>
    <td style="padding: 0.2em;">4.7%</td>
    <td style="padding: 0.2em;">MD Systems (365), Acquia (9)</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">5</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/99777">Wim Leers</a>
   </td>
    <td style="padding: 0.2em;">382</td>
    <td style="padding: 0.2em;">31.7%</td>
    <td style="padding: 0.2em;">98.2%</td>
    <td style="padding: 0.2em;">1.8%</td>
    <td style="padding: 0.2em;">Acquia (375)</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">6</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/155601">jhodgdon</a>
   </td>
    <td style="padding: 0.2em;">381</td>
    <td style="padding: 0.2em;">5.2%</td>
    <td style="padding: 0.2em;">3.4%</td>
    <td style="padding: 0.2em;">91.3%</td>
    <td style="padding: 0.2em;">Drupal Association (13), Poplar ProductivityWare (13)</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">7</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/160302">joelpittet</a>
   </td>
    <td style="padding: 0.2em;">294</td>
    <td style="padding: 0.2em;">23.8%</td>
    <td style="padding: 0.2em;">1.4%</td>
    <td style="padding: 0.2em;">76.2%</td>
    <td style="padding: 0.2em;">Drupal Association (4)</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">8</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/2833651">heykarthikwithu</a>
   </td>
    <td style="padding: 0.2em;">293</td>
    <td style="padding: 0.2em;">99.3%</td>
    <td style="padding: 0.2em;">100.0%</td>
    <td style="padding: 0.2em;">0.0%</td>
    <td style="padding: 0.2em;">Valuebound (293), Drupal Bangalore Community (3)</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">9</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/2416470">mglaman</a>
   </td>
    <td style="padding: 0.2em;">292</td>
    <td style="padding: 0.2em;">9.6%</td>
    <td style="padding: 0.2em;">96.9%</td>
    <td style="padding: 0.2em;">0.7%</td>
    <td style="padding: 0.2em;">Commerce Guys (257), Bluehorn Digital (14), Gaggle.net, Inc. (12), LivePerson, Inc (11), Bluespark (5), DPCI (3), Thinkbean, LLC (3), Digital Bridge Solutions (2), Matsmart (1)</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">10</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/205582">drunken monkey</a>
   </td>
    <td style="padding: 0.2em;">248</td>
    <td style="padding: 0.2em;">75.4%</td>
    <td style="padding: 0.2em;">55.6%</td>
    <td style="padding: 0.2em;">2.0%</td>
    <td style="padding: 0.2em;">Acquia (72), StudentFirst (44), epiqo (12), Vizala (9), Sunlime IT Services GmbH (1)</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">11</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/1485048">Sam152</a>
   </td>
    <td style="padding: 0.2em;">237</td>
    <td style="padding: 0.2em;">75.9%</td>
    <td style="padding: 0.2em;">89.5%</td>
    <td style="padding: 0.2em;">10.1%</td>
    <td style="padding: 0.2em;">PreviousNext (210), Code Drop (2)</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">12</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/2393360">borisson_</a>
   </td>
    <td style="padding: 0.2em;">207</td>
    <td style="padding: 0.2em;">62.8%</td>
    <td style="padding: 0.2em;">36.2%</td>
    <td style="padding: 0.2em;">15.9%</td>
    <td style="padding: 0.2em;">Acquia (67), Intracto digital agency (8)</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">13</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/1852732">benjy</a>
   </td>
    <td style="padding: 0.2em;">206</td>
    <td style="padding: 0.2em;">0.0%</td>
    <td style="padding: 0.2em;">98.1%</td>
    <td style="padding: 0.2em;">1.9%</td>
    <td style="padding: 0.2em;">PreviousNext (168), Code Drop (34)</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">14</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/3189199">edurenye</a>
   </td>
    <td style="padding: 0.2em;">184</td>
    <td style="padding: 0.2em;">0.0%</td>
    <td style="padding: 0.2em;">100.0%</td>
    <td style="padding: 0.2em;">0.0%</td>
    <td style="padding: 0.2em;">MD Systems (184)</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">15</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/35733">catch</a>
   </td>
    <td style="padding: 0.2em;">180</td>
    <td style="padding: 0.2em;">3.3%</td>
    <td style="padding: 0.2em;">44.4%</td>
    <td style="padding: 0.2em;">54.4%</td>
    <td style="padding: 0.2em;">Third and Grove (44), Tag1 Consulting (36), Drupal Association (4)</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">16</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/744628">slashrsm</a>
   </td>
    <td style="padding: 0.2em;">179</td>
    <td style="padding: 0.2em;">12.8%</td>
    <td style="padding: 0.2em;">96.6%</td>
    <td style="padding: 0.2em;">2.8%</td>
    <td style="padding: 0.2em;">Examiner.com (89), MD Systems (84), Acquia (18), Studio Matris (1)</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">17</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/205645">phenaproxima</a>
   </td>
    <td style="padding: 0.2em;">177</td>
    <td style="padding: 0.2em;">0.0%</td>
    <td style="padding: 0.2em;">94.4%</td>
    <td style="padding: 0.2em;">5.6%</td>
    <td style="padding: 0.2em;">Acquia (167)</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">18</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/3149657">mbovan</a>
   </td>
    <td style="padding: 0.2em;">174</td>
    <td style="padding: 0.2em;">7.5%</td>
    <td style="padding: 0.2em;">100.0%</td>
    <td style="padding: 0.2em;">0.0%</td>
    <td style="padding: 0.2em;">MD Systems (118), ACTO Team (43), Google Summer of Code (13)</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">19</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/241634">tim.plunkett</a>
   </td>
    <td style="padding: 0.2em;">168</td>
    <td style="padding: 0.2em;">14.3%</td>
    <td style="padding: 0.2em;">89.9%</td>
    <td style="padding: 0.2em;">10.1%</td>
    <td style="padding: 0.2em;">Acquia (151)</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">20</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/1177822">rakesh.gectcr</a>
   </td>
    <td style="padding: 0.2em;">163</td>
    <td style="padding: 0.2em;">100.0%</td>
    <td style="padding: 0.2em;">100.0%</td>
    <td style="padding: 0.2em;">0.0%</td>
    <td style="padding: 0.2em;">Valuebound (138), National Virtual Library of India (NVLI) (25)</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">21</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/2659379">martin107</a>
   </td>
    <td style="padding: 0.2em;">163</td>
    <td style="padding: 0.2em;">4.9%</td>
    <td style="padding: 0.2em;">0.0%</td>
    <td style="padding: 0.2em;">95.1%</td>
    <td style="padding: 0.2em;">
   </td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">22</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/266527">dsnopek</a>
   </td>
    <td style="padding: 0.2em;">152</td>
    <td style="padding: 0.2em;">0.7%</td>
    <td style="padding: 0.2em;">0.0%</td>
    <td style="padding: 0.2em;">99.3%</td>
    <td style="padding: 0.2em;">
   </td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">23</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/4420">mikeryan</a>
   </td>
    <td style="padding: 0.2em;">150</td>
    <td style="padding: 0.2em;">0.0%</td>
    <td style="padding: 0.2em;">89.3%</td>
    <td style="padding: 0.2em;">10.7%</td>
    <td style="padding: 0.2em;">Acquia (112), Virtuoso Performance (22), Drupalize.Me (4), North Studio (4)</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">24</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/208732">jhedstrom</a>
   </td>
    <td style="padding: 0.2em;">149</td>
    <td style="padding: 0.2em;">0.0%</td>
    <td style="padding: 0.2em;">83.2%</td>
    <td style="padding: 0.2em;">16.8%</td>
    <td style="padding: 0.2em;">Phase2 (124), Workday, Inc. (36), Memorial Sloan Kettering Cancer Center (4)</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">25</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/65776">xjm</a>
   </td>
    <td style="padding: 0.2em;">147</td>
    <td style="padding: 0.2em;">0.0%</td>
    <td style="padding: 0.2em;">81.0%</td>
    <td style="padding: 0.2em;">19.0%</td>
    <td style="padding: 0.2em;">Acquia (119)</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">26</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/314031">hussainweb</a>
   </td>
    <td style="padding: 0.2em;">147</td>
    <td style="padding: 0.2em;">2.0%</td>
    <td style="padding: 0.2em;">98.6%</td>
    <td style="padding: 0.2em;">1.4%</td>
    <td style="padding: 0.2em;">Axelerant (145)</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">27</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/551886">stefan.r</a>
   </td>
    <td style="padding: 0.2em;">146</td>
    <td style="padding: 0.2em;">0.7%</td>
    <td style="padding: 0.2em;">0.7%</td>
    <td style="padding: 0.2em;">98.6%</td>
    <td style="padding: 0.2em;">Drupal Association (1)</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">28</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/86106">bojanz</a>
   </td>
    <td style="padding: 0.2em;">145</td>
    <td style="padding: 0.2em;">2.1%</td>
    <td style="padding: 0.2em;">83.4%</td>
    <td style="padding: 0.2em;">15.2%</td>
    <td style="padding: 0.2em;">Commerce Guys (121), Bluespark (2)</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">29</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/959536">penyaskito</a>
   </td>
    <td style="padding: 0.2em;">141</td>
    <td style="padding: 0.2em;">6.4%</td>
    <td style="padding: 0.2em;">95.0%</td>
    <td style="padding: 0.2em;">3.5%</td>
    <td style="padding: 0.2em;">Lingotek (129), Cocomore AG (5)</td>
  </tr>
   <tr>
    <td style="padding: 0.2em;">30</td>
    <td style="padding: 0.2em;">
      <a href="https://www.drupal.org/user/395439">larowlan</a>
   </td>
    <td style="padding: 0.2em;">135</td>
    <td style="padding: 0.2em;">34.1%</td>
    <td style="padding: 0.2em;">63.0%</td>
    <td style="padding: 0.2em;">16.3%</td>
    <td style="padding: 0.2em;">PreviousNext (85), Department of Justice &amp; Regulation, Victoria (14), amaysim Australia Ltd. (1), University of Adelaide (1)</td>
  </tr>
 </table>
</small>

We observe that the top 30 contributors are sponsored by 45 organizations. This kind of diversity is aligned with our desire not to see Drupal controlled by a single organization. The top 30 contributors and the 45 organizations are from many different parts in the world and work with customers large or small. We could still benefit from more diversity, though. The top 30 lacks digital marketing agencies, large system integrators and end-users – all of whom could contribute meaningfully to making Drupal for them and others.

### Evolving the credit system

The credit system gives us quantifiable data about where our community's contributions come from, but that data is not perfect. Here are a few suggested improvements:

1. We need to find ways to recognize non-code contributions as well as code contributions outside of Drupal.org (i.e. on GitHub). Lots of people and organizations spend hundreds of hours putting together local events, writing documentation, translating Drupal, mentoring new contributors, and more–and [none of that gets captured by the credit system](https://www.drupal.org/node/2649100).
2. We'd benefit by finding a way to account for the complexity and quality of contributions; one person might have worked several weeks for just one credit, while another person might have gotten a credit for 30 minutes of work. We could, for example, consider the issue credit data in conjunction with Git commit data regarding insertions, deletions, and files changed.
3. We could try to leverage the credit system to encourage more companies, especially those that do not contribute today, to participate in large-scale initiatives. Dries presented some ideas two years ago in [his DrupalCon Amsterdam keynote](https://dri.es/state-of-drupal-presentation-september-2014) and Matthew has [suggested other ideas](https://www.lullabot.com/articles/better-then-bigger-cultivating-the-drupal-community), but we are open to more suggestions on how we might bring more contributors into the fold using the credit system.
4. We could segment out organization profiles between end users and different kinds of service providers. Doing so would make it easier to see who the top contributors are in each segment and perhaps foster more healthy competition among peers. In turn, the community could learn about the peculiar motivations within each segment.

Like Drupal the software, the credit system on Drupal.org is a tool that can evolve, but that ultimately will only be useful when the community uses it, understands its shortcomings, and suggests constructive improvements. In highlighting the organizations that sponsor work on Drupal.org, we hope to provoke responses that help evolve the credit system into something that incentivizes business to sponsor more work and that allows more people the opportunity to participate in our community, learn from others, teach newcomers, and make positive contributions. We view Drupal as a productive force for change and we wish to use the credit system to highlight (at least some of) the work of our diverse community of volunteers, companies, nonprofits, governments, schools, universities, individuals, and other groups.

### Conclusion

Our data shows that Drupal is a vibrant and diverse community, with thousands of contributors, that is constantly evolving and improving the software. While here we have examined issue credits mostly through the lens of sponsorship, in future analyses we plan to consider the same issue credits in conjunction with other publicly-disclosed Drupal user data, such as gender identification, geography, seasonal participation, mentorship, and event attendance.

Our analysis of the Drupal.org credit data concludes that most of the contributions to Drupal are sponsored. At the same time, the data shows that volunteer contribution remains very important to Drupal.

As a community, we need to understand that a healthy Open Source ecosystem is a diverse ecosystem that includes more than traditional Drupal agencies. The traditional Drupal agencies and Acquia contribute the most but we don't see a lot of contribution from the larger digital marketing agencies, system integrators, technology companies, or end-users of Drupal–we believe that might come as these organizations build out their Drupal practices and Drupal becomes more strategic for them.

To grow and sustain Drupal, we should support those that contribute to Drupal, and find ways to get those that are not contributing involved in our community. We invite you to help us figure out how we can continue to strengthen our ecosystem.

*We hope to repeat this work in 1 or 2 years' time so we can track our evolution. Special thanks to [Tim Lehnen](https://www.drupal.org/u/hestenet) (Drupal Association) for providing us the credit system data and supporting us during our research.*
