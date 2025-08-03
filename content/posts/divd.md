---
title: "Tidying the loose ends before the whole thing unravels"
date: 2025-08-03
subtitle: "A dive into the Dutch Institute for Vulnerability Disclosure’s proactive cybersecurity efforts."
tags:
  - cybersecurity
  - vulnerability disclosure
  - DIVD
  - Netherlands
  - responsible disclosure
  - digital security
draft: false
cover:
  image: "/images/divd.png"
  alt: "An enormous, intricate tapestry hanging on a wall, with lots of loose threads dangling, a person on a ladder sewing them back in, lots of bright golden yellow, Renaissance-inspired realism, ornate patterns, dramatic chiaroscuro lighting" 
  caption: ""
  relative: false 
---

In the spring of 2021, Dutch Institute for Vulnerability Disclosure (DIVD) researcher Wietse Boonstra quietly [uncovered seven critical flaws in Kaseya’s widely used IT management software](https://techxplore.com/news/2023-10-dutch-municipalities-adequately-vulnerabilities.html). DIVD warned the company within days, flagging more than 2,200 vulnerable systems across the globe. Weeks later, three flaws remained unpatched—and the REvil ransomware gang pounced. Overnight, some 1,500 organisations were paralysed, from supermarkets in Sweden to schools in New Zealand.

This was not an isolated close call. In a 2023 study with the University of Twente, DIVD found that [less than half of Dutch municipalities acted promptly when notified of exploitable flaws in their email systems](https://techxplore.com/news/2023-10-dutch-municipalities-adequately-vulnerabilities.html). In some cases, local authorities ignored the warnings entirely.

DIVD is in the business of making sure those warnings get heard—and acted on. They do it through a mix of detective work, diplomacy, and relentless follow‑up. When a scan flags a vulnerable system, a researcher confirms the risk, traces it to the responsible party, and contacts them directly—sometimes through technical staff, sometimes through executives, and, if needed, through national bodies like NCSC‑NL. For those who respond, DIVD provides remediation steps, links to vendor patches, and guidance until the fix is verified. For those who do not, they escalate—via hosting providers, industry partners, or, in extreme cases, public advisories. It is less “find and shout” and more “find, guide, and push until it’s fixed.”

## The DIVD model: Research‑driven prevention

DIVD’s process is designed for maximum impact with minimal fuss. First, the team scans broadly for exposed systems and known vulnerabilities, relying on a combination of automated tools and manual research. Once a potential issue is identified, they verify whether it is truly exploitable and urgent enough to warrant immediate attention. Next, DIVD reaches out directly to the affected party, whether that is a small business, a public institution, or a vendor, providing clear and actionable details about the vulnerability. Finally, they support remediation efforts by sharing guidance, linking to vendor patches, and, where appropriate, collaborating with national bodies like the NCSC‑NL to ensure the problem is fixed promptly and correctly.

For example, in the case of [DIVD‑2022‑00055](https://csirt.divd.nl/cases/DIVD-2022-00055), the team discovered numerous insecure server management interfaces worldwide. Before vendor patches were even available, DIVD proactively notified system administrators and advised isolating these interfaces behind bastion hosts or VPNs to reduce risk. This approach of combining detection with practical remediation guidance is typical of DIVD’s work and underscores their commitment to preventing breaches rather than simply documenting them.

---

## Ripple effects of responsible disclosure

The Kaseya case illustrates what is at stake when vulnerabilities are left unpatched: an entire software supply chain can be compromised, affecting thousands of downstream businesses in one strike. For smaller companies, especially SMEs without dedicated cybersecurity staff, a DIVD alert can mean the difference between a routine patch cycle and a multi‑week operational shutdown.

For security researchers, DIVD provides a legal and structured path for reporting vulnerabilities, avoiding the risk of prosecution or reputational harm that can accompany independent disclosure. This safe channel not only protects the researcher but ensures the vulnerability is handled responsibly.

For society, DIVD’s work safeguards critical infrastructure—hospitals, utilities, financial systems, and local government—against large‑scale disruption. The municipal email vulnerability research revealed that poor incident response processes are not just theoretical problems; they are active weaknesses that could be exploited to spread disinformation or conduct targeted scams.

---

## Challenges & opportunities: scaling the impact

Awareness remains one of DIVD’s biggest challenges. Many organisations still do not realise they can engage DIVD proactively, whether by inviting scans or by setting up formal reporting channels. Even when vulnerabilities are reported, the municipal study shows that response is inconsistent—over half of municipalities lacked a publicly documented Coordinated Vulnerability Disclosure (CVD) process at the time of testing.

Funding is another constraint. DIVD is volunteer‑driven and operates with the support of donations and sponsorships. Limited resources mean fewer scans, slower follow‑up, and reduced capacity to investigate global-scale issues like the Kaseya flaws. The question remains: what could be prevented if every Dutch organisation had both the awareness and the means to work with DIVD before incidents occur?

---

## How you can help amplify DIVD's work: a call to action

If you work in an organisation, you can start by inviting DIVD to scan your systems and by committing funds to sustain their work. Proactive security checks cost far less than breach recovery, both in money and reputation.

If you are a researcher, you can contribute by submitting vulnerabilities via DIVD rather than going it alone. Their structured disclosure process will protect both your findings and your professional standing.

If you are a citizen, you can raise awareness by sharing verified case studies like the Kaseya incident or the municipal research project. You can also advocate for government policies that require all public bodies to maintain functional CVD processes, in line with the upcoming NIS2 directive.

---

## Security is a shared responsibility

Cybersecurity is no longer a niche technical concern; it is part of the civic infrastructure that keeps services running and trust intact. From global ransomware events to municipal email spoofing risks, the pattern is clear: vulnerabilities will be found—either by ethical researchers or by criminals. DIVD focuses on the former, and on pushing those warnings to lead to action.

Act now: visit [divd.nl](https://www.divd.nl/) to report a vulnerability, partner with their team, or donate. Share this article and start a conversation—because security works best when everyone plays their part.
