---
url: 'https://dri.es/acquia-cloud-next-a-journey-in-platform-modernization'
title: 'Acquia Cloud Next, a journey in platform modernization'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2022-12-22T02:11:59-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: "Details on Acquia Cloud's transformation into a cloud-native, Kubernetes-based platform, enhancing performance, self-healing, and scaling capabilities."
tags:
  - Acquia
  - Drupal
  - Amazon
  - 'Acquia Cloud'
image: acquia/billboard-2018-1
published: true
featured: false
id: 5406
---

# Acquia Cloud Next, a journey in platform modernization

[image acquia/billboard-2018-1]

[Acquia Cloud](https://www.acquia.com/products/drupal-cloud/cloud-platform) was first [launched in 2009 as Acquia Hosting](https://dri.es/acquia-hosting-now-available). Acquia was one of the earliest adopters of [AWS](https://aws.amazon.com/). At the time, AWS had only 3 services: [EC2](https://aws.amazon.com/ec2/) , [S3](https://aws.amazon.com/s3/), and SimpleDB.

A lot has changed since 2009, which led us to re-architect Acquia Cloud starting in late 2019. This effort, labeled "Acquia Cloud Next" (ACN), became the largest technology overhaul in [Acquia's history](https://dri.es/acquia-first-decade-the-founding-story).

In 2013, four years after the launch of Acquia Cloud, [Docker](https://en.wikipedia.org/wiki/Docker_(software)) emerged. Docker popularized a lightweight container runtime, and a simple way to package, distribute and deploy applications.

Docker was built on a variety of Linux kernel developments, including "cgroups", "user namespaces" and "Linux containers":

1. In 2006, Paul Menage (Google) contributed [generic process containers](https://lkml.org/lkml/2006/10/20/251) to the Linux kernel, which was later [renamed control groups](https://lwn.net/Articles/256389/), or `cgroups`.
2. In 2008, Eric W. Biederman (Red Hat) introduced [user namespaces](https://lwn.net/Articles/528078/). User namespaces allow a Linux process to have its own set of users, and in particular, allow root privileges inside process containers.
3. In 2008, IBM created the [Linux Containers Project](https://linuxcontainers.org/) (LCP), a set of tools on top of `cgroups` and user namespaces.

Docker's focus was to deploy containers on a *single* machine. When organizations started to adopt Docker across a large number of machines, the need for a "container orchestrator" became clear.

Long before Docker was born, in the early 2000s, Google famously built its search engine on commodity hardware. Where competitors used expensive enterprise-grade hardware, Google realized that they could scale faster on cheap hardware running Linux. This worked as long as their software was able to cope with hardware failures. The key to building fault-tolerant software was the use of containers. To do so, Google not only contributed to the development of `cgroups` and user namespaces, but they also built an in-house, proprietary container orchestrator called [Borg](https://en.wikipedia.org/wiki/Borg_(cluster_manager)).

When Docker exploded in popularity, engineers involved in the Borg project branched off to develop [Kubernetes](https://kubernetes.io/). Google open sourced Kubernetes in 2014, and in the years following, Kubernetes grew to become the leading container management system in the world.

Back to [Acquia](https://www.acquia.com/). By the end of 2019, Acquia Cloud's infrastructure was delivering around 35 billion page views a month (excluding CDN). Our infrastructure had grown to tens of thousands of EC2 instances spread across many AWS regions. We supported some of the highest trafficked events in the world, including coverage of the Olympics, the [Australian Open](https://dri.es/2019-australian-open-aces-the-digital-experience-with-acquia-and-drupal), [Weather.com](https://dri.es/weather-com-using-drupal), the [Mueller report](https://dri.es/acquia-delivers-during-mueller-report-traffic-surge), and more.

Throughout 2019, we rolled out many "under the hood" improvements to Acquia Cloud. Thanks to these, our customers' sites saw performance improvements anywhere from 30% to 60%, at no cost to them.

That said, it became harder and harder to make improvements to the existing platform. Because of our scale, it could take weeks to roll out improvements to our fleet of EC2 instances. It was around that time that we set out to re-architect Acquia Cloud from scratch.

Acquia's journey to ACN started prior to Kubernetes and Docker becoming mainstream. Our initial approach was based on `cgroups` and Linux containers. But as Kubernetes and Docker established themselves in the market, it became clear we had to pivot. We decided to design ACN from the ground up to be a cloud-native, Kubernetes-native platform.

In March of 2021, after a year and a half of development, my little blog, [dri.es](https://dri.es/), was the first site to move to ACN. Getting my site live in production was a fun rallying point for our team. Even more so because my site was also [the first site to launch on the original Acquia Hosting platform](https://dri.es/acquia-hosting-now-available).

I never blogged about ACN because I wanted to wait until enough customer sites had upgraded. Fast forward another year and a half, and a large number of customers are running on ACN. We now have some of our highest traffic customers running on ACN. I can say without a doubt that ACN offers the highest levels of performance, self-healing, and dynamic scaling that Acquia customers have relied on.

ACN continuously monitors application performance, detects failures, reroutes traffic, and scales websites automatically without human assistance. ACN can handle billions of pageviews, gracefully deals with massive traffic spikes, all without manual intervention or architectural changes. Best of all, we can roll out new features in minutes or hours instead of weeks.

There is no better way to visualize this than by sharing a chart:

[image acquia/acquia-cloud-next-web-transactions-time-2022 resize=false]

Customers on Acquia Cloud Next get:

1. Much faster page performance and web transaction times (see chart above)
2. 5x faster databases compared to traditional MySQL server deployments
3. Faster dynamic auto-scaling and faster self-healing
4. Improved resource isolation - Nginx, Memcached, Cron, and other services all run in dedicated pods

To achieve these results, we worked closely with our partner, [AWS](https://aws.amazon.com/). We pushed the boundaries of certain AWS services, including [Amazon Elastic File System](https://aws.amazon.com/efs/) (EFS), [Amazon Elastic Kubernetes Service](https://aws.amazon.com/eks/) (EKS), and [Amazon Aurora](https://aws.amazon.com/aurora/). For example, AWS had to make changes to EKS to ensure that they could meet the scale at which we were growing. After 15 years of working with AWS, we continue to be impressed by AWS' willingness to partner with us and keep up with our demand.

In the process, AWS made upstream Kubernetes contributions to overcome some of our scaling challenges. These helped improve the speed and stability of Kubernetes. We certainly like that AWS shares our values and commitments to Open Source.

Last but not least, I'd be remiss not to give a big shoutout to Acquia's product, architect, and engineering teams. Re-architecting a platform with tens of thousands of EC2 instances running large-scale, mission-critical websites is no small feat.

Our team continued to find creative and state-of-the-art ways to build the best possible platform for Drupal. For a glimpse of that, take a look at [this presentation we gave at Kubecon 2022](https://www.youtube.com/watch?v=NqtfDy_KAqg). We learned that by switching our scaling metric from Kubernetes' built-in CPU utilization to a custom metric, we could reduce the churn on our clusters by ~1,000%.

Looking back at ACN's journey over the past 3+ years, I'm incredibly proud of how far we have come.
