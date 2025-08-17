---
title: "Nova's healthcare hack: How a Dutch lab failed half a million patients"
subtitle: "A case study in ransomware, regulatory failure, and the cost of silence"
description: "Analysis of the 2025 Clinical Diagnostics NMDL breach, where cybercriminals stole 300GB of sensitive medical data, exploiting unpatched Citrix systems and GDPR notification delays."
draft: false
date: 2025-08-17T00:00:00Z
tags:   
  - Dutch healthcare
  - Nova ransomware gang  
  - OopsSec
  - cyberhygiene
  - unpatched peril
  - hackable inertia
  - digital neglect
---


In July 2025, the Dutch healthcare sector faced one of its most devastating cybersecurity crises to date. The ransomware group Nova infiltrated Clinical Diagnostics NMDL, a laboratory critical to the Netherlands’ national cervical cancer screening program, exfiltrating 300 GB of sensitive patient data—including names, addresses, citizen service numbers (BSNs), and intimate medical test results 69. The breach, which affected 485,000 women and extended to other medical examinations, exposed systemic vulnerabilities in healthcare IT infrastructure, third-party risk management, and regulatory compliance.

---

## How Nova got in

In early July 2025, between the 3rd and the 6th, cybercriminals from the ransomware gang Nova infiltrated the IT systems of Clinical Diagnostics NMDL, a laboratory in Rijswijk handling cervical-smear and self-test processing for the Dutch national screening programme (Bevolkingsonderzoek Nederland, BDO).

At present, the Dutch National Cyber Security Centre (NCSC) hints at involvement of a Citrix NetScaler memory-overflow vulnerability ([CVE-2025-6543](https://nvd.nist.gov/vuln/detail/CVE-2025-6543)), which was publicly disclosed in May and may have been exploited in this case. But the lab had not publicly confirmed that this was the attack vector.

Once inside, Nova extracted a staggering 300 GB of highly sensitive data—ranging from names, addresses, dates of birth and citizen service numbers to test results and healthcare provider details. They then leaked around 100 MB of that trove—covering approximately 53,000 individuals—on the dark web to prove their seriousness.

The breach extended beyond cervical cancer data, affecting test results from skin, urine and genital examinations, as well as data from LUMC, Amphia and Alrijne hospitals dating back to 2022.

---

## The legal mess

### Late notification

Clinical Diagnostics discovered the breach on 6 July but did not inform BDO (the data controller) until 6 August—a full month later—delaying notification by weeks instead of the GDPR-mandated 72 hours. BDO itself then informed the Dutch Data Protection Authority (AP).

### Ransom payment and secrecy

Reports indicate that Clinical Diagnostics paid a multi-million-euro ransom to Nova in hopes of preventing further leaks—an admission the lab would not openly confirm, though indirect hints suggest as much.

### Regulatory inquiry and possible penalties

The Autoriteit Persoonsgegevens (AP) has launched an investigation to determine whether the lab violated GDPR rules around timely breach notification and damage mitigation. Under Article 33, breaches must be reported within 72 hours; under Article 34, affected individuals must be informed “without undue delay.” Late notification may afford fines up to €20 million or 4 % of global turnover.

Worryingly, some of those affected were residents of women’s shelters, exposing vulnerable individuals to heightened risk—an oversight that only adds to the disaster.

---

## How healthcare systems can stop repeating this clown show

It is rarely clever to wait for half a million breaches before acting. Let's spell out the bare minimum:

### Patch the basics—promptly

Equipment like Citrix gateways, VPNs and other internet-facing infrastructure must be patched promptly. The Citrix CVE-2025-6543 patch was published in May; by July, evidence of exploitation was already on the table. If your systems are still ticking away on legacy software, expect to hear about it in the papers.

### Secure supply chains

Outsourcing is not a free pass. BDO’s data passed through a subcontracted lab, a single weak link that compromised half a million records. Ensure that all partners meet stringent cybersecurity standards, with audits, penetration tests and shared security protocols.

### Encrypt everything—by default

Data at rest and in transit must be encrypted. Holding years of data—some legally irrelevant—without proper encryption is not prudent; it is negligence.

### Monitor like your reputation depends on it

If 300 GB of data exfiltrates undetected, your logging and monitoring are embarrassingly feeble. Deploy SIEM systems, anomaly detection, honeytokens—anything that alarms when the front door gets pick-pocketed.

### Restore from backups that criminals cannot reach

Backups must be isolated and tested, not just left on the same network behind the same firewall. Relying on backups that attackers can easily tamper with is what happens when someone copies the thief’s keys.

### Train for scams, not just protocols

Social engineering remains a favourite bypass for the tech-literates. Staff must be trained to spot phishing, AI-driven scams and voice-spoofing. As one cybersecurity analyst noted after the breach, healthcare remains “a prime target because the data is priceless, the networks are complex, and the sector is under constant pressure to deliver more with less”.

### Use ethical hacking

Invite honest testers—white-hat hackers—to probe your systems. An independent check is worth far more than discovering your flaws via publication—or worse, ransom notes.

### And for goodness’ sake, no hush money

Paying ransom only signals weakness. Even if the data disappears for now, the criminals still have it and may resurface. Transparency—alongside immediate notification—is mandatory.

---

## What happens next

### Regulatory hammer

The Dutch Data Protection Authority (AP) has already opened its investigation. Expect:

* Fines: Under GDPR, NMDL (via Eurofins) could face a penalty up to €20 million or 4% of global turnover. Eurofins earns billions globally, so the upper end is technically in play. Realistically, AP will weigh proportionality—but given the egregious month-long silence, expect something significant. A “symbolic slap” would cause political uproar.
* Binding orders: AP can mandate corrective measures—forcing Eurofins to overhaul its security posture, shorten data retention, and subject itself to third-party audits. Think of it as enforced homework, graded by regulators.

### Political theatre

The Dutch parliament will almost certainly haul ministers and BDO executives into hearings. Health IT failures make excellent televised outrage. Questions will focus on:

* Why was outsourcing to a single weak link allowed?
* Why were notifications so disastrously late?
* Why were vulnerable groups (such as women in shelters) not given extra safeguards?

Expect new promises of “lessons learned” and possibly rushed legislation tightening requirements for subcontractors in national health programmes.

### Class actions and civil claims

Dutch law allows individuals to sue for damages caused by mishandling personal data. With half a million people affected, class-action style suits are already brewing. Law firms will argue that reputational harm, stress, and risk of identity theft constitute “immaterial damage” under GDPR, entitling compensation. Even modest payouts per person would add up to eye-watering sums.

### International knock-on effects

Because Eurofins operates across Europe and beyond, regulators in other countries will scrutinise their local operations. If your lab partner is Eurofins, you may soon face “prove you are not next” conversations. Cross-border cooperation under GDPR’s one-stop-shop mechanism will drag this into EU-wide headlines.

### Criminal posturing

Nova will continue leaking data in chunks to maintain pressure. They will parade their “success” on dark-web forums to boost reputation and recruitment. Other gangs will take note that Dutch healthcare pays, which increases the risk of repeat targeting unless deterrence improves.

### Industry reaction

Hospitals and labs will scramble for cyber insurance, though premiums will spike. Expect a wave of “urgent audits” and half-hearted patch sprints. Consultancies will feast on post-mortems. Sadly, many will file the incident under “exceptional” until the next breach repeats the same pattern.

### Patients

For the women and men whose data is already circulating, the consequences are long-tail:

* Spam and scams using personal details.
* Identity theft via BSN (citizen service number) leakage.
* Humiliation risks if medical details are abused for doxxing.
  The government will be pressed to fund monitoring or protective services (credit checks, new BSNs, support for vulnerable individuals). Whether it actually delivers meaningful protection is another matter.

---

## Forecast in one line

Unless regulators make an example of Eurofins with a fine large enough to sting, healthcare will treat this as another 
embarrassing “incident” rather than a turning point. The clown show will be rescheduled in five years’ time—same tent, 
same tricks, just different patients.

---

## What you can do right now

By this point you may be wondering: fine, Nova got in, lawyers are sharpening their knives, and healthcare needs a crash course in 21st-century security hygiene—but what about me? Can I check if my information is floating around somewhere it should not?

The short answer: not yet. Bevolkingsonderzoek Nederland (BDO NL), which runs the cervical cancer screening programme, has chosen the old-fashioned route of sending letters to everyone whose data was exposed. There is no online lookup service, and for good reason—turning medical records into a searchable website would be handing burglars a master key.

So, for now, your job is to watch the post. If you participated in the screening programme between 2022 and July 2025, assume your details might have been caught in the breach until you either receive a letter or official reassurance that you are in the clear.

And yes—if a letter lands on your doormat confirming that you were in the breach, you are not powerless. Under GDPR you can claim compensation if mishandling of your data caused you damage, whether financial loss or the less tangible—but very real—stress and anxiety of knowing strangers have your medical details. Dutch courts have already set precedents here. Whether you join a collective action or sue individually, the option is open.

If lawsuits start piling up, private mucho-money-making healthcare providers may finally take data protection seriously, not out of ethics but out of fear of paying damages.

While waiting for snailmail, a few defensive manoeuvres are wise:

* Stay alert for scams: Phishing emails, texts, or calls that refer to your medical results or citizen service number (BSN) should be treated with extreme suspicion.
* Check your financial life: Keep an eye on bank accounts, credit alerts, or any unusual requests tied to your BSN.
* Verify before you trust: If someone contacts you claiming to be from a health service, pause and confirm through official channels before handing over anything.
* Ask if you are unsure: If you never receive a letter but are losing sleep over it, call BDO NL or speak with authorities to get clarity on your status.

It is not elegant, but it is practical. Until the legal smoke clears and the health sector actually learns from this fiasco, vigilance at the individual level is the best defence we have.

---

## Resources

* [Hackers breach cancer screening data of almost 500,000 women](https://www.digitalhealth.net/2025/08/hackers-breach-cancer-screening-data-of-almost-500000-women/)
* [Data Theft From Dutch Cancer Screening Lab Affects 485,000](https://www.bankinfosecurity.com/data-theft-from-dutch-cancer-screening-lab-affects-485000-a-29199)
* [Data breach at Dutch medical laboratory much larger than expected](https://www.techzine.eu/news/security/133713/data-breach-affects-dutch-485000-cervical-cancer-screening-participants/)
* [Lab paid off hackers who stole thousands of patients’ data: RTL](https://www.dutchnews.nl/2025/08/lab-paid-off-hackers-who-stole-thousands-of-patients-data-rtl/)
* [Privacy watchdog AP to start probe into clinic data breach](https://www.dutchnews.nl/2025/08/privacy-watchdog-ap-to-start-probe-into-clinic-data-breach/)
* [Dutch lab paid millions in ransom, but some data appeared online](https://www.techzine.eu/news/security/133780/dutch-lab-paid-millions-in-ransom-but-some-data-appeared-online/)
* [Hackers say Dutch lab paid ransom for stolen data; Laboratory won't confirm](https://nltimes.nl/2025/08/13/hackers-say-dutch-lab-paid-ransom-stolen-data-laboratory-wont-confirm)

