
---
title: The rise of neural ghosts and AI-driven hijacks
subtitle: "Why the first AI wars will be fought in our inboxes and routers, not in the movies."
tags:
  - AI-powered attacks
  - network security
  - defensive AI
  - malware evolution
  - nation state
  - APT
date: 2025-09-01T04:00:00.000Z
draft: false
---

We are no longer in the age of the lone script kiddie lobbing pre-cooked exploits from their mum’s basement. What is emerging instead are *neural ghosts*, AI-powered entities capable of autonomously probing, adapting, and burrowing into networks. Think of them as digital fungi: self-replicating, invisible, and patient enough to live under your floorboards for years before fruiting. Proof-of-concepts like [Neural Ghost](https://red.tymyrddin.dev/docs/in/network/earthworks/mycosec/neural-ghost) and [FungusFiber ISP hijacks](https://red.tymyrddin.dev/docs/in/network/earthworks/fungusfiber/hijack-isp) already sketch what such systems can become: distributed, stealthy, and frighteningly persistent.

## AI makes attack automation trivial

Attackers will no longer need to hard-code every evasion trick. AI models can learn from network responses, automatically mutate payloads, and improve their lateral movement as if they were playing a strategy game. Early signs are already here:

* Autonomous evasion, adaptive systems that can probe defences, adjust their signatures in flight, and even mimic legitimate traffic, for example in [adaptive evasion techniques](https://red.tymyrddin.dev/docs/in/network/roots/icmp/adaptive-evasion-techniques.html).
* [AI-powered BGP attacks](https://red.tymyrddin.dev/docs/in/network/roots/bgp/ai-powered-bgp-attacks.html), where models analyse routing tables, spot weak points, and launch precision hijacks to intercept global traffic flows.
* Protocol-level infiltration, using reinforcement learning to improve TCP-based attacks and blend with background noise. Examples can be found in [AI-powered TCP attacks](https://red.tymyrddin.dev/docs/in/network/roots/tcp/ai-powered-attacks.html).
* Autonomous campaign systems, swarms of small AI agents coordinating large-scale probing and exploitation without central human oversight. Sketched overview in [autonomous attack systems](https://red.tymyrddin.dev/docs/in/network/roots/icmp/autonomous-attack-systems.html).

The trajectory is obvious: what once required teams of analysts can now be condensed into self-updating playbooks inside a single model.

## Which AI-powered attack waves will hit first?

Not every terrifying scenario will arrive overnight. 

### By capability category

The first attack waves will cluster around where complexity is lowest and payoff is highest:

* AI-aided phishing and social engineering: Minimal coding overhead, just a decent LLM fine-tuned for persuasion. Resources: a cloud account and some creativity. Adversaries: criminal groups and mid-tier states already deploying these. Expect this wave *now*, not “in the future”.
* Autonomous scanning and adaptive evasion, with a moderate complexity. Models need training against IDS/IPS signatures, but open datasets exist. Resource needs are modest, and code is already floating around research repos. Likely adopters: both advanced criminal crews and state actors. Timeline: 1–2 years until commoditised.
* Protocol exploitation (TCP/ICMP mutation, low-level fuzzing): Higher complexity, as models must learn subtle timing and packet-level tricks. Resource needs: solid infrastructure for reinforcement learning. Nation-state labs will likely pioneer this, and when, fragments will trickle down. Timeline: 3–5 years.
* AI-directed BGP manipulation, with a very high complexity. Requires access to BGP-speaking infrastructure, data feeds, and political cover to avoid exposure. Resources: nation-state-scale. Adopters: Russia, China, and Israel are already experimenting with pieces of this puzzle. Timeline: sporadic use in targeted operations within 5 years, mass adoption only by top-tier actors.
* Truly autonomous campaigns (swarms of AI agents): Complexity is extreme. Needs orchestration, distributed decision-making, and stealth management across thousands of nodes. Resources: heavy compute and coordination. Likely only the US, China, and Russia can field these at scale in the next decade. Timeline: 5–10 years, unless someone releases a black-market framework sooner.

In short: expect a flood of AI-boosted low-to-mid complexity attacks within the next two years, and a slow creep of nation-state-grade AI weapons thereafter.

### By network layer/protocol

Likely order of appearance:

1. Adaptive ICMP evasion – simple, cheap, criminal use.
2. Autonomous scanning/exploitation – ransomware, state-aligned groups.
3. AI-driven TCP chaos – hybrid of crime and states.
4. AI-driven BGP hijacks – nation states, cyberwar scenarios.

## The case for AI-powered defences

Defending with yesterday’s playbooks is like bringing a crossword puzzle to a chess match. Static signatures and human-paced incident response will simply not keep up. As attackers lean on machine learning, defenders will need to do the same: anomaly detection that adapts in real time, predictive modelling of attack paths, and autonomous response systems that can counterattack at wire speed.

Even research warns of the feedback loop: as attackers refine autonomous evasion, defenders will need equally adaptive AI to recognise the shifting patterns. Without it, every SOC analyst is just bailing water out of a sinking ship with a teacup.

The coming waves demand proactive, adaptive, AI-supported defences.

* Moving beyond signatures: Signatures fail when every packet can be mutated on the fly. Behavioural, anomaly, and intent-based detection must replace legacy rules.
* AI on AI: The only system fast enough to counter adaptive AI attacks is another adaptive AI system.
* Data, not dashboards: Defence systems must learn from real-time, massive-scale data across multiple environments, not just a local SIEM with stale signatures.
* Human-AI collaboration: Humans cannot out-click machines, but they can provide judgement. Defence will be a hybrid sport.

## What to build first?

Based on which problems will hit first, which will scale fastest, and which will hurt the most if you’re not ready, a shot at priority defences to build first:

The first thing to build is human-layer resilience, because cheap AI-powered phishing is already here. The code is trivial, the models are commoditised, and every script-kiddie with a rented or stolen GPU can now send waves of believable deepfake emails, voice notes, or WhatsApp messages. Defences must start with hardened communications practices like signed messages, verification protocols, and multi-factor authentication. Just as critical are staff and community training sessions that assume perfectly polished lies will land in inboxes. Rapid-response playbooks for “that sounds like my boss” calls could be standard. Fail to prioritise this, and you will be bled dry long before the more sophisticated routing attacks come into play.

The second line of defence could be protocol-layer hygiene. AI-powered fuzzers are already automating ICMP/TCP probing and evasion. The coding complexity is low to medium, meaning what was once the preserve of nation states is quickly becoming democratised. Defence here requires strict patch discipline and aggressive fuzz-testing of your own systems before someone else does it for you. Intrusion detection and prevention systems (IDS/IPS) like Wazuh or Suricata need to be tuned to catch adaptive probing, ideally augmented with ML-based anomaly baselines. Network segmentation also matters: a single malformed packet should not be able to slither its way across your entire infrastructure. Neglect this step, and your systems will become a training ground for hostile AI.

Third, preparing for scanning and swarm automation, where autonomous agents coordinate reconnaissance and attacks at scale, could be next. The orchestration code is more complex, and GPU requirements higher, but once it’s commercialised into crimeware-as-a-service packages, the scale will be staggering. Defences could focus on continuous monitoring with decoy assets such as honeypots to waste attacker cycles. Behavioural analytics must be used to detect coordinated scanning swarms, while rate-limiting and throttling could be applied even to valid-looking inbound requests. Without these measures, your infrastructure risks drowning in background noise while the real intrusions slip by unnoticed.

Finally, BGP and routing manipulation sits at the high end of the spectrum. For now, it remains difficult, resource-intensive, and often requires infrastructure control or insider access. But AI lowers the technical and operational bar, making what was once an elite nation-state capability more accessible. Defences here could include pushing for RPKI adoption and strict route filtering from your upstream providers. Real-time monitoring of BGP anomalies using systems like [RIPE NCC RIS](https://www.ripe.net/analyse/internet-measurements/routing-information-service-ris/), [BGPmon](https://www.bgpmon.net/), or your own collectors is essential. You could also establish out-of-band communications in case your primary routes are hijacked. Fail here, and you risk losing not just data flows, but visibility itself, handing adversaries the high ground.

## Conclusion

The AI arms race in cyber operations has already started. First will come the low-cost, high-impact waves, phishing at scale, adaptive evasion, automated probing. Then, as nation states refine their toolchains, expect the tectonic shifts: AI-directed BGP hijacks, autonomous swarms, and neural ghosts haunting the backbone of the internet itself.

Defenders can either wait to be outpaced or start building their own AI systems now. The window for “humans alone” defence is already closing. 

