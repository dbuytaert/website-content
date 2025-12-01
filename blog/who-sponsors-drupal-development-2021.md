---
title: 'Who sponsors Drupal development? (2020-2021 edition)'
date: '2021-10-20T10:09:47-04:00'
author: Dries
summary: "An in-depth analysis of how Drupal's development was sponsored between July 1, 2020 and June 30, 2021."
image: drupal/contributions-by-individuals-vs-organizations-2021
tags:
  - Drupal
  - 'Drupal sponsors'
  - Diversity
  - Business
published: true
type: blog
url: /who-sponsors-drupal-development-2021
id: 5241
---

For the past few years, I've examined Drupal.org's contribution data to understand how the Drupal project works. Who develops Drupal? How diverse is the Drupal community? How much of Drupal's maintenance and innovation is sponsored? Where do sponsorships come from?

The report might be of interest even if you don't use Drupal. It provides insights into the inner workings of one of the largest Open Source projects in the world.

This year's report shows that:

- Compared to last year, we have fewer contributions and fewer contributors. The slowdown is consistent across organizations, countries, project types, and more. I believe this is the result of COVID-19, where we are in the *Drupal Super Cycle*, and many Drupal shops being <q>too busy growing</q>.
- Despite a slowdown, it's amazing to see that just in the last year, Drupal welcomed more than 7,000 individual contributors and over 1,100 corporate contributors.
- Two-thirds of all contributions are sponsored, but volunteer contributions remain important to Drupal's success.
- Drupal's maintenance and innovation depends mostly on smaller Drupal agencies and Acquia. We don't see many contributions from hosting companies, multi-platform digital agencies, system integrators, or end users.
- Drupal's contributors have become more diverse, but are still not diverse enough.

For comparison, you can also look at the [2016 report](https://dri.es/who-sponsors-drupal-development), [2017 report](https://dri.es/who-sponsors-drupal-development-2017), [2018 report](https://dri.es/who-sponsors-drupal-development-2018), [2019 report](https://dri.es/who-sponsors-drupal-development-2019), and the [2020 report](https://dri.es/who-sponsors-drupal-development-2020).

### Methodology

#### What data did I analyze?

I looked at all Drupal.org issues marked "closed" or "fixed" in the 12-month period from July 1, 2020 to June 30, 2021. This is across issues in Drupal Core and all contributed projects, including all major versions of Drupal.

#### What are Drupal.org issues?

Each "Drupal.org issue" tracks an idea, feature request, bug report, task, or more. It's similar to "issues" in GitHub or "tickets" in Jira. See <https://www.drupal.org/project/issues> for the list of all issues.

#### What are Drupal.org credits?

In the spring of 2015, [I proposed some ideas for how to give credit to Drupal contributors](https://dri.es/a-method-for-giving-credit-to-organizations-that-contribute-code-to-open-source). A year later, Drupal.org added the ability for contributors to [attribute their work](https://www.drupal.org/drupalorg/blog/a-guide-to-issue-credits-and-the-drupal.org-marketplace) to an organization or customer sponsor, or mark it the result of volunteer efforts.

[image drupal/example-issue-credit-on-drupal-org-2016 resize=false]

Drupal.org's credit system is unique and groundbreaking within the Open Source community. It provides unprecedented insights into the inner workings of a large Open Source project. There are a few limitations with this approach, which I'll address at the end of this report.

### How is the Drupal community doing?

In the 12-month period between July 1, 2020 and June 30, 2021, Drupal.org's credit system received contributions from 7,420 different individuals and 1,186 different organizations. We saw a 10% decline in individual contributors, and a 2% decrease in organizational contributors.

[image drupal/contributions-by-individuals-vs-organizations-2021]

For this report's time period, 23,882 issues were marked "closed" or "fixed", a 23% decline from the 2019-2020 period. This averages out to 65 issues marked "closed" or "fixed" each day.

In total, the Drupal community worked on 3,779 different Drupal.org projects this year compared to [4,195 projects in the 2019-2020 period](https://dri.es/who-sponsors-drupal-development-2020) – a 10% year-over-year decline.

<table>
  <colgroup>
   <col>
   <col style="width: 18%">
   <col style="width: 18%">
   <col style="width: 18%">
 </colgroup>
  <tr>
   <th>Metric</th>
   <th style="text-align: right;">2019 - 2020</th>
   <th style="text-align: right;">2020 - 2021</th>
   <th style="text-align: right;">Delta</th>
 </tr>
  <tr>
   <td>Number of individual contributors</td>
   <td style="text-align: right;">8,303</td>
   <td style="text-align: right;">7,420</td>
   <td style="text-align: right; background-color: #ff6461;">-12%</td>
 </tr>
  <tr>
   <td>Number of organizational contributors</td>
   <td style="text-align: right;">1,216</td>
   <td style="text-align: right;">1,186</td>
   <td style="text-align: right; background-color: #ff6461;">-2%</td>
 </tr>
  <tr>
   <td>Number of issues "fixed" or "closed"</td>
   <td style="text-align: right;">31,153</td>
   <td style="text-align: right;">23,882</td>
   <td style="text-align: right; background-color: #ff6461;">-23%</td>
 </tr>
  <tr>
   <td>Number of projects worked on</td>
   <td style="text-align: right;">4,195</td>
   <td style="text-align: right;">3,779</td>
   <td style="text-align: right; background-color: #ff6461;">-10%</td>
 </tr>
</table>

### Understanding the slowdown in contribution

#### Individual contributors slowed down

To understand the slowdown, I looked at the behavior of the top 1,000 contributors:

- The top 1,000 individual contributors are responsible for 65% of all contributions. The remaining 6,420 individuals account for the remaining 35%. Overall, Drupal follows a [long tail](https://en.wikipedia.org/wiki/Long_tail) model.
- In the last year, 77 of the top 1,000 individual contributors stopped contributing to Drupal, 671 contributed less, and 252 contributed more.

A 7.7% annual attrition rate in the top 1,000 contributors is very low. It means that the average contributor in the top 1,000 is active for 13 years. In other words, Drupal's top 1,000 contributors are *extremely* loyal – we should be grateful for their contributions and continued involvement in the Drupal project.

While we can't compare Open Source projects like Drupal to commercial companies, it might be useful to know that most commercial organizations are very happy with an attrition rate of 15% or less. This means that an employee stays with their employer for almost 6.5 years. Nowadays, a lot of people don't stay with their employer for that long. When it's put that way, you can see that an attrition rate of 7.7% is very good!

The big takeaway is that the top individual and organizational contributors aren't leaving Drupal. They just became less active in 2020-2021.

#### Organizational contributors also slowed down

Next, I looked at the behavior of the top 250 organizations:

- The top 250 organizational contributors are responsible for 82% of all contributions. The other 936 organizations account for the remaining 18%.
- In the last year, 8 organizations (3%) stopped contributing, 168 (67%) contributed less, and 74 (30%) contributed more.
- Five of the 8 organizations that stopped contributing were end users; they most likely switched their website away from Drupal. The remaining 3 were digital agencies. The end user attrition rate in the top 250 was 2%, while the digital agency attrition rate was 0.4%.

The top Drupal agencies remain very committed to Drupal. While many agencies contributed less, very few agencies stopped contributing to Drupal altogether.

#### Why are individuals and organizations contributing less?

As part of my research, I reached out to some of the top contributing Drupal agencies. The main reason why they are contributing less is that they are too busy growing:

- <q>We grew 33% so far in 2021. We have grown our contribution as well, but there has been a shift from code contributions to non-code contributions. We've contributed less code because Drupal has all the features we need to deliver amazing digital experiences, and has become really stable and robust. There has been less code to contribute.</q> – Baddý Sonja Breidert, CEO of [1xINTERNET](https://www.1xinternet.de/), Germany
- <q>We have grown 35% in the last year – from around 65 employees to 90.</q> – Nick Veenhof, CTO of [DropSolid](https://dropsolid.com/), Belgium
- <q>Customer investment in digital has accelerated by several years the past 12 months. We grew our Drupal practice by 35% in the past year.</q> – Paul Johnson, Drupal Director at [CTI Digital](https://www.ctidigital.com/), UK
- <q>We grew 27% in revenue last year. We expect to continue on that growth trajectory. Our only concern is shortage of Drupal talent.</q> – Janne Kalliola, CEO of [Exove](https://www.exove.com/), Finland
- <q>We grew 40% over the last year. This has been driven by an increased demand for large Drupal projects on tight deadlines. With more time pressures from clients and changing personal commitments, it's been more difficult for people to find the time to contribute. But also, more of our contribution shifted from Drupal.org to GitHub, and doesn't use the credit system.</q> – Stella Power, Managing Director of [Annertech](https://www.annertech.com/), Ireland
- <q>We experienced unexpected sales growth during COVID. Thanks to [Drupal Commerce](https://drupalcommerce.org/), we grew 95% in 2020 and 25% year to date. In addition, two of our leading contributors pursued other opportunities. As new team members get onboarded and the workload stabilizes, I'm hopeful we see our overall contributions increase again in 2022.</q> – Ryan Szrama, CEO of [Centarro](https://www.centarro.io/), United States

It's great to see so many Drupal agencies doing well.

Other than being too busy with client work, the following secondary reasons were provided:

- Drupal is a stable and mature software project. Drupal has all the features we need to deliver [ambitious digital experiences](https://dri.es/drupal-is-for-ambitious-digital-experiences). Furthermore, Drupal has never been this stable and robust; we don't have many bug fixes to contribute, either.
- There is a shortage of Drupal talent; the people we hire don't know how to contribute yet.
- COVID eliminated in-person events and code sprints. In-person events inspired our employees to contribute and collaborate. Without in-person events, it's hard to instill employees with a passion to contribute.
- It's more difficult to teach new employees how to contribute when everyone is remote.
- People want a vision for Drupal that they can rally behind. We have already achieved the vision: [Drupal is for ambitious digital experiences](https://dri.es/drupal-is-for-ambitious-digital-experiences). People want to know: what is next?
- The tools and processes to contribute are becoming more complex; contribution has become more difficult and less desirable.
- We are getting more efficient at managing major Drupal releases. [Rector](https://www.drupal.org/project/rector) automates more and more of the upgrade work. When we work smarter, contribution drops.

There is no doubt that COVID has accelerated a lot of digital transformation projects, but it has also slowed down contribution. Parents are busy home-schooling their children, people have Zoom-fatigue, some families may have lost income, etc. COVID added both stress and extra work to people's lives. For many, this made contribution more difficult or less possible.

#### Drupal Super Cycle

Drupal agencies provided many valid reasons for why contribution is down. In addition to those, I believe a *Drupal Super Cycle* might exist. The Drupal Super Cycle is a new concept that I have not talked about before. In fact, this is just a *theory* – and only time will tell if it is valid.

The Drupal Super Cycle is a recognition that Drupal's development cycle ebbs and flows between a "busy period" and "quiet period" depending on when the next major release takes place. There is a "busy period" before a major release, followed by a "quiet period" after each major release.

Major Drupal releases only happen every 2 or 3 years. When a major release is close, contributors work on making their projects compatible. This requires extra development work, such as adopting new APIs, subsystems, libraries, and more. Once projects are compatible, the work often shifts from active development to maintenance work.

[image drupal/drupal-super-cycle-2021]

The last major Drupal release was Drupal 9, [released in June of 2020](https://dri.es/drupal-9-released). Last year's report analyzed contribution activity between July 1, 2019 and June 30, 2020. This period includes the 11-month period leading up to the Drupal 9 release, the Drupal 9 release itself, and 1 month after the Drupal 9 release. It's the "busy period" of the Super Cycle because the Drupal community is getting thousands of contributed modules ready for Drupal 9.

This year's report analyzes contribution data starting 1 month *after* the Drupal 9 release. There was no major Drupal release this year, and we are still 9 to 14 months away from Drupal 10, currently targeted for the summer of 2022. We are in the "quiet period" of the Super Cycle.

If the Drupal Super Cycle concept is valid, we should see increased activity in next year's report, assuming we remain on track for a Drupal 10 release in June of 2022. Time will tell!

### What is the community working on?

Contribution credits decreased across all project types, but increased for Drupal Core.

[image drupal/contributions-by-project-type-1-2021]

Core contributions saw a 7% year-over-year increase in credits, while work on contributed projects – modules, themes and distributions – are all down compared to last year.

### Who are Drupal's top individual contributors?

The top 30 individual contributors between July 1, 2020 and June 30, 2021 are:

<div class="side-by-side">
  [image drupal/top-30-individuals-unweighted-2021]
  [image drupal/top-30-individuals-weighted-2021]
</div>

For the weighted ranking, I weighed each credit based on the adoption of the project the credit is attributed to. For example, each contribution credit to Drupal Core is given a weight of 10, because Drupal Core has about 1 million active installations. Credits to the [Webform module](https://www.drupal.org/project/webform), which has over 450,000 installations, get a weight of 4.5. And credits to [Drupal's Commerce project](https://www.drupal.org/project/commerce) get 0.5 points, as it is installed on around 50,000 sites.

The weighting algorithm also makes adjustments for [Drupal's strategic initiatives](https://www.drupal.org/about/core/strategic-initiatives). Strategic initiatives get a weight of 10, the highest possible score, regardless of whether these are being developed in Drupal Core's Git repository or in a sandbox on Drupal.org.

The idea is that these weights capture the end user impact of each contribution, but also act as a proxy for the effort required to get a change committed. Getting a change accepted in Drupal Core is both more difficult and more impactful than getting a change accepted to a much smaller, contributed project.

This weighting is far from perfect, but so is the unweighted view. For code contributions, the weighted chart may be more accurate than a purely unweighted approach. I included both charts:

No matter how you look at the data, all of these individuals put an incredible amount of time and effort into Drupal.

It's important to recognize that most of the top contributors are sponsored by an organization. We value the organizations that sponsor these remarkable individuals. Without their support, [it could be more challenging for these individuals to contribute](https://dri.es/the-privilege-of-free-time-in-open-source).

### How much of the work is sponsored?

When people contribute to Drupal, they can tag their contribution as a "volunteer contribution" or a "sponsored contribution". Contributions can be marked both volunteer and sponsored at the same time (shown in jamadar's screenshot near the top of this post). This could be the case when a contributor does paid work for a customer, in addition to using unpaid time to add extra functionality or polish.

For those credits with attribution details, 16% were "purely volunteer" (7,034 credits). This is in stark contrast to the 68% that were "purely sponsored" (29,240 credits). Put simply, roughly two-thirds of all contributions are "purely sponsored". Even so, volunteer contribution remains very important to Drupal.

[image drupal/contributions-by-volunteer-vs-sponsored-2021]

Volunteers contribute across all areas of the project. A lot of volunteer time and energy goes towards non-product related contributions such as event organization, mentoring, and more. Non-code contributions like these are very valuable, yet they are under-recognized in many Open Source communities.

[image drupal/contributions-by-project-type-2-2021]

### Who are Drupal's top organizational contributors?

Similar to the individual contributors, I've ranked organizations by both "unweighted contributions" and "weighted contributions". Unweighted scores are based solely on volume of contributions, while weighted scores also try to take into account both the effort and impact of each contribution.

<div class="side-by-side">
  [image drupal/top-30-organizations-unweighted-2021]
  [image drupal/top-30-organizations-weighted-2021]
</div>

If you are an end user looking for a company to work with, these are some of the companies I'd work with first. Not only do they know Drupal best, but they also [help improve your investment in Drupal](https://dri.es/shop-local-to-fuel-the-open-source-dividend). If you are a Drupal developer looking for work, these are some of the companies I'd apply to first.

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
   <td>Small-to-medium-sized professional services companies that primarily make money using Drupal. They typically employ fewer than 100 employees. Because they specialize in Drupal, many of these companies contribute frequently and are a huge part of our community. Examples are Third and Grove, OpenSense Labs, Srijan, etc.</td>
 </tr>
  <tr>
   <td>Digital marketing agencies</td>
   <td>Larger full-service agencies that have marketing-led practices using a variety of tools, typically including Drupal, Adobe Experience Manager, Sitecore, WordPress, etc. Many of these larger agencies employ thousands of people. Examples are Wunderman Thompson, Possible, and Mirum.</td>
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
   <td>Examples are the European Commission or Pfizer.</td>
 </tr>
</table>

A few observations:

- Most of the sponsors in the top 30 are traditional Drupal businesses with fewer than 100 employees. With the exception of Acquia, Drupal's maintenance and innovation largely depends on these small Drupal businesses.
- The larger, multi-platform digital marketing agencies are barely contributing to Drupal. Only 1 digital marketing agency shows up in the top 30: Intracto with 410 credits. Hardly any appear in the entire list of contributing organizations. I'm frustrated that we have not yet found the right way to communicate the value of contribution to these companies. We need to incentivize these firms to contribute with the same level of commitment that we see from traditional Drupal businesses.
- The only system integrator in the top 30 is CI&amp;T with 1,177 credits. CI&amp;T is a smaller system integrator with approximately 5,200 employees. We see various system integrators outside of the top 30, including EPAM Systems (138 credits), TATA Consultancy Services (109 credits), Publicis Sapient (60 credits), Capgemini (40 credits), Globant (8 credits), Accenture (2 credits), etc.
- Various hosting companies make a lot of money with Drupal, yet only Acquia appears in the top 30 with 1,263 credits. The contribution gap between Acquia and other hosting companies remains very large. Pantheon earned 71 credits compared to 122 last year. Platform.sh earned 8 credits compared to 23 in the last period. In general, there is a persistent problem with hosting companies not contributing back.
- We only saw 1 end user in the top 30 this year: Thunder (815 credits). Many end users contribute though: European Commission (152 credits), Pfizer (147 credits), bio.logis (111 credits), Johnson &amp; Johnson (93 credits), University of British Columbia (105 credits), Georgia Institute of Technology (75 credits), United States Department of Veterans Affairs (51 credits), NBCUniversal (45 credits), Princeton University (43 credits), Estée Lauder (38 credits), University of Texas at Austin (22 credits), and many more.

<div class="side-by-side">
  [image drupal/contributions-by-hosting-companies-2021]
  [image drupal/contributions-by-system-integrators-2021]
</div>

I often recommend end users to [mandate contributions from their partners](https://dri.es/shop-local-to-fuel-the-open-source-dividend). Pfizer, for example, [*only* works with agencies that contribute back to Drupal](https://dri.es/why-large-organizations-are-choosing-to-contribute-to-drupal). The [State of Georgia started doing the same](https://www.youtube.com/watch?v=dN_zar8J2G0); they made Open Source contribution a vendor selection criteria. If more end users took this stance, it could have a big impact on Drupal. We'd see many more digital agencies, hosting companies, and system integrators contributing to Drupal.

While we should encourage more organizations to sponsor Drupal contributions, we should also understand and respect that some organizations can give more than others – and that some might not be able to give back at all. Our goal is not to foster an environment that demands what and how others should give back. Instead, we need to help foster an environment worthy of contribution. This is clearly laid out in [Drupal's Values and Principles](https://www.drupal.org/about/values-and-principles).

### How diverse is Drupal?

Supporting diversity and inclusion is essential to the health and success of Drupal. The people who work on Drupal should reflect the diversity of people who use the web.

I looked at both the gender and geographic diversity of Drupal.org contributors.

#### Gender diversity

While Drupal is slowly becoming more diverse, less than 9% of the recorded contributions were made by contributors who do not identify as men. The gender imbalance in Drupal remains profound. We need to continue fostering diversity and inclusion in our community.

[image drupal/contributions-by-gender-1-2021]

A few years ago I wrote a post about [the privilege of free time in Open Source](https://dri.es/the-privilege-of-free-time-in-open-source). I made the case that Open Source is *not* a meritocracy. Not everyone has equal amounts of free time to contribute. For example, research shows that women still spend more than double the time as men doing unpaid domestic work, such as housework or childcare. This makes it more difficult for women to contribute to Open Source on an unpaid, volunteer basis. Organizations capable of giving back should consider financially sponsoring individuals from underrepresented groups to contribute to Open Source.

[image drupal/contributions-by-gender-2-2021]

Free time being a privilege is just one of the reasons why Open Source projects suffer from a lack of diversity.

The gender diversity chart above shows that there is a growing number of individuals that no longer share their gender identity on Drupal.org. This is because a couple of years ago, the gender field on Drupal.org profile was deprecated in favor of a [Big 8/Big 10 demographics field](https://www.isdnetwork.org/what-is-diversity.html).

Today, over 100,000 individuals have filled out the new "Big 8/Big 10" demographics field. The new demographics field allows for more axes of representation, but is also somewhat non-specific within each axis. Here are the results:

[image drupal/big8-big10-2021]

#### Diversity in leadership

Drupal.org recently introduced the ability for contributors to [identify what contributor roles they fulfill](https://www.drupal.org/drupalorg/blog/recognizing-people-who-hold-key-contributor-roles-in-the-drupal-community). The people who hold these key contribution roles can be thought of as the leaders of different aspects of our community, whether they are local community leaders, event organizers, project maintainers, etc. As more users begin to fill out this data, we can use it to build a picture of the key contributor roles in our community. Perhaps most importantly, we can look at the diversity of individuals who hold these key contributor roles. In next year's report we will provide a focused picture of diversity in these leadership positions.

#### Geographic diversity

We saw individual contributors from 6 continents and 121 countries. Consistent with the trends described above, most countries contributed less compared to a year earlier. Here are the top countries for 2020-2021:

[image drupal/contributions-by-country-2021]

Europe contributes more than North America. However, contribution from Europe continues to decline, while all other continents have become more active contributors.

[image drupal/contributions-by-continent-2021]

Asia, South America, and Africa remain big opportunities for Drupal; their combined population accounts for 6.3 billion out of 7.5 billion people in the world.

### Limitations of the credit system

It is important to note a few of the current limitations of Drupal.org's credit system:

- **The credit system doesn't capture all code contributions.** Parts of Drupal are developed on GitHub rather than Drupal.org. Contributions on GitHub usually aren't credited on Drupal.org. For example, a lot of the work on the Automatic Updates initiative is happening on GitHub instead of Drupal.org, and companies like Acquia and Pantheon don't get credit for that work.
- **The credit system is not used by everyone.** Because using the credit system is optional, many contributors don't. For example, while they could, not all event organizers and speakers capture their work in the credit system. As a result, contributions often have incomplete or no contribution credits. Where possible, we should automatically capture credits. For example, translation efforts on <https://localize.drupal.org> are not currently captured in the credit system, but could be automatically.
- **The credit system doesn't accurately value complexity and quality.** One person might have worked several weeks for just 1 credit, while another person might receive a credit for 10 minutes of work. Each year we see a few individuals and organizations trying to game the credit system. In this post, I used a basic weighting system based on project adoption. In future, we should consider refining that by looking at issue priority, patch size, number of reviews, etc. This could help incentivize people to work on larger and more important problems and save smaller issues, such as coding standards improvements, for new contributor sprints.

Because of these limitations, the actual number of contributions and contributors could be much higher than what we report.

### Conclusions

While we have fewer contributions and fewer contributors compared to last year, it is not something to be worried about. We can attribute this to various things, such as COVID-19, agency growth, and the Drupal Super Cycle.

Our data confirms that Drupal is a vibrant community full of contributors who are constantly evolving and improving the software. It's amazing to see that just in the last year, Drupal welcomed more than 7,000 individual contributors and over 1,100 corporate contributors.

To grow and sustain Drupal, we should [support those that contribute to Drupal](https://dri.es/shop-local-to-fuel-the-open-source-dividend) and find ways to get those that are not contributing involved in our community. We are working on several new ways to make it easier for new contributors to get started with Drupal, which I covered in my [latest DrupalCon keynote](https://dri.es/state-of-drupal-presentation-october-2021). Improving diversity within Drupal is critical, and we should welcome any suggestions that encourage participation from a broader range of individuals and organizations.

*Special thanks to [Tim Lehnen](https://www.drupal.org/u/hestenet), CTO at the [Drupal Association](https://www.drupal.org/association), for supporting me during my research.*
