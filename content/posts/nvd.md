---
title: "The slow death of the NVD"
subtitle: "How political neglect, funding cuts, and swelling CVE backlogs turned a cornerstone of cybersecurity into a liability"
description: "The National Vulnerability Database has stalled, starved of resources and battered by politics. With enrichment grinding to a halt and backlogs exploding, organisations can no longer treat it as a lifeline. Dissecting the decline and offering suggestions for a playbook for survival in the post-NVD era."
date: 2025-08-20T08:00:00Z
draft: false
tags: ["security", "NVD", "CVE", "vulnerability management", "policy", "funding cuts"]
---

The US National Vulnerability Database has slipped from a dull but dependable piece of security plumbing into a 
sputtering liability. Enrichment of CVEs has stalled, backlogs have exploded, and defenders are left with raw 
identifiers instead of usable intelligence. This collapse is not accidental—it is the predictable result of 
political austerity, funding cuts, and a fixation on flashy science over unglamorous infrastructure. In other 
words, the pipes have burst while Washington debates whether water is really a priority. For security teams all over 
the world, the message is blunt: stop waiting for rescue. Diversify your sources, automate your own triage, build peer 
networks, and treat metadata as survival gear, not a luxury.

## A slow-motion collapse beneath everyone’s radar

The National Vulnerability Database (NVD) has not exactly been thriving. Since around mid-March 2024, enrichment of 
new CVEs has all but halted—only a fraction of entries have the vital metadata that security professionals rely on: 
CWE designations, CVSS scores, CPE data and the like. Imagine throwing thousands of vulnerabilities over the fence 
without bothering to label them. It is precisely that careless. 
[Data shows](https://www.infosecurity-magazine.com/news/nist-vulnerability-database/) that from 2,700 new CVEs only 
about 200 were actually enriched. [Backlogs have worsened](https://www.infosecurity-magazine.com/news/nvd-revamps-operations-cve-surge/): 
from some 17,000 unprocessed CVEs in August 2024 to a staggering 25,000 by March 2025.

## A resource-starved system gasping for air

You may recall tales of congressional funding. NIST, the agency behind the NVD, has been trying to carry on while 
its lifeline is gradually strangled. The Trump administration’s 2026 budget proposed [slashing \$325 million from 
NIST’s discretionary funds](https://federalnewsnetwork.com/congress/2025/07/nist-to-get-funding-boost-under-house-bill/), 
including particularly nasty cuts to cybersecurity and privacy programmes. 
[It did not go that far](https://www.meritalk.com/articles/house-panel-rejects-nist-cuts-approves-1-28b-budget/).

Beyond NIST, [the broader scientific funding ecosystem has been slashed to ribbons](https://en.wikipedia.org/wiki/Science_policy_of_the_second_Trump_administration). 

## A political posture that says “sorry, not sorry” to science

One gets the sense that maintaining something as dull and foundational as the NVD does not quite fit with the 
Trump ethos of flashy breakthroughs and “economic security.” Indeed, ideological purges—including stripped LGBTQ+, 
climate-related and diversity-linked data, as well as mass scientific firings—have become alarmingly de rigueur. 
Meanwhile, programmes like 
[the US AI Safety Institute (AISI) were all but gutted](https://www.reddit.com/r/neoliberal/comments/1ith08a/us_ai_safety_institute_will_be_gutted_axios/)—think hundreds of roles cut, 
especially those tied to “guardrails” setting the tone for responsible AI.

## Mounting CVE tsunami meets bureaucratic snail pace

If there was ever a classic case of being overwhelmed by one’s own success—or failure, in this case—the NVD provides 
it. CVE submissions surged by about 32 per cent in 2024, only sharpening the contrast between blame-worthy growth 
and severely diminished processing capacity. Security researchers have been raising alarms. One open letter noted 
that only 4,355 of over 10,000 CVEs had been processed—with a mere 245 handled since March 2024. This is not just 
a lag; it is a breakdown [widely seen as threatening national cybersecurity](https://www.reddit.com/r/cybersecurity/comments/1c4q4zv/why_i_signed_an_open_letter_to_congress_on_the/).

## A reluctant sparrow tries to pick up the slack

Enter CISA—the Cybersecurity and Infrastructure Security Agency—[stepping into the void with its “vulnrichment” 
initiative](https://www.reversinglabs.com/blog/cisas-new-vulnrichment-program-attempts-to-address-nvd-slowdown). 
Its analysts are now enriching CVEs with CVSS, CPE, CWE and Known-Exploited-Vulnerability data. 
About 1,300 CVEs have already seen the benefit, thanks to this half-burnt, hero-in-the-making programme

## The bigger picture

Seen in total, this is not about one man’s whim. It is a structural meltdown: underfunding, deprioritisation of 
collaborative science, ideological disdain for anything “not sexy,” combined with a perfectly timed explosion in 
vulnerabilities. The NVD is a plumbing system for cybersecurity; nobody notices until it backs up.

## A playbook for survival in the post-NVD era

The decline of the NVD is not some abstract policy debate. It is an operational hazard. With enrichment stalled, 
backlogs ballooning, and political winds blowing towards anything other than dull public infrastructure, 
organisations need to stop treating the NVD as a lifeline. Below is a survival playbook for those unwilling to bet 
their security on bureaucratic resurrection.

### Diversify your intelligence diet

Depending solely on the NVD today is like trying to eat on nothing but plain crackers. Supplement it with vendor 
advisories, exploit feeds, and sector-based information sharing groups. Vendors like Red Hat, Microsoft, and Cisco 
routinely provide more timely and usable advisories than the NVD. For those with a budget, commercial services such 
as VulnDB, Risk Based Security, and Qualys fill the enrichment gap. For those without, community-driven feeds, 
mailing lists, and even curated GitHub repos provide at least partial relief.

### Automate triage at the edge

Waiting for enriched metadata is a fool’s errand. Build your own enrichment pipelines that link CVEs to your 
software inventory, asset database, and threat intelligence. Open-source tools like `vulners`, `grype`, and `trivy` 
can ingest raw CVE data and perform their own classification. Custom scripts that cross-reference CVEs with your 
installed packages or SBOMs (Software Bills of Materials) will not be as polished as NVD enrichment, but they give 
you usable context. Think of it as rolling your own plumbing when the water company has forgotten how pipes work.

### Use reproducible builds and binary analysis

Attackers exploit the gap between declared vulnerabilities and what actually runs on your systems. Defenders can 
close that gap by [analysing binaries directly](https://red.tymyrddin.dev/docs/through/reverse-engineering/index.html#foraging-for-secrets-in-binaries). 
Tools such as Ghidra, BinDiff, or commercial platforms like ReversingLabs can detect vulnerable code signatures 
without waiting for a CVE to be neatly tagged. [Reproducible builds](https://reproducible-builds.org/) add another 
layer of defence, letting teams verify that what they are running matches what upstream vendors intended—no mystery 
dependencies.

### Participate in peer networks

Cybersecurity has always been a team sport, and when central infrastructure fails, the importance of lateral 
sharing increases. Sectoral ISACs (Information Sharing and Analysis Centers) remain valuable, but informal peer 
groups, industry Slack channels, and trust networks are often faster. Think of it as moving from a centralised 
library to a bazaar where information is traded more chaotically but far more quickly. Ah, we are at the bazaar again. 
One is reminded of the early reuse hype.

### Advocate loudly and unapologetically

The failure of the NVD is not just a technical glitch; it is a policy choice. If defenders want reliable 
infrastructure, they must pressure lawmakers, agencies, and industry bodies to treat vulnerability management as 
critical infrastructure. That means showing up to consultations, submitting testimony, and making noise in 
forums that policymakers cannot ignore. Silence has already delivered us the backlog. Outrage might at least 
slow the decline.

### Build resilience into your playbook

Above all, assume the NVD will not recover quickly. Design processes that can withstand permanent degradation of 
centralised vulnerability services. Bake redundancy into your intelligence pipelines, keep manual triage capacity 
alive, and cultivate a culture that does not confuse “official” with “useful.” The goal is to survive in an ecosystem 
where metadata, once a given, has become a luxury.
