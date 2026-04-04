---
url: 'https://dri.es/the-sovereignty-prerequisite'
title: 'The Sovereignty Prerequisite'
author:
  name: 'Dries Buytaert'
  url: 'https://dri.es/about'
date: '2026-04-01T05:06:03-04:00'
license: 'https://creativecommons.org/licenses/by/4.0/'
type: blog
summary: "The EU's sovereignty framework scores Open Source at roughly 4%. It should be a prerequisite, not a rounding error."
tags:
  - 'Digital sovereignty'
  - Policy
  - 'Open Source'
image: blog/sovereignty-prerequisite
discussions:
  - { platform: LinkedIn, url: 'https://www.linkedin.com/posts/buytaert_opensource-digitalsovereignty-buyeuropean-share-7445060147489501184-GoEj/' }
published: true
featured: true
id: 6156
---

# The Sovereignty Prerequisite

[image blog/sovereignty-prerequisite priority=true schema=false]

Procurement frameworks aren't the most exciting topic. But the European Commission is about to propose the [Cloud and AI Development Act](https://www.europarl.europa.eu/legislative-train/theme-a-new-plan-for-europe-s-sustainable-prosperity-and-competitiveness/file-cloud-and-ai-development-act) (CADA), and how it treats Open Source will affect every Open Source project and Open Source business operating in Europe. This is one of those moments where the details matter.

Last month, I proposed a [Software Sovereignty Scale](https://dri.es/the-software-sovereignty-scale) that grades software from A to E based on how easily your rights can be taken away. My core argument: if you want sovereignty that lasts, Open Source matters more than buying European proprietary software.

I submitted the Software Sovereignty Scale as feedback to the European Commission, recommending that Open Source carry more weight in the [Cloud Sovereignty Framework](https://commission.europa.eu/document/download/09579818-64a6-4dd5-9577-446ab6219113_en?filename=Cloud-Sovereignty-Framework.pdf), the tool EU institutions like the Commission and Parliament use to evaluate cloud providers when purchasing cloud services for their own operations.

The Cloud Sovereignty Framework only applies to how EU institutions buy their own cloud services. The Cloud and AI Development Act, which is expected to build on its approach, would set rules for the entire EU cloud market, across all 27 member states. The difference in scale is enormous, and the time to get this right is now.

My [original recommendation](https://dri.es/the-software-sovereignty-scale) was to give Open Source more weight in the Cloud Sovereignty Framework's scoring. I've since realized that isn't enough. Licensing shouldn't be in the sovereignty score at all. It should be a prerequisite.

### Open Source is not a rounding error

The Cloud Sovereignty Framework evaluates providers across eight sovereignty objectives, each weighted into a composite score, as shown in the screenshot below. Contracting authorities use that score to rank and compare providers when selecting software and cloud services.

[image blog/eu-cloud-sovereignty-framework-weights resize=false schema=false]

Technology Sovereignty (SOV-6), the objective that covers Open Source, accounts for 15% of the total. Within it, open licensing is one of four contributing factors. That means software being Open Source can contribute roughly 4% to a provider's final sovereignty score.

Does that feel right to you? The one thing that guarantees sovereignty long-term is worth ~4%.

A framework designed to measure sovereignty treats the one factor that makes sovereignty permanent as a rounding error. I could argue the percentage should be higher, or that Open Source supports other objectives, but even at 40%, licensing would still be in the wrong place.

Licensing is fundamentally different from every other objective in the framework. Skype checked every sovereignty box until eBay acquired it in 2005. Every credential was valid before the acquisition and meaningless after.

Had Skype been Open Source, no one could have taken the code away. You would still retain the right to use, modify, and fork it regardless of who acquired the company. That right is permanent, but a European headquarters is not. 

That makes licensing a prerequisite, not something to average into a score. Scores compare trade-offs. Prerequisites define what is non-negotiable.

### The gate already exists

Beyond the composite score, the framework defines Sovereign Effectiveness Assurance Levels, or SEAL levels. These range from SEAL-0 (no sovereignty at all) to SEAL-4 (full EU control with no critical non-EU dependencies).

For each of the eight sovereignty objectives, the contracting authority sets a minimum SEAL level. Any provider that falls below the minimum is rejected outright. These minimums work as pass/fail gates.

My proposal: licensing belongs in the gate, not in the score. Make Open Source a minimum requirement for the highest SEAL levels. 

The [Software Sovereignty Scale](https://dri.es/the-software-sovereignty-scale) could map onto SEAL levels like this:

<div class="large">
<table>
  <thead>
  <tr>
  <th>SEAL level</th>
  <th>Framework definition</th>
  <th>Proposed licensing gate</th>
  <th>What it means in practice</th>
</tr>
</thead>
  <tbody>
  <tr>
  <td>SEAL-3 or above</td>
  <td>Digital Resilience / Full Digital Sovereignty</td>
  <td><a href="https://dri.es/the-software-sovereignty-scale">Grade A, B, or C</a> (Open Source)</td>
  <td>Software can be forked and maintained independently. Sovereignty survives acquisition.</td>
</tr>
  <tr>
  <td>SEAL-2</td>
  <td>Data Sovereignty</td>
  <td><a href="https://dri.es/the-software-sovereignty-scale">Grade D</a> or above (including European proprietary software)</td>
  <td>European jurisdiction, but structurally vulnerable to acquisition or relicensing.</td>
</tr>
  <tr>
  <td>SEAL-1</td>
  <td>Jurisdictional Sovereignty</td>
  <td>No licensing gate</td>
  <td>Minimal sovereignty assurance.</td>
</tr>
</tbody>
</table>
</div>

Under this proposal, mission-critical software with high switching costs would require a minimum of SEAL-3, making Open Source a requirement. For lower-risk procurement where the software is easy to replace, SEAL-2 would allow proprietary providers to compete.

Won't this exclude many proprietary providers? Yes, it would. But we have to be honest: proprietary software doesn't give you sovereignty that lasts.

I support the push to buy homegrown technology ("Buy European"). It keeps investment in Europe. But it doesn't solve the underlying problem.

### Which government is sovereign?

Consider two scenarios. In the first, a government runs proprietary software on a sovereign European cloud. The provider gets acquired by a non-EU company, and the government can't migrate without replacing the software entirely. It has jurisdiction but ultimately no control. It's not very sovereign.

In the second, a government runs Open Source software on Amazon Web Services (AWS), a US-owned cloud provider with data centers in Europe. If AWS becomes a problem because of the CLOUD Act, policy changes, or geopolitics, the government can move the same software to a European cloud provider. Switching cloud providers can be hard, but switching software is much harder.

It may seem counterintuitive, but the second government is in a stronger position. Open Source on a non-European cloud gives you more sovereignty than proprietary software on a European one, because you can always change the infrastructure. You can't fix the licensing.

This doesn't make the second scenario risk-free. The ideal solution would be Open Source on a sovereign European cloud.

People overestimate jurisdiction and underestimate licensing. Licensing is not one sovereignty factor among many. It's the sovereignty prerequisite.

*Special thanks to [Tiffany Farriss](https://www.drupal.org/u/farriss) and [Sachiko Muto](https://www.linkedin.com/in/sachikomuto/) for their review of this blog post.*

PS: Follow the discussion on [LinkedIn](https://www.linkedin.com/posts/buytaert_opensource-digitalsovereignty-buyeuropean-share-7445060147489501184-GoEj/).
