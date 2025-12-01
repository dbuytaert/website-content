---
title: 'We made Drupal a lot easier to evaluate'
date: '2018-09-14T02:44:51-04:00'
author: Dries
summary: 'Install Drupal in less than two minutes and experience a beautifully designed demo application'
image: drupal/improve-technical-evaluator-experience-2018
tags:
  - Drupal
published: true
type: blog
url: /we-made-drupal-a-lot-easier-to-evaluate
id: 4521
---

Seven months ago, [Matthew Grasmick](https://www.drupal.org/u/grasmash) published an article describing [how hard it is to install Drupal](http://matthewgrasmick.com/compare-php-frameworks). His article included the following measurements for creating a new application on his local machine, across four different PHP frameworks:

<table>
  <thead>
   <tr>
    <th>Platform</th>
    <th>Clicks</th>
    <th>Time</th>
  </tr>
 </thead>
  <tr>
   <td>Drupal</td>
   <td>20+</td>
   <td>15:00+</td>
 </tr>
  <tr>
   <td>Symfony</td>
   <td>3</td>
   <td>1:55</td>
 </tr>
  <tr>
   <td>WordPress</td>
   <td>7</td>
   <td>7:51</td>
 </tr>
  <tr>
   <td>Laravel</td>
   <td>3</td>
   <td>17:28</td>
 </tr>
</table>

The results from Matthew's blog were clear: Drupal is too hard to install. It required more than 15 minutes and 20 clicks to create a simple site.

[video 9E34hSVFE94]

Seeing these results prompted me to launch a number of initiatives to improve the evaluator experience at DrupalCon Nashville. Here is the slide from [my DrupalCon Nashville presentation](https://dri.es/state-of-drupal-presentation-april-2018):

[image drupal/improve-technical-evaluator-experience-2018 resize=false]

A lot has happened between then and now:

- We improved the [download page](https://www.drupal.org/download) to improve the discovery experience on drupal.org
- We added an [ Evaluator Guide to Drupal.org](https://www.drupal.org/docs/official_docs/en/_evaluator_guide.html)
- We added a quick-start command to Drupal 8.6
- We added the Umami demo profile to Drupal 8.6
- We started working on a more modern administration experience (in progress)

You can see the result of that work in this video:

[video 7k1Ub-MJMCU]

Thanks to this progress, here is the updated table:

<table>
  <thead>
   <tr>
    <th>Platform</th>
    <th>Clicks</th>
    <th>Time</th>
  </tr>
 </thead>
  <tr>
   <td>Drupal</td>
   <td>3</td>
   <td>1:27</td>
 </tr>
  <tr>
   <td>Symfony</td>
   <td>3</td>
   <td>1:55</td>
 </tr>
  <tr>
   <td>WordPress</td>
   <td>7</td>
   <td>7:51</td>
 </tr>
  <tr>
   <td>Laravel</td>
   <td>3</td>
   <td>17:28</td>
 </tr>
</table>

Drupal now requires the least time and is tied for least clicks! You can now install Drupal in less than two minutes. Moreover, the Drupal site that gets created isn't an "empty canvas" anymore; it's a beautifully designed and fully functional application with demo content.

Copy-paste the following commands in a terminal window if you want to try it yourself:

```shell
mkdir drupal && cd drupal && curl -sSL https://www.drupal.org/download-latest/tar.gz | tar -xz --strip-components=1
php core/scripts/drupal quick-start demo_umami

```

For more detailed information on how we achieved these improvements, read Matthew's latest blog post: [The New Drupal Evaluator Experience, by the numbers](https://matthewgrasmick.com/posts/new-drupal-evaluator-experience-numbers).

*A big thank you to [Matthew Grasmick](https://www.drupal.org/u/grasmash) (Acquia) for spearheading this initiative!*
