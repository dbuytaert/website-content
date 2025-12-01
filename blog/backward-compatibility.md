---
title: 'Backward compatibility'
date: '2006-05-17T04:52:18-04:00'
author: Dries
tags:
  - Drupal
published: true
type: blog
url: /backward-compatibility
id: 75
---

The issue of breaking backward compatibility comes up every once in a while – more and more in the form of a heated discussion.

When I first released Drupal, I chose not to preserve backward compatibility, because I was mainly interested in getting the technology right. Preserving backward compatibility often requires that you drag historical baggage along, and in interpreted languages like PHP, this comes at a significant performance cost. So it was decided that we can break people's code, but not people's data. Our mission was to make Drupal fast, small, clean and on the bleeding-edge of technology. In the early days I focused, completely and utterly, on the aesthetics of Drupal's code. I spent days trying to do something better, with fewer lines of code and more elegant than elsewhere. And with me, many others.

It was the right thing to do. Over the years, we've seen a lot of innovations happen that would not likely have happened while preserving backward compatibility (the node system being one of the most prominent examples). Developers always had free reign to implement their ideas in the best possible way. It is something that Drupal has in its favor compared to many other content management systems. It's been interesting to see how Drupal has spread and how it has grown to be more flexible and cover more niches than many other systems. If anything, this needs to be attributed to the fact that we haven't cared much about backward compatibility, and our single-mindedness to get the technology right.

Of course, breaking backward compatibility has its disadvantages. Expensive upgrade paths and frustrations due to lack of up-to-date modules being the examples that immediately come to mind. And for many people, this matters a lot.

Unfortunately, there is no right or wrong answer here: there are both advantages and disadvantages to backward compatibility. As a result, there will always be a tension between the need for hassle-free upgrades and the desire to have fast, cruft-free code with clean and flexible APIs. At the end of the day, we can't make everybody happy and it is very important that you realize that.

Most people, however, just worry about how they are going to upgrade their Drupal sites by next Friday, at the latest. As Drupal grows, these users become increasingly verbose about the issue of backward compatibility, and as a result, it becomes harder and harder to maintain our original core values. For many of us (including myself), this is hard to accept. It is hard to accept not because we don't care about people's problems, but because we realize that the only viable long-term strategy is to focus exclusively on getting the technology right. The only way to stay competitive, is to have the best product. It doesn't get any more complex than that. If you start dragging baggage along, your product will, eventually, be replaced by something that offers the same functionality but without the baggage. Something that is faster, smaller, cleaner and on the bleeding-edge of technology. Unfortunately, only those with a long-term interest or vision tend to care about this. End-users with sites to upgrade are challenged by a different set of problems, like a Friday night deadline. They are extremely short-sighted, and rightly so. Remember that both sides in this argument have valid points.

Given the fact that Drupal's main strengths have always been the agility with which it can respond to the ever-changing landscape of web development, and the almost infinite amount of flexibility and expansion it affords developers, I feel that preserving the ability to constantly innovate is of higher importance, at the present time at least, than preserving backward compatibility. None of us would be here now using Drupal were it not for this core value, and I strongly believe that it is fundamental to our future. It always has been.

But what to do if many of your users slowly force you to change one of your core values? It seems inevitable that sooner than later, we will have to be a lot more careful about breaking peoples' code. And when that happens, I fear that this will be the end of Drupal as we have come to know it. Probably not immediately, maybe not even for several years, but eventually Drupal will be surpassed by technology that can respond more quickly to change. Maybe that is bound to happen anyway, and when it does, having made as many people happy as possible (even at your own expense), is the only thing that really mattered?
