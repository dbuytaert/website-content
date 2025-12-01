---
title: 'Securing my email with SPF, DKIM and DMARC'
date: '2021-03-16T08:49:00-04:00'
author: Dries
image: blog/email-headers-2021
tags:
  - 'My site'
  - Personal
published: true
type: blog
url: /securing-my-email-with-spf-dkim-and-dmarc
id: 5176
---

I use my own domain name for email. Unfortunately, I received a few emails about `dries@buytaert.net` being used for phishing attacks. It's not the first time, but hopefully it will be the last!

I finally added SPF, DKIM and DMARC protection to my domains:

- [Sender Policy Framework](https://www.dmarcanalyzer.com/spf/) (SPF) restricts what servers can send emails using my domain name. To enable it, all I had to do is add a DNS record to my domain. The new DNS record specifies a list of authorized hostnames. Servers that receive an email from me, verify the hostname of the outgoing mail server against the approved list in my SPF DNS record.
- [Domain Keys Identified Mail](http://dkim.org/) (DKIM) uses [public-key cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography) to make sure that my email isn't tampered with. My mail server keeps a private cryptographic key. When I send an email, my mail server uses the private key to embed a digital signature into my emails. In turn, your mail server/client validates the signature using the corresponding public key. The public key is made available through a DNS record associated with my domain name. (I use [Google Workspace](https://workspace.google.com/) as my mail server, and it was easy to enable DKIM.)
- [Domain-based Message Authentication, Reporting and Conformance](https://dmarc.org/) (DMARC) allows me specify how emails that fail the SPF or DKIM test should be handled. I can set policies to reject or quarantine spoofed emails.

[image blog/email-headers-2021]

Many data breaches and financial losses start with a phishing email. If you use your own domain name for email, take five minutes to check how well you're protected. You can use one of the many checkers. Here are some of the checkers I used:

- <https://dmarcian.com/domain-checker/>
- <https://mxtoolbox.com/emailhealth/>
- <https://www.mail-tester.com/>

Owning your own domain name can be a bit of work, but it's also super interesting. I enjoyed learning about SPF, DKIM and DMARC.
