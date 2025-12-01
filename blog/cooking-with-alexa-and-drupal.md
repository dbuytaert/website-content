---
title: 'Cooking with Alexa and Drupal'
date: '2018-03-06T13:51:46-05:00'
author: Dries
summary: 'A demo of how you can integrate Drupal with Amazon Echo to build a voice-enabled cooking website.'
image: acquia/cooking-with-alexa
tags:
  - Drupal
  - Acquia
  - Amazon
published: true
type: blog
url: /cooking-with-alexa-and-drupal
id: 4216
---

When I'm home, one of the devices I use most frequently is the Amazon Echo. I use it to play music, check the weather, set timers, check traffic, and more. It's a gadget that is beginning to inform many of my daily habits.

Discovering how organizations can use a device like the Amazon Echo is big part of my professional life too. For the past two years, [Acquia Labs has been helping customers](https://dri.es/think-beyond-with-acquia-labs) take advantage of conversational interfaces, beacons and augmented reality [to remove friction from user experiences](https://dri.es/friduction-the-internets-unstoppable-drive-to-eliminate-friction). One of the most exciting examples of this was the development of [Ask GeorgiaGov](https://dri.es/think-beyond-with-acquia-labs), an Alexa skill that enables Georgia state residents to use an Amazon Echo to easily interact with government agencies.

The demo video below shows another example. It features a shopper named Alex, who has just returned from Freshland Market (a fictional grocery store). After selecting a salmon recipe from Freshland Market's website, Alex has all the ingredients she needs to get started. Alex begins by asking Alexa how to make her preferred salmon recipe for eight people. The recipe on Freshland Market's Drupal website is for four people, so the Freshland Market Alexa skill automatically adjusts the number of ingredients needed to accommodate eight people. By simply asking Alexa a series of questions, Alex is able to preheat the oven, make ingredient substitutions and complete the recipe without ever looking at her phone or laptop. With Alexa, Alex is able to stay focused on the joy of cooking, instead of following a complex recipe.

[video fFBYqPn8C4E]

This project was easy to implement because the team took advantage of the <a hef="https://www.drupal.org/project/alexa">Alexa integration module</a>, which allows Drupal to respond to Alexa skill requests. Originally created by Jakub Suchy (Acquia) and maintained by Chris Hamper (Acquia), the Alexa integration module enables Drupal to respond to custom voice commands, otherwise known as "skills".

[image acquia/cooking-with-alexa resize=false]

Once an Amazon Echo user provides a verbal query, known as an "utterance", this vocal input is converted into a text-based request (the "intent") that is sent to the Freshland Market website (the "endpoint"). From there, a combination of custom code and the Alexa module for Drupal 8 responds to the Amazon Echo with the requested information.

Over the past year, it's been very exciting to see the Acquia Labs team build a connected customer journey using [chatbots](https://dri.es/think-beyond-with-acquia-labs), [augmented reality](https://dri.es/shopping-with-augmented-reality) and now, voice assistance. It's a great example of how organizations can build cross-channel customer experiences that take place both online and offline, in store and at home, and across multiple touch points. While Freshland Market is a fictional store, any organization could begin creating these user experiences today.

*Special thanks to [Chris Hamper](https://www.drupal.org/u/hampercm) and [Preston So](https://www.drupal.org/u/prestonso) for building the Freshland Market Alexa skill, and thank you to [Ash Heath](https://twitter.com/burnashburn) and Drew Robertson for producing the demo videos.*
