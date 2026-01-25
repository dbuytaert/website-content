---
url: 'https://dri.es/state-of-drupal-presentation-april-2022'
title: 'State of Drupal presentation (April 2022)'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2022-05-03T11:15:07-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'DrupalCon North America 2022 Driesnote presentation'
tags:
  - Drupal
  - DrupalCon
  - 'State of Drupal'
  - Portland
image: drupalcon-portland-2022/driesnote
published: true
id: 5321
---

# State of Drupal presentation (April 2022)

Last week, 1,300 Drupalists gathered in Portland, Oregon for DrupalCon North America. It was the first in-person DrupalCon in more than two years. I can't tell you how amazing it was to see everyone face-to-face.

In good tradition, I delivered [my State of Drupal keynote](https://dri.es/tag/state-of-drupal). You can [watch the video of my keynote](https://youtu.be/Ig676RzJbLo) or [download my slides](https://dri.es/files/state-of-drupal-april-2022.pdf) (262 MB).

[video Ig676RzJbLo]

I covered a lot of ground in this presentation, so I broke down my written summary into a three-part blog series. Part 1 below focuses on Drupal 10 updates. I'll be publishing [Part 2](https://dri.es/drupal-is-for-ambitious-site-builders) and [Part 3](https://dri.es/a-plan-for-drupal-11) later this week, which will focus on [Drupal's evolved vision](https://dri.es/drupal-is-for-ambitious-site-builders) and [Drupal 11 proposed initiatives](https://dri.es/a-plan-for-drupal-11).

### Drupal stands with Ukraine

I couldn't begin my presentation without acknowledging the loss of life and destruction in Ukraine. It's impacting [many in the Drupal community](https://youtu.be/1J-kbaYaLnQ), which is heartbreaking.

You may not be aware, but Ukraine is the sixth most active country in the world in terms of Drupal contributions. If you were to look at these contributions per capita, Ukraine's contributions are even more significant.

[video 1J-kbaYaLnQ]

Both myself and the [Drupal Association](https://www.drupal.org/association) strongly condemn the Russian attacks on Ukraine. Many of us might want to know how to help. The Drupal Association has compiled a [list of organizations](https://www.drupal.org/association/blog/drupal-association-statement-of-support-for-ukraine) that are accepting charitable donations.

### Updates on Drupal 10

From there, I gave an update on Drupal 10. We had targeted a Drupal 10 release date of June 2022, but [we made the decision to postpone until December 2022](https://www.drupal.org/about/core/blog/drupal-10-will-be-released-december-14-2022).

We had to move the date back because we have more work to do on the CKEditor 5 migration path. We're upgrading from [CKEditor 4](https://ckeditor.com/ckeditor-4/) to [CKEditor 5](https://ckeditor.com/ckeditor-5/). CKEditor 5 is a complete rewrite, with no upgrade path or backwards compatibility.

The Drupal community (and [Acquia](https://www.acquia.com/) in particular) has spent thousands of hours working on an upgrade path for CKEditor to make the upgrade easy for all Drupal users. While that has gone well, we need some additional time to work through the remaining upgrade challenges. Fortunately, we are getting great support from [CKSource](https://cksource.com/), the company behind CKEditor.

Next, I walked through three important facts about Drupal 10.

1. **Symfony 6.2** – Drupal 10 will upgrade [Symfony](https://symfony.com/) – a PHP framework that Drupal relies on heavily – from Symfony 4 to Symfony 6.2. At the time of the Drupal 10 release, Symfony 6.2 will be the latest and greatest release. For planning purposes, if you use Symfony components in your custom Drupal modules, you will have to upgrade those to Symfony 6.x.
2. **PHP 8.1** – We have changed the minimum PHP requirement from PHP 7.4 for Drupal 9 to [PHP 8.1](https://www.php.net/releases/8.1/) for Drupal 10. This is in large part because Symfony 6.2 will require PHP 8.1. Drupal users will benefit from various improvements in the new version of PHP. It also means you might have to upgrade any custom code. Because Drupal 9.3 works with PHP 8.1, you could start that work now with Drupal 9.3. It's a good way to prepare for Drupal 10.
3. **Drupal 9 end-of-life** – Drupal 9 end-of-life will happen in November 2023. Once Drupal 10 is released, you will have 11 months to upgrade your Drupal 9 sites to Drupal 10. The good news is, this should be the easiest upgrade in the history of Drupal. On Drupal 9's release date, 71% of deprecated API uses in contributed projects had [automated conversions](https://www.drupal.org/project/rector). Today, [93% of deprecated API uses for Drupal 10 across all contributed projects have automated conversions](https://dev.acquia.com/drupal10/deprecation_status/projects). And we're working on getting that even higher by the time that Drupal 10 is released.

With that, I provided some exciting updates on the five major Drupal 10 initiatives.

#### Olivero

Drupal's new frontend theme, named Olivero, is now stable. It's the most accessible theme we've ever shipped. During DrupalCon, Olivero also became the default theme for Drupal 10. Everyone who installs Drupal 10 will be greeted by a new frontend theme. That is significant because we used the current default theme, Bartik, for 11 years.

#### Claro

Drupal's new backend theme, called Claro, also became the new default administration theme at DrupalCon. Another major milestone and reason to celebrate!

#### Starterkit

Starterkit, a new way of creating themes in Drupal, is on track to be stable by Drupal 10's new release date. Releasing Starterkit means that we can move faster with theming improvements in Drupal Core. It also means that end users won't need to worry about whether upgrading Drupal breaks any of their sites' themes.

Instead of sub-theming a core base theme, Starterkit generates a starter theme for you from its latest defaults. This new theme will be more of a clone or fork, and will not have a runtime dependency on a core base theme.

#### CKEditor 5

We have made great progress on our content authoring experience. Check out [this video](https://youtu.be/hQyH0CUXLwE) for the latest update:

[video hQyH0CUXLwE]

#### Automated updates

Automated updates, the Drupal community's number one feature request, is progressing well.

The plan is to have Automatic Updates in one of the first minor versions of Drupal 10, or even in 10.0 in December if the community can help us test and finalize it in time. Check out [this video](https://youtu.be/mH2THdCRuJI) to learn more:

[video mH2THdCRuJI]

In Parts 2 and 3 of this blog series later this week, I'll focus on our strategy and proposed initiatives for Drupal 11.

I'd like to thank everyone who made our first in-person DrupalCon in two years a reality. It was amazing to see everyone's faces again and collaborate in person. Your contributions and hard work, as always, are inspiring to me!

I would also like to thank all the people that helped with my keynote. In no particular order, they are: [Ash Sullivan](https://www.linkedin.com/in/burnashburn/), [Alex Bronstein](https://www.drupal.org/u/effulgentsia), [Matthew Grasmick](https://www.drupal.org/u/grasmash), [Gábor Hojtsy](https://www.drupal.org/u/g%C3%A1bor-hojtsy), [Jess (xjm)](https://www.drupal.org/u/xjm), [Ted Bowman](https://www.drupal.org/u/tedbow), [Baddy Sonja Breidert](https://www.drupal.org/u/baddysonja), [Leslie Glynn](https://www.drupal.org/u/leslieg), [Tim Lehnen](https://www.drupal.org/u/hestenet), [Adam Bergstein](https://www.drupal.org/u/nerdstein), [Adam Goodman](https://www.drupal.org/u/adamgoodman), [Theodore Biadala](https://www.drupal.org/u/nod_), and [Alex Pott](https://www.drupal.org/u/alexpott).
