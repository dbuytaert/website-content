---
title: 'Acquia blocks 500,000 attack attempts for SA-CORE-2018-002'
date: '2018-04-17T15:51:20-04:00'
author: Dries
summary: "A breakdown of how Drupal's SA-CORE-2018-002 security bug developed into a large-scale attack and how Acquia ensured its customers' safety."
image: acquia/sa-core-2018-002-timeline
tags:
  - Drupal
  - Acquia
  - Security
published: true
type: blog
url: /acquia-blocks-500000-attack-attempts-for-sa-core-2018-002
id: 4301
---

On March 28th, the Drupal Security Team released a bug fix for a critical security vulnerability, named [SA-CORE-2018-002](https://www.drupal.org/sa-core-2018-002). Over the past week, various exploits have been identified, as attackers have attempted to compromise unpatched Drupal sites. Hackers continue to try to exploit this vulnerability, and Acquia's own security team has observed more than 100,000 attacks a day.

The SA-CORE-2018-002 security vulnerability is highly critical; it allows an unauthenticated attacker to perform remote code execution on most Drupal installations. When the Drupal Security Team made the security patch available, there were no publicly known exploits or attacks against SA-CORE-2018-002.

That changed six days ago, after [Checkpoint Research](https://research.checkpoint.com) provided [a detailed explanation of the SA-CORE-2018-002 security bug](https://research.checkpoint.com/uncovering-drupalgeddon-2/), in addition to step-by-step instructions that explain how to exploit the vulnerability. A few hours after Checkpoint Research's blog post, Vitalii Rudnykh, a Russian security researcher, shared a proof-of-concept exploit on GitHub. Later that day, Acquia's own security team began to witness attempted attacks.

The article by Checkpoint Research and Rudnykh's proof-of-concept code have spawned numerous exploits, which are written in different programming languages such as Ruby, Bash, Python and more. As a result, the number of attacks have grown significantly over the past few days.

Fortunately, [Acquia](https://www.acquia.com) deployed a platform level mitigation for all Acquia Cloud customers one hour after the Drupal Security Team made the SA-CORE-2018-002 release available on March 28th. <span class="highlight">Over the past week, Acquia has observed over 500,000 attacks from more than 3,000 different IP addresses across our fleet of servers and customer base. To the best of our knowledge, every attempted exploitation of an Acquia customer has failed.</span>

[image acquia/sa-core-2018-002-timeline]

The scale and the severity of this attack suggests that if you failed to upgrade your Drupal sites, or your site is not supported by Acquia Cloud or another trusted vendor that provides platform level fixes, the chances of your site being hacked are very high. If you haven't upgraded your site yet and you are not on a protected platform then assume your site is compromised. Rebuild your host, reinstall Drupal from a backup taken before the vulnerability was announced and upgrade before putting the site back online. (Update: restoring a Drupal site from backup may not be sufficient as [some of the exploits reinstall themselves from crontab](https://isc.sans.edu/forums/diary/Drupal+CVE20187600+PoC+is+Public/23549/). You should assume the whole host is compromised.)

### Drupal's responsible disclosure policy

It's important to keep in mind that [all software has security bugs](https://dri.es/dont-blame-open-source-software-for-poor-security-practices), and fortunately for Drupal, critical security bugs are rare. It's been nearly four years since the Drupal Security Team published a security release for Drupal core that is this critical.

What matters is how software projects or software vendors deal with security bugs. The Drupal Security Team follows a "coordinated disclosure policy": issues remain private until there is a published fix. A public announcement is made when the threat has been addressed and a secure version of Drupal core is also available. Even when a bug fix is made available, the Drupal Security Team is very thoughtful with its communication. The team is careful to withhold as many details about the vulnerability as possible to make it difficult for hackers to create an exploit, and to buy Drupal site owners as much time as possible to upgrade. In this case, Drupal site owners had two weeks before the first public exploits appeared.

Historically, many proprietary CMS vendors have executed a different approach, and don't always disclose security bugs. Instead, they often fix bugs silently. In this scenario, secrecy might sound like a good idea; it prevents sites from being hacked and it avoids bad PR. However, hiding vulnerabilities provides a false sense of security, which can make matters much worse. This approach also functions under the assumption that hackers can't find security problems on their own. They can, and when they do, even more sites are at risk of being compromised.

<p class="pullquote">Drupal's approach to security is best-in-class – from fixing the bug, testing the solution, providing advance notice, coordinating the release, being thoughtful not to over communicate too many details, being available for press inquiries, and repeatedly reminding everyone to upgrade.</p>

### Acquia's platform level fix

In addition to the Drupal Security Team's responsible disclosure policy, Acquia's own security team has been closely monitoring attempted attacks on our infrastructure. Following the release of the Checkpoint Research article, Acquia has tracked the origin of the 500,000 attempted attacks:

[image acquia/sa-core-2018-002-map]

To date, over 50 percent of the attempted attacks Acquia has witnessed originate from the Ukraine:

[image acquia/sa-core-2018-002-countries]

At [Acquia](https://www.acquia.com), we provide customers with automatic security patching of both infrastructure and Drupal code, in addition to platform level fixes for security bugs. Our commitment to keeping our customers safe is reflected in our push to release a platform level fix one hour after the Drupal Security Team made SA-CORE-2018-002 available. This mitigation covered all customers with Acquia Cloud Free, Acquia Cloud Professional, Acquia Cloud Enterprise, and Acquia Cloud Site Factory applications; giving our customers peace of mind while they upgraded their Drupal sites, with or without our help. This means that when attempted exploits and attacks first appeared in the wild, Acquia's customers were safe. As a best practice, Acquia always recommends that customers upgrade to the latest secure version of Drupal core, in addition to platform mitigations.

*This blog post was co-authored by Dries Buytaert and [Cash Williams](https://twitter.com/cashwilliams).*
