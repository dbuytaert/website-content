---
title: 'Who sponsors Drupal development? (2019-2020 edition)'
date: '2020-11-09T06:17:49-05:00'
author: Dries
summary: "An in-depth analysis of how Drupal's development was sponsored between July 1, 2019 and June 30, 2020."
image: drupal/contributions-by-individuals-vs-organizations-2020
tags:
  - Drupal
  - 'Drupal sponsors'
  - Diversity
published: true
type: blog
url: /who-sponsors-drupal-development-2020
id: 5086
---

For the past few years, I've examined Drupal.org's contribution data to understand how the Drupal project works. Who develops Drupal? How diverse is the Drupal community? How much of Drupal's maintenance and innovation is sponsored? Where do sponsorships come from?

The report might be of interest even if you don't use Drupal. It provides insights into the inner workings of one of the largest Open Source projects in the world.

This year's report shows that:

- The recorded number of contributions increased year over year.
- More and more contributions are sponsored, but volunteer contributions remain important to Drupal's success.
- Drupal's maintenance and innovation depends mostly on smaller Drupal agencies and Acquia. We don't see many contributions from hosting companies, multi-platform digital agencies, system integrators or end users.
- Drupal's contributors have become more diverse, but are still not diverse enough.

You can also look at the [2016 report](https://dri.es/who-sponsors-drupal-development), the [2017 report](https://dri.es/who-sponsors-drupal-development-2017), the [2018 report](https://dri.es/who-sponsors-drupal-development-2018), and the [2019 report](https://dri.es/who-sponsors-drupal-development-2019).

### Methodology

#### What data did we analyze?

We looked at all Drupal.org issues marked "closed" or "fixed" in the 12-month period from July 1, 2019 to June 30, 2020. This for Drupal core and all contributed projects, across all major versions of Drupal.

#### What are Drupal.org issues?

Each "Drupal.org issue" tracks an idea, feature request, bug report, task, or more. It's similar to "issues" in GitHub or "tickets" in Jira. See <https://www.drupal.org/project/issues> for the list of all issues.

#### What are Drupal.org credits?

In the spring of 2015, [I proposed some ideas for how to give credit to Drupal contributors](https://dri.es/a-method-for-giving-credit-to-organizations-that-contribute-code-to-open-source). A year later, Drupal.org added the ability for contributors to [attribute their work](https://www.drupal.org/drupalorg/blog/a-guide-to-issue-credits-and-the-drupal.org-marketplace) to an organization or customer sponsor, or mark it the result of volunteer efforts.

[image drupal/example-issue-credit-on-drupal-org-2016 resize=false]

Drupal.org's credit system is unique and groundbreaking within the Open Source community. It provides unprecedented insights into the inner workings of a large Open Source project. There are a few limitations with this approach, which we'll address at the end of this report.

### What is the Drupal community working on?

In the 12-month period between July 1, 2019 and June 30, 2020, 31,153 issues were marked "closed" or "fixed", a 13% increase from the [27,522 issues in the 2018-2019 period](https://dri.es/who-sponsors-drupal-development-2019). This averages out to 85 issues marked "closed" or "fixed" each day. This is compared to 75 issues in 2018-2019.

In total, the Drupal community worked on 4,195 different Drupal.org projects this year compared to [3,474 projects in the 2018-2019 period](https://dri.es/who-sponsors-drupal-development-2019) – a large 20% year-over-year increase. I attribute the larger than normal growth to the Drupal 9 release.

<small>
  <table>
   <colgroup>
    <col style="width: 20%">
    <col style="width: 40%">
    <col style="width: 40%">
  </colgroup>
   <tr>
    <th>Time period</th>
    <th style="text-align: right;">Number of issues "fixed" or "closed" by day</th>
    <th style="text-align: right;">Number of projects worked on</th>
  </tr>
   <tr>
    <td>2017 - 2018</td>
    <td style="text-align: right;">67</td>
    <td style="text-align: right;">3,229</td>
  </tr>
   <tr>
    <td>2018 - 2019</td>
    <td style="text-align: right;">75</td>
    <td style="text-align: right;">3,474</td>
  </tr>
   <tr>
    <td>2019 - 2020</td>
    <td style="text-align: right;">85</td>
    <td style="text-align: right;">4,195</td>
  </tr>
 </table>
</small>

The majority of the credits are the result of work on contributed modules:

[image drupal/contributions-by-project-type-1-2020]

Compared to the previous period, contribution credits increased across all project types:

[image drupal/contributions-by-project-type-2-2020]

It is nice to see the "non-product credits" grow. More and more members in the community track credits for non-product contributions. These include organizing Drupal events, presenting at Drupal events, promoting Drupal, mentoring, and more. While some of these increases reflect new contributions, others are existing contributions that are newly reported. The fact that the credit system is becoming more accurate in recognizing more types of Open Source contributions is both important and positive.

### Who is working on Drupal?

For this report's time period, Drupal.org's credit system received contributions from 8,303 different individuals and 1,216 different organizations. We saw a 2.5% decline in individual contributors, but a 7% increase in organizational contributors.

[image drupal/contributions-by-individuals-vs-organizations-2020]

Consistent with previous years, approximately 50% of individual contributors received one credit. Meanwhile, the top 30 contributors (the top 0.4%) account for 20% of the total credits. In other words, a small number of individuals do the majority of the work.

Starting last year, I weighted each credit based on the adoption of the project the credit is attributed to. For example, each contribution credit to Drupal core is given a weight of 10 because Drupal core has about 1 million active installations. Credits to the [Webform module](https://www.drupal.org/project/webform), which has over 470,000 installations, get a weight of 4.7. And credits to [Drupal's Commerce project](https://www.drupal.org/project/commerce) get 0.6 points, as it is installed on around 60,000 sites.

The idea is that these weights capture the end user impact of each contribution, but also act as a proxy for the effort required to get a change committed. Getting a change accepted in Drupal core is both more difficult and more impactful than getting a change accepted to a much smaller, contributed project.

This weighting is far from perfect, but so is the unweighted view. For code contributions, the weighted chart may be more accurate than a purely unweighted approach. I included both charts:

<div class="side-by-side">
  [image drupal/top-30-individuals-unweighted-2020]
  [image drupal/top-30-individuals-weighted-2020]
</div>

No matter how you look at the data, all these individuals put an incredible amount of time and effort into Drupal.

It's important to recognize that most of the top contributors are sponsored by an organization. We value the organizations that sponsor these remarkable individuals. Without their support, [it could be more challenging to contribute](https://dri.es/the-privilege-of-free-time-in-open-source).

### How much of the work is sponsored?

When people contribute to Drupal, they can tag their contribution as a "volunteer contribution" or a "sponsored contribution". Contributions can be marked both volunteer and sponsored at the same time (shown in jamadar's screenshot near the top of this post). This could be the case when a contributor does paid work for a customer, in addition to using unpaid time to add extra functionality or polish.

For those credits with attribution details, 15% were "purely volunteer" (8,429 credits). This is in stark contrast to the 69% that were "purely sponsored" (37,399 credits). Put simply, roughly two-thirds of all contributions are "purely sponsored".

[image drupal/contributions-by-volunteer-vs-sponsored-2020]

This is the first time in Drupal's history that "purely volunteer" contributions stayed flat year over year. This might be related to COVID-19; coding sprints are harder to organize, people may have lost income, parents are busy home-schooling their children, people have Zoom-fatigue, and times are generally stressful. In contrast, we did see a very large increase in "purely sponsored" contributions.

Volunteer contribution remains very important to Drupal. Volunteers contribute across all areas of the project. A lot of volunteer time and energy goes towards non-product related contributions such as event organization, mentoring, and more.

[image drupal/contributions-by-project-type-3-2020]

### Who is sponsoring the work?

Now that we've established that the majority of contributions are sponsored, let's study which organizations contribute to Drupal. While 1,216 organizations contributed to Drupal, 50% of them received four credits or less. The top 30 organizations (roughly the top 2.5%) account for approximately 30% of the total credits. This means that the top 30 companies play a crucial role in the health of the Drupal project.

Similar to the individual contributors, I've ranked organizations by both "unweighted contributions" and "weighted contributions". Unweighted scores are based solely on volume of contributions, while weighted scores also try to take into account both the effort and impact of each contribution.

<div class="side-by-side">
  [image drupal/top-30-organizations-unweighted-2020]
  [image drupal/top-30-organizations-weighted-2020]
</div>

If you are an end user looking for a company to work with, these are some of the companies I'd work with first. Not only do they know Drupal well, they also [help improve your investment in Drupal](https://dri.es/shop-local-to-fuel-the-open-source-dividend). If you are a Drupal developer looking for work, these are some of the companies I'd apply to first.

A variety of different types of companies are active in Drupal's ecosystem:

<table>
  <thead>
   <tr>
    <th>Category</th>
    <th>Description</th>
  </tr>
 </thead>
  <tr>
   <td>Traditional Drupal businesses</td>
   <td>Small-to-medium-sized professional services companies that primarily make money using Drupal. They typically employ fewer than 100 employees. Because they specialize in Drupal, many of these companies contribute frequently and are a huge part of our community. Examples are Third &amp; Grove, Srijan, PreviousNext, MD Systems, etc.</td>
 </tr>
  <tr>
   <td>Digital marketing agencies</td>
   <td>Larger full-service agencies that have marketing-led practices using a variety of tools, typically including Drupal, Adobe Experience Manager, Sitecore, WordPress, etc. Many of these larger agencies employ thousands of people. Examples are Wunderman, Possible, and Mirum.</td>
 </tr>
  <tr>
   <td>System integrators</td>
   <td>Larger companies that specialize in bringing together different technologies into one solution. Example system integrators are Accenture, TATA Consultancy Services, EPAM Systems, and CI&amp;T.</td>
 </tr>
  <tr>
   <td>Hosting companies</td>
   <td>Examples are Acquia, Pantheon, and Platform.sh, but also Rackspace or Bluehost.</td>
 </tr>
  <tr>
   <td>End users</td>
   <td>Examples are Pfizer or bio.logis Genetic Information Management GmbH.</td>
 </tr>
</table>

A few observations:

- Most of the sponsors in the top 30 are traditional Drupal businesses with fewer than 50 employees. With the exception of Acquia, Drupal's maintenance and innovation largely depends on these small Drupal businesses.
- The larger, multi-platform digital marketing agencies are barely contributing to Drupal. Only one digital marketing agency shows up in the top 30: Intracto. Hardly any appear in the entire list of contributing organizations. I'm frustrated that we have not yet found the right way to communicate the value of contribution to these companies. We need to incentivize these firms to contribute with the same commitment that we see from traditional Drupal businesses.
- The only system integrator in the top 30 is CI&amp;T. CI&amp;T is a smaller system integrator with approximately 2,500 employees. We see various system integrators outside of the top 30, including EPAM Systems, Globant, Capgemini, Publicis Sapient, Accenture, and TATA Consultancy Services. Accenture and Wipro, despite doing quite a bit of Drupal work, did not receive any credits.
- Various hosting companies make a lot of money with Drupal, yet only Acquia appears in the top 30 with 1,823 credits. The contribution gap between Acquia and other hosting companies remains very large. It was great to see that Pantheon tripled its contributions from 43 to 122 this period. Platform.sh earned 23 credits compared to 22 in the last period. In general, there is a persistent problem with hosting companies not contributing back.
- We only saw two end users in the top 30 this year: Thunder (815 credits) and Pfizer (201 credits). Many end users contribute though: European Commission (290 credits), bio.logis (219 credits), Google (144), University of Waterloo (111 credits), Johnson &amp; Johnson (93 credits), University of British Columbia (91 credits), University of Texas at Austin (74 credits), NBCUniversal (48 credits), Workday (38 credits), PayPal (17 credits), and many more.

<div class="side-by-side">
  [image drupal/contributions-by-hosting-companies-2020]
  [image drupal/contributions-by-system-integrators-2020]
</div>

I often recommend end users to [mandate contributions from their partners](https://dri.es/shop-local-to-fuel-the-open-source-dividend). Pfizer, for example, [*only* works with agencies that contribute back to Drupal](https://dri.es/why-large-organizations-are-choosing-to-contribute-to-drupal). The [State of Georgia started doing the same](https://www.youtube.com/watch?v=dN_zar8J2G0); they made Open Source contribution a vendor selection criteria. If more end users took this stance, it could have a big impact on Drupal. We'd see many more digital agencies, hosting companies, and system integrators contribute to Drupal.

While we should encourage more organizations to sponsor Drupal contributions, we should also understand and respect that some organizations can give more than others – and that some might not be able to give back at all. Our goal is not to foster an environment that demands what and how others should give back. Instead, we need to help foster an environment worthy of contribution. This is clearly laid out in [Drupal's Values and Principles](https://www.drupal.org/about/values-and-principles).

### How diverse is Drupal?

Supporting diversity and inclusion is essential to the health and success of Drupal. The people who work on Drupal should reflect the diversity of people who use the web.

I looked at both the gender and geographic diversity of Drupal.org contributors.

#### Gender diversity

Only 10-11% of the recorded contributions were made by contributors who do not identify as men. This is a very small improvement compared to last year. The gender imbalance in Drupal is profound. We need to continue fostering diversity and inclusion in our community.

[image drupal/contributions-by-gender-1-2020]

Two years ago I wrote a post about [the privilege of free time in Open Source](https://dri.es/the-privilege-of-free-time-in-open-source). It made the case that Open Source is *not* a meritocracy. Not everyone has equal amounts of free time to contribute. For example, research shows that women still spend more than double the time as men doing unpaid domestic work, such as housework or childcare. This makes it more difficult for women to contribute to Open Source on an unpaid, volunteer basis. Organizations capable of giving back should consider financially sponsoring individuals from underrepresented groups to contribute to Open Source.

[image drupal/contributions-by-gender-2-2020]

Free time being a privilege is just one of the reasons why Open Source projects suffer from a lack of diversity. Other reasons include hostile environments and unconscious biases. We should consider collecting data on other systemic issues beyond gender. The Drupal Association is currently working to update demographic data collected at DrupalCon, and beyond, with the goal of better understanding our community. Knowing more about these trends could help us close existing gaps.

#### Geographic diversity

We saw individual contributors from six continents and 117 countries. The top countries:

[image drupal/contributions-by-country-2020]

Europe contributes more than North America in both absolute and relative terms.

[image drupal/contributions-by-continent-2020]

[image drupal/contributions-per-capita-2020]

Asia, South America, and Africa remain big opportunities for Drupal; their combined population accounts for 6.3 billion out of 7.5 billion people in the world.

### Limitations of the credit system

It is important to note a few of the current limitations of Drupal.org's credit system:

- **The credit system doesn't capture all code contributions.** Parts of Drupal are developed on GitHub rather than Drupal.org. Contributions on GitHub usually aren't credited on Drupal.org. For example, Drush is maintained on GitHub instead of Drupal.org, and companies like Pantheon don't get credit for that work.
- **The credit system is not used by everyone.** There are many ways to contribute to Drupal that are still [not captured in the credit system](https://www.palantir.net/blog/drupal-sustainability-contribution-credit-and-impact). Technically, that work can be captured. But because using the credit system is optional, many contributors don't. For example, not all event organizers and speakers capture their work in the credit system. As a result, contributions often have incomplete or no contribution credits. Where possible, we should automatically capture credits. For example, translation efforts on <https://localize.drupal.org> are not currently captured in the credit system, but could be automatically.
- **The credit system doesn't accurately value complexity and quality.** One person might have worked several weeks for just one credit, while another person might receive a credit for 10 minutes of work. Each year we see a few individuals and organizations trying to game the credit system. In this post, I used a basic weighting system based on project adoption. In future, we should consider refining that by looking at issue priority, patch size, number of reviews, etc. This could help incentivize people to work on larger and more important problems and save smaller issues such as coding standards improvements for new contributor sprints.

Because of these limitations, the actual number of contributions and contributors could be much higher than what we report.

Like Drupal itself, the Drupal.org credit system needs to continue to evolve. Starting this year, the Drupal Association, with the direction of the newly formed [Contribution Recognition Committee](https://www.drupal.org/contribution-credit), will start to evolve and leverage the credit system in new ways.

### Conclusions

Our data confirms that Drupal is a vibrant community full of contributors who are constantly evolving and improving the software. It's amazing to see that just in the last year, Drupal welcomed more than 8,000 individual contributors and over 1,200 corporate contributors. It's especially nice to see the growing number of contributions year over year.

To grow and sustain Drupal, we should [support those that contribute to Drupal](https://dri.es/shop-local-to-fuel-the-open-source-dividend) and find ways to get those that are not contributing involved in our community. Improving diversity within Drupal is critical, and we should welcome any suggestions that encourage participation from a broader range of individuals and organizations.
