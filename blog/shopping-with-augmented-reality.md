---
url: 'https://dri.es/shopping-with-augmented-reality'
title: 'Shopping with augmented reality'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2017-10-26T13:34:25-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'How we can use augmented reality with Drupal to superimpose useful information in a shopping experience'
tags:
  - Drupal
  - 'Augmented reality'
  - Acquia
image: blog/shopping-with-augmented-reality-example-2017
published: true
id: 4056
---

# Shopping with augmented reality

[image blog/shopping-with-augmented-reality-example-2017 resize=false]

Last spring, Acquia Labs [built a chatbot prototype](https://dri.es/think-beyond-with-acquia-labs) that helps customers choose recipes and plan shopping lists with dietary restrictions and preferences in mind. The ability to interact with a chatbot assistant rather than having to research and plan everything on your own can make grocery shopping much easier. We wanted to take this a step further and explore how augmented reality could also improve the shopping experience.

[video ZroFBG7-P7Q]

The demo video above features how a shopper named Alex can interact with an augmented reality application to [remove friction](https://dri.es/friduction-the-internets-unstoppable-drive-to-eliminate-friction) from her shopping experience at Freshland Market (a fictional grocery store). The Freshland Market mobile application not only guides Alex through her shopping list but also helps her to make more informed shopping decisions through augmented reality overlays. It superimposes useful information such as price, user ratings and recommended recipes, over shopping items detected by a smartphone camera. The application can personalize Alex's shopping experience by highlighting products that fit her dietary restrictions or preferences.

What is exciting about this demo is that the Acquia Labs team built the Freshland Market application with Drupal 8 and augmented reality technology that is commercially available today.

[image blog/shopping-with-augmented-reality-architecture-2017 resize=false]

The first step in developing the application was to use an augmented reality library, [Vuforia](https://www.vuforia.com), which identifies pre-configured targets. In our demo, these targets are images of product labels, such as the tomato sauce and cereal labels shown in the video. Each target is given a unique ID. This ID is used to query the Freshland Market Drupal site for content related to that target.

The Freshland Market site stores all of the product information in Drupal, including price, dietary concerns, and reviews. Thanks to [Drupal's web services support](https://dri.es/tag/web-services) and the [JSON API module](https://www.drupal.org/project/jsonapi), Drupal 8 can serve content to the Freshland Market application. This means that if the Drupal content for Rosemary &amp; Olive Oil chips is edited to mark the item on sale, this will automatically be reflected in the content superimposed through the mobile application.

In addition to information on price and nutrition, the Freshland Market site also stores the location of each product. This makes it possible to guide a shopper to the product's location in the store, evolving the shopping list into a shopping route. This makes finding grocery items easy.

Augmented reality is building momentum because it moves beyond the limits of a traditional user interface, or in our case, the traditional website. It superimposes a digital layer onto a user's actual world. This technology is still emerging, and is not as established as virtual assistants and wearables, but it continues to gain traction. In 2016, the augmented reality market was valued at $2.39 billion and it is [expected to reach $61.39 billion by 2023](https://www.prnewswire.com/news-releases/augmented-reality-market-to-reach-613-billion-by-2023-increasing-demand-for-ar-devices--applications-in-medical-retail--e-commerce-300495971.html).

What is exciting is that these new technology trends require content management solutions. In the featured demo, there is a large volume of product data and content that needs to be managed in order to serve the augmented reality capabilities of the Freshland Market mobile application. The Drupal community's emphasis on [making Drupal API-first](https://dri.es/drupal-is-api-first-not-api-only) in addition to supporting distributions like [Reservoir](https://dri.es/reservoir-a-simple-way-to-decouple-drupal) means that Drupal 8 is prepared to support emerging channels.

If you are ready to start reimagining how your organization interacts with its users, or how to take advantage of new technology trends, [Acquia Labs is here to help](https://www.acquia.com/resources/acquia-labs).

*Special thanks to [Chris Hamper](https://www.drupal.org/u/hampercm) and [Preston So](https://www.drupal.org/u/prestonso) for building the Freshland Market augmented reality application, and thank you to [Ash Heath](https://twitter.com/burnashburn) and Drew Robertson for producing the demo video.*
