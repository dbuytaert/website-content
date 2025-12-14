---
title: 'Who sponsors Drupal development? (2016-2017 edition)'
date: '2017-09-13T07:46:37-04:00'
author: Dries
summary: "An in-depth analysis of how Drupal's development was sponsored between July 1, 2016 and June 30, 2017."
image: drupal/contributions-top-30-organizations-2017
tags:
  - Drupal
  - 'Open Source'
  - Diversity
  - 'Drupal sponsors'
published: true
type: blog
url: /who-sponsors-drupal-development-2017
id: 4016
---

***Update:** The most recent version of this post is available at [Who sponsors Drupal development? (2018-2019 edition)](https://dri.es/who-sponsors-drupal-development-2019). For a list of all previous versions, see <https://dri.es/tag/drupal-sponsors>.*

Last year, Matthew Tift and I examined Drupal.org's commit data to understand who develops Drupal, how much of that work is sponsored, and where that sponsorship comes from. We published our analysis in a blog post called "[Who Sponsors Drupal Development?](https://dri.es/who-sponsors-drupal-development)". A year later, I wanted to present an update. This year's report will also cover additional data, including gender and geographical diversity, and project sponsorship.

Understanding how an open-source project works is important because it establishes a benchmark for project health and scalability. Scaling an open-source project is a difficult task. As an open-source project's rate of adoption grows, the number of people that benefit from the project also increases. Often the open-source project also becomes more complex as it expands, which means that [the economic reward of helping to improve the project decreases](https://dri.es/state-of-drupal-presentation-september-2014).

A [recent article on the Bitcoin and Ethereum contributor communities](https://medium.com/@FEhrsam/funding-the-evolution-of-blockchains-87d160988481) illustrates this disparity perfectly. Ethereum and Bitcoin have market capitalizations valued at $30 billion and $70 billion, respectively. However, both projects have fewer than 40 meaningful contributors, and contribution isn't growing despite the rising popularity of cryptocurrency.

[image drupal/number-of-bitcoin-contributors-2017 resize=false]

[image drupal/number-of-ethereum-contributors-2017 resize=false]

Drupal, by comparison, has a diverse community of contributors. In the 12-month period between July 1, 2016 to June 30, 2017 we saw code contributions on Drupal.org from 7,240 different individuals and 889 different companies. This does not mean that Drupal is exempt from the challenges of scaling an open-source project. We hope that this report provides transparency about Drupal project development and encourages more individuals and organizations incentive to contribute. We also will highlight areas where our community can and should do better.

### What is the Drupal.org credit system?

In the spring of 2015, after [proposing ideas for giving credit](https://dri.es/a-method-for-giving-credit-to-organizations-that-contribute-code-to-open-source) and [discussing various approaches at length](https://www.drupal.org/node/2288727), Drupal.org added the ability for people to [attribute their work](https://www.drupal.org/drupalorg/blog/a-guide-to-issue-credits-and-the-drupal.org-marketplace) to an organization or customer in the Drupal.org issue queues. Maintainers of Drupal modules, themes and distributions can award issues credits to people who help resolve issues with code, translations, documentation, design and more.

[image drupal/example-issue-credit-on-drupal-org-2016 resize=false]

Credits are a powerful motivator for both individuals and organizations. Accumulating credits provides individuals with a way to showcase their expertise. Organizations can utilize credits to help recruit developers or to increase their visibility in the [Drupal.org marketplace](https://www.drupal.org/drupal-services).

While the benefits are evident, it is important to note a few of the limitations in Drupal.org's current credit system:

- Contributing to issues on Drupal.org is not the only way to contribute. Other activities, such as sponsoring events, promoting Drupal, and providing help and mentorship, are important to the long-term health of the Drupal project. Many of these activities are not currently captured by the credit system. For this post, we chose to only look at code contributions.
- We acknowledge that parts of Drupal are developed on GitHub and therefore aren't fully credited on Drupal.org. The actual number of contributions and contributors could be significantly higher than what we report.
- Even when development is done on Drupal.org, the credit system is not used consistently; because using the credit system is optional, a lot of code committed on Drupal.org has no or incomplete contribution credits.
- Not all code credits are the same. We currently don't have a way to account for the complexity and quality of contributions; one person might have worked several weeks for just one credit, while another person might receive a credit for ten minutes of work. In the future, we should consider issuing credit data in conjunction with issue priority, patch size, etc. We can also reduce the need for trivial credits by [automating patch rerolls](https://www.drupal.org/node/2252787) and [automating coding style fixes](https://www.drupal.org/node/1299710).

### Who is working on Drupal?

For our analysis we looked at all the issues that were marked "closed" or "fixed" in the 12-month period from July 1, 2016 to June 30, 2017. What we learned is that there were 23,238 issues marked "closed" or "fixed", a 22% increase from the 19,095 issues in the 2015-2016 period. Those 23,238 issues had 42,449 issue credits, a 30% increase from the [32,711 issue credits recorded in the previous year](https://dri.es/who-sponsors-drupal-development). Issue credits against Drupal core remained roughly the same year over year, meaning almost all of this growth came from increased activity in contributed projects. This is no surprise. Drupal development is cyclical, and during this period of the Drupal 8 development cycle, most of the Drupal community has been focused on porting modules from Drupal 7 to Drupal 8. Of the 42,449 issue credits reported this year, 20% (8,619 credits) were for Drupal core, while 80% (33,830 credits) went to contributed themes, modules and distributions.

Compared to the previous year, **we also saw an increase in both the number of people contributing and the number of organizations contributing**. Drupal.org received code contributions from 7,240 different individuals and 889 different organizations.

[image drupal/contributions-by-individuals-vs-organizations-2017 resize=false]

While the number of individual contributors rose, a relatively small number of individuals still do the majority of the work. Approximately 47% of individual contributors received just one credit. Meanwhile, the top 30 contributors (the top 0.4%) account for over 17% of the total credits, indicating that these individuals put an incredible amount of time and effort in developing Drupal and its contributed projects:

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
      <a href="https://www.drupal.org/u/jrockowitz">jrockowitz</a>
   </td>
    <td>537</td>
  </tr>
   <tr>
    <td>2</td>
    <td>
      <a href="https://www.drupal.org/u/dawehner">dawehner</a>
   </td>
    <td>421</td>
  </tr>
   <tr>
    <td>3</td>
    <td>
      <a href="https://www.drupal.org/u/renatog">RenatoG</a>
   </td>
    <td>408</td>
  </tr>
   <tr>
    <td>4</td>
    <td>
      <a href="https://www.drupal.org/u/bojanz">bojanz</a>
   </td>
    <td>351</td>
  </tr>
   <tr>
    <td>5</td>
    <td>
      <a href="https://www.drupal.org/u/berdir">Berdir</a>
   </td>
    <td>335</td>
  </tr>
   <tr>
    <td>6</td>
    <td>
      <a href="https://www.drupal.org/u/mglaman">mglaman</a>
   </td>
    <td>334</td>
  </tr>
   <tr>
    <td>7</td>
    <td>
      <a href="https://www.drupal.org/u/wim-leers">Wim Leers</a>
   </td>
    <td>332</td>
  </tr>
   <tr>
    <td>8</td>
    <td>
      <a href="https://www.drupal.org/u/alexpott">alexpott</a>
   </td>
    <td>329</td>
  </tr>
   <tr>
    <td>9</td>
    <td>
      <a href="https://www.drupal.org/u/damienmckenna">DamienMcKenna</a>
   </td>
    <td>245</td>
  </tr>
   <tr>
    <td>10</td>
    <td>
      <a href="https://www.drupal.org/u/jhodgdon">jhodgdon</a>
   </td>
    <td>242</td>
  </tr>
   <tr>
    <td>11</td>
    <td>
      <a href="https://www.drupal.org/u/drunken-monkey">drunken monkey</a>
   </td>
    <td>238</td>
  </tr>
   <tr>
    <td>12</td>
    <td>
      <a href="https://www.drupal.org/u/naveenvalecha">naveenvalecha</a>
   </td>
    <td>196</td>
  </tr>
   <tr>
    <td>13</td>
    <td>
      <a href="https://www.drupal.org/u/munavijayalakshmi">Munavijayalakshmi</a>
   </td>
    <td>192</td>
  </tr>
   <tr>
    <td>14</td>
    <td>
      <a href="https://www.drupal.org/u/borisson_">borisson_</a>
   </td>
    <td>191</td>
  </tr>
   <tr>
    <td>15</td>
    <td>
      <a href="https://www.drupal.org/u/yongt9412">yongt9412</a>
   </td>
    <td>189</td>
  </tr>
   <tr>
    <td>16</td>
    <td>
      <a href="https://www.drupal.org/u/klausi">klausi</a>
   </td>
    <td>185</td>
  </tr>
   <tr>
    <td>17</td>
    <td>
      <a href="https://www.drupal.org/u/sam152">Sam152</a>
   </td>
    <td>184</td>
  </tr>
   <tr>
    <td>18</td>
    <td>
      <a href="https://www.drupal.org/u/miro_dietiker">miro_dietiker</a>
   </td>
    <td>182</td>
  </tr>
   <tr>
    <td>19</td>
    <td>
      <a href="https://www.drupal.org/u/pavan-b-s">Pavan B S</a>
   </td>
    <td>180</td>
  </tr>
   <tr>
    <td>20</td>
    <td>
      <a href="https://www.drupal.org/u/ajay_reddy">ajay_reddy</a>
   </td>
    <td>176</td>
  </tr>
   <tr>
    <td>21</td>
    <td>
      <a href="https://www.drupal.org/u/phenaproxima">phenaproxima</a>
   </td>
    <td>172</td>
  </tr>
   <tr>
    <td>22</td>
    <td>
      <a href="https://www.drupal.org/u/sanchiz">sanchiz</a>
   </td>
    <td>162</td>
  </tr>
   <tr>
    <td>23</td>
    <td>
      <a href="https://www.drupal.org/u/slashrsm">slashrsm</a>
   </td>
    <td>161</td>
  </tr>
   <tr>
    <td>24</td>
    <td>
      <a href="https://www.drupal.org/u/jhedstrom">jhedstrom</a>
   </td>
    <td>155</td>
  </tr>
   <tr>
    <td>25</td>
    <td>
      <a href="https://www.drupal.org/u/xjm">xjm</a>
   </td>
    <td>151</td>
  </tr>
   <tr>
    <td>26</td>
    <td>
      <a href="https://www.drupal.org/u/catch">catch</a>
   </td>
    <td>147</td>
  </tr>
   <tr>
    <td>27</td>
    <td>
      <a href="https://www.drupal.org/u/larowlan">larowlan</a>
   </td>
    <td>145</td>
  </tr>
   <tr>
    <td>28</td>
    <td>
      <a href="https://www.drupal.org/u/rakeshgectcr">rakesh.gectcr</a>
   </td>
    <td>141</td>
  </tr>
   <tr>
    <td>29</td>
    <td>
      <a href="https://www.drupal.org/u/benjy">benjy</a>
   </td>
    <td>139</td>
  </tr>
   <tr>
    <td>30</td>
    <td>
      <a href="https://www.drupal.org/u/dhruveshdtripathi">dhruveshdtripathi</a>
   </td>
    <td>138</td>
  </tr>
 </table>
</small>

Out of the top 30 contributors featured, 19 were also recognized as top contributors in [our 2015-2016 report](https://dri.es/who-sponsors-drupal-development). These Drupalists' dedication and continued contribution to the project has been crucial to Drupal's development. It's also exciting to see 11 new names on the list. This mobility is a testament to the community's evolution and growth.

Next, we looked at both the gender and geographic diversity of Drupal.org code contributors. While these are only two examples of diversity, this is the only available data that contributors can choose to share on their Drupal.org profiles. The reported data shows that only 6% of the recorded contributions were made by contributors that identify as female, which indicates a steep gender gap. Like in most open-source projects, the gender imbalance in Drupal is profound and underscores the need to continue fostering diversity and inclusion in our community.

[image drupal/contributions-by-gender-2017 resize=false]

When measuring geographic diversity, we saw individual contributors from 6 different continents and 116 different countries:

[image drupal/contributions-by-continent-2017 resize=false]
[image drupal/contributions-by-country-2017 resize=false]

### How much of the work is sponsored?

Drupal is used by more than one million websites. The vast majority of the individuals and organizations behind these Drupal websites never participate in the development of the project. They might use the software as it is or might not feel the need to help drive its development. We have to provide more incentive for these individuals and organizations to contribute back to the project.

Issue credits can be marked as "volunteer" and "sponsored" simultaneously (shown in jamadar's screenshot near the top of this post). This could be the case when a contributor does the minimum required work to satisfy the customer's need, in addition to using their spare time to add extra functionality.

While Drupal started out as a 100% volunteer-driven project, today the majority of the code on Drupal.org is sponsored by organizations. Only 11% of the commit credits that we examined in 2016-2017 were "purely volunteer" credits (4,498 credits), in stark contrast to the 46% that were "purely sponsored". In other words, there were four times as many "purely sponsored" credits as "purely volunteer" credits.

A few comparisons with the 2015-2016 data:

- **The credit system is used more.** Between July 1, 2015 and June 30, 2016, 37% of all credits had no attribution while in the more recent period between July 1, 2016 to June 30, 2017, only 28% of credits lacked attribution. More people have become aware of the credit system, the attribution options, and their benefits.
- **Sponsored credits are growing faster than volunteer credits.** Both "purely volunteer" and "purely sponsored" credits grew, but "purely sponsored" credits grew faster. There are two reasons why this could be the case: (1) more contributions are sponsored and (2) organizations are more likely to use the credit system compared to volunteers.

[image drupal/contributions-by-volunteer-vs-sponsored-2017 resize=false]

No data is perfect, but it feels safe to conclude that most of the work on Drupal is sponsored. At the same time, the data shows that volunteer contribution remains very important to Drupal. Maybe most importantly, while the number of volunteers and sponsors has grown year over year in absolute terms, sponsored contributions appear to be growing faster than volunteer contributions. This is consistent with [how open source projects grow and scale](https://dri.es/scaling-open-source-communities).

### Who is sponsoring the work?

Now that we have established that most of the work on Drupal is sponsored, we want to study which organizations contribute to Drupal. While 889 different organizations contributed to Drupal, approximately 50% of them received four credits or fewer. The top 30 organizations (roughly the top 3%) account for about 48% of the total credits, which implies that the top 30 companies play a crucial role in the health of the Drupal project. The graph below shows the top 30 organizations and the number of credits they received between July 1, 2016 and June 30, 2017:

[image drupal/contributions-top-30-organizations-2017 resize=false]

While not immediately obvious from the graph above, different types of companies are active in Drupal's ecosystem:

<table>
  <thead>
   <tr>
    <th>Category</th>
    <th>Description</th>
  </tr>
 </thead>
  <tr>
   <td>Traditional Drupal businesses</td>
   <td>Small-to-medium-sized professional services companies that make money primarily using Drupal. They typically employ fewer than 100 employees, and because they specialize in Drupal, many of these professional services companies contribute frequently and are a huge part of our community. Examples are Chapter Three (shown on graph) and Lullabot (shown on graph).</td>
 </tr>
  <tr>
   <td>Digital marketing agencies</td>
   <td>Larger full-service agencies that have marketing-led practices using a variety of tools, typically including Drupal, Adobe Experience Manager, Sitecore, WordPress, etc. They tend to be larger, with the larger agencies employing thousands of people. Examples are Wunderman and Mirum.</td>
 </tr>
  <tr>
   <td>System integrators</td>
   <td>Larger companies that specialize in bringing together different technologies into one solution. Example system agencies are Accenture, TATA Consultancy Services, Capgemini and CI&amp;T.</td>
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

- Almost all of the sponsors in the top 30 are traditional Drupal businesses. Companies like MD Systems (12 employees), Valuebound (34 employees), Chapter Three (27 employees), Commerce Guys (7 employees) and PreviousNext (20 employees) are, despite their size, critical to Drupal's success.
   
   It's worth highlighting MD Systems, which ranks second in the list of the top 30 contributing organizations, and is the number-one contributor among traditional Drupal businesses. What distinguishes MD Systems from most others is that it has embedded contribution into its corporate philosophy. For every commercial project, [MD Systems invests 20% of that project's value back into Drupal](https://www.md-systems.ch/en/blog/md-systems/2016/09/28/we-are-striving-to-invest-20-of-every-projects-value-back-into-the). They believe that using commercial projects as the foundation for community contribution leads to more meaningful and healthier contributions for Drupal and a lower total cost of ownership for their customers. This is different from other organizations, where employees are allotted a number of hours per month to contribute outside of customer-facing projects. There is no denying that MD Systems has had a tremendous impact on the Drupal community with contributions that are both frequent and impactful.
- Compared to these traditional Drupal businesses, Acquia has nearly 800 employees and several full-time Drupal contributors. Acquia's [Office of the CTO (OCTO)](https://dri.es/announcing-the-office-of-the-cto-at-acquia) works to resolve some of the most complex issues on Drupal.org, many of which are not recognized by the credit system (e.g. release management, communication, sprint organizing, and project coordination). However, I believe that Acquia should contribute even more due to our comparative size.
- No digital marketing agencies show up in the top 30, though some of them are starting to contribute. It is exciting that an increasing number of digital marketing agencies are delivering beautiful experiences using Drupal. As a community, we need to work to ensure that each of these firms are contributing back to the project with the same commitment that we see from firms like Chapter Three, MD Systems or CI&amp;T.
- The only system integrator in the top 30 is CI&amp;T, which ranked 6th with 664 credits. As far as system integrators are concerned, CI&amp;T is a smaller player with approximately 2,500 employees. However, we do see various system integrators outside of the top 30, including Globant, Capgemini, Sapient and TATA Consultancy Services. Each of these system integrators reported 30 to 70 credits in the past year. Finally, Wipro began contributing this year with 2 credits. We expect, or hope, to see system integrators contribute more and more, especially given the number of Drupal developers they employ. Many have sizable Drupal practices with hundreds of Drupal developers, yet contributing to open source is relatively new and often not well-understood.
- Infrastructure and software companies play an important role in our community, yet only Acquia appears in the top 30. While Acquia has a professional services division, 75% of the contributions come from the product organization (including the [Office of the CTO](https://dri.es/announcing-the-office-of-the-cto-at-acquia) and the [Acquia Lightning team](https://www.drupal.org/project/lightning)). Other contributing infrastructure companies include Pantheon and Platform.sh, which are both venture-backed platform-as-a-service companies that originated from the Drupal community. Pantheon has 17 credits and Platform.sh has 47 credits. Amazee Labs, who is building an infrastructure business, reported 51 credits. Rackspace is a public company hosting thousands of Drupal sites; they have 48 credits. Lingotek offers cloud-based translation management software and has 94 credits.
- We saw two end-users in the top 30 corporate sponsors: Pfizer (251 credits, up from 158 credits the year before) and the German company bio.logis (212 credits). Other notable customers outside of the top 30 were Workday, Wolters Kluwer, Burda Media, University of Colorado Boulder, YMCA and OpenY, CARD.com and NBCUniversal.

[image drupal/contributions-by-technology-companies-2017 resize=false]

We can conclude that technology and infrastructure companies, digital marketing agencies, system integrators and end-users are not meaningfully contributing code to Drupal.org today. How can we explain this disparity in comparison to traditional Drupal businesses who contribute the most? We believe the biggest reasons are:

1. **Drupal's strategic importance.** A variety of the traditional Drupal agencies have been involved with Drupal for 10 years and almost entirely depend on Drupal to support their business. Given both their expertise and dependence on Drupal, they are most likely to look after Drupal's development and well-being. These organizations are typically recognized as Drupal experts and are sought out by organizations that want to build a Drupal website. Contrast this with most of the digital marketing agencies and system integrators who are sized to work with a diversified portfolio of content management platforms and who are historically only getting started with Drupal and open source. They deliver digital marketing solutions and aren't necessarily sought out for their Drupal expertise. As their Drupal practices grow in size and importance, this could change. In fact, contributing to Drupal can help grow their Drupal business because it helps their name stand out as Drupal experts and gives them a competitive edge with their customers.
2. **The level of experience with Drupal and open source.** Drupal aside, many organizations have little or no experience with open source, so it is important that we motivate and teach them to contribute.
3. **Legal reservations.** We recognize that some organizations are not legally permitted to contribute, let alone attribute their customers. We hope that will change as open source continues to get adopted.
4. **Tools and process barriers.** Drupal contribution still involves a patch-based workflow on Drupal.org's unique issue queue system. This presents a fairly steep learning curve to most developers, who primarily work with more modern and common tools such as GitHub. Getting the code change proposal uploaded is just the first step; **getting code changes *accepted* into an upstream Drupal project – especially Drupal core – is hard work**. Peer reviews, gates such as automated testing and documentation, required sign-offs from maintainers and committers, knowledge of best practices and other community norms are a few of the challenges a contributor must face to get code accepted into Drupal.

Consequently, this data shows that the Drupal community can do more to entice companies to contribute code to Drupal.org. The Drupal community has a long tradition of encouraging organizations to share code rather than keep it behind firewalls. While the spirit of the Drupal project cannot be reduced to any single ideology – not every organization can or will share their code – we would like to see organizations continue to prioritize collaboration over individual ownership. **Our aim is not to criticize those who do not contribute, but rather to help foster an environment worthy of contribution.** Given the vast amount of Drupal users, we believe continuing to encourage organizations and end-users to contribute could be a big opportunity.

There are substantial benefits and business drivers for organizations that contribute: (1) it improves their ability to sell and win deals and (2) it improves their ability to hire. Companies that contribute to Drupal tend to promote their contributions in RFPs and sales pitches. Contributing to Drupal also results in being recognized as a great place to work for Drupal experts.

### The uneasy alliance with corporate contributions

As mentioned above, when community-driven open-source projects grow, there is [a bigger need for organizations to help drive their development](https://dri.es/the-commercialization-of-a-volunteer-driven-open-source-project). It almost always creates an uneasy alliance between volunteers and corporations.

This theory played out in the Linux community well before it played out in the Drupal community. The Linux project is 25 years old and has seen a steady increase in the number of corporate contributors for roughly 20 years. While Linux companies like Red Hat and SUSE rank high on the contribution list, so do non-Linux-centric companies such as Samsung, Intel, Oracle and Google. All of these corporate contributors are (or were) using Linux as an integral part of their business.

The 889 organizations that contribute to Drupal (which includes corporations) is more than four times the number of organizations that sponsor development of the Linux kernel. This is significant because Linux is considered "one of the largest cooperative software projects ever attempted". In fairness, Linux has a different ecosystem than Drupal. The Linux business ecosystem has various large organizations (Red Hat, Google, Intel, IBM and SUSE) for whom Linux is very strategic. As a result, many of them employ dozens of full-time Linux contributors and invest millions of dollars in Linux each year.

### What projects have sponsors?

In total, the Drupal community worked on 3,183 different projects (modules, themes and distributions) in the 12-month period between July 1, 2016 to June 30, 2017. To understand where the organizations sponsoring Drupal put their money, I've listed the top 20 most sponsored projects:

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
    <td>4745</td>
  </tr>
   <tr>
    <td>2</td>
    <td>
      <a href="https://www.drupal.org/project/commerce">Drupal Commerce</a> (distribution)</td>
      <td>526</td>
   </tr>
    <tr>
      <td>3</td>
      <td>
       <a href="https://www.drupal.org/project/webform">Webform</a>
     </td>
      <td>361</td>
   </tr>
    <tr>
      <td>4</td>
      <td>
       <a href="https://www.drupal.org/project/openy">Open Y</a> (distribution)</td>
       <td>324</td>
     </tr>
      <tr>
       <td>5</td>
       <td>
        <a href="https://www.drupal.org/project/paragraphs">Paragraphs</a>
      </td>
       <td>231</td>
     </tr>
      <tr>
       <td>6</td>
       <td>
        <a href="https://www.drupal.org/project/inmail">Inmail</a>
      </td>
       <td>223</td>
     </tr>
      <tr>
       <td>7</td>
       <td>
        <a href="https://www.drupal.org/project/user_guide">User guide</a>
      </td>
       <td>218</td>
     </tr>
      <tr>
       <td>8</td>
       <td>
        <a href="https://www.drupal.org/project/jsonapi">JSON API</a>
      </td>
       <td>204</td>
     </tr>
      <tr>
       <td>9</td>
       <td>
        <a href="https://www.drupal.org/project/paragraphs_collection">Paragraphs collection</a>
      </td>
       <td>200</td>
     </tr>
      <tr>
       <td>10</td>
       <td>
        <a href="https://www.drupal.org/project/entity_browser">Entity browser</a>
      </td>
       <td>196</td>
     </tr>
      <tr>
       <td>11</td>
       <td>
        <a href="https://www.drupal.org/project/diff">Diff</a>
      </td>
       <td>190</td>
     </tr>
      <tr>
       <td>12</td>
       <td>
        <a href="https://www.drupal.org/project/group">Group</a>
      </td>
       <td>170</td>
     </tr>
      <tr>
       <td>13</td>
       <td>
        <a href="https://www.drupal.org/project/metatag">Metatag</a>
      </td>
       <td>157</td>
     </tr>
      <tr>
       <td>14</td>
       <td>
        <a href="https://www.drupal.org/project/facets">Facets</a>
      </td>
       <td>155</td>
     </tr>
      <tr>
       <td>15</td>
       <td>
        <a href="https://www.drupal.org/project/commerce_pos">Commerce Point of Sale (PoS)</a>
      </td>
       <td>147</td>
     </tr>
      <tr>
       <td>16</td>
       <td>
        <a href="https://www.drupal.org/project/search_api">Search API</a>
      </td>
       <td>143</td>
     </tr>
      <tr>
       <td>17</td>
       <td>
        <a href="https://www.drupal.org/project/social">Open Social</a> (distribution)</td>
        <td>133</td>
      </tr>
       <tr>
        <td>18</td>
        <td>
          <a href="https://www.drupal.org/project/dvg">Drupal voor Gemeenten</a> (distribution)</td>
          <td>131</td>
       </tr>
        <tr>
          <td>19</td>
          <td>
           <a href="https://www.drupal.org/project/search_api_solr">Solr Search</a>
         </td>
          <td>122</td>
       </tr>
        <tr>
          <td>20</td>
          <td>
           <a href="https://www.drupal.org/project/geolocation">Geolocation field</a>
         </td>
          <td>118</td>
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
      <a href="https://www.drupal.org/u/jrockowitz">jrockowitz</a>
   </td>
    <td>537</td>
    <td>88%</td>
    <td>45%</td>
    <td>9%</td>
    <td>The Big Blue House (239), Kennesaw State University (6), Memorial Sloan Kettering Cancer Center (4)</td>
  </tr>
   <tr>
    <td>2</td>
    <td>
      <a href="https://www.drupal.org/u/dawehner">dawehner</a>
   </td>
    <td>421</td>
    <td>67%</td>
    <td>83%</td>
    <td>5%</td>
    <td>Chapter Three (328), Tag1 Consulting (19), Drupal Association (12), Acquia (5), Comm-press (1)</td>
  </tr>
   <tr>
    <td>3</td>
    <td>
      <a href="https://www.drupal.org/u/renatog">RenatoG</a>
   </td>
    <td>408</td>
    <td>0%</td>
    <td>100%</td>
    <td>0%</td>
    <td>CI&amp;T (408)</td>
  </tr>
   <tr>
    <td>4</td>
    <td>
      <a href="https://www.drupal.org/u/bojanz">bojanz</a>
   </td>
    <td>351</td>
    <td>0%</td>
    <td>95%</td>
    <td>5%</td>
    <td>Commerce Guys (335), Adapt A/S (38), Bluespark (2)</td>
  </tr>
   <tr>
    <td>5</td>
    <td>
      <a href="https://www.drupal.org/u/berdir">Berdir</a>
   </td>
    <td>335</td>
    <td>0%</td>
    <td>93%</td>
    <td>7%</td>
    <td>MD Systems (310), Acquia (7)</td>
  </tr>
   <tr>
    <td>6</td>
    <td>
      <a href="https://www.drupal.org/u/mglaman">mglaman</a>
   </td>
    <td>334</td>
    <td>3%</td>
    <td>97%</td>
    <td>1%</td>
    <td>Commerce Guys (319), Thinkbean, LLC (48), LivePerson, Inc (46), Bluespark (22), Universal Music Group (16), Gaggle.net, Inc. (3), Bluehorn Digital (1)</td>
  </tr>
   <tr>
    <td>7</td>
    <td>
      <a href="https://www.drupal.org/u/wim-leers">Wim Leers</a>
   </td>
    <td>332</td>
    <td>14%</td>
    <td>87%</td>
    <td>2%</td>
    <td>Acquia (290)</td>
  </tr>
   <tr>
    <td>8</td>
    <td>
      <a href="https://www.drupal.org/u/alexpott">alexpott</a>
   </td>
    <td>329</td>
    <td>7%</td>
    <td>99%</td>
    <td>1%</td>
    <td>Chapter Three (326), TES Global (1)</td>
  </tr>
   <tr>
    <td>9</td>
    <td>
      <a href="https://www.drupal.org/u/damienmckenna">DamienMcKenna</a>
   </td>
    <td>245</td>
    <td>2%</td>
    <td>95%</td>
    <td>4%</td>
    <td>Mediacurrent (232)</td>
  </tr>
   <tr>
    <td>10</td>
    <td>
      <a href="https://www.drupal.org/u/jhodgdon">jhodgdon</a>
   </td>
    <td>242</td>
    <td>0%</td>
    <td>1%</td>
    <td>99%</td>
    <td>Drupal Association (2), Poplar ProductivityWare (2)</td>
  </tr>
   <tr>
    <td>11</td>
    <td>
      <a href="https://www.drupal.org/u/drunken-monkey">drunken monkey</a>
   </td>
    <td>238</td>
    <td>95%</td>
    <td>11%</td>
    <td>1%</td>
    <td>Acquia (17), Vizala (8), Wunder Group (1), Sunlime IT Services GmbH (1)</td>
  </tr>
   <tr>
    <td>12</td>
    <td>
      <a href="https://www.drupal.org/u/naveenvalecha">naveenvalecha</a>
   </td>
    <td>196</td>
    <td>74%</td>
    <td>55%</td>
    <td>1%</td>
    <td>Acquia (152), Google Summer of Code (7), QED42 (1)</td>
  </tr>
   <tr>
    <td>13</td>
    <td>
      <a href="https://www.drupal.org/u/munavijayalakshmi">Munavijayalakshmi</a>
   </td>
    <td>192</td>
    <td>0%</td>
    <td>100%</td>
    <td>0%</td>
    <td>Valuebound (192)</td>
  </tr>
   <tr>
    <td>14</td>
    <td>
      <a href="https://www.drupal.org/u/borisson_">borisson_</a>
   </td>
    <td>191</td>
    <td>66%</td>
    <td>39%</td>
    <td>22%</td>
    <td>Dazzle (70), Acquia (6)</td>
  </tr>
   <tr>
    <td>15</td>
    <td>
      <a href="https://www.drupal.org/u/yongt9412">yongt9412</a>
   </td>
    <td>189</td>
    <td>0%</td>
    <td>97%</td>
    <td>3%</td>
    <td>MD Systems (183), Acquia (6)</td>
  </tr>
   <tr>
    <td>16</td>
    <td>
      <a href="https://www.drupal.org/u/klausi">klausi</a>
   </td>
    <td>185</td>
    <td>9%</td>
    <td>61%</td>
    <td>32%</td>
    <td>epiqo (112)</td>
  </tr>
   <tr>
    <td>17</td>
    <td>
      <a href="https://www.drupal.org/u/sam152">Sam152</a>
   </td>
    <td>184</td>
    <td>59%</td>
    <td>92%</td>
    <td>7%</td>
    <td>PreviousNext (168), amaysim Australia Ltd. (5), Code Drop (2)</td>
  </tr>
   <tr>
    <td>18</td>
    <td>
      <a href="https://www.drupal.org/u/miro_dietiker">miro_dietiker</a>
   </td>
    <td>182</td>
    <td>0%</td>
    <td>99%</td>
    <td>1%</td>
    <td>MD Systems (181)</td>
  </tr>
   <tr>
    <td>19</td>
    <td>
      <a href="https://www.drupal.org/u/pavan-b-s">Pavan B S</a>
   </td>
    <td>180</td>
    <td>0%</td>
    <td>98%</td>
    <td>2%</td>
    <td>Valuebound (177)</td>
  </tr>
   <tr>
    <td>20</td>
    <td>
      <a href="https://www.drupal.org/u/ajay_reddy">ajay_reddy</a>
   </td>
    <td>176</td>
    <td>100%</td>
    <td>99%</td>
    <td>0%</td>
    <td>Valuebound (180), Drupal Bangalore Community (154)</td>
  </tr>
   <tr>
    <td>21</td>
    <td>
      <a href="https://www.drupal.org/u/phenaproxima">phenaproxima</a>
   </td>
    <td>172</td>
    <td>0%</td>
    <td>99%</td>
    <td>1%</td>
    <td>Acquia (170)</td>
  </tr>
   <tr>
    <td>22</td>
    <td>
      <a href="https://www.drupal.org/u/sanchiz">sanchiz</a>
   </td>
    <td>162</td>
    <td>0%</td>
    <td>99%</td>
    <td>1%</td>
    <td>Drupal Ukraine Community (107), Vinzon (101), FFW (60), Open Y (52)</td>
  </tr>
   <tr>
    <td>23</td>
    <td>
      <a href="https://www.drupal.org/u/slashrsm">slashrsm</a>
   </td>
    <td>161</td>
    <td>6%</td>
    <td>95%</td>
    <td>3%</td>
    <td>MD Systems (153), Acquia (47)</td>
  </tr>
   <tr>
    <td>24</td>
    <td>
      <a href="https://www.drupal.org/u/jhedstrom">jhedstrom</a>
   </td>
    <td>155</td>
    <td>4%</td>
    <td>92%</td>
    <td>4%</td>
    <td>Phase2 (143), Workday, Inc. (134), Memorial Sloan Kettering Cancer Center (1)</td>
  </tr>
   <tr>
    <td>25</td>
    <td>
      <a href="https://www.drupal.org/u/xjm">xjm</a>
   </td>
    <td>151</td>
    <td>0%</td>
    <td>91%</td>
    <td>9%</td>
    <td>Acquia (137)</td>
  </tr>
   <tr>
    <td>26</td>
    <td>
      <a href="https://www.drupal.org/u/catch">catch</a>
   </td>
    <td>147</td>
    <td>3%</td>
    <td>83%</td>
    <td>16%</td>
    <td>Third and Grove (116), Tag1 Consulting (6)</td>
  </tr>
   <tr>
    <td>27</td>
    <td>
      <a href="https://www.drupal.org/u/larowlan">larowlan</a>
   </td>
    <td>145</td>
    <td>12%</td>
    <td>92%</td>
    <td>7%</td>
    <td>PreviousNext (133), University of Technology, Sydney (30), amaysim Australia Ltd. (6), Australian Competition and Consumer Commission (ACCC) (1), Department of Justice &amp; Regulation, Victoria (1)</td>
  </tr>
   <tr>
    <td>28</td>
    <td>
      <a href="https://www.drupal.org/u/rakeshgectcr">rakesh.gectcr</a>
   </td>
    <td>141</td>
    <td>100%</td>
    <td>91%</td>
    <td>0%</td>
    <td>Valuebound (128)</td>
  </tr>
   <tr>
    <td>29</td>
    <td>
      <a href="https://www.drupal.org/u/benjy">benjy</a>
   </td>
    <td>139</td>
    <td>0%</td>
    <td>94%</td>
    <td>6%</td>
    <td>PreviousNext (129), Brisbane City Council (8), Code Drop (1)</td>
  </tr>
   <tr>
    <td>30</td>
    <td>
      <a href="https://www.drupal.org/u/dhruveshdtripathi">dhruveshdtripathi</a>
   </td>
    <td>138</td>
    <td>15%</td>
    <td>100%</td>
    <td>0%</td>
    <td>DevsAdda (138), OpenSense Labs (44)</td>
  </tr>
 </table>
</small>

We observe that the top 30 contributors are sponsored by 46 organizations. **This kind of diversity is aligned with our desire not to see Drupal controlled by a single organization.** These top contributors and organizations are from many different parts of the world and work with customers large and small. Nonetheless, we will continue to benefit from more diversity.

### Evolving the credit system

Like Drupal itself, the credit system on Drupal.org is an evolving tool. Ultimately, the credit system will only be useful when the community uses it, understands its shortcomings, and suggests constructive improvements. In highlighting the organizations that sponsor the development of code on Drupal.org, we hope to elicit responses that help evolve the credit system into something that incentivizes business to sponsor more work and enables more people to participate in our community, learn from others, teach newcomers and make positive contributions. Drupal is a positive force for change and we wish to use the credit system to highlight (at least some of) the work of our diverse community, which includes volunteers, companies, nonprofits, governments, schools, universities, individuals, and other groups.

One of the challenges with the existing credit system is it has no way of "weighting" contributions. A typo fix counts just as much as giving multiple detailed technical reviews on a critical core issue. This appears to have the effect of incentivizing organizations' employees to work on "lower-hanging fruit issues", because this bumps their companies' names in the rankings. One way to help address this might be to adjust the credit ranking algorithm to consider things such as issue priority, patch size, and so on. This could help incentivize companies to work on larger and more important problems and save coding standards improvements for new contributor sprints. Implementing a scoring system that ranks the complexity of an issue would also allow us to develop more accurate reports of contributed work.

### Conclusion

Our data confirms Drupal is a vibrant community full of contributors who are constantly evolving and improving the software. While we have amazing geographic diversity, we need greater gender diversity. Our analysis of the Drupal.org credit data concludes that most contributions to Drupal are sponsored. At the same time, the data shows that volunteer contribution remains very important to Drupal.

As a community, we need to understand that a healthy open-source ecosystem includes more than traditional Drupal businesses that contribute the most. For example, we don't see a lot of contribution from the larger digital marketing agencies, system integrators, technology companies, or end-users of Drupal – we believe that might come as these organizations build out their Drupal practices and Drupal becomes more strategic for them.

To grow and sustain Drupal, we should support those that contribute to Drupal and find ways to get those that are not contributing involved in our community. We invite you to help us continue to strengthen our ecosystem.

*Special thanks to [Tim Lehnen](https://www.drupal.org/u/hestenet) and [Neil Drumm](https://www.drupal.org/u/drumm) from the Drupal Association for providing us with the Drupal.org credit system data and for supporting us during our research. I would also like to extend a special thanks to [Matthew Tift](https://www.drupal.org/u/mtift) for helping to lay the foundation for this research, collaborating on last year's blog post, and for reviewing this year's edition. Finally, thanks to [Angie Byron](https://www.drupal.org/u/webchick), [Gábor Hojtsy](https://www.drupal.org/u/g%C3%A1bor-hojtsy), [Jess (xjm)](https://www.drupal.org/u/xjm), [Preston So](https://www.drupal.org/u/prestonso), [Ted Bowman](https://www.drupal.org/u/tedbow), [Wim Leers](https://www.drupal.org/u/wim-leers) and Gigi Anderson for providing feedback during the writing process.*
