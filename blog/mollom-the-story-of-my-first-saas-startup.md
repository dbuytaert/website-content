---
title: 'Mollom: The story of my first SaaS startup'
date: '2018-04-30T07:57:37-04:00'
author: Dries
summary: 'How I started, grew, sold and retired my first SaaS business'
image: mollom/team-december-2011
tags:
  - Drupal
  - Mollom
  - Acquia
  - 'Startup lessons'
published: true
type: blog
url: /mollom-the-story-of-my-first-saas-startup
id: 4316
---

Last month, Acquia discontinued service and support for Mollom, the spam service I started more than ten years ago. As a goodbye, I want to share the untold story of how I founded Mollom.

In 2007, I read Tim Ferriss' book [The 4-Hour Work Week](https://en.wikipedia.org/wiki/The_4-Hour_Workweek), and was hooked. The book provides a blueprint for how entrepreneurs can structure and build a business to fund the lifestyle of their dreams. It's based on Ferriss' own experience; he streamlined his business, automated systems and outsourced tasks until it was not only more profitable, but also took less of his time to operate. The process of automation and outsourcing was so efficient, Ferriss only spent four hours a week to run his business; this gave him time and freedom to take "mini-retirements", travel the world, and write a book. When I first read Ferriss' book, I was inspired by the idea of simultaneously having that much free time and being financially stable.

While I was reading Ferriss' book, I was also working on a website spam filter for my blog, called Mollom. I had started to build Mollom as a personal project for exclusive use on my own blog. Inspired by the 4-Hour Work Week, I was convinced I could turn Mollom into a small SaaS service with global customers, complete self-service, and full automation. This would allow me to operate Mollom from anywhere in the world, and would require just a few hours of my time each week. Because I was starting to use machine learning, I enlisted the help of one of my best friends, Benjamin Schrauwen, a professor in machine learning at the University of Ghent.

In the same year, Jay Batson and I met at DrupalCon Sunnyvale, and [we had already started to explore the idea of founding Acquia](https://dri.es/acquia-first-decade-the-founding-story). My oldest son Axl was also born in the summer of 2007, and I was [working hard to finish my PhD](https://dri.es/dissertation-wrestling). Throughout all of this, we were also working to get Drupal 6 released. Needless to say, it was a busy summer.

With my PhD nearly complete, I needed to decide what to do next. I knew that starting [Acquia](https://www.acquia.com) was going to have a big impact, not just on [Drupal](https://www.drupal.org) but also on my life. However, I was also convinced that Mollom, while much smaller in scope and ambition, could provide a path to the freedom and independence Ferriss describes.

### Mollom's foundational years

Exciting 2007, I determined that both Acquia and Mollom were important opportunities to pursue. Jay and I raised $7 million in venture capital, and [we publicly launched Acquia in November 2007](https://dri.es/acquia-my-drupal-startup). Meanwhile, Ben and I pooled together €18,000 of our own money, bootstrapped Mollom, and [publicly launched Mollom in March 2008](https://dri.es/mollom-my-content-monitoring-startup).

I always made a point to run both businesses separately. Even after [I moved from Belgium to the US](https://dri.es/moving-to-boston-for-two-years) in the summer of 2010, I continued to run Mollom and Acquia independently. The Mollom team was based in Europe, and once or twice a week, I would get up at 4 AM to have a two-hour conference call with the team. After my conference call, I'd help my family get ready for the day, and then I was off to work at Acquia.

By 2011, Mollom had achieved the goals our team set out to accomplish; our revenues had grown to about €250,000 in recurring annual revenue, our gross margins were over 85 percent, and we could pretty much run the business on autopilot. Our platform was completely self-serviced for our users, the anti-spam algorithms self-learning, the service was built to be [highly-available](https://en.wikipedia.org/wiki/High_availability), and the backend operations were almost entirely automated. Not bad for a side hustle. I often joked about how I could run Mollom from the beach in Greece, with less than an hour of work a day.

However, our team at Mollom wasn't satisfied yet, so instead of sitting on the beach, we decided to invest Mollom's profits in feature development. We had a team of three engineers working on adding new capabilities, in addition to re-architecting and scaling Mollom to keep up with its growth. On average, Mollom handled more than 100 web service requests per second, and we regularly saw peaks of up to 3,000 web service request per second. In a way, Mollom's architecture was ahead of its time – it used a micro-services architecture with a REST API, a decoupled administration backend and relied heavily on machine learning. From day one, our terms of service respected people's privacy, and we never had a data breach.

[image mollom/team-december-2011]

In the meantime, Acquia had really taken off; Acquia's revenue had grown to over $22 million annually, and I was often working 60 hour work weeks to grow the company. Acquia's Board of Directors wanted my full attention, and had even offered to acquire Mollom a few times. I recognized that running Mollom, Acquia and Drupal simultaneously was not sustainable – you can only endure regular 4 AM meetings for so long. Plus, we had ambitious goals for Mollom; we wanted to add many-site content moderation, sentiment analysis and detection for certain code of conduct violations. Doing these things would require more capital, and unless you are [Elon Musk](https://en.wikipedia.org/wiki/Elon_Musk), it's really hard to raise capital for multiple companies at the same time. Most importantly, I wanted to focus more on growing Drupal and driving Acquia's expansion.

### Acquia acquires Mollom

By the end of 2012, [Ben and I agreed to sell Mollom to Acquia](https://dri.es/mollom-acquired-by-acquia). Acquia's business model was to provide SaaS services around Drupal, and Mollom was exactly that – a SaaS service used by tens of thousands of Drupal sites.

Selling Mollom was a life-changing moment for me. It proved that I was able to bootstrap and grow a company, steer it to profitability and exit successfully.

[image mollom/mollom-closing-3]

### Acquia retires Mollom

By 2017, five years after the acquisition, it became clear that Mollom was no longer a strategic priority for Acquia. As a result, Acquia decided it was best to shut down Mollom by April 2018. As the leader of the product organization at Acquia, I'm supportive of this decision. It allows us to sharpen our focus and to better [deliver on our mission](https://dri.es/the-evolution-of-acquia-product-strategy).

While it was a rational decision, it's bittersweet. I still believe that Mollom could have continued to have a big impact on the [Open Web](https://dri.es/tag/open-web). Not only did that make the web better, it saved people millions of hours moderating their content. I also considered keeping Mollom running as part of Acquia's "Give back more" principle. However, [Acquia gives back a lot](https://dri.es/who-sponsors-drupal-development-2017), and I believe that giving back to Drupal should be our priority.

[image mollom/mollom-end-of-life-announcement]

Overall, Mollom was a success. While I never got my 4-hour work week, I enjoyed successfully creating a company from scratch, and seeing it evolve through every stage of its life. I learned how to build and run a SaaS service, I made some money in the process, and best of all, Mollom blocked over 15 billion spam comments across tens of thousands of websites. This translates to saving people around the world millions of hours, which would otherwise be devoted to content moderation. Mollom also helped to protect the websites of some of the world's most famous brands; from Harvard, to The Economist, Tesla, Twitter, Sony Music and more. Finally, we were able to offer Mollom for free to the vast majority of our users, which is something we took a lot of pride in.

If you were a user of Mollom the past 10+ years, I hope you enjoyed our service. I also want to extend a special thank you to everyone who contributed to Mollom over the past 11 years!

Rest in peace, Mollom! Thank you for blocking so much spam. I'll think about you next time I visit Greece.
