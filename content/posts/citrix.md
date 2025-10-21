---
title: "The Unpatchables: How Citrix turned into a welcome mat"
subtitle: "A case study in why 'update later' is the cybercriminal’s best friend"
description: "When Dutch prosecutors found themselves locked out of their own systems in 2025, it wasn’t due to some cyberweapon. The culprits simply used known Citrix flaws – the digital equivalent of entering through a door marked 'Please Hack Here.'"
draft: false
date: 2025-08-12T00:00:00Z
tags:
  - lazy hacking
  - OopsSec
  - procrastipwned
  - cyberhygiene
  - unpatched peril
  - hackable inertia
  - digital neglect
cover:
  image: "/images/citrix.png"
  alt: "A set of ornate, antique keys floating in midair, each engraved with lines of computer code, with one key glowing red as it is lifted away by an unseen hand." 
  caption: ""
  relative: false
---

In July 2025, the Netherlands faced a crisis that unfolded not in public squares but across invisible networks. The Public Prosecution Service, several courts, and parts of the Ministry of Justice were forced to halt operations. Hearings were postponed, case files became inaccessible, and whole sections of the justice system were brought to a standstill.

The cause was not ransomware flashing on screens or stolen data dumped online. It was the silent exploitation of Citrix NetScaler, a remote-access system used by thousands of organisations to let staff work securely from anywhere. Think of Citrix as a heavily guarded front door to an office: only authorised people can enter, and it keeps prying eyes out. In theory. In July, that door had both a faulty lock and an absent guard.

## How it happened

### The weaknesses exploited

The attackers’ success hinged on two critical security flaws that had been publicly disclosed but not universally fixed.

The first, [CVE-2025-6543](https://nvd.nist.gov/vuln/detail/CVE-2025-6543), was a software vulnerability that allowed an intruder to seize control of a Citrix system remotely. Imagine a locksmith’s error that meant a skeleton key could be shaped from a photograph of the lock.

The second flaw, [CVE-2025-5777](https://nvd.nist.gov/vuln/detail/CVE-2025-5777), became known as Citrix Bleed 2.0. It allowed the theft of “session tokens”, digital passes that prove you are already logged in and therefore do not need to provide your password again. These tokens are what keep you connected to your email or work portal without repeatedly authenticating. In the wrong hands, they work like cloned security badges: they bypass not only passwords, but also two-factor authentication systems designed to stop intruders.

For those interested in understanding how vulnerabilities like these are identified, analysed, and prioritised, see 
[Zero-day threat modelling](https://broomstick.tymyrddin.dev/posts/zero-day-threat-modelling/). It offers a clear guide 
on how defenders assess unknown or newly discovered software flaws before patches are available.

### The attack unfolds

* May 2025 – Security analysts noticed suspicious internet scanning of Citrix systems, later linked to a group with Russian state ties, dubbed [Laundry Bear](https://cybersecuritynews.com/dutch-intelligence-laundry-bear/). This was not a gang of opportunists; it was an outfit with a track record in espionage.
* Early July 2025 – Dutch systems were breached. Using Citrix Bleed 2.0, the attackers harvested live session tokens, slipping into networks as if they were staff.
* Mid July 2025 – The Public Prosecution Service confirmed the breach. Entire systems were shut down to contain it, halting court operations and creating a backlog that would take weeks to clear.

### Inside the breach

With stolen session tokens, the attackers could move through systems without touching a password prompt. From there, they explored, copied data, and likely planted software for later use. Because the network believed they were legitimate users, their movements blended into normal activity.

When the breach was uncovered, they erased logs and other traces, making it difficult to reconstruct exactly what they had accessed or changed.

### Why it worked

Citrix had released patches to fix both flaws, but installing them is rarely instantaneous. Large organisations must schedule, test, and sometimes delay updates to avoid breaking essential systems. Unfortunately, attackers have no such operational constraints.

The real weakness was the delay between knowing about the problem and fixing it. That is the window in which attackers thrive.

While the Dutch breach was a measured, deliberate intrusion, the [CitrixBleed 2.0 vulnerability has affected over 
100 organisations worldwide](https://www.securityweek.com/citrixbleed-2-100-organizations-hacked-thousands-of-instances-still-vulnerable/), with thousands of instances remaining vulnerable months after patches were released. 
This broader picture reveals a systemic issue: delays in applying security updates and a general underestimation of 
risk leave entire sectors exposed. Known vulnerabilities become open doors not only for patient, state-sponsored 
espionage but also for opportunistic criminals. The attack on the justice system was just one high-profile example 
of a widespread and ongoing challenge.

### The wider implications

If the Laundry Bear attribution holds, this was more than a disruptive act, it was a strategic probe. Targeting the justice system of an EU state undermines public trust, clogs the machinery of law, and signals that even core democratic institutions can be quietly stalled. It sends a message to other European states: your critical systems are reachable, and we know where to knock. The attack was a reminder that in modern geopolitics, destabilisation does not require troops on borders. Sometimes, it just requires the right bug in the wrong system.

## Groundhog day for digital security

Security updates are not housekeeping; they are structural repairs. Ignoring them because the timing is awkward is like noticing a crack in a dam wall and deciding to deal with it after the rainy season.

It is also a mistake to think you are too small, too niche, or too important to be targeted. If you have valuable 
data and a connection to the internet, you qualify as prey.

And session tokens are not harmless technical leftovers. Session tokens are crown jewels. Protect them as fiercely as 
your passwords. Weakly implemented tokens have been exploited before, for instance, the 
[Brute-forcing a stay-logged-in cookie](https://red.tymyrddin.dev/docs/in/app/burp/auth/9) 
walkthrough shows how a poorly designed session cookie can be guessed and used to access another user’s account.
The principle is the same: once an attacker holds a valid token, they hold the keys to the building.

## A thought

The Dutch Citrix hack was not a high-speed, cinematic hacking scene. It was a slow, methodical walk through the 
corridors of justice by people who already had the keys.

The technology failed, yes. But the deeper failure was the comfortable belief that known risks can be dealt with later. 
Later is when they are already inside.






 