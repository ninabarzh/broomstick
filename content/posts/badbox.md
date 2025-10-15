---
title: 'BadBox 2.0: When devices spy straight out of the box'
subtitle: "Even brand-new tablets and TVs can come preloaded with malware. Why that matters, especially in IPA support work — and how to spot the risk."
date: 2025-06-08T00:00:00.000Z
draft: false
tags: 
  - IPA
  - digital safety
  - supply chain threats
  - badbox
  - security
  - malware
---

You’ve spotted a cheap Android tablet or TV box online, taken by how cheap it looks—until you plug it in. Now, interred in its firmware, there’s malware. Not something you can remove, because it's buried beneath the operating system.

This is **BadBox**: a class of threats embedded in devices at the factory or during shipping. It isn’t just an app you can delete; it's pre-installed, hidden in the firmware, and ready to phone home as soon as the device connects to the internet.

---

## What is BadBox, really?

BadBox isn’t a single mystery app but a poisoning of the device supply chain. Anxiously cheap devices—like tablets, Android TV boxes, routers and even children’s tablets—leave the factory already compromised. As soon as you power them up, they begin connecting to remote servers run by threat actors.

These compromised devices are used for fraud, stolen data collection, installing more malware, account hijacking, and even turning your device into a proxy for cybercriminal activity.

---

## Why should survivors and advocates care?

For services working with survivors of [intimate partner abuse (IPA)](https://blue.tymyrddin.dev/docs/ipa/)), this 
isn’t abstract tech horror—it’s a real-world threat. Off‑brand devices donated to shelters, community centres, or 
survivors may be unknowingly infected. Once in the wild, they morph from helpful tools into surveillance nodes, 
privacy risks or entry points for further exploitation.

---

## Signs a device could be infected

Detecting a BadBox-infected device isn’t easy, because it survives factory resets and isn’t visible to antivirus. Some red flags include:

* The battery or data usage is unusually high even when idle.
* Pre‑installed apps can’t be uninstalled or disabled.
* The device behaves strangely or feels sluggish right from the start.
* It connects to obscure servers or IPs as soon as it goes online.

Network‑aware IT teams using tools like Pi-hole, DNS logging or firewall analysis may pick up unusual connections. But most users won’t notice — and that’s exactly why it matters.

---

## What has research uncovered?

In October 2023, Human Security’s Satori team first uncovered at least 74,000 infected devices, including Android 
phones, tablets and TV boxes—all based on variations of the Triada backdoor. By December, a Bitsight report detailed 
a botnet of over 190,000 Android devices, including smart TVs and smartphones, active across Russia, China, India, 
Belarus, Brazil, and Ukraine. In March 2025, researchers confirmed that BadBox 2.0 had spread to roughly 
**one million** devices globally, including tablets, projectors, and infotainment systems. Most alarming of all: 
the compromises weren’t confined to ultra-cheap devices — high-end models like Yandex smart TVs and Hisense 
smartphones were also affected.

Germany’s security agency even sinkholed BadBox servers tied to 30,000 compromised devices in late 2024.

---

## What you can do

If you're distributing devices to survivors or low-income groups, avoid off-brand hardware from grey‑market 
retailers such as eBay, AliExpress, or cheap listings on Amazon. Instead, buy from recognised brands with 
genuine firmware and valid Google Play Protect certification. Even so, admit that firmware-level supply chain 
attacks are fiendishly hard to avoid completely.

If you must use lower-cost or older devices, always isolate them. Do not store personal data or log into sensitive 
accounts on these. Connect them to separate guest or air‑gapped networks to limit potential damage.

For organisations: ask your tech supplier where the devices come from. If possible, run them through network 
analysis tools. When in doubt, treat compromised devices like contaminated equipment.

---

## Resources

* Trojans All the Way Down (Human Security, BadBox 1.0 & Peachpit) https://www.humansecurity.com/wp-content/themes/human/hubspot/hubfs/HUMAN_Report_BADBOX-and-PEACHPIT.pdf
* Bitsight report on pre-installed malware and BadBox botnets https://www.bitsight.com/blog/badbox-botnet-back
* 1 Million Third-Party Android Devices Have a Secret Backdoor for Scammers (Wired) https://www.wired.com/story/1-million-third-party-android-devices-badbox-2
* Your Cheap Android TV Streaming Box May Have a Dangerous Backdoor (Wired) https://www.wired.com/story/android-tv-streaming-boxes-china-backdoor
* Dataconomy: BadBox 2.0 affects 1 million Android devices https://dataconomy.com/2025/03/07/badbox-2-0-malware-is-infecting-a-million-android-devices-right-now/
* Germany reports 1 Million BadBox-infected devices (Heise) https://www.heise.de/news/Badbox-2-0-Eine-Million-infizierte-Geraete-im-Botnet-10327338.html
