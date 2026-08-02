---
url: 'https://dri.es/responsibility-follows-control'
title: 'Responsibility follows control'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2026-07-30T12:46:27-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'Open weights split creation, distribution, and use across different actors. Responsibility should follow control.'
tags:
  - 'Artificial Intelligence'
  - Policy
  - Drupal
image: blog/human-ai-shared-control
discussions:
  - { platform: LinkedIn, url: 'https://www.linkedin.com/feed/update/urn:li:share:7488626348006006787/' }
published: true
featured: false
id: 6291
---

# Responsibility follows control

![A person and a robot stand before a giant floating sphere in a futuristic industrial landscape.](http://default/files/cache/blog/human-ai-shared-control-640w.jpg)

An AI model does not decide what data it can access, which tools it can use, or whether it can act without approval. People make those decisions at different points. Upstream, a model developer trains and tests the model and decides whether and how to release it. Downstream, a developer builds the model into a system, connects that system to data and tools, and decides whether a person must review its proposed actions before they take effect.

Those choices determine whether harm is possible at all. So when harm occurs, responsibility should fall on those who controlled the relevant choices. That responsibility may be shared: model developers control training and release, product builders control permissions and deployment, and users control deliberate misuse.

Responsibility should follow meaningful control

That principle is missing from much of the debate over open-weight AI models, which often treats the decision to release a model as the only one that counts.

Axios recently reported that United States officials had [considered measures that could restrict American companies from using Chinese open-weight models](https://www.axios.com/2026/07/20/ai-us-china-open-source-kimi). Open-weight models make their trained parameters available for others to download, modify, and run on their own infrastructure, without going through the company that built them.

More than 230 companies and organizations have since signed an [industry letter defending open weights](https://www.microsoft.com/en-us/corporate-responsibility/topics/open-weight/). After critics accused Anthropic of supporting a ban on open-weight models, Anthropic CEO Dario Amodei published a [statement denying that position](https://www.anthropic.com/news/position-open-weights-models). He described open-weight models that do not have dangerous capabilities as a public good and supported mandatory safety testing for sufficiently capable models, open or closed.

The disagreement is less about whether open weights can create risk than about when those risks justify restricting a release, and whether restrictions would improve safety or mainly concentrate power in the largest AI labs.

I am firmly in the open-weights camp. I have [run and compared open-weight models](https://dri.es/comparing-local-llms-for-alt-text-generation-round-2), argued that [digital sovereignty depends on who controls software, not where it comes from](https://dri.es/the-software-sovereignty-scale), and believe organizations should control their infrastructure and data instead of depending on a handful of providers.

I also believe consequential algorithms need oversight. More than a decade ago, I argued that we would eventually need [something like an FDA for software](https://dri.es/algorithms-rule-our-lives-so-who-should-rule-them). The harder question is where responsibility for that oversight should lie.

## Open-weight models unbundle control

With hosted, closed-weight models from providers such as Anthropic and OpenAI, the provider typically keeps the weights private, controls how customers access the model, and decides when to update the hosted service.

Open weights can separate those roles. One organization creates and releases the model. A repository such as Hugging Face hosts and distributes the weights. Another team might fine-tune them. A product builder incorporates the model into a product and connects it to data, tools, and users.

Each team controls something different. Because open weights unbundle control, it becomes harder to say who is responsible when harm occurs.

A model developer controls the training process, capability testing, documentation, and release decisions. A repository controls what information it displays about a model's origin, which security checks it performs on uploaded files, and which access restrictions it provides or enforces. A product builder controls what data and tools the resulting system can reach, which actions require human approval, and what gets logged.

Control is not the only thing that matters, but it shows who could still have changed the outcome. When harm involves AI, several actors may bear responsibility for the same incident because each controlled a different opportunity to prevent it.

## Open Source shows how responsibility follows control

Like open-weight models, Drupal's Open Source code can be copied and changed without asking anyone's permission. A site owner could use it to spread misinformation or operate a fraudulent website. The site owner controls the content and operation of the site and is responsible for those choices. The Drupal project is not responsible merely because someone used its code.

But the Drupal project controls other decisions. When someone privately reports a security vulnerability, the Drupal Security Team follows a [coordinated disclosure policy](https://www.drupal.org/drupal-security-team/general-information). It keeps the issue private while a fix is prepared. Once a security release is available, the team publishes an advisory and tells site owners to upgrade. The timing of that disclosure can give site owners a fair chance to protect themselves.

The same distinction applies to AI. Responsibility should follow the decisions each actor controls.

## Products turn capability into authority

A model generates outputs. An agent is a software system that uses a model to work toward a goal, often by calling tools and taking actions. The people who build and configure the agent decide what it can access, which actions it can take, and when it needs a person's approval.

In a coding agent such as Claude Code, a model can generate a database command. Whether that command can run depends on the tools and permissions the agent provides, as well as the access allowed by the computer, network, and database.

A content management agent can propose deleting an article. The content management system (CMS) determines whether the agent has permission to delete it, whether the deletion is reversible, and whether the action is recorded.

Permissions, isolation, audit logs, rate limits, human approval, and rollback are not merely engineering details. They determine who has control at the point where harm can still be prevented. That is why AI governance is becoming an essential part of product architecture.

## Regulate AI at each point of control

Deciding who should answer *after* harm is the easier half of this, even when the answer is not obvious. The harder half is deciding what government should require *before* any harm has happened.

If control and responsibility are distributed across several actors, government rules should be distributed across them too. This is not a new idea. We already regulate many technologies this way.

More than a decade ago, when I argued for something like an FDA for software, I had drug approval in mind. I no longer think that is the right model. The FDA approves a drug for one or more intended uses, while a general-purpose model may be used for many different purposes.

Cars are a better comparison. The government sets safety standards, and manufacturers certify that their vehicles meet them.  Separately, drivers must pass a test defined by the government before they are licensed to drive. 

The layers extend beyond cars and drivers. States set legal blood-alcohol limits for drivers and require bars to have licenses they can lose. In many states, a bar can also be held liable for serving a visibly intoxicated person who later causes harm.

Each rule targets the actor who controls a particular decision. Together, they reduce risk for everyone. I would take the same layered approach to AI.

Blocking a model's release is a much stronger step, and one that should rarely be used. For an open-weight model, that means preventing the developer from publishing the weights. For a closed model, it could mean preventing the provider from offering access.

I would support that only when safeguards in products and rules governing their use could not prevent a serious danger in time. The two-part test below applies only to this exceptional step, not to AI regulation in general.

## Require extraordinary evidence to block a release

The strongest argument for restricting an open-weight release is that it is effectively irreversible. Once the weights are public, the developer cannot withdraw every copy, monitor how the model is used, or ensure that its safeguards remain in place.

If a model made catastrophic harm much easier, its release could be the last moment anyone had meaningful control. By catastrophic, I mean mass-casualty or comparably systemic harm, not ordinary product failure, fraud, or abuse.

As of July 2026, I have not seen public evidence that an open-weight model has crossed this threshold. That said, I believe it is just a matter of time, which is why I still think meaningful regulation is coming.

Before blocking a model's release, a government should have clear evidence that the answer to both questions is yes:

1. **Would releasing this model make catastrophic harm much easier?** Compare it with closed models and other tools people can already access.

2. **Would blocking its release meaningfully reduce that danger?** A restriction should not merely shift access to another country or distribution channel.

## Default to openness with distributed responsibility

So where do I land today? I would default to allowing publication and place obligations where control already exists: on model creators for testing and release decisions, on distributors for provenance and file integrity, on product builders for permissions and deployment, and on users for deliberate misuse.

This approach also protects competition. A regulatory regime that only the largest labs can satisfy could protect them from competition without necessarily making anyone safer. It could also push organizations toward depending on a handful of providers for infrastructure they cannot inspect.

Open weights do not eliminate control. They distribute it, making it harder to say who is responsible when harm occurs. Regulation should follow that structure: place obligations on each actor at the point where harm can still be prevented, and block publication only when release would make catastrophic harm substantially easier and a restriction would materially reduce the danger.

PS: Follow the discussion on [LinkedIn](https://www.linkedin.com/feed/update/urn:li:share:7488626348006006787/).
