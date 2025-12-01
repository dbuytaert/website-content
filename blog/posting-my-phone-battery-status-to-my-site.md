---
title: "Posting my phone's battery status to my site"
date: '2018-02-25T20:56:19-05:00'
author: Dries
summary: 'Working towards being able to publish notes and photos from my phone'
tags:
  - Drupal
  - POSSE
  - 'Web services'
published: true
type: blog
url: /posting-my-phone-battery-status-to-my-site
id: 4191
---

Earlier this month, [I uninstalled Facebook from my phone](https://dri.es/taking-control-of-my-data-and-social-media). I also made a commitment [to own my own content](https://dri.es/to-pesos-or-to-posse) and [to share shorter notes on my site](https://dri.es/reclaiming-my-blog-as-my-thought-space).

One thing that I like about Facebook and Twitter is how easy it is to share quick updates, especially from my phone. If I'm going to be serious about [POSSE](https://dri.es/to-pesos-or-to-posse), having a good iOS application that removes friction from the publishing process is important.

I always wanted to learn some iOS development, so I decided to jump in and start building a basic iOS application to post notes and photos directly to my site. I've already made some progress; so far my iOS application shares the state of my phone battery at <https://dri.es/status>. This is what it looks like:

[image blog/phone-battery-status-2018 resize=false]

This was inspired by [Aaron Parecki](https://aaronparecki.com), who not only tracks his phone battery but also tracks [his sleep](https://aaronparecki.com/sleep), [his health patterns](https://aaronparecki.com/health) and [his diet](https://aaronparecki.com/ate). Talk about owning your own data and liking tacos!

Sharing the state of my phone's battery might sound silly but it's a first step towards being able to publish notes and photos from my phone. To post the state of my phone's battery on my Drupal site, my iOS application reads my battery status, wraps it in a JSON object and sends it to a new REST endpoint on my Drupal site. It took less than 100 lines of code to accomplish this. More importantly, it uses the same web services approach as posting notes and photos will.

In an unexpected turn of events (yes, unnecessary scope creep), I decided it would be neat to keep my status page up-to-date with real-time battery information. In good tradition, the scope creep ended up consuming most of my time. Sending periodic battery updates turned out to be difficult because when a user is not actively using an iOS application, iOS suspends the application. This means that the applications can't listen to battery events nor send data using web services. This makes sense: suspending the application helps improve battery life, and allows iOS to devote more system resources to the active application in the foreground.

The old Linux hacker in me wasn't going to be stopped though; I wanted my application to keep sending regular updates, even when it's not the active application. It turns out iOS makes a few exceptions and allows certain categories of applications – navigation, music and VOIP applications – to keep running in the background. For example, Waze continues to provide navigation instructions and Spotify will play music even when they are not the active application running in the foreground.

You guessed it; the solution was to turn my note-posting-turned-battery application into a navigation application. This requires the application to listen to location update events from my phone's GPS. Doing so prevents the application from being suspended. As a bonus, I can use my location information for future use cases such as geotagging posts.

This navigation hack works really well, but the bad news is that my application drains my phone battery rather quickly. The good news is that I can easily instruct Drupal to send me email notifications to remind me to charge my phone.

Scope creep aside, it's been fun to work with [Drupal 8's built-in REST API](https://dri.es/tag/web-services) and to learn some iOS application development. Now I can post my phone's battery on my site, posting notes or photos shouldn't be much more difficult.
