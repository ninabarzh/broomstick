---
title: "Governmental backdoors: skeleton keys and fairy tales"
subtitle: "How states demand the impossible and leave ordinary users exposed"
description: "A satirical exploration of government backdoors, tracing their history, failures, and consequences for everyday users."
tags: ["security", "privacy", "encryption", "government surveillance", "satire", "backdoors"]
draft: false
date: 2025-09-09
cover:
  image: "/images/granny.png"
  alt: "Granny Weatherwax, clad in a long, woven black dress and pointy hat, grasping the Sceptre of Omnicide"
  caption: ""
  relative: false 
---

The trouble with governments and cryptography is that they keep mistaking mathematics for magic. In Ankh-Morpork, this was the sort of thinking that once led the Wizards of Unseen University to try and regulate gravity, on the grounds that it was “inconvenient.” It ended, inevitably, in bruises.

In our world, the same logic has produced the noble invention of the “government backdoor.” A handy hole in the wall of your digital house, through which the Watch can come and go as it pleases. The Watch insists it will *only* use this hole to catch thieves and murderers. Unfortunately, thieves and murderers are rather good at using holes too.

## The history: or, how to fail repeatedly with great determination

The Americans, bless them, once dreamt up the [Clipper Chip](https://www.cryptomuseum.com/crypto/usa/clipper.htm). 
It was a cunning plan, cunning in the sense used by Baldrick, to give every device a magic crystal that would encrypt your 
secrets, but with a spare key kept safely in the hands of the government. Which is to say: the key was kept in a 
box labelled “Please Steal Me” with a helpful map. The chip failed, because mathematics, unlike politicians, does 
not negotiate.

They followed this with [CALEA](https://techcrunch.com/2024/10/07/the-30-year-old-internet-backdoor-law-that-came-back-to-bite/), 
which mandated that all telecoms equipment be built with surveillance hooks. This is like legislating that every door 
must have a cat flap, because occasionally the fire brigade might want to crawl through. Naturally, burglars were 
delighted.

Then came [PRISM](https://www.eff.org/deeplinks/2013/06/what-we-need-to-know-about-prism) and 
[BULLRUN](https://www.eff.org/deeplinks/2013/09/crucial-unanswered-questions-about-nsa-bullrun-program), which sound 
less like surveillance programs and more like pub quiz teams. They would win every round, except the one on “ethics.” 
These provided intelligence agencies with convenient ways to collect *all the information, everywhere, all the time.*

Not to be left out, the United Kingdom brought forth the 
[Investigatory Powers Act](https://www.theregister.com/2016/12/06/parallel_construction_lies_in_english_courts/), 
a law so broad it practically gave the postman authority to read your diary. France proposed [inserting “ghosts” 
into encrypted chats](https://www.eff.org/deeplinks/2025/03/win-encryption-france-rejects-backdoor-mandate), because 
nothing says “liberty” quite like a state-sponsored invisible friend. Meanwhile, Russia and China skipped the 
euphemisms and built enormous surveillance machines with names like [SORM](https://citizenlab.ca/?s=SORM) and 
[Golden Shield Project](https://www.wired.com/2008/05/leaked-cisco-do/), which is a little like calling your torture 
chamber the “Happy Fun Hut.”

## The hypocrisy: good backdoors, bad backdoors

Governments assure us that these keys are only for serious matters: terrorism, paedophilia, organised crime. Lovely 
words. Meanwhile, history shows a strong preference for using them on 
[civil rights leaders](https://www.lib.berkeley.edu/about/news/fbi), on 
[economic rivals (economic espionage)](https://en.wikipedia.org/wiki/Global_surveillance_disclosures_%282013%E2%80%93present%29#Economic_espionage), 
and occasionally [their own citizens](https://www.socialistalternative.org/no-to-bushs-war-on-iraq/cointelpro-the-fbis-secret-war-on-the-civil-rights-movement/) when they become inconvenient.

And here is the kicker: criminals are not stupid. They download perfectly robust encryption software from the internet, 
beyond the reach of legislation, and carry on. The only people who end up using the weakened systems are ordinary 
folk—people like you and me—who then get robbed, hacked, and spied on with cheerful efficiency.

It is as if the Patrician of Ankh-Morpork insisted that every lock in the city be built with a master key, while 
every actual thief simply used their own private locks and laughed.

## The laws of mathematics (unimpressed by Parliament)

Mathematics is rather unlike politics. It does not do compromise. You cannot have “strong encryption with a 
responsible backdoor,” any more than you can have “a watertight bucket with a small hole for emergencies.” 
Every serious cryptographer has pointed this out repeatedly, and governments have responded by nodding sagely 
and commissioning yet another doomed scheme.

The Clipper Chip failed. CALEA weakened infrastructure. 
[Apple refused the FBI](https://www.theguardian.com/technology/2016/feb/17/inside-the-fbis-encryption-battle-with-apple), 
each time, the backers muttered darkly about “national security,” and each time reality intervened with the subtlety 
of a falling piano."

## Implications for ordinary people (that is, you and me)

What does all this mean for the person reading this on a phone, hoping the battery lasts the day? Quite a lot. 
Your banking app, your medical portal, your family WhatsApp group—they all rely on encryption. Introduce a backdoor, 
and you may as well post your credit card number on the office noticeboard.

When [China was caught](https://www.reuters.com/world/china/china-exploited-backdoors-us-firms-2024-05-14/) 
exploiting backdoors to snoop on communications, it was not a shocking revelation. It was Tuesday. Backdoors 
are like leaving your front door ajar with a sign saying “burglars, please knock.”

The social consequences are worse. Backdoors are a tyrant’s dream. They turn private life into public property, 
dissent into evidence, and everyone into suspects. And before you insist that “our democracy would never do that,” 
remember how anti-terror laws have been cheerfully applied to 
[stop and search in the UK](https://www.hrw.org/report/2010/07/04/without-suspicion/stop-and-search-under-terrorism-act-2000) and other bureaucratic 
delights. Or like the 
[US PATRIOT Act’s “roving wiretap” provision](https://www.justice.gov/archive/ll/highlights.htm)—intended for 
tracking terrorism suspects—has been used in ordinary financial crimes, including tax fraud investigations. 
The Department of Justice confirms how these powers have crossed into non-terrorist territory. As for the EU, well, 
it has [more loopholes than a wizard’s sock](https://www.amnesty.org/en/latest/press-release/2017/01/eu-orwellian-counter-terrorism-laws-stripping-rights-under-guise-of-defending-them/). 
Misuse of emergency powers has been recorded in several EU member countries.

It is a classic playbook: (claim to) build a tool for extreme circumstances, then use it for everyday administration. 
Once the authority is established, it’s a rubber stamp away from being re-hired for auditing.

***Once the mechanism exists, it will be used, said Veterinari.***

## The bottom line: skeleton keys and fairy tales

The “secure backdoor” belongs in the same category as unicorns, perpetual motion, and politicians who answer 
questions directly. Every attempt to create one has collapsed in failure, scandal, or ridicule. And every 
attempt has left ordinary citizens less safe, while the powerful acquire more levers of control.

If governments genuinely wanted to protect their people, they would invest in secure systems, education, and 
resilience. Instead, they persist in demanding skeleton keys, apparently believing that only *they* will use them. 
This is like giving Granny Weatherwax the Sceptre of Omnicide and asking her to “only use it when absolutely necessary.” 
Possible, perhaps, but not exactly comforting.

The truth is simple: encryption without exceptions is the last defence between citizens and chaos. Undermine it, 
and you are not protecting anyone. You are handing burglars the crown jewels and asking politely that they return 
them later.
