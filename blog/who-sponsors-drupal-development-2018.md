---
title: 'Who sponsors Drupal development? (2017-2018 edition)'
date: '2018-09-11T01:01:42-04:00'
author: Dries
summary: "An in-depth analysis of how Drupal's development was sponsored between July 1, 2017 and June 30, 2018."
image: drupal/contributions-top-30-organizations-2018
tags:
  - Drupal
  - 'Open Source'
  - Diversity
  - 'Drupal sponsors'
published: true
type: blog
url: /who-sponsors-drupal-development-2018
id: 4506
---

***Update 1:** The most recent version of this post is available at [Who sponsors Drupal development? (2018-2019 edition)](https://dri.es/who-sponsors-drupal-development-2019). For a list of all previous versions, see <https://dri.es/tag/drupal-sponsors>.*

***Update 2:** The company "Drupal Partners" has not complied with the [Drupal trademark policy](https://www.drupal.org/about/trademark) and has not responded to our repeated outreach.*

For the past two years, I've examined Drupal.org's commit data to understand who develops Drupal, how much of that work is sponsored, and where that sponsorship comes from.

I have now reported on this data for three years in a row, which means I can start to better compare year-over-year data. Understanding how an open-source project works is important because it establishes a benchmark for project health and scalability.

I would also recommend taking a look at the [2016 report](https://dri.es/who-sponsors-drupal-development) or the [2017 report](https://dri.es/who-sponsors-drupal-development-2017). Each report looks at data collected in the 12-month period between July 1st and June 30th.

This year's report affirms that Drupal has a large and diverse community of contributors. In the 12-month period between July 1, 2017 and June 30, 2018, 7,287 different individuals and 1,002 different organizations contributed code to Drupal.org. This include contributions to Drupal core and all contributed projects on Drupal.org.

In comparison to last year's report, both the number of contributors and contributions has increased. Our community of contributors (including both individuals and organizations) is also becoming more diverse. This is an important area of growth, but there is still work to do.

For this report, we looked at all of the issues marked "closed" or "fixed" in our ticketing system in the 12-month period from July 1, 2017 to June 30, 2018. This includes Drupal core and all of the contributed projects on Drupal.org, across all major versions of Drupal. This year, 24,447 issues were marked "closed" or "fixed", a 5% increase from the 23,238 issues in the 2016-2017 period. **This averages out to 67 feature improvements or bug fixes a day.**

In total, we captured 49,793 issue credits across all 24,447 issues. This marks a 17% increase from the [42,449 issue credits recorded in the previous year](https://dri.es/who-sponsors-drupal-development-2017). Of the 49,793 issue credits reported this year, 18% (8,822 credits) were for Drupal core, while 82% (40,971 credits) went to contributed projects.

"Closed" or "fixed" issues are often the result of multiple people working on the issue. We try to capture who contributes through Drupal.org's unique credit system. We used the data from the credit system for this analysis. There are a few limitations with this approach, which we'll address at the end of this report.

### What is the Drupal.org credit system?

In the spring of 2015, after [proposing ideas for giving credit](https://dri.es/a-method-for-giving-credit-to-organizations-that-contribute-code-to-open-source) and [discussing various approaches at length](https://www.drupal.org/node/2288727), Drupal.org added the ability for people to [attribute their work](https://www.drupal.org/drupalorg/blog/a-guide-to-issue-credits-and-the-drupal.org-marketplace) to an organization or customer in the Drupal.org issue queues. Maintainers of Drupal modules, themes, and distributions can award issue credits to people who help resolve issues with code, translations, documentation, design and more.

[image drupal/example-issue-credit-on-drupal-org-2016 resize=false]

Credits are a powerful motivator for both individuals and organizations. Accumulating credits provides individuals with a way to showcase their expertise. Organizations can utilize credits to help recruit developers, to increase their visibility within the [Drupal.org marketplace](https://www.drupal.org/drupal-services), or to showcase their Drupal expertise.

### Who is working on Drupal?

In the 12-month period between July 1, 2017 to June 30, 2018, Drupal.org received code contributions from 7,287 different individuals and 1,002 different organizations.

[image drupal/contributions-by-individuals-vs-organizations-2018 resize=false]

While the number of individual contributors rose, a relatively small number of individuals still do the majority of the work. Approximately 48% of individual contributors received just one credit. Meanwhile, the top 30 contributors (the top 0.4%) account for more than 24% of the total credits. These individuals put an incredible amount of time and effort in developing Drupal and its contributed projects:

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
    <td>1</td>
    <td>
      <a href="https://www.drupal.org/u/renatog">RenatoG</a>
   </td>
    <td>851</td>
  </tr>
   <tr>
    <td>2</td>
    <td>
      <a href="https://www.drupal.org/u/rajabnatshah">RajabNatshah</a>
   </td>
    <td>745</td>
  </tr>
   <tr>
    <td>3</td>
    <td>
      <a href="https://www.drupal.org/u/jrockowitz">jrockowitz</a>
   </td>
    <td>700</td>
  </tr>
   <tr>
    <td>4</td>
    <td>
      <a href="https://www.drupal.org/u/adriancid">adriancid</a>
   </td>
    <td>529</td>
  </tr>
   <tr>
    <td>5</td>
    <td>
      <a href="https://www.drupal.org/u/bojanz">bojanz</a>
   </td>
    <td>515</td>
  </tr>
   <tr>
    <td>6</td>
    <td>
      <a href="https://www.drupal.org/u/berdir">Berdir</a>
   </td>
    <td>432</td>
  </tr>
   <tr>
    <td>7</td>
    <td>
      <a href="https://www.drupal.org/u/alexpott">alexpott</a>
   </td>
    <td>414</td>
  </tr>
   <tr>
    <td>8</td>
    <td>
      <a href="https://www.drupal.org/u/mglaman">mglaman</a>
   </td>
    <td>414</td>
  </tr>
   <tr>
    <td>9</td>
    <td>
      <a href="https://www.drupal.org/u/wim-leers">Wim Leers</a>
   </td>
    <td>395</td>
  </tr>
   <tr>
    <td>10</td>
    <td>
      <a href="https://www.drupal.org/u/larowlan">larowlan</a>
   </td>
    <td>360</td>
  </tr>
   <tr>
    <td>11</td>
    <td>
      <a href="https://www.drupal.org/u/damienmckenna">DamienMcKenna</a>
   </td>
    <td>353</td>
  </tr>
   <tr>
    <td>12</td>
    <td>
      <a href="https://www.drupal.org/u/dawehner">dawehner</a>
   </td>
    <td>340</td>
  </tr>
   <tr>
    <td>13</td>
    <td>
      <a href="https://www.drupal.org/u/catch">catch</a>
   </td>
    <td>339</td>
  </tr>
   <tr>
    <td>14</td>
    <td>
      <a href="https://www.drupal.org/u/heddn">heddn</a>
   </td>
    <td>327</td>
  </tr>
   <tr>
    <td>15</td>
    <td>
      <a href="https://www.drupal.org/u/xjm">xjm</a>
   </td>
    <td>303</td>
  </tr>
   <tr>
    <td>16</td>
    <td>
      <a href="https://www.drupal.org/u/pifagor">pifagor</a>
   </td>
    <td>284</td>
  </tr>
   <tr>
    <td>17</td>
    <td>
      <a href="https://www.drupal.org/u/quietone">quietone</a>
   </td>
    <td>261</td>
  </tr>
   <tr>
    <td>18</td>
    <td>
      <a href="https://www.drupal.org/u/borisson_">borisson_</a>
   </td>
    <td>255</td>
  </tr>
   <tr>
    <td>19</td>
    <td>
      <a href="https://www.drupal.org/u/adci_contributor">adci_contributor</a>
   </td>
    <td>255</td>
  </tr>
   <tr>
    <td>20</td>
    <td>
      <a href="https://www.drupal.org/u/volkswagenchick">volkswagenchick</a>
   </td>
    <td>254</td>
  </tr>
   <tr>
    <td>21</td>
    <td>
      <a href="https://www.drupal.org/u/drunken-monkey">drunken monkey</a>
   </td>
    <td>231</td>
  </tr>
   <tr>
    <td>22</td>
    <td>
      <a href="https://www.drupal.org/u/amateescu">amateescu</a>
   </td>
    <td>225</td>
  </tr>
   <tr>
    <td>23</td>
    <td>
      <a href="https://www.drupal.org/u/joachim">joachim</a>
   </td>
    <td>199</td>
  </tr>
   <tr>
    <td>24</td>
    <td>
      <a href="https://www.drupal.org/u/mkalkbrenner">mkalkbrenner</a>
   </td>
    <td>195</td>
  </tr>
   <tr>
    <td>25</td>
    <td>
      <a href="https://www.drupal.org/u/chrfritsch">chr.fritsch</a>
   </td>
    <td>185</td>
  </tr>
   <tr>
    <td>26</td>
    <td>
      <a href="https://www.drupal.org/u/gauravkapoor">gaurav.kapoor</a>
   </td>
    <td>178</td>
  </tr>
   <tr>
    <td>27</td>
    <td>
      <a href="https://www.drupal.org/u/phenaproxima">phenaproxima</a>
   </td>
    <td>177</td>
  </tr>
   <tr>
    <td>28</td>
    <td>
      <a href="https://www.drupal.org/u/mikeytown2">mikeytown2</a>
   </td>
    <td>173</td>
  </tr>
   <tr>
    <td>29</td>
    <td>
      <a href="https://www.drupal.org/u/joelpittet">joelpittet</a>
   </td>
    <td>170</td>
  </tr>
   <tr>
    <td>30</td>
    <td>
      <a href="https://www.drupal.org/u/timmillwood">timmillwood</a>
   </td>
    <td>169</td>
  </tr>
 </table>
</small>

Out of the top 30 contributors featured, 15 were also recognized as top contributors in [our 2017 report](https://dri.es/who-sponsors-drupal-development-2017). These Drupalists' dedication and continued contribution to the project has been crucial to Drupal's development. It's also exciting to see 15 new names on the list. This mobility is a testament to the community's evolution and growth. It's also important to recognize that a majority of the 15 repeat top contributors are at least partially sponsored by an organization. We value the organizations that sponsor these remarkable individuals, because without their support, it could be more challenging to be in the top 30 year over year.

### How diverse is Drupal?

Next, we looked at both the gender and geographic diversity of Drupal.org code contributors. While these are only two examples of diversity, this is the only available data that contributors can currently choose to share on their Drupal.org profiles. The reported data shows that only 7% of the recorded contributions were made by contributors that do not identify as male, which continues to indicate a steep gender gap. This is a one percent increase compared to last year. The gender imbalance in Drupal is profound and underscores the need to continue fostering diversity and inclusion in our community.

To address this gender gap, in addition to advancing representation across various demographics, the Drupal community is supporting two important initiatives. The first is to adopt more inclusive user demographic forms on Drupal.org. Adopting Open Demographics on Drupal.org will also allow us to improve reporting on diversity and inclusion, which in turn will help us better support initiatives that advance diversity and inclusion. The second initiative is supporting the Drupal Diversity and Inclusion Contribution Team, which works to better include underrepresented groups to increase code and community contributions. The DDI Contribution Team recruits team members from diverse backgrounds and underrepresented groups, and provides support and mentorship to help them contribute to Drupal.

It's important to reiterate that supporting diversity and inclusion within Drupal is essential to the health and success of the project. The people who work on Drupal should reflect the diversity of people who use and work with the software. While there is still a lot of work to do, I'm excited about the impact these various initiatives will have on future reports.

[image drupal/contributions-by-gender-2018 resize=false]

When measuring geographic diversity, we saw individual contributors from 6 different continents and 123 different countries:

[image drupal/contributions-by-continent-2018 resize=false]

[image drupal/contributions-by-country-2018 resize=false]

123 different countries is seven more compared to the 2017 report. The new countries include Rwanda, Namibia, Senegal, Sierra Leone, and Swaziland, Zambia. Seeing contributions from more African countries is certainly a highlight.

### How much of the work is sponsored?

Issue credits can be marked as "volunteer" and "sponsored" simultaneously (shown in jamadar's screenshot near the top of this post). This could be the case when a contributor does the minimum required work to satisfy the customer's need, in addition to using their spare time to add extra functionality.

While Drupal started out as a 100% volunteer-driven project, today the majority of the code on Drupal.org is sponsored by organizations. Only 12% of the commit credits that we examined in 2017-2018 were "purely volunteer" credits (6,007 credits), in stark contrast to the 49% that were "purely sponsored". In other words, there were four times as many "purely sponsored" credits as "purely volunteer" credits.

[image drupal/contributions-by-volunteer-vs-sponsored-2018 resize=false]

A few comparisons between the 2017-2018 and the 2016-2017 data:

- **The credit system is being used more frequently.** In total, we captured 49,793 issue credits across all 24,447 issues in the 2017-2018 period. This marks a 17% increase from the [42,449 issue credits recorded in the previous year](https://dri.es/who-sponsors-drupal-development-2017). Between July 1, 2016 and June 30, 2017, 28% of all credits had no attribution while in the period between July 1, 2017 to June 30, 2018, only 25% of credits lacked attribution. More people have become aware of the credit system, the attribution options, and their benefits.
- **Sponsored credits are growing faster than volunteer credits.** Both "purely volunteer" and "purely sponsored" credits grew, but "purely sponsored" credits grew faster. There are two reasons why this could be the case: (1) more contributions are sponsored and (2) organizations are more likely to use the credit system compared to volunteers.

No data is perfect, but it feels safe to conclude that most of the work on Drupal is sponsored. At the same time, the data shows that volunteer contribution remains very important to Drupal. Maybe most importantly, while the number of volunteers and sponsors has grown year over year in absolute terms, sponsored contributions appear to be growing faster than volunteer contributions. This is consistent with [how open source projects grow and scale](https://dri.es/scaling-open-source-communities).

### Who is sponsoring the work?

Now that we've established a majority of contributions to Drupal are sponsored, we want to study which organizations contribute to Drupal. While 1,002 different organizations contributed to Drupal, approximately 50% of them received four credits or less. The top 30 organizations (roughly the top 3%) account for approximately 30% of the total credits, which implies that the top 30 companies play a crucial role in the health of the Drupal project. The graph below shows the top 30 organizations and the number of credits they received between July 1, 2017 and June 30, 2018:

[image drupal/contributions-top-30-organizations-2018 resize=false]

While not immediately obvious from the graph above, a variety of different types of companies are active in Drupal's ecosystem:

<table>
  <thead>
   <tr>
    <th>Category</th>
    <th>Description</th>
  </tr>
 </thead>
  <tr>
   <td>Traditional Drupal businesses</td>
   <td>Small-to-medium-sized professional services companies that primarily make money using Drupal. They typically employ fewer than 100 employees, and because they specialize in Drupal, many of these professional services companies contribute frequently and are a huge part of our community. Examples are Chapter Three and Lullabot (both shown on graph).</td>
 </tr>
  <tr>
   <td>Digital marketing agencies</td>
   <td>Larger full-service agencies that have marketing-led practices using a variety of tools, typically including Drupal, Adobe Experience Manager, Sitecore, WordPress, etc. They tend to be larger, with the larger agencies employing thousands of people. Examples are Wunderman and Mirum.</td>
 </tr>
  <tr>
   <td>System integrators</td>
   <td>Larger companies that specialize in bringing together different technologies into one solution. Example system agencies are Accenture, TATA Consultancy Services, Capgemini and CI&amp;T (shown on graph).</td>
 </tr>
  <tr>
   <td>Technology and infrastructure companies</td>
   <td>Examples are Acquia (shown on graph), Lingotek, BlackMesh, Rackspace, Pantheon and Platform.sh.</td>
 </tr>
  <tr>
   <td>End-users</td>
   <td>Examples are Pfizer (shown on graph) or NBCUniversal.</td>
 </tr>
</table>

A few observations:

- Almost all of the sponsors in the top 30 are traditional Drupal businesses. Companies like MD Systems (12 employees), Valuebound (58 employees), Chapter Three (33 employees), Commerce Guys (13 employees) and PreviousNext (22 employees) are, despite their size, critical to Drupal's success.
- Compared to these traditional Drupal businesses, Acquia has nearly 800 employees and at least ten full-time Drupal contributors. Acquia works to resolve some of the most complex issues on Drupal.org, many of which are not recognized by the credit system (e.g. release management, communication, sprint organizing, and project coordination). Acquia added several full-time contributors compared to last year, however, I believe that Acquia should contribute even more due to its comparative size.
- No digital marketing agencies show up in the top 30, though some of them are starting to contribute. It's exciting that an increasing number of digital marketing agencies are delivering beautiful experiences using Drupal. As a community, we need to work to ensure that each of these firms are contributing back to the project with the same commitment that we see from firms like Commerce Guys, CI&amp;T or Acro Media. Compared to last year, we have not made meaningful progress on growing contributions from digital marketing agencies. It would be interesting to see what would happen if more large organizations mandated contributions from their partners. Pfizer, for example, only works with agencies and vendors that contribute back to Drupal, and requires that its agency partners contribute to open source. If more organizations took this stance, it could have a big impact on the number of digital agencies that contribute to Drupal
- The only system integrator in the top 30 is CI&amp;T, which ranked 3rd with 959 credits. As far as system integrators are concerned, CI&amp;T is a smaller player with approximately 2,500 employees. However, we do see various system integrators outside of the top 30, including Globant, Capgemini, Sapient and TATA Consultancy Services. Each of these system integrators reported 30 to 85 credits in the past year. The top contributor is TATA with 85 credits.
- Infrastructure and software companies also play an important role in our community, yet only Acquia appears in the top 30. While Acquia has a professional services division, more than 75% of the contributions come from the product organization. Other infrastructure companies include Pantheon and Platform.sh, which are both venture-backed, platform-as-a-service companies that were born from the Drupal community. Pantheon has 6 credits and Platform.sh has 47 credits. Amazee Labs, a company that is building an infrastructure business, reported 40 credits. Compared to last year, Acquia and Rackspace have slightly more credits, while Pantheon, Platform.sh and Amazee contributed less. Lingotek, a vendor that offers cloud-based translation management software has 84 credits.
- We also saw three end-users in the top 30 as corporate sponsors: Pfizer (491 credits, up from 251 credits the year before), Thunder (432 credits), and the German company, bio.logis (319 credits, up from 212 credits the year before). Other notable customers outside of the top 30, include Workday, Wolters Kluwer, Burda Media, YMCA and OpenY, CARD.com and NBCUniversal. We also saw contributions from many universities, including University of Colorado Boulder, University of Waterloo, Princeton University, University of Adelaide, University of Sydney, University of Edinburgh, McGill University and more.

[image drupal/contributions-by-technology-companies-2018 resize=false]

We can conclude that technology and infrastructure companies, digital marketing agencies, system integrators and end-users are not making significant code contributions to Drupal.org today. How can we explain this disparity in comparison to the traditional Drupal businesses that contribute the most? We believe the biggest reasons are:

1. **Drupal's strategic importance.** A variety of the traditional Drupal agencies almost entirely depend on Drupal to support their businesses. Given both their expertise and dependence on Drupal, they are most likely to look after Drupal's development and well-being. Contrast this with most of the digital marketing agencies and system integrators who work with a diversified portfolio of content management platforms. Their well-being is less dependent on Drupal's success.
2. **The level of experience with Drupal and open source.** Drupal aside, many organizations have little or no experience with open source, so it is important that we motivate and teach them to contribute.
3. **Legal reservations.** We recognize that some organizations are not legally permitted to contribute, let alone attribute their customers. We hope that will change as open source continues to get adopted.
4. **Tools barriers.** Drupal contribution still involves a patch-based workflow on Drupal.org's unique issue queue system. This presents a fairly steep learning curve to most developers, who primarily work with more modern and common tools such as GitHub. We hope to lower some of these barriers through [our collaboration with GitLab](https://about.gitlab.com/2018/08/16/drupal-moves-to-gitlab/).
5. **Process barriers.** Getting code changes accepted into a Drupal project – especially Drupal core – is hard work. Peer reviews, gates such as automated testing and documentation, required sign-offs from maintainers and committers, knowledge of best practices and other community norms are a few of the challenges a contributor must face to get code accepted into Drupal. Collaborating with thousands of people on a project as large and widely-used as Drupal requires such processes, but new contributors often don't know that these processes exist, or don't understand *why* they exist.

### We should do more to entice contribution

Drupal is used by more than one million websites. Everyone who uses Drupal benefits from work that thousands of other individuals and organizations have contributed. Drupal is great because it is continuously improved by a diverse community of contributors who are enthusiastic to give back.

However, the vast majority of the individuals and organizations behind these Drupal websites never participate in the development of the project. They might use the software as it is or don't feel the need to help drive its development. We have to provide more incentive for these individuals and organizations to contribute back to the project.

Consequently, this data shows that the Drupal community can do more to entice companies to contribute code to Drupal.org. The Drupal community has a long tradition of encouraging organizations to share code rather than keep it behind firewalls. While the spirit of the Drupal project cannot be reduced to any single ideology – not every organization can or will share their code – we would like to see organizations continue to prioritize collaboration over individual ownership.

We understand and respect that some can give more than others and that some might not be able to give back at all. Our goal is not to foster an environment that demands what and how others should give back. Our aim is not to criticize those who do not contribute, but rather to help foster an environment worthy of contribution. This is clearly laid out in [Drupal's Values and Principles](https://www.drupal.org/about/values-and-principles).

Given the vast amount of Drupal users, we believe continuing to encourage organizations and end-users to contribute is still a big opportunity. From my own conversations, it's clear that organizations still need education, training and help. They ask questions like: *"Where can we contribute?"*, *"How can we convince our legal department?"*, and more.

There are substantial benefits and business drivers for organizations that contribute: (1) it improves their ability to sell and win deals and (2) it improves their ability to hire. Companies that contribute to Drupal tend to promote their contributions in RFPs and sales pitches. Contributing to Drupal also results in being recognized as a great place to work for Drupal experts.

### What projects have sponsors?

To understand where the organizations sponsoring Drupal put their money, I've listed the top 20 most sponsored projects:

<small>
  <table>
   <thead>
    <tr>
      <th style="padding: 0.2em;">Rank</th>
      <th style="padding: 0.2em;">Project name</th>
      <th style="padding: 0.2em;">Issues</th>
   </tr>
  </thead>
   <tr>
    <td>1</td>
    <td>
      <a href="https://www.drupal.org/project/drupal">Drupal core</a>
   </td>
    <td>5919</td>
  </tr>
   <tr>
    <td>2</td>
    <td>
      <a href="https://www.drupal.org/project/webform">Webform</a>
   </td>
    <td>905</td>
  </tr>
   <tr>
    <td>3</td>
    <td>
      <a href="https://www.drupal.org/project/commerce">Drupal Commerce</a>
   </td>
    <td>607</td>
  </tr>
   <tr>
    <td>4</td>
    <td>
      <a href="https://www.drupal.org/project/varbase">Varbase: The Ultimate Drupal 8 CMS Starter Kit (Bootstrap Ready)</a>
   </td>
    <td>551</td>
  </tr>
   <tr>
    <td>5</td>
    <td>
      <a href="https://www.drupal.org/project/commerce_pos">Commerce Point of Sale (POS)</a>
   </td>
    <td>324</td>
  </tr>
   <tr>
    <td>6</td>
    <td>
      <a href="https://www.drupal.org/project/views">Views</a>
   </td>
    <td>318</td>
  </tr>
   <tr>
    <td>7</td>
    <td>
      <a href="https://www.drupal.org/project/commerce_migrate">Commerce Migrate</a>
   </td>
    <td>307</td>
  </tr>
   <tr>
    <td>8</td>
    <td>
      <a href="https://www.drupal.org/project/jsonapi">JSON API</a>
   </td>
    <td>304</td>
  </tr>
   <tr>
    <td>9</td>
    <td>
      <a href="https://www.drupal.org/project/paragraphs">Paragraphs</a>
   </td>
    <td>272</td>
  </tr>
   <tr>
    <td>10</td>
    <td>
      <a href="https://www.drupal.org/project/social">Open Social</a>
   </td>
    <td>222</td>
  </tr>
   <tr>
    <td>11</td>
    <td>
      <a href="https://www.drupal.org/project/search_api_solr">Search API Solr Search</a>
   </td>
    <td>212</td>
  </tr>
   <tr>
    <td>12</td>
    <td>
      <a href="https://www.drupal.org/project/janrain_connect">Drupal Connector for Janrain Identity Cloud</a>
   </td>
    <td>197</td>
  </tr>
   <tr>
    <td>13</td>
    <td>
      <a href="https://www.drupal.org/project/projectapplications">Drupal.org security advisory coverage applications</a>
   </td>
    <td>189</td>
  </tr>
   <tr>
    <td>14</td>
    <td>
      <a href="https://www.drupal.org/project/facets">Facets</a>
   </td>
    <td>171</td>
  </tr>
   <tr>
    <td>15</td>
    <td>
      <a href="https://www.drupal.org/project/openy">Open Y</a>
   </td>
    <td>162</td>
  </tr>
   <tr>
    <td>16</td>
    <td>
      <a href="https://www.drupal.org/project/metatag">Metatag</a>
   </td>
    <td>162</td>
  </tr>
   <tr>
    <td>17</td>
    <td>
      <a href="https://www.drupal.org/project/web_page_archive">Web Page Archive</a>
   </td>
    <td>154</td>
  </tr>
   <tr>
    <td>18</td>
    <td>
      <a href="https://www.drupal.org/project/jsdrupal">Drupal core - JavaScript Modernization Initiative</a>
   </td>
    <td>145</td>
  </tr>
   <tr>
    <td>19</td>
    <td>
      <a href="https://www.drupal.org/project/thunder">Thunder</a>
   </td>
    <td>144</td>
  </tr>
   <tr>
    <td>20</td>
    <td>
      <a href="https://www.drupal.org/project/xmlsitemap">XML sitemap</a>
   </td>
    <td>120</td>
  </tr>
 </table>
</small>

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
    <td>1</td>
    <td>
      <a href="https://www.drupal.org/u/renatog">RenatoG</a>
   </td>
    <td>851</td>
    <td>0%</td>
    <td>100%</td>
    <td>0%</td>
    <td>CI&amp;T (850), Johnson &amp; Johnson (23)</td>
  </tr>
   <tr>
    <td>2</td>
    <td>
      <a href="https://www.drupal.org/u/rajabnatshah">RajabNatshah</a>
   </td>
    <td>745</td>
    <td>14%</td>
    <td>100%</td>
    <td>0%</td>
    <td>Vardot (653), Webship (90)</td>
  </tr>
   <tr>
    <td>3</td>
    <td>
      <a href="https://www.drupal.org/u/jrockowitz">jrockowitz</a>
   </td>
    <td>700</td>
    <td>94%</td>
    <td>97%</td>
    <td>1%</td>
    <td>The Big Blue House (680), Memorial Sloan Kettering Cancer Center (7), Rosewood Marketing (2), Kennesaw State University (1)</td>
  </tr>
   <tr>
    <td>4</td>
    <td>
      <a href="https://www.drupal.org/u/adriancid">adriancid</a>
   </td>
    <td>529</td>
    <td>99%</td>
    <td>19%</td>
    <td>0%</td>
    <td>Ville de Montréal (98)</td>
  </tr>
   <tr>
    <td>5</td>
    <td>
      <a href="https://www.drupal.org/u/bojanz">bojanz</a>
   </td>
    <td>515</td>
    <td>0%</td>
    <td>98%</td>
    <td>2%</td>
    <td>Commerce Guys (503), Torchbox (17), Adapt (6), Acro Media (4), Bluespark (1)</td>
  </tr>
   <tr>
    <td>6</td>
    <td>
      <a href="https://www.drupal.org/u/berdir">Berdir</a>
   </td>
    <td>432</td>
    <td>0%</td>
    <td>92%</td>
    <td>8%</td>
    <td>MD Systems (396), Translations.com (10), Acquia (2)</td>
  </tr>
   <tr>
    <td>7</td>
    <td>
      <a href="https://www.drupal.org/u/alexpott">alexpott</a>
   </td>
    <td>414</td>
    <td>13%</td>
    <td>84%</td>
    <td>10%</td>
    <td>Chapter Three (123), Thunder (120), Acro Media (103)</td>
  </tr>
   <tr>
    <td>8</td>
    <td>
      <a href="https://www.drupal.org/u/mglaman">mglaman</a>
   </td>
    <td>414</td>
    <td>5%</td>
    <td>96%</td>
    <td>1%</td>
    <td>Commerce Guys (393), Impactiv (17), Circle Web Foundry (16), Rosewood Marketing (14), LivePerson (13), Bluespark (4), Acro Media (4), Gaggle.net (3), Thinkbean (2), Matsmart (2)</td>
  </tr>
   <tr>
    <td>9</td>
    <td>
      <a href="https://www.drupal.org/u/wim-leers">Wim Leers</a>
   </td>
    <td>395</td>
    <td>8%</td>
    <td>94%</td>
    <td>0%</td>
    <td>Acquia (371)</td>
  </tr>
   <tr>
    <td>10</td>
    <td>
      <a href="https://www.drupal.org/u/larowlan">larowlan</a>
   </td>
    <td>360</td>
    <td>13%</td>
    <td>97%</td>
    <td>1%</td>
    <td>PreviousNext (350), University of Technology, Sydney (24), Charles Darwin University (10), Australian Competition and Consumer Commission (ACCC) (1), Department of Justice &amp; Regulation, Victoria (1)</td>
  </tr>
   <tr>
    <td>11</td>
    <td>
      <a href="https://www.drupal.org/u/damienmckenna">DamienMcKenna</a>
   </td>
    <td>353</td>
    <td>1%</td>
    <td>95%</td>
    <td>5%</td>
    <td>Mediacurrent (334)</td>
  </tr>
   <tr>
    <td>12</td>
    <td>
      <a href="https://www.drupal.org/u/dawehner">dawehner</a>
   </td>
    <td>340</td>
    <td>48%</td>
    <td>86%</td>
    <td>4%</td>
    <td>Chapter Three (279), Torchbox (10), Drupal Association (5), Tag1 Consulting (3), Acquia (2), TES Global (1)</td>
  </tr>
   <tr>
    <td>13</td>
    <td>
      <a href="https://www.drupal.org/u/catch">catch</a>
   </td>
    <td>339</td>
    <td>1%</td>
    <td>97%</td>
    <td>3%</td>
    <td>Third and Grove (320), Tag1 Consulting (8)</td>
  </tr>
   <tr>
    <td>14</td>
    <td>
      <a href="https://www.drupal.org/u/heddn">heddn</a>
   </td>
    <td>327</td>
    <td>2%</td>
    <td>99%</td>
    <td>1%</td>
    <td>MTech (325)</td>
  </tr>
   <tr>
    <td>15</td>
    <td>
      <a href="https://www.drupal.org/u/xjm">xjm</a>
   </td>
    <td>303</td>
    <td>0%</td>
    <td>97%</td>
    <td>3%</td>
    <td>Acquia (293)</td>
  </tr>
   <tr>
    <td>16</td>
    <td>
      <a href="https://www.drupal.org/u/pifagor">pifagor</a>
   </td>
    <td>284</td>
    <td>32%</td>
    <td>99%</td>
    <td>1%</td>
    <td>GOLEMS GABB (423), Drupal Ukraine Community (73)</td>
  </tr>
   <tr>
    <td>17</td>
    <td>
      <a href="https://www.drupal.org/u/quietone">quietone</a>
   </td>
    <td>261</td>
    <td>48%</td>
    <td>55%</td>
    <td>5%</td>
    <td>Acro Media (143)</td>
  </tr>
   <tr>
    <td>18</td>
    <td>
      <a href="https://www.drupal.org/u/borisson_">borisson_</a>
   </td>
    <td>255</td>
    <td>93%</td>
    <td>55%</td>
    <td>3%</td>
    <td>Dazzle (136), Intracto digital agency (1), Acquia (1), DUG BE vzw (Drupal User Group Belgium) (1)</td>
  </tr>
   <tr>
    <td>19</td>
    <td>
      <a href="https://www.drupal.org/u/adci_contributor">adci_contributor</a>
   </td>
    <td>255</td>
    <td>0%</td>
    <td>100%</td>
    <td>0%</td>
    <td>ADCI Solutions (255)</td>
  </tr>
   <tr>
    <td>20</td>
    <td>
      <a href="https://www.drupal.org/u/volkswagenchick">volkswagenchick</a>
   </td>
    <td>254</td>
    <td>1%</td>
    <td>100%</td>
    <td>0%</td>
    <td>Hook 42 (253)</td>
  </tr>
   <tr>
    <td>21</td>
    <td>
      <a href="https://www.drupal.org/u/drunken-monkey">drunken monkey</a>
   </td>
    <td>231</td>
    <td>91%</td>
    <td>22%</td>
    <td>0%</td>
    <td>DBC (24), Vizala (20), Sunlime Web Innovations GmbH (4), Wunder Group (1), epiqo (1), Zebralog (1)</td>
  </tr>
   <tr>
    <td>22</td>
    <td>
      <a href="https://www.drupal.org/u/amateescu">amateescu</a>
   </td>
    <td>225</td>
    <td>3%</td>
    <td>95%</td>
    <td>3%</td>
    <td>Pfizer (211), Drupal Association (1), Chapter Three (1)</td>
  </tr>
   <tr>
    <td>23</td>
    <td>
      <a href="https://www.drupal.org/u/joachim">joachim</a>
   </td>
    <td>199</td>
    <td>56%</td>
    <td>44%</td>
    <td>19%</td>
    <td>Torchbox (88)</td>
  </tr>
   <tr>
    <td>24</td>
    <td>
      <a href="https://www.drupal.org/u/mkalkbrenner">mkalkbrenner</a>
   </td>
    <td>195</td>
    <td>0%</td>
    <td>99%</td>
    <td>1%</td>
    <td>bio.logis (193), OSCE: Organization for Security and Co-operation in Europe (119)</td>
  </tr>
   <tr>
    <td>25</td>
    <td>
      <a href="https://www.drupal.org/u/chrfritsch">chr.fritsch</a>
   </td>
    <td>185</td>
    <td>0%</td>
    <td>99%</td>
    <td>1%</td>
    <td>Thunder (183)</td>
  </tr>
   <tr>
    <td>26</td>
    <td>
      <a href="https://www.drupal.org/u/gauravkapoor">gaurav.kapoor</a>
   </td>
    <td>178</td>
    <td>0%</td>
    <td>81%</td>
    <td>19%</td>
    <td>OpenSense Labs (144), DrupalFit (55)</td>
  </tr>
   <tr>
    <td>27</td>
    <td>
      <a href="https://www.drupal.org/u/phenaproxima">phenaproxima</a>
   </td>
    <td>177</td>
    <td>0%</td>
    <td>99%</td>
    <td>1%</td>
    <td>Acquia (176)</td>
  </tr>
   <tr>
    <td>28</td>
    <td>
      <a href="https://www.drupal.org/u/mikeytown2">mikeytown2</a>
   </td>
    <td>173</td>
    <td>0%</td>
    <td>0%</td>
    <td>100%</td>
    <td>
   </td>
  </tr>
   <tr>
    <td>29</td>
    <td>
      <a href="https://www.drupal.org/u/joelpittet">joelpittet</a>
   </td>
    <td>170</td>
    <td>28%</td>
    <td>74%</td>
    <td>16%</td>
    <td>The University of British Columbia (125)</td>
  </tr>
   <tr>
    <td>30</td>
    <td>
      <a href="https://www.drupal.org/u/timmillwood">timmillwood</a>
   </td>
    <td>169</td>
    <td>1%</td>
    <td>100%</td>
    <td>0%</td>
    <td>Pfizer (169), Appnovation  (163), Millwood Online (6)</td>
  </tr>
 </table>
</small>

We observe that the top 30 contributors are sponsored by 58 organizations. This kind of diversity is aligned with our desire to make sure that Drupal is not controlled by a single organization. These top contributors and organizations are from many different parts of the world, and work with customers large and small. Nonetheless, we will continue to benefit from an increased distribution of contribution.

### Limitations of the credit system and the data

While the benefits are evident, it is important to note a few of the limitations in Drupal.org's current credit system:

- Contributing to issues on Drupal.org is not the only way to contribute. Other activities, such as sponsoring events, promoting Drupal, and providing help and mentorship are also important to the long-term health of the Drupal project. Many of these activities are not currently captured by the credit system. For this post, we chose to only look at code contributions.
- We acknowledge that parts of Drupal are developed on GitHub and therefore aren't fully credited on Drupal.org. The actual number of contributions and contributors could be significantly higher than what we report. The Drupal Association is working to integrate GitLab with Drupal.org. GitLab will provide support for "merge requests", which means contributing to Drupal will feel more familiar to the broader audience of open source contributors who learned their skills in the post-patch era. Some of GitLab's tools, such as inline editing and web-based code review, will also lower the barrier to contribution, and should help us grow both the number of contributions and contributors on Drupal.org.
- Even when development is done on Drupal.org, the credit system is not used consistently. As using the credit system is optional, a lot of code committed on Drupal.org has no or incomplete contribution credits.
- Not all code credits are the same. We currently don't have a way to account for the complexity and quality of contributions; one person might have worked several weeks for just one credit, while another person might receive a credit for ten minutes of work. In the future, we should consider issuing credit data in conjunction with issue priority, patch size, etc. This could help incentivize people to work on larger and more important problems and save coding standards improvements for new contributor sprints. Implementing a scoring system that ranks the complexity of an issue would also allow us to develop more accurate reports of contributed work.

Like Drupal itself, the Drupal.org credit system needs to continue to evolve. Ultimately, the credit system will only be useful when the community uses it, understands its shortcomings, and suggests constructive improvements.

### Conclusion

Our data confirms that Drupal is a vibrant community full of contributors who are constantly evolving and improving the software. While we have amazing geographic diversity, we still need greater gender diversity, in addition to better representation across various demographic groups. Our analysis of the Drupal.org credit data concludes that most contributions to Drupal are sponsored. At the same time, the data shows that volunteer contribution remains very important to Drupal.

As a community, we need to understand that a healthy open source ecosystem includes more than the traditional Drupal businesses that contribute the most. We still don't see a lot of contribution from the larger digital marketing agencies, system integrators, technology companies, or end-users of Drupal – we believe that might come as these organizations build out their Drupal practices and Drupal becomes more strategic for them.

To grow and sustain Drupal, we should support those that contribute to Drupal and find ways to get those that are not contributing involved in our community. We invite you to help us continue to strengthen our ecosystem.
