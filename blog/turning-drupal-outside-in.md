---
title: 'Turning Drupal outside-in'
date: '2016-02-10T05:49:27-05:00'
author: Dries
tags:
  - Drupal
  - Usability
  - JavaScript
  - Outside-in
published: true
type: blog
url: /turning-drupal-outside-in
id: 3561
---

There has been a lot of discussion around the future of the Drupal front end both on [Drupal.org](https://www.drupal.org) ([\#2645250](https://www.drupal.org/node/2645250), [\#2645666](https://www.drupal.org/node/2645666), [\#2651660](https://www.drupal.org/node/2651660), [\#2655556](https://www.drupal.org/node/2655556)) and on my blog posts about [the future of decoupled Drupal](https://dri.es/the-future-of-decoupled-drupal), [why a standard framework in core is a good idea](https://dri.es/should-we-decouple-drupal-with-a-client-side-framework), and [the process of evaluating frameworks](https://dri.es/selecting-a-client-side-framework-for-drupal). These all relate to my concept of "progressive decoupling", in which some portions of the page are handed over to client-side logic after Drupal renders the initial page (not to be confused with "full decoupling").

My blog posts have drawn a variety of reactions. Members of the Drupal community, including [Lewis Nyman](http://lewisnyman.co.uk/blog/should-drupal-add-another-js-framework-into-core-not-in-the-name-of-ux/), [Théodore Biadala](http://read.theodoreb.net/2016/drupal-gets-feature-request-out-of-the-blue.html) and [Campbell Vertesi](https://ohthehugemanatee.org/blog/2015/12/08/how-drupal-should-handle-client-side-framework-obsolescence/), have written blog posts with their opinions, as well as [Ed Faulkner](https://eaf4.com/decoupled-drupal-from-an-ember-maintainers-perspective/) of the [Ember community](http://emberjs.com). Last but not least, in response to [my last blog post](https://dri.es/selecting-a-client-side-framework-for-drupal), Google changed [Angular 2's license from Apache to MIT](https://github.com/angular/angular/blob/master/LICENSE) for better compatibility with Drupal. I read all the posts and comments with great interest and wanted to thank everyone for all the feedback; the open discussion around this is nothing short of amazing. This is exactly what I hoped for: community members from around the world brainstorming about the proposal based on their experience, because only with the combined constructive criticism will we arrive at the best solution possible.

Based on the discussion, rather than selecting a client-side JavaScript framework for progressive decoupling right now, I believe the overarching question the community wants to answer first is: *How do we keep Drupal relevant and widen Drupal's adoption by improving the user experience (UX)?*

Improving Drupal's user experience is a topic near and dear to my heart. Drupal's user experience challenges led to [my invitation to Mark Boulton to redesign Drupal 7](https://dri.es/mark-boulton-to-help-with-drupal-7), the creation of the [Spark initiative](https://dri.es/announcing-spark-authoring-improvements-for-drupal-7-and-drupal-8) to improve the authoring experience for Drupal 8, and continued support for usability-related initiatives. In fact, the impetus behind progressive decoupling and adopting a client-side framework is the need to improve Drupal's user experience.

It took me a bit longer than planned, but I wanted to take the time to address some of the concerns and share more of my thoughts about improving Drupal's UX (and JavaScript frameworks).

### To iterate or to disrupt?

In [his post](http://lewisnyman.co.uk/blog/should-drupal-add-another-js-framework-into-core-not-in-the-name-of-ux/), Lewis writes that the issues facing Drupal's UX "go far deeper than code" and that many of [the biggest problems found during the Drupal 8 usability study](https://www.drupal.org/node/2497361) last year are not resolved with a JavaScript framework. This is true; [the results of the Drupal 8 usability study](https://www.youtube.com/watch?v=E31e5hzHMOE) show that Drupal can confuse users with its complex mental models and terminology, but it also shows how modern features like real-time previews and in-page block insertion are increasingly assumed to be available.

To date, much of our UX improvements have been based on an *iterative* process, meaning it converges on a more refined end state by removing problems in the current state. However, we also require *disruptive* thinking, which is about introducing entirely new ideas, for true innovation to happen. It's essentially removing all constraints and imagining what an ideal result would look like.

I think we need to recognize that while some of the [documented usability problems](https://www.drupal.org/node/2497361) coming out of the Drupal 8 usability study can be addressed by making incremental changes to Drupal's user experience (e.g. our terminology), other well-known usability problems most likely require a more disruptive approach (e.g. our complex mental model). I also believe that we must acknowledge that disruptive improvements are possibly more impactful in keeping Drupal relevant and widening Drupal's adoption.

At this point, to get ahead and lead, I believe we have to do both. We have to iterate *and* disrupt.

### From inside-out to outside-in

Let's forget about Drupal for a second and observe the world around us. Think of all the web applications you use on a regular basis, and consider the interaction patterns you find in them. In popular applications like Slack, the user can perform any number of operations to edit preferences (such as color scheme) and [modify content](https://www.youtube.com/watch?v=LFzM4fw8C38) (such as in-place editing) without incurring a single full page refresh. Many elements of the page can be changed without the user's flow being interrupted. Another example is Trello, in which [users can create new lists on the fly and then add cards to them](https://www.youtube.com/watch?v=xky48zyL9iA) without ever having to wait for a server response.

Contrast this with Drupal's approach, where any complex operation requires the user to have detailed prior knowledge about the system. In our current mental model, everything begins in the administration layer at the most granular level and requires an unmapped process of bottom-up assembly. A user has to make a content type, add fields, create some content, configure a view mode, build a view, and possibly make the view the front page. If each individual step is already this involved, consider how much more difficult it becomes to traverse them in the right order to finally see an end result. While very powerful, the problem is that Drupal's current model is "inside-out". This is why it would be disruptive to move Drupal towards an "outside-in" mental model. In this model, I should be able to start entering content, click anything on the page, seamlessly edit any aspect of its configuration in-place, and see the change take effect immediately.

Drupal 8's in-place editing feature is actually a good start at this; it enables the user to edit what they see without an interrupted workflow, with faster previews and without needing to find what thing it is before they can start editing.

### Making it real with content modeling

Eight years ago in 2007, [I wrote about a database product called DabbleDB](https://dri.es/dabbledb-cck-views-twelve-duvels). I shared my belief that it was important to move CCK and Views into Drupal's core and learn from DabbleDB's integrated approach. DabbleDB was acquired by Twitter in 2010 but you can still find [an eight-year-old demo video on YouTube](https://www.youtube.com/watch?v=6wZmYMWKLkY). While the focus of DabbleDB is different, and the UX is obsolete, there is still a lot we can learn from it today: (1) it shows a more integrated experience between content creation, content modeling, and creating views of content, (2) it takes more of an outside-in approach, (3) it uses a lot less intimidating terminology while offering very powerful capabilities, and (4) it uses a lot of in-place editing. At a minimum, DabbleDB could give us some inspiration for what a better, integrated content modeling experience could look like, with the caveat that the UX should be as effortless as possible to match modern standards.

Other new data modeling approaches with compelling user experiences have recently entered the landscape. These include back end-as-a-service (BEaaS) solutions such as [Backand](https://www.backand.com), which provides a visually clean drag-and-drop interface for data modeling and helpful features for JavaScript application developers. Our use cases are not quite the same, but Drupal would benefit immensely from a holistic experience for content modeling and content views that incorporates both the rich feature set of DabbleDB and the intuitive UX of Backand.

This sort of vision was not possible in 2007 when CCK was a contributed module for Drupal 6. It still wasn't possible in Drupal 7 when Views existed as a separate contributed module. But now that both CCK and Views are in Drupal 8 core, we can finally start to think about how we can more deeply integrate the two. This kind of integration would be nontrivial but could dramatically simplify Drupal's UX. This should be really exciting because so many people are attracted to Drupal exactly because of features like CCK and Views. Taking an integrated approach like DabbleDB, paired with a seamless and easy-to-use experience like Slack, Trello and Backand, is exactly the kind of disruptive thinking we should do.

What most of the examples above have in common are in-place editing, immediate previews, no page refreshes, and non-blocking workflows. The implications on our form and render systems of providing configuration changes directly on the rendered page are significant. To achieve this requires us to have robust state management and rendering on the client side as well as the server side. In my vision, Twig will provide structure for the overall page and non-interactive portions, but more JavaScript will more than likely be necessary for certain parts of the page in order to achieve the UX that all users of the web have come to expect.

We shouldn't limit ourselves to this one example, as there are a multitude of Drupal interfaces that could all benefit from both big and small changes. We all want to improve Drupal's user experience – and we have to. To do so, we have to constantly iterate and disrupt. I hope we can all collaborate on figuring out what that looks like.

*Special thanks to [Preston So](https://www.drupal.org/u/prestonso) and [Kevin O'Leary](https://www.drupal.org/u/tkoleary) for contributions to this blog post and to [Wim Leers](https://www.drupal.org/u/wim-leers) for feedback.*
