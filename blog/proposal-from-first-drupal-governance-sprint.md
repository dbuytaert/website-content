---
title: 'Proposal from first Drupal Governance Sprint'
date: '2012-08-01T12:11:43-04:00'
author: Dries
tags:
  - Drupal
  - 'Drupal Association'
  - Governance
published: true
type: blog
url: /proposal-from-first-drupal-governance-sprint
id: 2726
---

*(This blog post is jointly written by [Angela Byron](https://www.drupal.org/user/24967), [Randy Fay](https://www.drupal.org/user/30906/), [Greg Dunlap](https://www.drupal.org/user/128537), [David Strauss](https://www.drupal.org/user/93254) and [Dries Buytaert](https://www.drupal.org/user/1).)*

As mentioned [last month](https://dri.es/drupal-governance-sprint), on July 16 - 17, 2012, several community leaders in the Drupal project sat down with several community leaders from other open source projects and tried to hash out a governance structure to support the Drupal community's continued growth. "Governance" in this case, encompassing all the things we do to organize ourselves, make plans and decisions together, get things done, and resolve conflicts.

Here are the proposals we came up with, and we are actively seeking community feedback on the ideas within.

### What problems are we trying to solve?

We began the sprint by brainstorming a list of problems we're hitting, given the scale of our community. This list included items such as:

- No obvious answer to the question, "Who can make a decision here?" and as a result, important decisions can get stale-mated, or in the worst case leave smouldering craters where a healthy, functioning community used to be.
- Because the Code of Conduct punts on the topic of conflict resolution, a handful of already swamped individuals get tapped on an ad-hoc basis to intervene in conflict situations. This both burns out those individuals, and also leaves the vast majority of the community who don't know who those individuals are with no conflict resolution path apart from "repeat what I already said, but with more volume".
- While our "do-ocracy" model generally works well for our community, it can also lead to situations like "Tyranny of the person with the most time on their hands." We need ways for smart people who can't be on IRC 18 hours a day or read 300+ reply issues to participate and be respected as equals.

Over the course of two days, Drupal community members Dries Buytaert, Angela Byron, Randy Fay, Greg Dunlap, and David Strauss met and discussed a variety of these and other governance topics, and we also received input from [Jono Bacon](https://www.jonobacon.com/), community manager for the [Ubuntu project](https://www.ubuntu.com/), [Jared Smith](http://jaredsmith.net), former project lead of the [Fedora project](http://fedoraproject.org), and [David Eaves](http://eaves.ca).

[Steve Edwards](https://www.drupal.org/user/87591) also recorded [a podcast about the Governance Sprint](https://www.acquia.com/resources/podcasts/acquia-podcast-55-improving-drupal-governance); it provides more background on what problems we are trying to solve.

### Overview of proposed changes

We propose the creation of a number of "working groups" that essentially make more explicit community structures that already exist. Each working group would consist of ~5 people, appointed by Dries, in charge of collaborating with the community in order to establish effective policy. Each working group will have one "lead" member (chair) who communicates major items and works with Dries. Some working groups will have a set duration (e.g. life cycle of a Drupal core release), others may have terms. Dries, as project lead, also reserves the ability to terminate a group at any time if it feels like they are overstepping their scope (charter).

The summary, in essence:

- Establish clearly chartered working groups where currently loosely defined individuals are taking on things that are community-shaping in their scope.
- Empower these working groups to make decisions, so important community governance decisions do not get stalemated. Keep the groups small enough that decision-making can take place efficiently, but large enough that a diversity of opinions are represented.
- Make it more transparent and obvious, to newcomers and community insiders alike, where "the buck stops" with decision-making in our community in various areas, what the structure of the community is, What is expected of them, and who to turn to for help.

### "Drupal" groups

The "Drupal" groups encompass areas that touch Drupal core or contrib, or the Drupal community itself. The ultimate "buck stops here" with these groups is with Dries Buytaert, the Drupal project lead.

[image drupal/governance-sprint-2012-community resize=false]

#### <a id="community">Community Working Group</a>

Inspired by the Fedora Community Working Group, this group would be responsible for maintaining a friendly and welcoming community, and their charter will likely consist of items such as:

- Maintaining and updating community-governing policies like the Drupal Code of Conduct.
- Helping with mentorship and on-boarding of new community members.
- Ensuring existing community members have their needs met.
- Intervening as mediators in cases of conflict resolution (where the conflict cannot be worked out among individuals first) or burnout.
- Issuing sanctions in cases of extreme policy violations.

In other words, this working group tries to make sure the "people" side of our community is functioning well. It doesn't set technical policy or intervene in any code-related matters; this is the role of the [Technical Working Group](#technical). The ideal make-up of this group would be community-minded people with extreme amounts of patience, empathy, and diplomacy skills.

#### <a id="technical">Technical Working Group</a>

A corollary to the [Community Working Group](#community), this group would set and maintain policies around the technical aspects of our community, including:

- Develop and maintain policies around things such as: 
   - [Git repository usage](https://www.drupal.org/node/1001544)
   - [Full-project approval](https://www.drupal.org/node/1011698)
   - [Coding standards](https://www.drupal.org/coding-standards)
- Establishing best practices and recommendations around bug/issue workflows; for example, strongly encouraging a workflow of idea -&gt; architecture review -&gt; implementation -&gt; code style/clean-up.
- Recommending to the Drupal Association tool changes that will help accelerate contribution.
- Intervening as mediators in cases of technical conflict (where the conflict cannot be worked out among individuals first).

In other words, this working group tries to make sure the "technical" side of our community is working well. "People" problems would be escalated to the [Community Working Group](#community). Nevertheless, the ideal make-up of this group would be community-minded people who are also technical, known to be fair, and adverse to making *new* rules.

#### Drupal Core

A *lot* of time was devoted at the sprint to discussing Drupal Core, and how to address some of the challenges surrounding its development. For example, there is currently a lot of tapping of internal networks to move things along in core, and those without access to those networks can feel blocked out. It's also very difficult to get an answer as to whether or not something is "core-worthy" until far too late in its development process, making major feature development a risky affair.

The recommendation from the Governance Sprint is something like the following, which would not take effect until the Drupal 9 development cycle.

##### Drupal Core Initiative Working Group

This group works with Dries Buytaert, the Drupal project lead, in order to tackle strategically vital initiatives within Drupal core. Membership includes the initiative leads. This would entail a bit more formalized structure, including milestones and progress tracking, bi-weekly meetings among the various initiatives, and so on.

This would be essentially formalizing what already exists today with the Drupal 8 initiatives and initiative leads.

#### Contributions repository

At the Governance Sprint, we agreed to continue *not* to impose any additional governance structure on contrib, by design. This allows contrib to be an incubator not only for technical solutions, but also for governance itself.

The exception would be conflicts between maintainers or maintainers and their users which are not able to be resolved among the individuals. These would then go to either the [Community Working Group](#community) or [Technical Working Group](#technical), as appropriate.

#### Security and documentation teams

We have a few overall "Teams" that touch elements of the product, including the Documentation Team and Security Team (we also discussed the establishment of a Support Team). As part of the new governance model, we recommend creating charters for these teams that make it explicit to others what their roles and responsibilities are, how to join, and what is expected of them. It's likely these charters will be modeled after something like the [Documentation Team and Leader Responsibilities](https://www.drupal.org/node/1399884) page.

### "Operations / Administration" groups

These groups act in support of the Drupal project and its community. The ultimate "buck stops here" with these groups is with the Drupal Association board instead of Dries. Many of these have a financial impact on the Drupal Association and greatly affect its ability to get things done in support of its mission.

[image drupal/governance-sprint-2012-operations resize=false]

### And what about Drupal.org?

[image drupal/governance-sprint-2012-drupal-org resize=false]

Next to Drupal core, this is probably where we spent the most time discussing. Drupal.org is special, in that it straddles both the community side of things, as well as the operations / support side of things. It functions through a combination of numerous volunteers as well as funding via the Drupal Association for support staff and development on major initiatives.

At the moment, the best place to put Drupal.org seems like it's at a halfway point between the "Drupal" and "Operations" sides of things, and for the charter of this working group to include the necessity to work with the Drupal Association and community members alike. Though eventually, for both legal and simplicity reasons, it would be better for this to be located under the purview of the Drupal Association board.

A few areas there was broad agreement on, however, were the following:

- Split off a separate "Drupal.org content" working group from the "Drupal.org webmasters" working group; different skills/levels of trust are needed for managing the content on Drupal.org versus managing access and performing moderation of abuse.
- Identify a much smaller subset of the Drupal.org webmasters group to form policy for this team. Currently, there are nearly 150 members with "site maintainer" privileges, and they often make and enforce policy on an ad-hoc, individual basis. Community members currently encounter very inconsistent experiences in the queue.
- While the Drupal Association doesn't manage these groups, it's generally expected that the charters of these groups will include directives to collaborate with the DA in their policy-making decisions in order to ensure the financial sustainability of Drupal.org.

### Next steps

We're very interested in community feedback on this direction, either in comments below or privately. We'll provide an update on the progress at DrupalCon Munich.

We encourage everyone to come and get involved in this discussion. As our community grows, it is essential that we come up with a governance structure that matches our core values and allows us our community to be more sustainable for the long haul.
