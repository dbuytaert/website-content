---
title: 'Balancing Makers and Takers to scale and sustain Open Source'
date: '2019-09-19T08:51:02-04:00'
author: Dries
summary: 'To scale and sustain Open Source ecosystems in a more efficient and fair manner, Open Source projects need to embrace new governance, coordination and incentive models.'
image: blog/open-source-makers-and-takers-1
tags:
  - Drupal
  - 'Open Source'
  - Business
featured: true
published: true
type: blog
url: /balancing-makers-and-takers-to-scale-and-sustain-open-source
id: 4931
---

[image blog/open-source-makers-and-takers-1]

In many ways, Open Source has won. Most people know that Open Source provides better quality software, at a lower cost, without vendor lock-in. But despite Open Source being widely adopted and more than 30 years old, scaling and sustaining Open Source projects remains challenging.

Not a week goes by that I don't get asked a question about Open Source sustainability. How do you get others to contribute? How do you get funding for Open Source work? But also, how do you protect against others monetizing your Open Source work without contributing back? And what do you think of [MongoDB](https://www.mongodb.com/), [Cockroach Labs](https://www.cockroachlabs.com/) or [Elastic](https://www.elastic.co/) changing their license away from Open Source?

This blog post talks about how we can make it easier to scale and sustain Open Source projects, Open Source companies and Open Source ecosystems. I will show that:

- Small Open Source communities can rely on volunteers and self-governance, but as Open Source communities grow, their governance model most likely needs to be reformed so the project can be maintained more easily.
- There are three models for scaling and sustaining Open Source projects: *self-governance*, *privatization*, and *centralization*. All three models aim to reduce *coordination failures*, but require Open Source communities to embrace forms of *monitoring*, *rewards* and *sanctions*. While this thinking is controversial, it is supported by decades of research in adjacent fields.
- Open Source communities would benefit from experimenting with new governance models, coordination systems, license innovation, and incentive models.

### Some personal background

Scaling and sustaining Open Source projects and Open Source businesses has been the focus of most of [my professional career](https://dri.es/about).

Drupal, the Open Source project I founded 18 years ago, is used by more than one million websites and [reaches pretty much everyone on the internet](https://dri.es/reaching-the-next-billion-with-drupal).

With [over 8,500 individuals and about 1,100 organizations](https://dri.es/who-sponsors-drupal-development-2019) contributing to [Drupal](https://www.drupal.org/) annually, Drupal is one of the healthiest and contributor-rich Open Source communities in the world.

For the past 12 years, I've also helped build [Acquia](https://www.acquia.com/), an Open Source company that heavily depends on Drupal. With almost 1,000 employees, Acquia is the largest contributor to Drupal, yet responsible for less than 5% of all contributions.

This article is *not* about Drupal or Acquia; it's about scaling Open Source projects more broadly.

I'm interested in how to make Open Source production more sustainable, more fair, more egalitarian, and more cooperative. I'm interested in doing so by redefining the relationship between end users, producers and monetizers of Open Source software through a combination of technology, market principles and behavioral science.

### Why it must be easier to scale and sustain Open Source

We need to make it easier to scale and sustain both Open Source projects and Open Source businesses:

1. Making it easier to scale and sustain **Open Source projects** might be *the only way* to solve some of the world's most important problems. For example, I believe Open Source to be the only way to build a [pro-privacy, anti-monopoly, open web](https://dri.es/the-web-i-want-for-my-kids). It requires Open Source communities to be long-term sustainable – possibly for hundreds of years.
2. Making it easier to grow and sustain **Open Source businesses** is the last hurdle that prevents Open Source from taking over the world. I'd like to see *every* technology company become an Open Source company. Today, Open Source companies are still extremely rare.

The alternative is that we are stuck in the world we live in today, where proprietary software dominates most facets of our lives.

### Disclaimers

This article is focused on Open Source governance models, but there is more to growing and sustaining Open Source projects. Top of mind is the need for Open Source projects to become more diverse and inclusive of underrepresented groups.

Second, I understand that the idea of systematizing Open Source contributions won't appeal to everyone. Some may argue that the suggestions I'm making go against the altruistic nature of Open Source. I agree. However, I'm also looking at Open Source sustainability challenges from the vantage point of running both an Open Source project (Drupal) and an Open Source business (Acquia). I'm not implying that every community needs to change their governance model, but simply offering suggestions for communities that operate with some level of commercial sponsorship, or communities that struggle with issues of long-term sustainability.

Lastly, this post is long and dense. I'm 700 words in, and I haven't started yet. Given that this is a complicated topic, there is an important role for more considered writing and deeper thinking.

### Defining Open Source Makers and Takers

#### Makers

Some companies are born out of Open Source, and as a result believe deeply and invest significantly in their respective communities. With their help, Open Source has revolutionized software for the benefit of many. Let's call these types of companies *Makers*.

As the name implies, Makers help *make* Open Source projects; from investing in code, to helping with marketing, growing the community of contributors, and much more. There are usually one or more Makers behind the success of large Open Source projects. For example, [MongoDB](https://www.mongodb.com/) helps make MongoDB, [Red Hat](https://www.redhat.com/) helps make [Linux](https://www.kernel.org/), and [Acquia](https://www.acquia.com/) (along with [many other companies](https://dri.es/who-sponsors-drupal-development-2019)) helps make Drupal.

Our definition of a Maker assumes intentional and meaningful contributions and excludes those whose only contributions are unintentional or sporadic. For example, a public cloud company like Amazon can provide a lot of credibility to an Open Source project by offering it as-a-service. The resulting value of this contribution can be substantial, however that doesn't make Amazon a Maker in our definition.

I use the term Makers to refer to anyone who purposely and meaningfully invests in the maintenance of Open Source software, i.e. by making engineering investments, writing documentation, fixing bugs, organizing events, and more.

#### Takers

Now that Open Source adoption is widespread, lots of companies, from technology startups to technology giants, monetize Open Source projects without contributing back to those projects. Let's call them *Takers*.

I understand and respect that some companies can give more than others, and that many might not be able to give back at all. Maybe one day, when they can, they'll contribute. We limit the label of Takers to companies that have the means to give back, but choose not to.

<p class="pullquote">The difference between Makers and Takers is not always 100% clear, but as a rule of thumb, Makers directly invest in growing both their business and the Open Source project. Takers are solely focused on growing their business and let others take care of the Open Source project they rely on.</p>

Organizations can be both Takers and Makers at the same time. For example, [Acquia](https://www.acquia.com/), my company, is a Maker of Drupal, but a Taker of [Varnish Cache](http://varnish-cache.org/). We use Varnish Cache extensively but we don't contribute to its development.

[image blog/open-source-makers-and-takers-2]

### Takers hurt Makers

To be financially successful, many Makers mix Open Source contributions with commercial offerings. Their commercial offerings usually take the form of proprietary or closed source IP, which may include a combination of premium features and hosted services that offer performance, scalability, availability, productivity, and security assurances. This is known as the [Open Core business model](https://en.wikipedia.org/wiki/Open-core_model). Some Makers offer professional services, including maintenance and support assurances.

When Makers start to grow and demonstrate financial success, the Open Source project that they are associated with begins to attract Takers. Takers will usually enter the ecosystem with a commercial offering comparable to the Makers', but without making a similar investment in Open Source contribution. Because Takers don't contribute back meaningfully to the Open Source project that they take from, they can focus disproportionately on their own commercial growth.

Let's look at a theoretical example.

When a Maker has $1 million to invest in R&amp;D, they might choose to invest $500k in Open Source and $500k in the proprietary IP behind their commercial offering. The Maker intentionally balances growing the Open Source project they are connected to with making money. To be clear, the investment in Open Source is not charity; it helps make the Open Source project competitive in the market, and the Maker stands to benefit from that.

When a Taker has $1 million to invest in R&amp;D, nearly all of their resources go to the development of proprietary IP behind their commercial offerings. They might invest $950k in their commercial offerings that compete with the Maker's, and $50k towards Open Source contribution. Furthermore, the $50k is usually focused on self-promotion rather than being directed at improving the Open Source project itself.

<div class="large">
  [image blog/open-source-makers-and-takers-3]
</div>

Effectively, the Taker has put itself at a competitive advantage compared to the Maker:

- The Taker takes advantage of the Maker's $500k investment in Open Source contribution while only investing $50k themselves. Important improvements happen "for free" without the Taker's involvement.
- The Taker can out-innovate the Maker in building proprietary offerings. When a Taker invests $950k in closed-source products compared to the Maker's $500k, the Taker can innovate 90% faster. The Taker can also use the delta to disrupt the Maker on price.

In other words, Takers reap the benefits of the Makers' Open Source contribution while simultaneously having a more aggressive monetization strategy. The Taker is likely to disrupt the Maker. On an equal playing field, the only way the Maker can defend itself is by investing more in its proprietary offering and less in the Open Source project. To survive, it has to behave like the Taker to the detriment of the larger Open Source community.

<p class="pullquote">Takers harm Open Source projects. An aggressive Taker can induce Makers to behave in a more selfish manner and reduce or stop their contributions to Open Source altogether. Takers can turn Makers into Takers.</p>

### Open Source contribution and the Prisoner's Dilemma

The example above can be described as a [Prisoner's Dilemma](https://en.wikipedia.org/wiki/Prisoner%27s_dilemma). The Prisoner's Dilemma is a standard example of [game theory](https://en.wikipedia.org/wiki/Game_theory), which allows the study of strategic interaction and decision-making using mathematical models. I won't go into detail here, but for the purpose of this article, it helps me simplify the above problem statement. I'll use this simplified example throughout the article.

Imagine an Open Source project with only two companies supporting it. The rules of the game are as follows:

- If both companies contribute to the Open Source project (*both are Makers*), the total reward is $100. The reward is split evenly and each company makes $50.
- If one company contributes while the other company doesn't (*one Maker, one Taker*), the Open Source project won't be as competitive in the market, and the total reward will only be $80. The Taker gets $60 as they have the more aggressive monetization strategy, while the Maker gets $20.
- If both players choose not to contribute (*both are Takers*), the Open Source project will eventually become irrelevant. Both walk away with just $10.

This can be summarized in a pay-off matrix:

<table>
  <colgroup>
   <col style="width: 33%">
   <col style="width: 33%">
   <col style="width: 33%">
 </colgroup>
  <tr>
   <td>
  </td>
   <th>Company A contributes</th>
   <th>Company A doesn't contribute</th>
 </tr>
  <tr>
   <th style="width: 30%;">Company B contributes</th>
   <td>A makes $50B makes $50</td>
   <td>A makes $60B makes $20</td>
 </tr>
  <tr>
   <th style="width: 30%;">Company B doesn't contribute</th>
   <td>A makes $20B makes $60</td>
   <td>A makes $10B makes $10</td>
 </tr>
</table>

In the game, each company needs to decide whether to contribute or not, but Company A doesn't know what company B decides; and vice versa.

The Prisoner's Dilemma states that each company will optimize its own profit and not contribute. Because both companies are rational, both will make that same decision. In other words, when both companies use their "best individual strategy" (*be a Taker, not a Maker*), they produce an equilibrium that yields the worst possible result for the group: the Open Source project will suffer and as a result they only make $10 each.

A real-life example of the Prisoner's Dilemma that many people can relate to is washing the dishes in a shared house. By not washing dishes, an individual can save time (*individually rational*), but if that behavior is adopted by every person in the house, there will be no clean plates for anyone (*collectively irrational*). How many of us have tried to get away with not washing the dishes? I know I have.

Fortunately, the problem of individually rational actions leading to collectively adverse outcomes is not new or unique to Open Source. Before I look at potential models to better sustain Open Source projects, I will take a step back and look at how this problem has been solved elsewhere.

### Open Source: a public good or a common good?

In economics, the concepts of [public goods](https://en.wikipedia.org/wiki/Public_good) and [common goods](https://en.wikipedia.org/wiki/Common_good) are decades old, and have similarities to Open Source.

<div class="large">
  [image blog/open-source-makers-and-takers-4]
</div>

Public goods and common goods are what economists call [non-excludable](https://en.wikipedia.org/wiki/Non-excludable) meaning it's hard to exclude people from using them. For example, everyone can benefit from fishing grounds, whether they contribute to their maintenance or not. Simply put, public goods and common goods have *open access*.

Common goods are [rivalrous](https://en.wikipedia.org/wiki/Rivalry_(economics)); if one individual catches a fish and eats it, the other individual can't. In contrast, public goods are [non-rivalrous](https://en.wikipedia.org/wiki/Rivalry_(economics)); someone listening to the radio doesn't prevent others from listening to the radio.

I've long believed that Open Source projects are public goods: everyone can use Open Source software (non-excludable) and someone using an Open Source project doesn't prevent someone else from using it (non-rivalrous).

However, through the lens of Open Source companies, Open Source projects are also common goods; everyone can use Open Source software (non-excludable), but when an Open Source end user becomes a customer of Company A, that same end user is unlikely to become a customer of Company B (rivalrous).

<p class="pullquote">For end users, Open Source projects are <em>public goods</em>; the shared resource is the <em>software</em>. But for Open Source companies, Open Source projects are <em>common goods</em>; the shared resource is the (potential) <em>customer</em>.</p>

Next, I'd like to extend the distinction between *"Open Source software being a public good"* and *"Open Source customers being a common good"* to the [free-rider problem](https://en.wikipedia.org/wiki/Free-rider_problem): we define *software free-riders* as those who use the software without ever contributing back, and *customer free-riders* (or Takers) as those who sign up customers without giving back.

All Open Source communities should encourage *software free-riders*. Because the software is a public good (non-rivalrous), a software free-rider doesn't exclude others from using the software. Hence, it's better to have a user for your Open Source project, than having that person use your competitor's software. Furthermore, a software free-rider makes it more likely that other people will use your Open Source project (by word of mouth or otherwise). When some portion of those other users contribute back, the Open Source project benefits. Software free-riders can have positive network effects on a project.

However, when the success of an Open Source project depends largely on one or more corporate sponsors, the Open Source community should not forget or ignore that customers are a common good. Because a customer can't be shared among companies, it matters a great deal for the Open Source project where that customer ends up. When the customer signs up with a Maker, we know that a certain percentage of the revenue associated with that customer will be invested back into the Open Source project. When a customer signs up with a *customer free-rider* or Taker, the project doesn't stand to benefit. In other words, Open Source communities should find ways to route customers to Makers.

<p class="pullquote">Both volunteer-driven and sponsorship-driven Open Source communities should encourage <em>software free-riders</em>, but sponsorship-driven Open Source communities should discourage <em>customer free-riders</em>.</p>

### Lessons from decades of Common Goods management

Hundreds of research papers and books have been written on public good and common good governance. Over the years, I have read many of them to figure out what Open Source communities can learn from successfully managed public goods and common goods.

Some of the most instrumental research was Garrett Hardin's [Tragedy of the Commons](https://en.wikipedia.org/wiki/Tragedy_of_the_commons) and Mancur Olson's work on [Collective Action](https://en.wikipedia.org/wiki/Collective_action). Both Hardin and Olson concluded that groups don't self-organize to maintain the common goods they depend on.

As Olson writes in the beginning of his book, [The Logic of Collective Action](https://www.amazon.com/Logic-Collective-Action-Printing-Appendix/dp/0674537513): <q>Unless the number of individuals is quite small, or unless there is coercion or some other special device to make individuals act in their common interest, rational, self-interested individuals will not act to achieve their common or group interest.</q>.

Consistent with the Prisoner's Dilemma, Hardin and Olson show that groups don't act on their shared interests. Members are disincentivized from contributing when other members can't be excluded from the benefits. It is individually rational for a group's members to free-ride on the contributions of others.

Dozens of academics, Hardin and Olson included, argued that an *external agent* is required to solve [the free-rider problem](https://en.wikipedia.org/wiki/Free-rider_problem). The two most common approaches are (1) centralization and (2) privatization:

1. When a common good is *centralized*, the government takes over the maintenance of the common good. The government or state is the external agent.
2. When a public good is *privatized*, one or more members of the group receive *selective benefits* or *exclusive rights* to harvest from the common good in exchange for the ongoing maintenance of the common good. In this case, one or more corporations act as the external agent.

The wide-spread advice to centralize and privatize common goods has been followed extensively in most countries; today, the management of natural resources is typically managed by either the government or by commercial companies, but no longer directly by its users. Examples include public transport, water utilities, fishing grounds, parks, and much more.

Overall, the privatization and centralization of common goods has been very successful; in many countries, public transport, water utilities and parks are maintained better than volunteer contributors would have on their own. I certainly value that I don't have to help maintain the train tracks before my daily commute to work, or that I don't have to help mow the lawn in our public park before I can play soccer with my kids.

For years, it was a long-held belief that centralization and privatization were *the only way* to solve [the free-rider problem](https://en.wikipedia.org/wiki/Free-rider_problem). It was [Elinor Ostrom](https://en.wikipedia.org/wiki/Elinor_Ostrom) who observed that a third solution existed.

Ostrom found hundreds of cases where common goods are successfully managed by their communities, *without* the oversight of an external agent. From the management of irrigation systems in Spain to the maintenance of mountain forests in Japan – all have been successfully self-managed and self-governed by their users. Many have been long-enduring as well; the youngest examples she studied were more than 100 years old, and the oldest exceed 1,000 years.

Ostrom studied why some efforts to self-govern commons have failed and why others have succeeded. She summarized the conditions for success in the form of [core design principles](https://en.wikipedia.org/wiki/Elinor_Ostrom#Design_principles_for_Common_Pool_Resource_(CPR)_institution). Her work led her to win the Nobel Prize in Economics in 2009.

Interestingly, all successfully managed commons studied by Ostrom switched at some point from *open access* to *closed access*. As Ostrom writes in her book, [Governing the Commons](https://www.amazon.com/Governing-Commons-Evolution-Institutions-Collective/dp/0521405998): <q>For any appropriator to have a minimal interest in coordinating patterns of appropriation and provision, some set of appropriators must be able to exclude others from access and appropriation rights.</q>. Ostrom uses the term *appropriator* to refer to those who use or withdraw from a resource. Examples would be fishers, irrigators, herders, etc – or companies trying to turn Open Source users into paying customers. In other words, the shared resource must be made exclusive (to some degree) in order to incentivize members to manage it. Put differently, Takers will be Takers until they have an incentive to become Makers.

Once access is closed, explicit rules need to be established to determine how resources are shared, who is responsible for maintenance, and how self-serving behaviors are suppressed. In all successfully managed commons, the regulations specify (1) who has access to the resource, (2) how the resource is shared, (3) how maintenance responsibilities are shared, (4) who inspects that rules are followed, (5) what fines are levied against anyone who breaks the rules, (6) how conflicts are resolved and (7) a process for collectively evolving these rules.

### Three patterns for long-term sustainable Open Source

Studying the work of Garrett Hardin (*Tragedy of the Commons*), the Prisoner's Dilemma, Mancur Olson (*Collective Action*) and Elinor Ostrom's core design principles for self-governance, a number of shared patterns emerge. When applied to Open Source, I'd summarize them as follows:

1. Common goods fail because of a failure to coordinate collective action. To scale and sustain an Open Source project, Open Source communities need to transition from individual, uncoordinated action to cooperative, coordinated action.
2. Cooperative, coordinated action can be accomplished through privatization, centralization, or self-governance. All three work – and can even be mixed.
3. Successful privatization, centralization, and self-governance *all* require clear rules around membership, appropriation rights, and contribution duties. In turn, this requires monitoring and enforcement, either by an external agent (centralization + privatization), a private agent (self-governance), or members of the group itself (self-governance).

Next, let's see how these three concepts – centralization, privatization and self-governance – could apply to Open Source.

### Model 1: Self-governance in Open Source

For small Open Source communities, self-governance is very common; it's easy for its members to communicate, learn who they can trust, share norms, agree on how to collaborate, etc.

As an Open Source project grows, contribution becomes more complex and cooperation more difficult: it becomes harder to communicate, build trust, agree on how to cooperate, and suppress self-serving behaviors. The incentive to free-ride grows.

You can scale successful cooperation by having strong norms that encourage other members to do their fair share and by having face-to-face events, but eventually, that becomes hard to scale as well.

As Ostrom writes in *Governing the Commons*: <q>Even in repeated settings where reputation is important and where individuals share the norm of keeping agreements, reputation and shared norms are insufficient by themselves to produce stable cooperative behavior over the long run.</q> and <q>In all of the long-enduring cases, active investments in monitoring and sanctioning activities are quite apparent.</q>.

To the best of my knowledge, no Open Source project currently implements Ostrom's design principles for successful self-governance. To understand how Open Source communities might, let's go back to our running example.

Our two companies would negotiate rules for how to share the rewards of the Open Source project, and what level of contribution would be required in exchange. They would set up a contract where they both agree on how much each company can earn and how much each company has to invest. During the negotiations, various strategies can be proposed for how to cooperate. However, both parties need to agree on a strategy before they can proceed. Because they are negotiating this contract among themselves, no external agent is required.

These negotiations are non-trivial. As you can imagine, any proposal that does not involve splitting the $100 fifty-fifty is likely rejected. The most likely equilibrium is for both companies to contribute equally and to split the reward equally. Furthermore, to arrive at this equilibrium, one of the two companies would likely have to go backwards in revenue, which might not be agreeable.

Needless to say, this gets even more difficult in a scenario where there are more than two companies involved. Today, it's hard to fathom how such a self-governance system can successfully be established in an Open Source project. In the future, [Blockchain](https://en.wikipedia.org/wiki/Blockchain)-based coordination systems might offer technical solutions for this problem.

<p class="pullquote">Large groups are less able to act in their common interest than small ones because (1) the complexity increases and (2) the benefits diminish. Until we have better community coordination systems, it's easier for large groups to transition from self-governance to privatization or centralization than to scale self-governance.</p>

The concept of major projects growing out of self-governed volunteer communities is not new to the world. The first trade routes were ancient trackways which citizens later developed on their own into roads suited for wheeled vehicles. Privatization of roads improved transportation for all citizens. Today, we certainly appreciate that our governments maintain the roads.

[image blog/open-source-makers-and-takers-5]

### Model 2: Privatization of Open Source governance

In this model, Makers are rewarded unique benefits not available to Takers. These exclusive rights provide Makers a commercial advantage over Takers, while simultaneously creating a positive social benefit for all the users of the Open Source project, Takers included.

For example, [Mozilla](https://www.mozilla.org) has the exclusive right to use the Firefox trademark and to set up paid search deals with search engines like Google, Yandex and Baidu. In 2017 alone, Mozilla made $542 million from searches conducted using Firefox. As a result, Mozilla can make continued engineering investments in Firefox. Millions of people and organizations benefit from that every day.

Another example is [Automattic](https://automattic.com/), the company behind WordPress. Automattic is the only company that can use [WordPress.com](https://wordpress.com), and is in the unique position to make hundreds of millions of dollars from WordPress' official SaaS service. In exchange, Automattic invests millions of dollars in the Open Source WordPress each year.

Recently, there have been examples of Open Source companies like [MongoDB](https://techcrunch.com/2018/10/16/mongodb-switches-up-its-open-source-license/), [Redis](https://techcrunch.com/2019/02/21/redis-labs-changes-its-open-source-license-again/), [Cockroach Labs](https://www.cockroachlabs.com/blog/oss-relicensing-cockroachdb/) and others adopting stricter licenses because of perceived (and sometimes real) threats from public [cloud companies that behave as Takers](https://onezero.medium.com/open-source-betrayed-industry-leaders-accuse-amazon-of-playing-a-rigged-game-with-aws-67177bc748b7). The ability to change the license of an Open Source project is a form of privatization.

### Model 3: Centralization of Open Source governance

Let's assume a government-like central authority can monitor Open Source companies A and B, with the goal to reward and penalize them for contribution or lack thereof. When a company follows a cooperative strategy (*being a Maker*), they are rewarded $25 and when they follow a defect strategy (*being a Taker*), they are charged a $25 penalty. We can update the pay-off matrix introduced above as follows:

<table>
  <colgroup>
   <col style="width: 33%">
   <col style="width: 33%">
   <col style="width: 33%">
 </colgroup>
  <tr>
   <td>
  </td>
   <th>Company A contributes</th>
   <th>Company A doesn't contribute</th>
 </tr>
  <tr>
   <th>Company B contributes</th>
   <td>A makes $75 ($50 + $25)B makes $75 ($50 + $25)</td>
   <td>A makes $35 ($60 - $25)B makes $45 ($20 + 25)</td>
 </tr>
  <tr>
   <th>Company B doesn't contribute</th>
   <td>A makes $45 ($20 + $25)B makes $35 ($60 - $25)</td>
   <td>A makes $0 ($10 - $25)B makes $0 ($10 - $25)</td>
 </tr>
</table>

We took the values from the pay-off matrix above and applied the rewards and penalties. The result is that both companies are incentivized to contribute and the optimal equilibrium (both become Makers) can be achieved.

The money for rewards could come from various fundraising efforts, including membership programs or advertising (just as a few examples). However, more likely is the use of *indirect monetary rewards*.

One way to implement this is Drupal's credit system. Drupal's non-profit organization, the [Drupal Association](https://www.drupal.org/association) [monitors who contributes what](https://dri.es/a-method-for-giving-credit-to-organizations-that-contribute-code-to-open-source). Each contribution earns you credits and the credits are used to provide visibility to Makers. The more you contribute, the more visibility you get on [Drupal.org](https://www.drupal.org) (visited by 2 million people each month) or at Drupal conferences (called DrupalCons, visited by thousands of people each year).

[image drupal/example-issue-credit-on-drupal-org-2016 resize=false]

While there is a lot more the Drupal Association could and should do to balance its Makers and Takers and achieve a more optimal equilibrium for the Drupal project, it's an emerging example of how an Open Source non-profit organization can act as a regulator that monitors and maintains the balance of Makers and Takers.

The big challenge with this approach is the accuracy of the monitoring and the reliability of the rewarding (and sanctioning). Because Open Source contribution comes in different forms, tracking and valuing Open Source contribution is a very difficult and expensive process, not to mention full of conflict. Running this centralized government-like organization also needs to be paid for, and that can be its own challenge.

### Concrete suggestions for scaling and sustaining Open Source

#### Suggestion 1: Don't just appeal to organizations' self-interest, but also to their fairness principles

If, like most economic theorists, you believe that organizations act in their own self-interest, we should appeal to that self-interest and better explain the benefits of contributing to Open Source.

Despite the fact that hundreds of articles have been written about the benefits of contributing to Open Source – highlighting speed of innovation, recruiting advantages, market credibility, and more – many organizations still miss these larger points.

It's important to keep sharing Open Source success stories. One thing that we have *not* done enough is appeal to organizations' fairness principles.

While a lot of economic theories correctly assume that most organizations are self-interested, I believe some organizations are also driven by fairness considerations.

Despite the term "Takers" having a negative connotation, it does *not* assume malice. For many organizations, it is not apparent if an Open Source project needs help with maintenance, or how one's actions, or lack thereof, might negatively affect an Open Source project.

As mentioned, Acquia is a heavy user of Varnish Cache. But as Acquia's Chief Technology Officer, I don't know if Varnish needs maintenance help, or how our lack of contribution negatively affects Makers in the Varnish community.

It can be difficult to understand the consequences of our own actions within Open Source. Open Source communities should help others understand where contribution is needed, what the impact of not contributing is, and why certain behaviors are not fair. Some organizations will resist unfair outcomes and behave more cooperatively if they understand the impact of their behaviors and the fairness of certain outcomes.

Make no mistake though: most organizations won't care about fairness principles and will only contribute when they have to. For example, most people would not voluntarily redistribute 25-50% of their income to those who need it. However, most of us agree to redistribute money by paying taxes, but only so long as all others have to do so as well and the government enforces it.

#### Suggestion 2: Encourage end users to offer selective benefits to Makers

We talked about Open Source projects giving selective benefits to Makers (e.g. Automattic, Mozilla, etc), but end users can give selective benefits as well. For example, end users can mandate Open Source contributions from their partners. We have some successful examples of this in the Drupal community:

- Pfizer uses Drupal for hundreds of their websites. They work with dozens of digital agencies to build and maintain these sites. As a policy, Pfizer [*only* works with agencies that contribute back to Drupal](https://dri.es/why-large-organizations-are-choosing-to-contribute-to-drupal).
- The [State of Georgia started doing the same](https://www.youtube.com/watch?v=dN_zar8J2G0); they also made Open Source contribution a vendor selection criteria.

If more end users of Open Source took this stance, it could have a very big impact on Open Source sustainability. For governments, in particular, this seems like a very logical thing to do. Why would a government *not* want to put every dollar of IT spending back in the public domain? For Drupal alone, the impact would be measured in tens of millions of dollars each year.

#### Suggestion 3: Experiment with new licenses

I believe we can create licenses that support the creation of Open Source projects with sustainable communities and sustainable businesses to support it.

For a directional example, look at what [MariaDB](https://mariadb.com) did with their [Business Source License (BSL)](https://mariadb.com/bsl11/). The BSL gives users complete access to the source code so users can modify, distribute and enhance it. Only when you use more than *x* of the software do you have to pay for a license. Furthermore, the BSL guarantees that the software becomes Open Source over time; after *y* years, the license automatically converts from BSL to [General Public License (GPL)](https://www.gnu.org/licenses/licenses.html#GPL), for example.

A second example is the [Community Compact](https://github.com/adamhjk/community-compact), a license proposed by [Adam Jacob](https://www.linkedin.com/in/adamjacob/). It mixes together a modern understanding of social contracts, copyright licensing, software licensing, and distribution licensing to create a sustainable and harmonious Open Source project.

<p class="pullquote">We can create licenses that better support the creation, growth and sustainability of Open Source projects and that are designed so that both users and the commercial ecosystem can co-exist and cooperate in harmony.</p>

I'd love to see new licenses that encourage *software free-riding* (sharing and giving), but discourage *customer free-riding* (unfair competition). I'd also love to see these licenses support many Makers, with built-in inequity and fairness principles for smaller Makers or those not able to give back.

If, like me, you believe there could be future licenses that are *more* "Open Source"-friendly, not less, it would be smart to implement a *contributor license agreement* for your Open Source project; it allows Open Source projects to relicense if/when better licenses arrive. At some point, current Open Source licenses will be at a disadvantage compared to future Open Source licenses.

### Conclusions

As Open Source communities grow, volunteer-driven, self-organized communities become harder to scale. Large Open Source projects should find ways to balance Makers and Takers or the Open Source project risks not innovating enough under the weight of Takers.

Fortunately, we don't have to accept that future. However, this means that Open Source communities potentially have to get comfortable experimenting with how to monitor, reward and penalize members in their communities, particularly if they rely on a commercial ecosystem for a large portion of their contributions. Today, that goes against the values of most Open Source communities, but I believe we need to keep an open mind about how we can grow and scale Open Source.

Making it easier to scale Open Source projects in a sustainable and fair way is one of the most important things we can work on. If we succeed, Open Source can truly take over the world – it will pave the path for every technology company to become an Open Source business, and also solve some of the world's most important problems in an open, transparent and cooperative way.
