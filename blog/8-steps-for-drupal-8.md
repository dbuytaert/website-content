---
title: '8 steps for Drupal 8'
date: '2009-11-16T04:13:41-05:00'
author: Dries
tags:
  - Drupal
published: true
type: blog
url: /8-steps-for-drupal-8
id: 1211
---

The Drupal 7 code freeze triggered a lot of retrospective about Drupal core, and the Drupal core development model. Some of these discussions are collectively referred to as "smallcore".

While I'd prefer to postpone such a retrospective until after Drupal 7 is released and we're about to open up the Drupal 8 development branch, the discussion is already beginning on the web, and it is my responsibility to internalize people's thoughts and recommendations.

I've brainstormed about this a lot the last couple of weeks, and talked about it with various people. In this post, I propose 8 steps to help improve Drupal core development going forward. Some of these steps make Drupal better for end-users, some of these steps make Drupal better for developers, and other steps focus on making Drupal a better product. They might not address every concern that has been raised, but I hope they make for a good start and that they provide some focus.

We'll obviously have more thinking and brainstorming to do about Drupal 8. I'd like to thank everyone for their suggestions, for bearing with some of the growing pains, and for helping us raise our game. It is what makes Drupal so great.

The 8 steps are as follows:

1. Create better separation between framework and product
2. Grow Drupal by making it a better product
3. Select two strategic co-maintainers
4. Distributions could help, if we do them right
5. Experiment with distributed revision control systems
6. Backport small changes to stable releases
7. Continue to streamline the patch review process
8. Aim for a shorter release cycle

### Step 1: Create better separation between framework and product

As people start to build more products on top of Drupal, it is important that Drupal doesn't get in the way, and that it provides the flexibility and ease of customization for Drupal distribution builders. Drupal has always been king of flexibility, and missing or poorly designed APIs have always been considered and treated as bugs.

The current state of affairs is that, while Drupal is super-flexible, we do have some hard-coded assumptions, and not everything can be reused or replaced. Clearly the work on improving our APIs needs to continue, and creating better separation between the framework and the product will continue to be one of our goals during the Drupal 8 release cycle.

Over-engineering is a real threat though. When people fall in love with framework design, they tend to decouple everything, abstracting it up, down, and sideways. Before you know it, you end up with abstractions that make Drupal harder to develop for, and that could make Drupal a lot slower. When looking for a Drupal 8 co-maintainer, I'll look for someone who can help us walk this fine line. More on co-maintainers below.

I also don't like the term "smallcore" as a term for this work. First, the term seems to drive a wedge in the community – which I don't support. Second, the term is misleading and deceptive as core is more likely to get bigger as we improve our APIs, add more subsystems and potentially add more features. Third, the term alarms people who see the value in having a strong Drupal product, as it sounds antithetical to that goal. Let's stop saying "smallcore".

### Step 2: Grow Drupal by making it a better product

Drupal 7 became more mature as a framework but it is also shipping with new features, as well as a lot of usability improvements that help make Drupal easier to use for content editors and site builders. A number of people are wondering how to undo some of the usability changes, and now dream about an "easy to undo" CMS. Making the framework better is a great goal, but not at the expense of our users.

The single biggest barrier to the success of Drupal is its ease of use. This is repeatedly shown in studies, competitive comparisons and blog posts. The broader market is impeded by Drupal's usability, and not with the fact that Drupal isn't a good framework.

To focus only on the power and flexibility of the framework mainly serves to keep the Drupal insiders happy, while the market and customer base passes them by to adopt tools that do not need their specialized skills because other products solve the market's needs out of the box.

There is a long history of how successful software projects evolve. In the end, there is only ever one winner in a market segment, and typically one runner-up. Everyone else becomes irrelevant in the big picture. This is true for desktop systems (Microsoft/Apple), server systems (Unix-Linux/Microsoft), ERP systems (SAP/Oracle), databases (Oracle/Microsoft) and so on ... It is what will happen in the CMS market too. My goal as the project lead, is to lead Drupal to become the dominant web platform. We do not want Drupal to be irrelevant.

We should all agree that at the end of the day, success should be measured by the number of people working *with* Drupal, not by the number of people working *on* Drupal.

A lot of the motivation for current discussions comes from frustrations with the core development process. I would like to shift the discussion, reframe the conversation, and focus on our goal to make Drupal the number one web platform. Fortunately, creating a better separation between the framework and the product aligns with that goal, but just focusing on making the framework better won't make us succeed. We should focus on making Drupal core a better and easier to use product as that is the number one barrier for Drupal's wider adoption.

We cannot afford to let Drupal remain a niche platform. Any user or organization that depends on Drupal also depends on Drupal's ability to grow. Failing to grow and improve will mean that the easier-to-use CMS competition will pass Drupal by as those products mature. This is what I called the [The Ockham's Razor Principle of Content Management Systems](https://dri.es/ockhams-razor-principle-of-content-management-systems) back in 2006 and why I'm obsessed with driving both innovation and usability – even if they sometimes seem to be at odds. I feel very strong about that vision, and can only conclude that so far, it has worked – we've come a really long way since 2006.

If we want Drupal to be relevant longer term, it needs to be a capable, robust product that people can use out of the box. Distributions can exist to meet different market segments, but they need to build on the usability patterns set by Drupal core, as that is how we lower the total cost and risk of adoption of Drupal solutions.

### Step 3: Select two strategic co-maintainers

Every Drupal release has had one or more targets for improvement. Drupal 5 focused on the installer, Drupal 6 focused on internationalization, and Drupal 7 focused on usability. Why? [Neil Drumm](https://dri.es/neil-drumm) (Drupal 5 co-maintainer) cared deeply about the installer, [Gábor Hojtsy](https://dri.es/gabor-hojtsy) (Drupal 6 co-maintainer) was and still is passionate about internationalization, and [Angie "webchick" Byron](https://dri.es/angela-webchick-byron) (Drupal 7 co-maintainer) cares deeply about usability. This isn't a coincidence – I picked them with strategic objectives in mind.

I think Drupal 8 needs to have two general areas of focus, as reflected by "Step 1: Create better separation between framework and product ". To this end I am considering picking a *Core framework co-maintainer* and a *Core product co-maintainer*. The role of the *Framework co-maintainer* would be to tend to APIs and base level tools, and help steer us to our goal of achieving better separation between the framework and the product. The role of the *Product co-maintainer* would be to make Drupal the best CMS in the world, by increasing usability and adding and improving features. My role in this plan is to assist and manage both co-maintainers, and to help with decision making, vision and product management.

By picking and empowering two people, and assigning them separate areas of responsibility, all the while coordinating with both of them to guarantee a unified product at the end of the day, I hope to increase the velocity of development for the Drupal 8 release cycle. I also intend to accomplish the goal of making Drupal easier to use, more feature rich, and at the same time more architecturally flexible.

When looking for Drupal 8 Framework and Product co-maintainers, I'll look for people who share that same vision – but who challenge me at the same time. A number of people come to mind, but is too early to share my current thinking. Watching people during the code freeze is a very important part of the recruiting process. After all, managing bug fixes, saying "no", and stabilizing the code base will end up being a critical part of any co-maintainer's job, especially after the development phase when the branch goes into maintenance mode.

### Step 4: Distributions could help, if we do them right

So how do we improve Drupal as a product? We've had Drupal distributions since the Drupal 4.6 era and I [first wrote about the potential of Drupal distributions in 2005](https://dri.es/drupal-distributions). Drupal distributions have great potential – turnkey solutions help us compete in new and different markets, something that could help Drupal become a significant player. The number of verticals is nearly unlimited and the opportunities are numerous.

There is a risk involved with distributions as well, which means that we need to approach them the right way. The risk is fragmentation, and it is why I feel it is important that distributions build on the usability patterns set by Drupal core. Distributions will be most helpful if they are tools that give you a head start towards building a particular type of Drupal site. Distributions that steal focus away from Drupal, or become hard to administer and extend using Drupal core usability patterns, will lead to fragmentation.

Drupal has a lot of momentum today, but we are still a niche player in the bigger CMS market. Drupal feels bigs, but we're still small. If by enabling more distributions all we do is create a lot of inconsistent niche products, some of which will be competing with one another, the Drupal project will lose momentum. If we can build competitive distributions that strengthen and accelerate the shared Drupal brand by using shared design patterns and user experience, we'll win.

Another risk is that small incompatibilities among distributions can drive distributions further and further apart. When distributions start building their own communities of contributors, having their own issue queues, all disconnected from drupal.org, then we have a problem. The difference between a distribution and a fork can be subtle. A proliferation of incompatible, incomplete and disconnected distributions could quickly become problematic. It would make it a lot harder for all of us to support and market Drupal.

We have written a lot of the the packaging scripts needed to put distributions together for Drupal.org, but we haven't decided yet how we want to use it and what a winning strategy could look like. What remains is a strategy discussion, not a technical discussion.

As a community, we have to take responsibility, and make sure that distributions collaborate rather than compete, much like the way that we attempt to work together on modules. That starts by centralizing all the code on drupal.org, by making Drupal core flexible enough, but also by encouraging shared design patterns and user experience. With distributions, community responsibility and leadership becomes even more important. Building one product is hard. Building a set of products in a way that strengthens and accelerates Drupal is much, much harder.

### Step 5: Experiment with distributed revision control systems

If the road to success is making Drupal a better product (along with making it a better framework), we need to be able to add new features to Drupal core.

Some features in Drupal core, like forums, blogs, polls and aggregator, haven't evolved as fast as the Drupal framework itself. For many people these modules are fine as they are, but more advanced alternatives have emerged in the contributed module repository. It begs the question: should we advance the modules in core or are they sufficient for 80% of our users? But also; are there any modules that we should be adding to core to make Drupal a better product?

I think we should advance those modules, and add some more. This is what I want the *Product co-maintainer* to help me with.

Giving more CVS write accounts or splitting core in smaller projects could help those modules advance faster, but it will also hurt us. A much better implementation to accomplish the same goal seems to be to experiment with distributed revision control systems. There are various technical issues to sort out to make this feasible, but I think it is worth the experiment because it will allow us to interact in new ways; ways that empower individual contributors, ways that allow people to self-organize around features, and that enable me to pull in bigger changes in a controlled fashion so we maintain consistency, quality and vision. To do it in a way that I'm comfortable with, it will require a significant investment in the project module and the Drupal.org infrastructure though.

In other words, I see myself experimenting with a distributed revision control system like Git or bzr. Not immediately, but somewhere in the Drupal 8 development cycle. Right now, I want everyone to be laser focused on getting Drupal 7 out. At least initially, I'd want the CVS repository to be the main, canonical repository from which Drupal core is packaged. However, I'd additionally pull in changes through Git/bzr for some period of time, to help decide if Git/bzr is what we want.

### Step 6: Backport small changes to stable releases

Some people suggested that the framework and the product could move at different speeds. I am uncomfortable with that concept.

Feature development drives API advancements. API improvements drive new and better features. It's an important feedback loop. My conviction is that feature development and API development are so related that it would be detrimental to try to do them asynchronously. Drupal's APIs have been changing for 10 years and there is no reason to believe that they will all be stable one day.

That said, there might be certain changes, like smaller usability improvements, standalone features, or new hooks that don't break existing code, that could be backported to previous Drupal releases during the development cycle. Of course the changes cannot break any code or invalidate existing documentation, but I think having a good test harness will help. Going forward, I'd be comfortable backporting certain changes that help Drupal advance, as long it is transparent to existing Drupal installations.

### Step 7: Continue to streamline the patch review process

A key problem still seems to be that it is difficult to get solid patch reviews, making it slow for some patches to get committed. Finding solid reviewers is hard, especially as Drupal becomes more advanced. I still believe this is a primary source of frustration, and that we should continue to streamline the patch review process.

We've introduced new rules in the patch review process lately (e.g. wrapping at 80 character length, formatting of PHPdoc, capitalization rules, etc). The proliferation of rules makes it more difficult to get your patch in. As a frequent reviewer and committer, I've found that code-style reviews, while important, can add quite some noise to an issue, and that it can derail API and architecture review.

One way to streamline the patch review process is to automate code style reviews just like we automated testing – at least to the extend possible because coding standards can be both complex and subtle. In an ideal world, code style reviews would take almost no comments, and would be reduced to a green or red status message just like with our automated testing. It could reduce the size of the 'needs review' queue further to things which actually merit review etc. By doing so, it would provide more focus, and help improve our velocity.

It doesn't necessarily solve the problem that one can't find enough good reviewers for one's patch but I think it will help.

### Step 8: Aim for a shorter release cycle

There is a sentiment amongst developers that the Drupal 7 core release cycles was too long. It can make it frustrating to contribute to Drupal core development. Who wants to work on a feature that might not be used in production for another 18 to 24 months? Near the end of the code freeze, things heat up, and people submit a lot more patches. In other words, shorter release cycles could make it more compelling to contribute.

At the same time, I don't think the Drupal 7 release cycle was too long, per se. A lot of the big new features, such as the new database abstraction layer and Field API (formerly known as [Content Construction Kit (CCK)](https://dri.es/custom-content-types)), took several months of work, and many months more to be usable. We finished converting code to the new database abstraction layer over a year after the initial commit. Drupal 7's Field API is probably the biggest architectural change in the last 5 years – it will take a couple more major releases for Field API to be truly integrated into Drupal. In other words, sometimes we need a longer release cycle to allow for big, game-changing changes.

How long the Drupal 8 release cycle will be I can't say yet, but let's aim for a shorter release cycle. The length of the release cycle depends on how fast Drupal 7 is adopted, how fast the contributed modules reach the "plateau of productivity", and how fast Drupal 8 shapes up to be a great release. You don't want it to be too long, but you don't want it to be too short, either. Furthermore, as a goal, the length of the release cycle shouldn't trump the larger, overarching goals of any given release. I'll take constant temperature of where we are and balance all the different pros and cons (eg. innovation versus stability).

Another adjustment to the release cycle could be separate code freezes for the Framework (APIs) and the Product (user features and usability). The Framework/API freeze would precede the Product/CMS freeze, and would let us focus on establishing the underlying changes earlier in the overall cycle, with focus shifting to features and usability later in the cycle. This will make feature development easier as the APIs will not be shifting around as much, and it will give a period of time after the Framework freeze where we can focus on bugfixing and performance improving the Framework, even while new features are still being developed.

### Some closing thoughts

The 8 steps outlined above describe actions and steps that we can take to help make Drupal 8 rock. As we look forward to Drupal 8 development, I think it is important to focus on the right things. If we want Drupal to win and prevent Drupal from being stuck as a small player in the bigger picture, we need to focus on making Drupal easier to use for both end-users and developers, while maintaining our innovative edge. Some of these 8 steps make Drupal better for end-users, some of these steps make Drupal better for developers and some of these steps make Drupal a better product. I truly believe we can all win.
