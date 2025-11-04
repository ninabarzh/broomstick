---
title: 'Cloud-on-prem vs Big Tech'
subtitle: "Or: Do not fund Silicon Valley's technofeudal empire"
date: 2025-11-04
draft: false
tags: 
  - big tech vs cloud-on-prem
  - AWS
  - GCP
  - Azure
  - cloud-on-prem
  - exodus
  - greener
  - LUMI
  - Europe
  - EU
  - US
---

An uncomfortable truth: Every byte uploaded to AWS, Azure, or Google Cloud isn't just data, it's *cloud capital*. Coined by economist Yanis Varoufakis, the term captures how tech giants transform your digital activity into privatised infrastructure. It's not merely about hosting files; it's about hoarding power. And right now, the US holds the keys, turning Europe into a lodger in its digital manor.

But there is an alternative: cloud-on-prem, a return to digital self-sufficiency, and European providers like Hetzner, who offer control, compliance, and a way to starve the beast. Think of it less as going backwards and more as refusing to pay rent to your colonial landlord.

Here's why dumping Big Tech's cloud might be the most rebellious, and most reasonable, thing your organisation does this year.

## The cloud capital conundrum

### What is cloud capital?

Cloud capital isn't servers and code, but the political economy of dependency. It's the soft power Amazon, Microsoft, and Google wield by owning the pipes and APIs of modern life. They don't merely sell computing, they lease out control, one serverless function at a time.

Imagine a medieval fiefdom, only instead of land, you're tied to the whims of AWS billing and Google's usage quotas. Your "freemium" is their fealty.

### Europe's weak hand

As of [Q2 2025](https://www.techopedia.com/cloud-market-share-leaders), the US controls approximately 63% of the 
global cloud infrastructure market, with AWS holding 30%, Microsoft Azure 20%, and Google Cloud 13%. Europe, for all its regulatory might, is playing catch-up with both hands tied behind its back. This isn't simply a business concern, it's strategic infrastructure.

Cloud capital funds surveillance tech, AI development, and policy lobbying. In relying on US hyperscalers, the 
EU doesn't just outsource storage, it outsources sovereignty. The 
[January 2025 DeepSeek incident](https://www.forbes.com/sites/greatspeculations/2025/02/03/deepseeks-ai-shockwave-hits-nvidia-hard-wiping-out-billions/) 
provided a stark reminder of this fragility. When the Chinese startup's open-source AI model hit app stores and 
immediately exceeded ChatGPT's downloads, it sent shockwaves through Silicon Valley—Nvidia's stock plummeted 17% in a 
single day, and the Nasdaq lost over 600 points. DeepSeek demonstrated that perhaps matching US model performance at a 
fraction of the cost was possible, tearing the perceived mask off America's AI supremacy and reminding us all how brittle 
proprietary cloud empires can be.

### Why it matters

* Vendor lock-in: Tools like AWS Lambda are functionally narcotic. Quitting requires therapy, budget approvals, and possibly an exorcist.
* Data sovereignty: US clouds fall under the CLOUD Act, significantly weakening GDPR protections if your backups live in Virginia. The legal grey area creates genuine compliance risks for European organisations.
* Economic leakage: Every euro sent to AWS subsidises American tech IPOs, not European innovation.

## The case for cloud-on-prem

### Control without compromise

Cloud-on-prem, or hybrid setups, give you cloud-like features *without* the overlords. With platforms like OpenStack, Kubernetes, or even a good old Proxmox cluster, you can self-host without self-harm.

Benefits include:

* No surprise invoices: Azure's infamous egress fees become someone else's horror story.
* Actual compliance: Store medical or legal data where it belongs, under your own jurisdiction.
* Performance gains: Transatlantic latency is fine for email, less so for anything real-time.

That said, cloud-on-prem comes with its own challenges: you need skilled staff to manage infrastructure, capital investment for hardware, and systems that can handle demand spikes. The hybrid approach acknowledges these realities—keep hyperscale where it genuinely makes sense, but don't let it become your default.

### Hetzner and other European alternatives

In a world of cloud greenwashing and vague ESG slideshows, 
[Hetzner actually walks her talk](https://www.hetzner.com/unternehmen/nachhaltigkeit/). June 2025, their 
data centres operate with an average 
[PUE (Power Usage Effectiveness) of 1.1](https://mastodon.hetzner.social/@hetzner/114675489563835308), with 
individual facilities ranging between 1.10 and 1.16 (exceptionally efficient by industry standards). Their 
German facilities have used electricity from hydropower since 2008, and their Finnish data centre park has run 
on hydropower since opening in 2018.

They also partner with Nokia to deliver 400G networking that's both fast and (dare we say) elegant. If AWS 
is a digital motorway littered with tollbooths, Hetzner is the backroad with better views and no surveillance.

Other European providers worth considering include OVHcloud (France), Scaleway (France), and IONOS 
(Germany), each offering varying degrees of sovereignty, compliance, and local support. The point is not 
to promote any single vendor, it is to demonstrate that a viable European cloud ecosystem exists.

## The greener (and smarter) alternative

### Finland's data centre advantage

Hetzner's Finnish outposts make clever use of geography and engineering:

* Free cooling: Arctic air handles most of the year's cooling needs, Mother Nature as sysadmin.
* Waste heat reuse: Diverted into local district heating, proving that servers can warm more than just CPUs.
* [Water efficiency](https://www.eesi.org/articles/view/data-centers-and-water-consumption): US data centres collectively consumed an estimated 163.7 billion gallons of water annually as of 2021 (equivalent to 449 million gallons per day). Large facilities can consume up to 5 million gallons daily, equivalent to a town of 10,000-50,000 people. Hetzner's operations, by contrast, sip modestly using hydropower and climate advantages.

### Cost vs conscience

Cloud-on-prem isn't free, but it's refreshingly honest.

* Industry reports suggest growing numbers of enterprises are repatriating workloads from public clouds due to cost concerns and opacity in hyperscaler pricing models.
* Hetzner's server auctions and open power statistics make Amazon look positively Victorian in comparison.

Want to run ARM64 nodes that use 30% less energy than x86? They've got you. Want a predictable bill at the end of the month? Also covered.

## When Big Tech still wins (for now)

### AI and hyperscale realities

Large language models like ChatGPT require infrastructure the size of small nations. Yes, they run on Big Tech's hyperscale platforms, for now. Training frontier AI models demands coordination, capital, and compute resources that exceed what most organisations—or even most nations—can muster independently.

But Europe isn't entirely out of the race. The [LUMI supercomputer](https://www.lumi-supercomputer.eu/), housed in Finland and powered by renewables, is a stark rebuttal to the notion that AI dominance must be carbon-heavy and American. LUMI demonstrates that high-performance computing and environmental responsibility aren't mutually exclusive.

### The hybrid hedge

You don't have to quit cold turkey. Keep bursty workloads (like AI training or render farms) on AWS. But move core data—personally identifiable information, legal documents, customer records—onto your own kit or European providers. Hybrid is often less a compromise than a rebalancing of power.

This approach acknowledges the genuine technical advantages of hyperscale (global CDN networks, instant scaling, massive GPU clusters for AI) whilst reclaiming sovereignty over your most sensitive assets.

## Reclaim your cloud capital

The cloud was meant to free us from hardware, not hand us over to digital landlords. By adopting cloud-on-prem or hybrid models, you:

1. Starve technofeudalism: Every workload you move is one less tithe to Silicon Valley.
2. Strengthen European tech: Support providers that don't treat GDPR like an optional questline.
3. Future-proof compliance: Remember Schrems II? Schrems III is surely in the mail.

As Varoufakis argues, cloud capital functions much like oil did in the colonial era—a strategic resource that defines power relationships between nations. In his analysis, Europe remains the colonised rather than the coloniser in this new digital economy. Time to sink your own digital well.

## How to start your cloud exodus

1. Audit your workloads: Identify lock-in, technical debt, and cost traps.
2. Pilot a European provider: Test Hetzner's ARM64 nodes or try on-prem with OpenStack. [I explored it](https://blue.tymyrddin.dev/docs/dev/devsecops/on-prem/), and I still have root access.
3. Go hybrid with intent: Keep hyperscale where genuinely needed (AI training, global CDN, extreme burst capacity), but don't let it become your default.
4. [Make a checklist like this one](https://blue.tymyrddin.dev/docs/dev/devsecops/cicd/exit-checklist).

The cloud isn't just infrastructure, it's a power structure. Choose yours with both eyes open.
