---
url: 'https://dri.es/drupal-distributions'
title: 'Drupal distributions'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2006-10-30T11:28:03-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
  - 'Drupal distributions'
image: drupal/distributions
published: true
featured: true
id: 173
---

# Drupal distributions

Drupal 5.0, the upcoming Drupal release, will have better support for *Drupal distributions*. Each distribution takes some set of Drupal themes and modules and packages them together with the Drupal core, along with custom installation steps, documentation, and so on. For example, one could create a distribution called "Drupal for Education"; it could have pre-configured roles and permissions for both teachers and students, and ship with additional modules that allow one to offer online courses and testing.

### New and different markets

Distributions allow people to create ready-made downloadable packages with their own focus and vision. This will enable Drupal to reach out to both new and different markets. If we had a "Drupal for Education" distribution it might, at one point, be able to compete head on with the other course management systems like [Moodle](https://moodle.org/) and [Blackboard](http://www.blackboard.com/).

Not only will distributions allow Drupal to compete in existing markets, it will also enable people to create new markets. For example, someone could create a "Drupal for Student Organizations" distribution and instantly be the number one tool in that market. The number of verticals is nearly unlimited and the opportunities are numerous. Divide and conquer.

While the possibilities are nearly unlimited, it does impose a number of challenges ... (Click [read more](drupal-distributions) to learn more about these.)

### Collaboration, not competition

It is important that Drupal distributions collaborate, and not compete. To do so, we have to provide Drupal distributions an environment that encourages collaboration, and that allows for specialization (such as custom documentation and support) without introducing incompatibilities that drive competition.

The good news is that we know how to do this. We've been through this already with [CivicSpace](http://civicspacelabs.org/) (previously called "DeanSpace"), a Drupal distribution for online campaign management and grassroots activism. They were quick to realize that the success of the CivicSpace distribution depends on the success Drupal core, and vice versa. The decided they shouldn't fork core development. Instead, CivicSpace decided to do all its development on the drupal.org infrastructure, to synchronize releases, to submit all patches upstream, to centralize bug reports, and to share documentation where possible. Collaboration, not competition.

The bad news is that can be hard work. People will find that creating a distribution is fun and easy, but that being a [responsible maintainer](/responsible-maintainers) might be a lot less fun. Who wants to track changes, write documentation, maintain modules, provide upgrade paths, manage releases and provide support for years to come?

So how can we can encourage distributions to collaborate, and how can we avoid users getting stuck with an old Drupal version because a distribution is not maintained properly? Remember the "Drupal for Bloggers" distribution? Hundreds of users had no upgrade path and were stuck with an insecure Drupal fork. The author decided to compete rather than to collaborate, and introduced various incompatibilities that, in the end, negatively affected the users. It is a good example of what we want to avoid.

So here is a simple rule: don't create a distribution because you can. Create a distribution because you want to provide users a service. If you don't want to collaborate or if you can't commit to providing a service around your distribution, you are likely to do more harm than good.

We also have to keep in mind that there will never be a perfect solution. Even if a distribution is maintained properly, consider this simple fact: no distribution will be able to provide timely bug fixes, and no matter what you do, users will always complain that it takes too long to roll a new security or bugfix release.

What exactly the solution is going to look like, I don't know, but I think the short answer is: *community responsibility*. We can't implement a technical solution for what might be a social issue. This is a community challenge that needs a community solution.

As a community we should disapprove Drupal distributions that do not intend to collaborate, that have no signs of long term commitment, or that risk locking people in. It might involve [new and bigger growing pains](/drupal-predictions-for-2006) but so far, we have done amazingly well figuring these things out – and that is reflected by our healthy growth.

### Fragmentation and natural selection

Things might be more subtle than that. Even if we collaborate and all Drupal distributions are built on the exact same Drupal core, there will still be incompatibilities in terms of documentation, support and vision. After all, most Drupal distributions will want to provide specialized documentation and support. Being able to create this kind of value is the very reason why distributions exist.

These incompatibilities can create an incentive to compete. Just look at what is happening with Debian and Ubuntu. Ubuntu began as a fork of Debian with the aim of drawing from Debian's code regularly in order to allow for frequent releases. So Debian diverged and Ubuntu was created. Now, they are driven more and more apart by these incompatibilities, and as a result, Debian risks being superseded. The same is happening with Mambo and Joomla, with NetBSD and FreeBSD, already happened with Unices and Linux, and might happen with RedHat and Oracle.

If we are not careful, Drupal risks suffering a similar fate: *splintering into multiple competing distributions*. It is a slow process and often takes many years (and is therefore often disregarded by the people who are too closely involved). The good news is that this isn't necessarily a bad thing because ultimately more people win. It is how nature works and it is called "mutation" and "natural selection".

That said, we should disapprove distributions that are created out of frustration (eg. a "Drupal Pro" distribution or a "Drupal Lite" distribution whose main reason of existence is driven by frustration). The difference between a distribution and a fork can be a subtle. Listening to our users and changing the way things work should continue to be the preferred answer to user frustration. As Darwin said, it's not the strongest organisms that win, it's the most adaptable to change.

[image drupal/distributions resize=false]

### Conclusions

The fact that Drupal 5.0 will support distributions is big, and most people have yet to see its full potential. I don't think that any other Open Source project has done something like this before – or at least, not on the scale that we might end up doing this. Time will tell. It is going to be an exciting change, and I'm confident that we'll be able to untap the incredible potential.

But as a community, we have to take responsibility, and make sure that distributions collaborate rather than compete. We also have to make sure that we disapprove distributions that are not properly maintained. Community responsibility will become ever important as we move forward with this awesome adventure. I hope it all works out.
