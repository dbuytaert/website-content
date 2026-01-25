---
url: 'https://dri.es/drupal-7-development-process-retrospective-summary'
title: 'Drupal 7 development process retrospective summary'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2011-02-11T15:23:13-05:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
tags:
  - Drupal
  - Retrospective
published: true
id: 2186
---

# Drupal 7 development process retrospective summary

I spent a couple of hours recently summarizing all of the comments on [my Drupal 7 development process retrospective post](https://dri.es/drupal-7-development-process-retrospective). Thanks for all the feedback; it was very useful. I organized the responses into two groups related to the Drupal 7 development cycle: improvements we made during development that people think we should keep, and problems observed during development that people think we should address.

I have been thinking about a number of solutions, or experiments, that I would like to try during the Drupal 8 development cycle. However, I'm not ready yet to talk about them publicly. I'm still in listening mode, and will soon begin discussing my thoughts in #drupal on IRC, in the issue queues, and in the comments of related blog posts. I'd like to make a first set of decisions by DrupalCon Chicago.

In the mean time, below is my summary of the most notable items.

### Improvements made in the Drupal 7 development cycle (compared to Drupal 6 development cycle)

- The long release cycle was beneficial for many customers;
- Providing regular development snapshots helped in organizing the work;
- Continuously innovating and adding cutting edge technology is something we need to continue to do;
- It was very effective having a core committer available in IRC for discussions frequently and in real-time;
- Automated testing integrated in the drupal.org issue queues workflow was a huge win;
- We appreciated the availability of a usability team to provide support;
- We also appreciated the availability of an accessibility team to provide support;
- The semi-official and unplanned API clean-up phase during code freeze will make development saner;
- We liked the introduction of the 'major' priority as people were abusing the 'critical' priority;
- The D7CX initiative to get contributed modules upgraded (although it didn't necessarily meet expectations) was good;
- Having issue summaries for long issues helped to focus our plans and goals;
- The visibility of domain experts was evident by reworking and updating MAINTAINERS.txt;
- The exceptions during the code freeze provided focus;
- The fact that we added tests for the upgrade path prevented regressions and helped to get the release out;
- Issue tags provided a major workflow improvement;
- The fact that some larger initiatives where successfully organized outside of the issue queue was a plus;
- Starting to update developer and API documentation along with code changes kept our activities in order and helped everyone to understand what had been accomplished along the way;
- It's a good idea that we plan to try to backport some changes from Drupal 8 to Drupal 7; and
- The fact that we are doing an official post-mortem makes this all even better. :)

### Problems and difficulties observed during the Drupal 7 development cycle

- We should provide more attention to contributed module upgrades;
- It would be useful to make the release cycle shorter for developers and customers;
- The uncertain length of the release cycle makes it difficult to plan;
- Breaking backwards compatibility becomes increasingly costly;
- Lack of head-to-head upgrade path badly delayed the code freeze;
- It would be good to better enforce the code freeze; especially for the string and UI freeze;
- The original freeze deadlines may have been unrealistic (i.e., too bunched together, not enough time to actually polish the UI, and then respond to it by changing help text strings);
- Not all documentation (and almost no end-user documentation) was updated as part of the developer workflow;
- "Commit + Needs work" pattern for tests and documentation led to an unresolved backlog;
- There were unclear responsibilities and authority for sub-system maintainers;
- We need better priorities and maybe even a road map;
- There was too much emphasis on MAINTAINERS.txt;
- There needs to be more usability testing and usability data.
- The critical issue count was allowed to become too large, leading to a delayed releases;
- There is too much variability in reviewing and committing patches; some patches were committed within hours (not giving enough time for others to review), while others waited for weeks or months; and
- Performance is often an after-thought which led to performance regressions.

If there are points missing, or if some of them could be summarized better, please let me know and I'll update this post. I think I have a good sense of the primary problems experienced. However, if many of you think it would be useful, I could also conduct a quick survey to help prioritize these points.
