---
url: 'https://dri.es/exploring-a-marketplace-for-drupal-site-templates'
title: 'Exploring a marketplace for Drupal site templates'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2025-04-02T13:29:31-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: 'This post looks at the idea of a Drupal Site Template marketplace and whether it should support both open source and commercial templates.'
tags:
  - Drupal
  - 'Drupal Association'
image: drupal/marketplace
published: true
featured: false
id: 5786
---

# Exploring a marketplace for Drupal site templates

[image drupal/marketplace lazy=false priority=true]

This is an unusual post for my blog, but I'm sharing it to start a broader conversation about an idea we're exploring: a marketplace for Drupal Site Templates. Both the Drupal CMS Leadership Team and the Drupal Association have discussed this concept, but no decision has been made. I'm posting to share our current thinking and invite feedback as we shape this together.

This post will also be [cross-posted to Drupal.org](https://www.drupal.org/blog/exploring-a-marketplace-for-drupal-site-templates), where comments are open. You're also welcome to join the conversation in the `#drupal-cms-marketplace` channel on [Drupal Slack](https://www.drupal.org/join-slack).

In [my DrupalCon Atlanta keynote](https://dri.es/state-of-drupal-presentation-march-2025), I introduced the concept of Site Templates for Drupal. If you haven't seen my keynote yet, I recommend watching it first. It provides helpful context for the rest of this post.

Site Templates provide pre-configured website starting points that combine Drupal recipes, themes, and default content. While Site Templates will help users launch websites faster, I also posed a bigger question: should we create a marketplace where users can discover and download or install these templates? And if so, should that marketplace offer only open source Site Templates, or should we also allow commercial templates?

### What are Site Templates?

Site Templates combine Drupal recipes, a theme, design elements, and default content to give users a fully functional website right from the start. They solve one of Drupal's biggest challenges: the time it takes to build a site from scratch.

Unlike a bare Drupal installation, a Site Template provides all the components needed for a specific use case. A restaurant template might include menu management, reservation systems, and food photography. A nonprofit template could feature donation processing, event management, and impact reporting tools.

[image drupalcon-atlanta-2025/site-template]

### Why consider a marketplace?

A Drupal marketplace for Site Templates would:

1. Help new users launch a professional-looking site instantly
2. Showcase Drupal's full potential through high-quality starting points
3. Generate new revenue opportunities for Drupal agencies and developers
4. Support Drupal's long-term sustainability through a revenue-sharing model with the Drupal Association

### Should we support both open source and commercial Site Templates?

Fully open source Site Templates align naturally with Drupal's values. They could function much like community-contributed modules and themes, and we hope that many contributors will take this approach.

A marketplace requires ongoing investment. The Drupal Association would need to maintain the platform, review submissions, provide support, and ensure templates meet high standards. Without dedicated resources, quality and sustainability would suffer.

This is why supporting both open source and commercial templates makes sense. Paid templates can create a sustainable revenue stream to fund infrastructure, quality control, and support.

Commercial incentives also give creators a reason to invest in polished, well-documented, and well-supported templates.

### How can a template be commercial while respecting Drupal's open source values?

First, rest assured: Drupal modules will always be open source.

Drupal is licensed under the GNU General Public License, or GPL. We've always taken a conservative approach to interpreting the GPL. In practice, this means we treat any code that builds on or interacts closely with Drupal as subject to the GPL. This includes PHP, Twig templates, etc. If it relies on Drupal's APIs or is executed by Drupal, it must be GPL-licensed.

Some parts of a site template fall into a gray area. JavaScript is an example. If JavaScript code is integrated with Drupal, we treat it as GPL-covered. If JavaScript code is standalone, such as a self-contained React component, it may not be considered a derivative work. The same may apply to CSS or configuration files not tightly coupled with Drupal APIs. These cases aren't always clear, but our stance has been to treat all code that ships with and interacts with Drupal as GPL. This keeps things simple.

Other parts of a Site Template are likely not subject to the GPL. Assets like images, fonts and icons are not code and are not derived from Drupal. The same applies to demo content, such as placeholder text or sample articles. These elements are not integrated with Drupal in a technical sense and can use other licenses, including commercial ones.

So when we talk about a commercial Site Template, we mean one that combines open source code with separately licensed assets or is sold alongside value-added services like documentation, support, or updates.

### What would people actually be paying for in a commercial template?

While the *legal* distinction clarifies which parts of a Site Template can be licensed commercially, it's only part of the picture. The real question is the *value proposition*: what are users actually paying for when they choose a commercial template?

When purchasing a commercial template, users wouldn't just be paying for code. They're potentially paying for:

- Professional design assets and media
- Time saved in configuration and setup
- Documentation and support
- Ongoing updates and maintenance

This approach aligns with the [Free Software Foundation](https://www.fsf.org/)'s stance (the organization that created the GPL), which has always supported commercial distribution of free software. Creating a commercial template means balancing open source code with separately licensed assets. However, the real commercial value often extends beyond just the files you can license differently.

A sustainable commercial strategy combines proper licensing with controlled distribution channels and value-added services, like support. This approach ensures the value of a site template isn't limited to easily copied assets, but includes expertise that can't be simply downloaded. This is how a template can be commercial while staying true to Drupal's open source values.

### How would we maintain quality in the marketplace?

A marketplace filled with low-quality or abandoned templates would damage Drupal's reputation. To ensure quality we probably need:

- Technical reviews of templates for security and performance
- Standards for documentation and support
- Processes to handle outdated or abandoned templates
- Community ratings and reviews
- Processes for resolving disputes

These quality assurance measures require ongoing time, effort, and funding. This is why including a commercial component makes sense. A revenue-sharing model with template creators could help fund platform maintenance, reviews, support, and other efforts needed to keep the marketplace high quality and trustworthy.

### What pricing models might be available?

We don't know yet, but we've heard many good suggestions from the community.

Ideas include one-time purchases for unlimited use, annual subscriptions with ongoing updates, and a marketplace membership model for template creators.

The marketplace could support multiple approaches, giving creators flexibility to choose what works best for their offerings.

### Is it fair for template creators to profit while module contributors aren't paid?

When a site template is sold commercially, it raises an important question. What about the maintainers of the modules included in the template? The template builder receives payment. The Drupal Association may collect a revenue share. But the individual contributors who created the modules or core functionality do not receive direct compensation, even though their work is essential to the Site Template.

This may feel frustrating or unfair. Contributors often donate their time to improve Drupal for everyone. Seeing others earn money by building on that work without recognition can be disheartening, and could even discourage future contributions. It's an important concern, and one we plan to take seriously as we evaluate the marketplace model.

At the same time, this dynamic is not new. Agencies and developers already build paid Drupal sites using contributed modules without directly compensating the people who made the underlying code possible. This is both legal, expected, and common in open source.

A marketplace would not create this reality, but it would make it more visible. That visibility gives us a chance to confront a long-standing tension in open source: the gap between those who contribute foundational work and those who profit from it. As I wrote in [Makers and Takers](https://dri.es/balancing-makers-and-takers-to-scale-and-sustain-open-source), sustaining open source requires a better balance between contribution and benefit. A marketplace could give us a way to explore new approaches to recognize, support, and sustain the people who make Drupal possible. Transparency alone won't solve the issue, but it opens the door to progress and experimentation.

When commercial activity happens off Drupal.org, there is no way to recognize the contributors who made it possible. When it happens on Drupal.org, we have an opportunity to do better. We can explore models for financial support, community recognition, and long-term sustainability.

Others could build marketplaces for Drupal templates, but these would likely focus on profit rather than community support. An official Drupal Association marketplace allows us to reinvest in the project and the people behind it. It keeps value within our ecosystem, and gives us a platform to explore more equitable ways to sustain open source contribution.

### Would this hurt digital agencies?

Many organizations pay thousands of dollars to digital agencies as part of a custom Drupal build. If Site Templates are available at a much lower cost, will that undercut agencies?

I don't believe it will.

Organizations investing in a Drupal website are not paying for a theme alone. Agencies provide strategy, consulting, design, customization, user testing, performance optimization, and long-term support. A template offers a starting point, but doesn't replace tailored work or a trusted partnership.

### Could templates help agencies grow?

A template marketplace could expand the Drupal ecosystem by lowering the barrier to entry, making Drupal accessible to smaller organizations. Some of these will grow and require custom solutions, creating more opportunities for agencies in the long run.

Templates can also serve as powerful demonstrations of an agency's capabilities, attracting clients who want similar but customized solutions. For agencies, templates become both a product and a marketing tool.

### What revenue opportunities would digital agencies have?

A template marketplace offers two revenue streams for Drupal agencies and freelancers.

First, agencies would earn direct income from template sales through revenue-sharing with the Drupal Association. While this income might be modest, it could provide recurring revenue as the marketplace grows.

Second, templates could serve as a foundation for more comprehensive service packages, including hosting, maintenance, and customization services.

### How would templates connect agencies with new clients?

A marketplace could connect end users directly with service providers. With proper consent, contact details from template purchases could be shared with creators, opening the door to professional service opportunities. Template listings could also include a built-in contact form, making it easy for users to request customization or support.

This lead generation benefits both sides. Users access trusted professionals who understand their implementation, while agencies connect with qualified prospects who have already invested in their work. A marketplace becomes a matchmaking platform connecting those who need Drupal expertise with those who provide it.

### Why is now the right time for this initiative?

With Drupal CMS, we're focused on growth. To succeed, we need to address two long-standing challenges: the lack of ready-made themes and a steep learning curve. Some of our new tools (Recipes, Experience Builder, and Site Templates) allow us to address these longstanding issues.

The result? We can take Drupal's flexibility and make it more available across different markets and use cases.

### What was the initial reaction at DrupalCon?

The day after my keynote, we organized a Birds of a Feather (BoF) session to discuss the marketplace concept. Approximately 75 people attended, representing a cross-section of our community.

The discussion was lively and constructive. Participants raised thoughtful concerns about quality control, licensing, and impact on module contributors. They also offered suggestions for implementation, pricing, and sustainability models.

At the session's conclusion, we informally polled the audience. We asked people to raise their hand showing 1 finger if they thought a marketplace was a terrible idea, and 5 if they considered it a very impactful idea. Most responses were 4, with some 5s. Very few people indicated less than 3.

This initial reaction is encouraging, though we recognize that much work remains to address the questions raised during the session.

We also opened the #drupal-cms-marketplace channel in [Drupal Slack](https://www.drupal.org/join-slack) to continue the conversation with the wider community.

### What are the next steps?

The Drupal CMS Leadership Team and the Drupal Association Innovation Working Group have been exploring this idea the past month.

We believe it could be one of our strongest opportunities to grow Drupal adoption, support our Maker community, and strengthen the Drupal Association. (As a disclaimer: I serve on both the Drupal CMS Leadership Team and the Drupal Association Board of Directors.)

To be clear, *no* decision has been made. We recognize this initiative would have a substantial impact on our community and ecosystem. Before moving forward, we need to assess:

- Feasibility: Can we build and operate a marketplace efficiently?
- Sustainability: How will we support ongoing operations?
- Ecosystem impact: How would this affect contributors, agencies, and users?
- Funding: How do we bootstrap this initiative when we don't have spare resources?
- Values alignment: Does this approach honor Drupal's open source principles?
- Governance: Who makes decisions about the marketplace and how?

We cannot and should not make these assessments in isolation. We need the Drupal community's involvement through:

- Research into similar marketplaces and their impact
- User experience design for the marketplace interface
- Technical prototyping of the marketplace infrastructure
- Financial analysis of various revenue models
- Legal research on open source licensing considerations
- Community input on governance structures

Our goal is to make a decision by DrupalCon Vienna, 6 months from now, or sooner if clarity emerges. We want that decision to reflect input from the CMS Leadership Team, the Drupal Association Board, Certified Drupal Partners, and the wider Drupal community.

We're chartering a Marketplace Working Group with stakeholders from across the Drupal ecosystem. I'm pleased to announce that [Tiffany Farriss](https://www.drupal.org/u/farriss) (Drupal Association Board Member) has agreed to lead this effort. Please join the `#drupal-cms-marketplace` channel on [Drupal Slack](https://www.drupal.org/join-slack) to share your thoughts and follow the conversation.

Drupal's greatest strength has always been its community and adaptability. I believe that by thoughtfully exploring new ideas together, we can make Drupal more accessible and widely adopted while staying true to our core values.

*Thank you to everyone on the Drupal Association Innovation Working Group and the Drupal CMS Leadership Team who took the time to review this post and share thoughtful feedback. I really appreciate your input.*
