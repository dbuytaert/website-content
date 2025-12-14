---
title: 'Cross-channel user experiences with Drupal'
date: '2016-05-16T10:55:56-04:00'
author: Dries
summary: 'How new user experiences and distribution platforms will change the way we build the web in the future'
image: blog/javascript-powered-multichannel
tags:
  - Drupal
  - 'Headless Drupal'
published: true
type: blog
url: /cross-channel-user-experiences-with-drupal
id: 3681
---

[image blog/javascript-powered-multichannel resize=false]

Last year around this time, I wrote that [The Big Reverse of Web](https://dri.es/the-big-reverse-of-the-web) would force a major re-architecture of the web to bring the right information, to the right person, at the right time, in the right context. I believe that conversational interfaces like [Amazon Echo](https://www.nytimes.com/2016/03/10/technology/the-echo-from-amazon-brims-with-groundbreaking-promise.html) are further proof that the big reverse is happening.

New user experience and distribution platforms only come along every 5-10 years, and when they do, they cause massive shifts in the web's underlying technology. The last big one was mobile, and the web industry adapted. Conversational interfaces could be the next user experience and distribution platform – just look at [Amazon Echo](https://www.youtube.com/watch?v=2fxDQUe57-k) (aka Alexa), [Facebook's messenger](https://www.wired.com/2016/04/facebook-believes-messenger-will-anchor-post-app-internet/) or [Microsoft's Conversation-as-a-Platform](https://www.theverge.com/2016/3/30/11331388/microsoft-chatbots-ai-build).

Today, hardly anyone questions whether to build a mobile-optimized website. A decade from now, we might be saying the same thing about optimizing digital experiences for voice or chat commands. The convenience of a customer experience will be a critical key differentiator. As a result, no one will think twice about optimizing their websites for multiple interaction patterns, including conversational interfaces like voice and chat. Anyone will be able to deliver a continuous user experience across multiple channels, devices and interaction patterns. In some of these cross-channel experiences, users will never even look at a website. Conversational interfaces let users disintermediate the website by asking anything and getting instant, often personalized, results.

To prototype this future, my team at [Acquia](https://www.acquia.com) built a fully functional demo based on Drupal 8 and recorded a video of it. In the [demo video below](https://youtu.be/VbgULXtITro), we show a sample supermarket chain called Gourmet Market. Gourmet Market wants their customers to not only shop online using their website, but also use Echo or push notifications to do business with them.

We built an [Alexa integration module](https://www.drupal.org/project/alexa) to connect Alexa to the Gourmet Market site and to answer questions about sale items. For example, you can speak the command: "Alexa, ask Gourmet Market what fruits are on sale today". From there, Alexa would make a call to the Gourmet Market website, finding what is on sale in the specified category and pull only the needed information related to your ask.

On the website's side, a store manager can tag certain items as "on sale", and Alexa's voice responses will automatically and instantly reflect those changes. The marketing manager needs no expertise in programming – Alexa composes its response by talking to Drupal 8 using web service APIs.

The [demo video](https://youtu.be/VbgULXtITro) also shows how a site could deliver smart notifications. If you ask for an item that is not on sale, the Gourmet Market site can automatically notify you via text once the store manager tags it as "On sale".

[video VbgULXtITro]

From a technical point of view, we've had to teach Drupal how to respond to a voice command, otherwise known as a "Skill", coming into Alexa. Alexa Skills are fairly straightforward to create. First, you specify a list of "Intents", which are basically the commands you want users to run in a way very similar to Drupal's routes. From there, you specify a list of "Utterances", or sentences you want Echo to react to that map to the Intents. In the example of Gourmet Market above, the Intents would have a command called `GetSaleItems`. Once the command is executed, your Drupal site will receive a webhook callback on `/alexa/callback` with a payload of the command and any arguments. The [Alexa module for Drupal 8](https://www.drupal.org/project/alexa) will validate that the request really came from Alexa, and fire a Drupal Event that allows any Drupal module to respond.

It's exciting to think about how new user experiences and distribution platforms will change the way we build the [web in the future](https://dri.es/the-post-browser-era-of-the-web-is-coming). As I referenced in [Drupalcon New Orleans keynote](https://dri.es/state-of-drupal-presentation-may-2016), the Drupal community needs to put some thought into how to design and build multichannel customer experiences. Voice assistance, chatbots or notifications are just one part of the greater equation. If you have any further thoughts on this topic, please share them in the comments.

[image blog/digital-trends-2016 resize=false]
