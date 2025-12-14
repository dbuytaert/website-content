---
title: 'Acquia retrospective 2017'
date: '2018-01-08T05:45:29-05:00'
author: Dries
summary: '2017 year in review for Acquia'
image: acquia/acquia-roadmap-2017
tags:
  - Acquia
  - Drupal
  - Retrospective
published: true
type: blog
url: /acquia-retrospective-2017
id: 4121
---

[image acquia/acquia-hq-entrance-2017]

For the past nine years, I've sat down every January to write an Acquia retrospective. It's always a rewarding blog post to write as it gives me an opportunity to reflect on what Acquia has accomplished over the past 12 months. If you'd like to read my previous annual retrospectives, they can be found here: [2016](https://dri.es/acquia-retrospective-2016),[ 2015](https://dri.es/acquia-retrospective-2015), [2014](https://dri.es/acquia-retrospective-2014), [2013](https://dri.es/acquia-retrospective-2013), [2012](https://dri.es/acquia-retrospective-2012), [2011](https://dri.es/acquia-retrospective-2011), [2010](https://dri.es/acquia-retrospective-2010), [2009](https://dri.es/acquia-retrospective-2009). When read together, they provide insight to what has shaped Acquia into the company it is today.

This year's retrospective is especially meaningful because 2017 marked Acquia's 10th year as a company. Over the course of Acquia's [first decade](https://dri.es/acquia-first-decade-the-founding-story), our long-term investment in open source and cloud has made us the leader in web content management. 2017 was one of our most transformative years to date; not only did we have to manage leadership changes, but we also broadened our horizons beyond website management to data-driven customer journeys.

### The next phase of Acquia leadership

[image acquia/tom-and-dries-4]

In my [first retrospective from 2009](https://dri.es/acquia-retrospective-2009), I shared that Jay Batson and I had asked Tom Erickson to come aboard as Acquia's new CEO. For the next eight years, Tom and I worked side-by-side to build and grow Acquia. Tom's expertise in taking young companies to the next level was a natural complement to my technical strength. His leadership was an example that enabled me to develop my own business building skills. When Tom announced last spring that he would be stepping down as Acquia's CEO, I assumed more responsibility to help guide the company through the transition. My priorities for 2017 were centered around three objectives: (1) the search for a new CEO, (2) expanding our product strategy through a stronger focus on innovation, and (3) running our operations more efficiently.

The search for a new CEO consumed a great deal of my time in 2017. After screening over 140 candidates and interviewing ten of them in-depth, we asked [Mike Sullivan to join Acquia as CEO](https://dri.es/mike-sullivan-joins-acquia-as-ceo). Mike has been on the job for three weeks and I couldn't be more excited.

[image acquia/mike-sullivan-joins-acquia-2017]

### Market trends

I see three major market trends that I believe are important to highlight and that help inform our strategy.

#### Trend #1: Customers are driven by time-to-value and low cost of maintenance

Time-to-value and low maintenance costs are emerging as two of the most important differentiators in the market. This is consistent with a post I wrote eleven years ago, in regards to [The Ockham's Razor Principle of Content Management Systems](https://dri.es/ockhams-razor-principle-of-content-management-systems). The principle states that given two functionally equivalent content management systems, the simplest one should be selected. Across both the low and the high ends of the market, time-to-value and total cost of ownership matter a great deal. Simplicity wins.

In the **low end of the market** simple sites, such as single blogs and brochure sites, are now best served by SaaS tools such as Squarespace and Wix. Over the past five years, SaaS solutions have been rising in prominence because their templated approach to simple site building makes them very easy to use. The total cost of ownership is also low as users don't have to update and maintain the software and infrastructure themselves. Today, I believe that [Drupal is no longer ideal for most simple sites](https://dri.es/state-of-drupal-presentation-september-2017) and instead [is best suited for more ambitious use cases](https://dri.es/drupal-is-for-ambitious-digital-experiences). Not everyone likes that statement, but I believe it to be true.

In the **mid-market**, SaaS tools don't offer the flexibility and customization required to support sites with more complexity. Often mid-market companies need more customizable solutions like Drupal or WordPress. Time-to-value and total maintenance costs still matter; people don't want to spend a lot of time installing or upgrading their websites. Within the scope of Ockham's Razor Principle, WordPress does better than Drupal in this regard. WordPress is growing faster than Drupal for websites with medium complexity because ease of use and maintenance often precede functionality. However, when superior flexibility and architecture are critical to the success of building a site, Drupal will be selected.

In the **enterprise**, a growing emphasis on time-to-value means that customers are less interested in boil-the-ocean projects that cost hundreds of thousands (or millions) of dollars. Customers still want to do large and ambitious projects, but they want to start small, see results quickly, and measure their ROI every step along the way. Open source and cloud provide this agility by reducing time-to-market, cost and risk. This establishes a competitive advantage for Acquia compared to traditional enterprise vendors like Adobe and Sitecore.

At Acquia, understanding how we can make our products easier to use by enhancing self-service and reducing complexity will be a major focus of 2018. For Drupal, it means we have to stay focused on the initiatives that will improve usability and time to value. In addition to adopting a [JavaScript framework in core](https://dri.es/drupal-looking-to-adopt-react) to facilitate the building of a better administration experience, work needs to continue on [Workspaces](https://dri.es/an-update-on-the-workflow-initiative-for-drupal-8-4-8-5) (content staging), [Layout Builder](https://dri.es/an-update-on-the-layout-initiative-for-drupal-8-4-8-5) (drag-and-drop blocks), and the [Media](https://dri.es/an-update-on-the-media-initiative-for-drupal-8-4-8-5), [Outside-in](https://dri.es/drupal-8-2-now-with-more-outside-in) and [Out-of-the-box](https://www.drupal.org/project/ideas/issues/2847582) initiatives. Finally, I anticipate that a Drupal initiative around [automated upgrades](https://dri.es/state-of-drupal-presentation-september-2017) will kick off in 2018. I'm proud to say that Acquia has been a [prominent contributor](https://dri.es/who-sponsors-drupal-development-2017) to many of these initiatives, by either sponsoring developers, contributing code, or providing development support and coordination.

#### Trend #2: Frictionless user experiences require greater platform complexity

For the past ten years, I've observed one significant factor that continues to influence the trajectory of digital: the [internet's continuous drive to mitigate friction](https://dri.es/friduction-the-internets-unstoppable-drive-to-eliminate-friction) in user experience and business models. The history of the web dictates that lower-friction solutions will surpass what came before them because they eliminate inefficiencies from the customer experience.

This not only applies to how technology is adopted, but how customer experiences are created. Mirroring Ockham's Razor Principle, end users and consumers also crave simplicity. End users are choosing to build relationships with brands that guarantee contextual, personalized and frictionless interactions. However, simplicity for end users does not translate into simplicity for CMS owners. Organizations need to be able to manage more data, channels and integrations to deliver the engaging experiences that end users now expect. This desire on the part of end users creates greater platform complexity for CMS owners.

For example, [cross-channel experiences](https://dri.es/cross-channel-user-experiences-with-drupal) are starting to remove certain inefficiencies around traditional websites. In order to optimize the customer experience, enterprise vendors must now expand their digital capabilities beyond web content management and invest in both systems of engagement (various front-end solutions such as conversational interfaces, chatbots, and AR/VR) and systems of intelligence (marketing tools for personalization and predictive analytics).

[image acquia/shopping-with-augmented-reality-2017 resize=false]

These trends give organizations the opportunity to [reimagine their customer experience](https://dri.es/shopping-with-augmented-reality). By taking advantage of more channels and more data (e.g. being more intelligent, personalized, and contextualized), we can leapfrog existing customer experiences. However, these ambitious experiences require a platform that prioritizes customization and functionality.

#### Trend #3: The decoupled CMS market is taking the world by storm

In the web development world, few trends are spreading more rapidly than decoupled content management systems. The momentum is staggering as some decoupled CMS vendors are growing at a rate of 150% year over year. This trend has a significant influence on the technology landscape surrounding Drupal, as a growing number of Drupal agencies have also started using modern JavaScript technologies. For example, more than [50% of Drupal agencies](https://dri.es/state-of-drupal-presentation-september-2017) are also using Node.js to support the needs of their customers.

The Drupal community's emphasis on [making Drupal API-first](https://dri.es/a-roadmap-for-making-drupal-more-api-first), in addition to supporting tools such as [Waterwheel](https://dev.acquia.com/article/waterwheel-drupal-sdk-ecosystem) and Drupal distributions such as [Reservoir](https://dri.es/reservoir-a-simple-way-to-decouple-drupal), [Contenta](http://www.contentacms.org) and [Lightning](https://dri.es/distributions-remain-a-growing-opportunity-for-drupal), means that Drupal 8 is well-prepared to support decoupled CMS strategies. For years, including in 2017, Acquia has been a very prominent contributor to [a variety of API-first initiatives](https://dri.es/tag/web-services).

### Product milestones

In addition to my focus on finding a new CEO, driving innovation to expand our product offering was another primary focus in 2017.

Throughout Acquia's first decade, we've been focused primarily on providing our customers with the tools and services necessary to scale and succeed with Drupal. We've been very successful with this mission. However, many of our customers need more than content management to be digital winners. The ability to orchestrate customer experiences across different channels is increasingly important to our customers' success. We need to be able to support these efforts on the Acquia platform.

We kicked off our new product strategy by adding new products to our portfolio, and by extending our existing products with new capabilities that align with our customers' evolving needs.

- **Acquia Cloud**: A "continuous integration" and "continuous delivery" service for developers was our #1 requested feature, so we delivered **Acquia Cloud CD** early in 2017. Later in the year, we expanded [**Acquia Cloud to support Node.js**](https://dri.es/announcing-node-js-on-acquia-cloud), the popular open-source JavaScript runtime. This was the first time we expanded our cloud beyond Drupal. Previously, if an organization wanted to build a decoupled Drupal architecture with Node.js, it was not able to host the Node.js application on Acquia Cloud. Finally, in order to make Acquia Cloud easier to use, we started to focus more on self-service. We saw rapid customer adoption of our new **Stack Metrics** feature, which gives customers valuable insight into performance and utilization. We also introduced a new **Cloud Service Management** model, which empowers our customer to scale their Acquia Cloud infrastructure on the fly.
- **Acquia Lift**: In order to best support our customers as they embed personalization into their digital strategies, we have continued to add product enhancements to the [new version of Acquia Lift](https://dri.es/personalization-takes-flight-with-the-new-acquia-lift). This included improving Acquia Lift's content authoring capabilities, enhanced content recommendations, and advanced analytics and reporting. The Acquia Lift team grew, as we also founded a **machine learning and artificial intelligence team**, which will lead to new features and products in 2018. In 2017, Acquia Lift has added over 200 new features, tracks 200% more profiles than in 2016, and has grown 45% in revenue.

[image acquia/connected-journeys resize=false]

Next, we added two new products to support our evolution from content management to data-driven customer journeys: [Acquia Journey and Acquia Digital Asset Manager (DAM)](https://dri.es/the-evolution-of-acquia-product-strategy).

- **Acquia Journey** allows marketers to easily map, assemble, orchestrate and manage customer experiences across different channels. One of the strengths of Acquia Journey is that it allows technical teams to integrate many different technologies, from marketing and advertising technologies to CRM tools and commerce platforms. Acquia Journey unifies these various interaction points within a single user interface, making it possible to quickly assemble powerful and complex customer journeys. In turn, marketers can take advantage of a flowchart-style journey mapping tool with unified customer profiles and an automated decision engine to determine the best-next action for engaging customers.
- **Acquia DAM**: Many organizations lack a single-source of truth when it comes to managing digital assets. This challenge has been amplified as the number of assets has rapidly increased in a world with more devices, more channels, more campaigns, and more personalized and contextualized experiences In addition to journey orchestration, it became clear that large organizations are seeking a digital asset management solution that centralizes control of creative assets for the entire company. With Acquia DAM, our customers can rely on one dedicated application to gather requirements, share drafts, consolidate feedback and collect approvals for high-value marketing assets.

Acquia's new product strategy is very ambitious. I'm proud of our stronger focus on innovation and the new features and products that we launched in 2017. Launching this many products and features is hard work and requires tactical coordination across every part of the company. The transition from a single-product company to a multi-product company is challenging, and I hope to share more [lessons learned](https://dri.es/tag/startup-lessons) in future blog posts.

[image acquia/acquia-roadmap-2017 resize=false]

While each new product we announced was well-received, there is still a lot of work to be done: we need to continue to drive end-user demand for our new products and help our digital agency partners build practices around them.

#### Leading by example

At Acquia, our mission is to deliver "the universal platform for the greatest digital experiences", and we want to lead by example. In an effort to become a thought-leader in our field, the Office of the CTO launched [Acquia Labs](https://dri.es/think-beyond-with-acquia-labs), our research and innovation lab. Acquia Labs aims to link together the new realities in our market, our customers' needs in coming years, and the goals of Acquia's products and open-source efforts in the long term.

Finally, we rounded out the year by [redesigning Acquia.com on Drupal 8](https://dri.es/evolving-acquia-com). The new site places a greater emphasis on taking advantage of our own products. We wanted to show (not tell) the power of the Acquia platform. For example, Acquia Lift delivers visitors personalized content throughout the site. The new site represents a bolder and more innovative Acquia, aligned with [the evolution of our product strategy](https://dri.es/the-evolution-of-acquia-product-strategy).

### Business momentum

We continued to grow at a steady pace in 2017 and hired a lot of new people. We focused on the growth of our recurring revenue, which includes new customers and the renewal and expansion of our work with existing customers. We also focused on our bottom line.

In 2017, the top industry analysts published very positive reviews based on their independent research. I'm proud that Acquia was recognized by Forrester Research as the leader for strategy and vision, ahead of every other vendor including Adobe and Sitecore, in [The Forrester Wave: Web Content Management Systems, Q1 2017](https://dri.es/acquia-a-leader-in-the-2017-forrester-wave-for-web-content-management-systems). Acquia was also named a leader in the [2017 Gartner Magic Quadrant for Web Content Management](https://dri.es/acquia-a-leader-in-2016-gartner-magic-quadrant-for-web-content-management), marking our placement as a leader for the fourth year in a row. In addition to being the only leader that is open-source or has a cloud-first strategy, Acquia was hailed by analysts for our investments in open APIs across all our products.

Over the course of 2017 Acquia welcomed an impressive roster of new customers who included Astella Pharma, Glanbia, the Commonwealth of Massachusetts, Hewlett Packard Enterprise, and Bayer GmbH. As we enter 2018, Acquia can count 26 of the Fortune 100 among its customers, up from 16 at the beginning of 2017.

This year was also an incredible growth period for our Asia Pacific business, which is growing ARR at a rate of 80% year over year. We have secured new business in Japan, Hong Kong, Singapore, Indonesia, Malaysia, Philippines and India. When we started our business in Australia in 2012, 70% of the pipeline came from [govCMS](https://dri.es/how-to-move-an-entire-government-to-a-new-digital-platform), the platform offered by the Australian government to all national, territorial and local agencies. Today, our business is much more diverse, with 50% of the region's pipeline coming from outside of Australia.

[image acquia/jeannie-finks-at-the-stevies-awards-2017]

Customer success continues to be the most important driver of the evolution of Acquia's strategy. This commitment was reflected in 2017 customer satisfaction levels, which remains extremely high at 94 percent. Acquia's global support team also received top honors from the American Business Awards and won a Gold Stevie for [Customer Service Team of the Year](https://www.acquia.com/about-us/newsroom/press-releases/acquia-customer-support-team-earns-gold-stevie-award-honors-2017).

This year, we also saw our annual customer conference, Acquia Engage, grow. We welcomed over 650 people to Boston and saw presentations from over twenty customers, including Johnson &amp; Johnson, NBC Sports, Whole Foods, AMD, the YMCA and many more. It was inspiring to hear our customers explain why Acquia and Drupal are essential to their business.

Finally, our partner ecosystem continues to advance. In 2016, we achieved a significant milestone as numerous global systems integrators repeatedly recommended Acquia to their clients. One year later, these partners are building large centers of excellence to scale their Acquia and Drupal practices. Digital agencies and Drupal companies also continue to extend their investments in Acquia, and are excited about the opportunity presented in our expanded product portfolio. In some markets, over 50 percent of our new subscriptions originate from our partner ecosystem.

The growth and performance of the partner community is validation of our strategy. For example, in 2017 we saw multiple agencies and integrators that were entirely committed to Adobe or Sitecore, join our program and begin to do business with us.

### Opportunities for Acquia in 2018

When thinking about how Acquia has evolved its product strategy, I like to consider it in terms of Greylocks' Jerry Chen's take on [the stack of enterprise systems](https://news.greylock.com/the-new-moats-53f61aeac2d9). I've modified his thesis to fit the context of Acquia and our long-term strategy to help organizations with their digital transformation.

Chen's thesis begins with "systems of record", which are sticky and defensible not only because of their data, but also based on the core business process they own. Jerry identifies three major systems of record today; your customers, your employees and your assets. CRM owns your customers (i.e. Salesforce), HCM owns your employees (i.e. Workday), and ERP/Financials owns your assets. Other applications can be built around a system of record but are usually not as valuable as the actual system of record. For example, marketing automation companies like Marketo and Responsys built big businesses around CRM, but never became as strategic or as valuable as Salesforce. We call these "secondary systems of record". We believe that a "content repository" (API-first Drupal) and a "user profile repository" (Acquia Lift) are secondary systems of record. We will continue our efforts to improve Drupal's content repository and Lift's user profile repository to become stronger systems of record.

[image acquia/systems-of-engagement-intelligence-record-and-delivery-1 resize=false]

"Systems of engagement" are the interface between users and the systems of record. They control the end-user interactions. Drupal and Lift are great examples of systems of engagement as they allow for the rapid creation of end-user experiences.

Jerry Chen further suggests that "systems of intelligence" will be a third component. Systems of intelligence will be of critical importance for determining the optimal customer journey across various applications. Personalization (Acquia Lift), recommendations (Acquia Lift) and customer journey building (Acquia Journey) are systems of intelligence. They are very important initiatives for our future.

While Chen does not include "systems of delivery" in his thesis, I believe it is an important component. Systems of delivery not only dictate how content is delivered to users, but how organizations build projects faster and more efficiently for their stakeholders and users. This includes multi-site management (Acquia Cloud Site Factory) and continuous delivery services (Acquia Cloud CD), which extend the benefits of PaaS beyond scalability and reliability to include high-productivity and faster time-to-value for our customers. As organizations increase their investments in cross-channel experiences, they must manage more complexity and orchestrate the testing, integration and deployment of different technologies. Systems of delivery, such as Acquia Cloud and Acquia Site Factory, remove complexity from building and managing modern digital experiences.

This is all consistent with the diagram I've been using for a few years now where "user profile" and "content repository" represent two systems of record, `getBestNextExperience()` is the system of intelligence, and Drupal is the system of engagement to build the customer experience:

[image acquia/systems-of-engagement-intelligence-record-and-delivery-2 resize=false]

We are confident in the market shift towards "intelligent connected experiences" or "data-driven customer journeys" and the opportunity it provides to Acquia. Every team at Acquia has demonstrated both commitment and focus as we have initiated a shift to make our vision relevant in the market for years to come. I believe we have strong investments across systems of record, intelligence, delivery and engagement that will continue to put us at the center of our customers' technology and digital strategies in 2027.

### Thank you

Of course, none of these 2017 results and milestones would be possible without the hard work of the Acquia team, our customers, partners, the Drupal community, and our many friends. Thank you for your support in 2017 and over the past ten years – I can't wait to see what the next decade will bring!
