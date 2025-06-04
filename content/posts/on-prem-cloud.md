---
title: 'Cloud-on-prem vs Big Tech'
subtitle: "Or: Why Your Data Shouldn’t Fund Silicon Valley’s Technofeudal Empire"
date: 2025-06-05T05:00:00.000Z
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

An uncomfortable truth: Every byte uploaded to AWS, Azure, or Google Cloud isn’t just data—it’s *cloud capital*. Coined by economist Yanis Varoufakis, the term captures how tech giants transform your digital activity into privatised infrastructure. It’s not merely about hosting files; it’s about hoarding power. And right now, the United States holds the keys, turning Europe into a lodger in its digital manor.

But there is an alternative: **cloud-on-prem**—a return to digital self-sufficiency—and European providers like **Hetzner**, who offer control, compliance, and a way to starve the beast. Think of it less as going backwards and more as refusing to pay rent to your colonial landlord.

Here’s why dumping Big Tech’s cloud might be the most rebellious—and most reasonable—thing your organisation does this year.

---

## The cloud capital conundrum

### What is cloud capital?

Cloud capital isn’t servers and code, but the political economy of dependency. It’s the soft power Amazon, Microsoft, and Google wield by owning the pipes and APIs of modern life. They don’t merely sell computing—they lease out control, one serverless function at a time.

Imagine a medieval fiefdom, only instead of land, you’re tied to the whims of AWS billing and Google's usage quotas. Your “freemium” is their fealty.

### Europe’s weak hand

The US controls around **63% of the global cloud market**. Europe, for all its regulatory might, is playing catch-up with both hands tied behind its back. This isn't simply a business concern—it’s strategic infrastructure.

Cloud capital funds surveillance tech, AI development, and policy lobbying. In relying on US hyperscalers, the EU doesn’t just outsource storage—it outsources sovereignty. Just ask the folks still reeling from the **DeepSeek AI shock of 2025**, when a Chinese open-source model tore the mask off America’s AI supremacy and reminded us all how brittle proprietary cloud empires really are.

### Why it matters

* **Vendor lock-in**: Tools like AWS Lambda are functionally narcotic. Quitting requires therapy, budget approvals, and possibly an exorcist.
* **Data sovereignty**: US clouds fall under the **CLOUD Act**, making European GDPR assurances about as useful as an ashtray on a motorbike if your backups live in Virginia.
* **Economic leakage**: Every euro sent to AWS subsidises American tech IPOs—not European innovation.

---

## The case for cloud-on-prem

### Control without compromise

Cloud-on-prem—or hybrid setups—give you cloud-like features *without* the overlords. With platforms like **OpenStack**, **Kubernetes**, or even a good old Proxmox cluster, you can self-host without self-harm.

Benefits include:

* **No surprise invoices**: Azure’s infamous egress fees become someone else’s horror story.
* **Actual compliance**: Store medical or legal data where it belongs—under your own jurisdiction.
* **Performance gains**: Transatlantic latency is fine for email, less so for anything real-time.

### Hetzner: Germany’s quiet rebellion

In a world of cloud greenwashing and vague ESG slideshows, Hetzner actually walks the walk. Their Finnish data centres run on **100% hydropower**, boast a **PUE of 1.13**, and don’t demand your soul in exchange for a dashboard.

They also partner with **Nokia** to deliver 400G networking that’s both fast and (dare we say) elegant. If AWS is a digital motorway littered with tollbooths, Hetzner is the backroad with better views and no surveillance.

---

## The greener (and smarter) alternative

### Finland’s data centre boom

Hetzner’s Finnish outposts make clever use of geography and engineering:

* **Free cooling**: Arctic air handles most of the year’s cooling needs—Mother Nature as sysadmin.
* **Waste heat reuse**: Diverted into local district heating, proving that servers can warm more than just CPUs.
* **Water efficiency**: US hyperscalers consume **billions of litres daily**; Hetzner’s operations sip modestly by comparison.

### Cost vs conscience

Cloud-on-prem isn’t free—but it’s refreshingly honest.

* A 2025 survey found **37% of enterprises repatriated workloads** due to Big Tech’s opaque pricing.
* Hetzner’s server auctions and open power stats make Amazon look positively Victorian in comparison.

Want to run ARM64 nodes that use 30% less energy than x86? They’ve got you. Want a predictable bill at the end of the month? Also covered.

---

## When Big Tech still wins (for now)

### AI’s dirty secret

Large language models like ChatGPT require infrastructure the size of small nations. Yes, they run on Big Tech’s hyperscale platforms—for now.

But Europe isn’t entirely out of the race. The [**LUMI supercomputer**](https://www.lumi-supercomputer.eu/), housed in Finland and powered by renewables, is a stark rebuttal to the notion that AI dominance must be carbon-heavy and American.

### The hybrid hedge

You don’t have to quit cold turkey. Keep bursty workloads (like AI training or render farms) on AWS. But move core data—PII, legal docs, customer records—onto your own kit. Hybrid is often less a compromise than a rebalancing of power.

---

## Reclaim your cloud capital

The cloud was meant to free us from hardware—not hand us over to digital landlords. By adopting **cloud-on-prem** or **hybrid** models, you:

1. **Starve technofeudalism**: Every workload you move is one less tithe to Silicon Valley.
2. **Strengthen European tech**: Support providers that don’t treat GDPR like an optional questline.
3. **Future-proof compliance**: Remember Schrems II? Schrems III is surely in the mail.

As Varoufakis warns, *“cloud capital is the new oil—and Europe is still the colonised, not the coloniser.”* Time to sink your own digital well.

---

## How to start your cloud exodus

1. **Audit your workloads**: Identify lock-in, technical debt, and cost traps.
2. **Pilot a European provider**: Test Hetzner’s ARM64 nodes or try on-prem with OpenStack. [I did](https://blue.tymyrddin.dev/docs/dev/devsecops/on-prem/), and I still have root access.
3. **Go hybrid with intent**: Keep hyperscale where needed, but don’t let it become your default.

The cloud isn’t just infrastructure—it’s a power structure. Choose yours with both eyes open.

---

## Cloud exit checklist

### Phase 1: Reality check

☐ **Audit your current cloud usage**

* Inventory services, dependencies, regions, and lurking Lambda functions.
* Identify critical workloads vs vanity projects.

☐ **Estimate total cloud cost**

* Include hidden gremlins: egress fees, storage tiers, and zombie VMs.
* Compare with realistic on-prem or hybrid costs (include staff, power, hardware).

☐ **Check for vendor lock-in**

* Look for managed services with no easy exit (e.g., proprietary databases, serverless traps).
* Document migration blockers (formats, APIs, service contracts).

☐ **Assess compliance risk**

* Are you GDPR-compliant or just spiritually so?
* Know where your data physically lives and under which jurisdiction.

---

### Phase 2: Plan your escape

☐ **Choose your model**

* Cloud-on-prem: full local hosting with cloud-like tools.
* Hybrid: local core + hyperscale for bursts or AI training.
* Multicloud: diversify, but be ready to juggle.

☐ **Select your toolkit**

* **Orchestration**: Kubernetes, Nomad, or a stiff gin.
* **IaaS replacement**: OpenStack, Proxmox, Harvester.
* **CI/CD + secrets**: GitLab, ArgoCD, HashiCorp Vault.

☐ **Pick a European provider (if applicable)**

* Hetzner for power-efficient, no-nonsense infra.
* UpCloud for low-latency EU edge.
* Greenhost or 1984.is if you fancy civil liberties with your compute.

☐ **Pilot and test**

* Start with dev/test environments.
* Benchmark latency, throughput, and your team’s morale.

---

### Phase 3: Migrate like a professional

☐ **Move core workloads**

* Prioritise data sovereignty: HR, healthcare, legal, anything that screams “breach me”.
* Document every step—future you will be grateful.

☐ **Refactor or replace cloud-native services**

* Replace proprietary functions (e.g., AWS Lambda) with open equivalents.
* Use containers, not Stockholm Syndrome.

☐ **Set up proper monitoring and alerting**

* Grafana > guessing.
* Avoid outages caused by a silent disk filling up since last Christmas.

☐ **Implement backup & disaster recovery**

* Test restores, not just backups.
* Store backups somewhere Uncle Sam doesn’t have keys.

---

### Phase 4: Post-migration hygiene

☐ **Decommission responsibly**

* Delete unused cloud resources (don't just *think* you did).
* Watch final invoices like a hawk with trust issues.

☐ **Update policies and documentation**

* New infrastructure = new responsibilities.
* Train staff. Resist eye-rolls.

☐ **Monitor for regression**

* Don’t slide back into “just this one AWS S3 bucket…”
* Build cloud repatriation into your tech strategy.

☐ **Celebrate with your team**

* Cake, if budget allows.
* Stickers for the sysadmins.
* Inner peace from no longer funding data surveillance.

---

### Phase 5: Tell your compliance officer

* They’ll sleep better knowing your backups don’t reside under the [CLOUD Act](https://www.justice.gov/criminal/cloud-act-resources).
* And you might just avoid explaining your infrastructure to a [Data Protection Authority](https://en.wikipedia.org/wiki/National_data_protection_authority) with a grudge.
