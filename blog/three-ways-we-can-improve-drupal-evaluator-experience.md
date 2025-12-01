---
title: "Three ways we can improve Drupal's evaluator experience"
date: '2018-02-27T10:41:13-05:00'
author: Dries
summary: "It’s time to improve Drupal's download process and end-user documentation. I believe we can improve Drupal's evaluator experience with these three steps."
image: drupal/evaluator-conversion-funnel
tags:
  - Drupal
  - Usability
  - 'Drupal Association'
  - Governance
published: true
type: blog
url: /three-ways-we-can-improve-drupal-evaluator-experience
id: 4196
---

Last week, [Matthew Grasmick](https://www.drupal.org/u/grasmash) stepped into the shoes of a developer who has no Drupal experience, and attempted to get a new "Hello world!" site up and running using four different PHP frameworks: [WordPress](https://wordpress.org), [Laravel](https://laravel.com), [Symfony](https://symfony.com) and [Drupal](https://www.drupal.org). He shared his experience in [a transparent blog post](http://matthewgrasmick.com/compare-php-frameworks). In addition to detailing the inefficiencies in Drupal's download process and end-user documentation, Matt also shows that out of the four frameworks, Drupal required the most steps to get installed.

While it is sobering to read, I'm glad Matthew brought this problem to the forefront. Having a good evaluator experience is critical as it has a direct impact on adoption rates. A lot goes into a successful evaluator experience: from learning what Drupal is, to understanding how it works, getting it installed and getting your first piece of content published.

So how can we make some very necessary improvements to Drupal's evaluator experience?

I like to think of the evaluator experience as a *conversion funnel*, similar to the [purchase funnel](https://en.wikipedia.org/wiki/Purchase_funnel) developed in 1898 by E. St. Elmo Lewis. It maps an end-user journey from the moment a product attracts the user's attention to the point of use. It's useful to visualize the process as a funnel, because it helps us better understand where the roadblocks are and where to focus our efforts. For example, we know that more than 13 million people visited Drupal.org in 2017 (top of the funnel) and that approximately 75,000 new Drupal 8 websites launched in production (bottom of the funnel). A very large number of evaluators were lost as they moved down the conversion funnel. It would be good to better understand what goes on in between.

[image drupal/evaluator-conversion-funnel resize=false]

As you can see from the image above, the **Drupal Association** plays an important role at the top of the funnel; from educating people about Drupal, to providing a streamlined download experience on Drupal.org, to helping users find themes and modules, and much more.

The [Drupal Association](https://www.drupal.org/association) could do more to simplify the evaluator experience. For example, I like the idea of the Drupal Association offering and promoting a hosted, one-click trial service. This could be built by extending a service like [Simplytest.me](https://simplytest.me) into a hosted evaluation service, especially when combined with the [upcoming Umami installation profile](https://www.drupal.org/project/ideas/issues/2847582). (The existing "Try Drupal" program could evolve into a "Try hosting platforms" program. This could help resolve the expectation mismatch with the current "Try Drupal" program, which is currently more focused on showcasing hosting offerings than providing a seamless Drupal evaluation experience.)

The good news is that the Drupal Association recognizes the same needs, and in the past months, we have been working together on plans to improve Drupal's conversional funnel. The Drupal Association will share [its 2018 execution plans](https://www.drupal.org/association/blog/drupal-association-2018-execution-plan) in the upcoming weeks. As you'll see, the plans address some of the pain points for evaluators (though not necessarily through a hosted trial service, as that could take significant engineering and infrastructure resources).

The **Documentation Working Group** also plays a very important role in this process. After reading Matthew's post, I reached out to [Joe Shindelar](https://www.drupal.org/u/eojthebrave), who is a member of the [Drupal Documentation Working Group](https://www.drupal.org/governance/doc-working-group). He explained that the Documentation Working Group has not been meeting regularly nor coordinating initiatives for some time.

It is time to rethink our approach around Drupal's documentation. [Adam Hoenich](https://www.drupal.org/u/phenaproxima), a long-time Drupal contributor, recommends that documentation becomes [a full-fledged core initiative](https://medium.com/@djphenaproxima/how-can-we-fix-drupals-documentation-497f9baa7fe1), including the addition of a Documentation Maintainer to the [Core Committer team](https://www.drupal.org/contribute/core/maintainers#committer). His proposal includes blocking commits to Drupal on documentation.

I've no doubt that we have to evolve our governance model surrounding documentation. It's hard to write world-class documentation by committee without good governance and Adam's recommendations are compelling. Drupal's [API documentation](https://api.drupal.org), for example, is governed by the Core Committers; while there is always room for improvement, it's really well-maintained. Some of you might remember that we had an official Documentation Maintainer role in the past, filled by [Jennifer Hodgdon](https://www.drupal.org/u/jhodgdon). Reinstating this position could bring documentation back into clearer focus and provide the necessary governance. I also suspect that a stronger emphasis on coordination, governance and recognition for documentation work, would inspire more contributors to help.

Last but not least, this also affects the **Drupal (Core) Contributors**. Evaluators often spend hours trying to get their web server configured, PHP installed or their database setup. As a community, we could help alleviate this pain by deciding to have a single, recommended default installation environment. For example, we could maintain and promote a Docker container (including an official `docker-compose.yml`) that ships with the latest version of Drupal. It would simplify many of our documentation efforts, and eliminate many roadblocks from the evaluation process.

To narrow down my recommendations, I would propose the following three steps:

1. A single, recommended default installation environment (e.g. Docker container) for evaluators or developers taking their first steps in Drupal development.
2. Infrastructure budget and engineering resources for the Drupal Association so they can offer a true hosted "Try Drupal" service.
3. A Documentation Maintainer who can focus on end-user documentation, is a member of the Core Committer team and is responsible for defining the scope of what should be documented. Given the amount of work this position would entail, it would be ideal if this person could be at least partially funded.

Of course, there are many other solutions, but these are the areas I'd focus on. As always, success depends on our ability to align on solutions, coordinate all the work, and allocate the time and money to implement the necessary improvements. If you think you can help with any of the proposed steps, please [let us know in the comments](https://dri.es/three-ways-we-can-improve-drupal-evaluator-experience#comments), and we'll help you get involved.
