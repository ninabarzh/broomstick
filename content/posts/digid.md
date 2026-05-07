---
title: "DigiD and the rented engine room"
date: 2026-05-07
draft: false
description: "Solvinity operates the infrastructure underneath DigiD, Kyndryl looks set to acquire Solvinity, and European digital sovereignty keeps colliding with procurement reality."
tags:
  - digital sovereignty
  - DigiD
  - Netherlands
  - infrastructure
  - EU
---

The story is, on paper, narrow. Solvinity, the Dutch contractor that operates infrastructure underneath Logius and
DigiD, looks set to be acquired by Kyndryl, an American spin-off of IBM's managed-services arm. DigiD itself remains
owned by the Dutch state via Logius, so technically the system is still Dutch. Politically and operationally, the
distinction does not calm many people down.

A rented engine room is still part of the ship.

Across Europe there has been a push for "digital sovereignty", meaning less dependency on American hyperscalers and
infrastructure providers after years of quietly outsourcing half the state to Silicon Valley with the serene confidence
of a man juggling chainsaws because the first three catches worked out fine.

Governments spent decades optimising for lowest cost, outsourcing, scalability, procurement convenience, and "the market will solve it".

Digital sovereignty, in that period, was treated mostly as a philosophical hobby for slightly anxious cryptographers and
one Dutch professor with concerning amounts of coffee.

Then geopolitics changed faster than procurement cycles.

## Dependency and the US angle

The concern is not that Americans individually are evil masterminds twirling ethernet cables. The concern is
jurisdiction and leverage.

If infrastructure is operated by a US-headquartered company, several things potentially enter the picture.

### US CLOUD Act

The US CLOUD Act, passed in 2018, amended the Stored Communications Act so US authorities can compel disclosure from US
providers regardless of where the data physically sits. The trigger is “possession, custody, or control”, and corporate
control is enough: an order served on [Kyndryl](https://www.kyndryl.com) in New York can reach
data its staff can access in a Dutch datacentre.

Such orders commonly arrive with gag provisions attached. Providers can
challenge them through a comity process, but that only functions properly when the foreign state has a CLOUD Act
executive agreement. The UK has one. The Netherlands does not. That leaves no formal mechanism
for [Logius](https://www.logius.nl),
the [Autoriteit Persoonsgegevens](https://www.autoriteitpersoonsgegevens.nl), or the Dutch
government to be informed, contest the order, or even know disclosure occurred.

The risk is not wholesale extraction of
DigiD. It is targeted access to records, logs, or metadata without Dutch visibility. See
the [US CLOUD Act text](https://www.congress.gov/bill/115th-congress/house-bill/4943).

### FISA

Foreign Intelligence Surveillance Act operates in parallel on the intelligence side. Section 702 allows the US
government to compel providers to assist with surveillance targeting non-US persons abroad through classified FISA Court
proceedings.

The 2024 RISAA reforms broadened the definition of covered providers significantly, potentially including
firms with routine access to communications infrastructure. Authentication telemetry, session metadata, and
account-linkage records all sit on systems companies like Kyndryl may maintain. Unlike ordinary gag orders, the
existence of a FISA directive itself can remain classified.

There is no Dutch judicial review or parliamentary
visibility. This is the scenario Dutch MPs gesture toward when warning about the US “pulling the plug”, though “plug” is
the wrong metaphor. It is closer to a tap nobody is allowed to mention. See
the [EFF overview of FISA 702](https://www.eff.org/issues/nsa-spying/section-702).

### Sanctions pressure

Sanctions pressure works differently. Through Office of Foreign Assets Control, US firms face major legal and financial
exposure if they facilitate prohibited transactions.

The result is often over-compliance: restrictions appear before
direct orders do. After 2022, firms like [Microsoft](https://www.microsoft.com)
and [Amazon Web Services](https://aws.amazon.com) restricted services in Russia under sanctions
pressure.

In DigiD’s case, the concern is not that “the US disables Dutch citizens”. It is that operational decisions
inside a Dutch civic identity system begin reflecting US sanctions logic because the operator cannot afford not to
comply. The Dutch state then discovers the restriction through support escalation rather than treaty process.

### Geopolitical coercion

Geopolitical coercion is softer, and historically more common. It does not require warrants or classified directives. It
works through tariffs, export controls, intelligence-sharing leverage, procurement pressure, and market access. 

The
current US administration has shown willingness to apply such pressure to allies over disputes involving trade, defence
posture, and international institutions. In infrastructure terms, the mechanism is conditional cooperation: support
tickets slow down, updates arrive later, renewals gain awkward clauses, priorities quietly shift elsewhere. 

None of this
has to be illegal, and little of it leaves a clean audit trail. The autonomy loss sits upstream of the technology
itself. Dutch policy decisions on unrelated geopolitical questions begin carrying implicit operational costs in the
civic identity layer.

### Corporate dependency risks and operational lock-in

Corporate dependency and operational lock-in deepen all of the
above. [Kyndryl](https://www.kyndryl.com) is a US-listed services firm operating under
shareholder pressure. It can restructure, cut staff, reprioritise sectors, or increase prices once switching costs
become painful. 

Meanwhile, the technical environment grows harder to leave each year: tooling, monitoring, deployment
pipelines, certifications, and institutional knowledge become tightly coupled to the operator. Migration stops being a
procurement exercise and turns into a multi-year engineering programme. Dependency compounds over time. Each renewal
narrows Dutch leverage while widening the gap between European “digital sovereignty” rhetoric and the infrastructure
reality underneath it.

[Experts, MPs, and senior privacy officials linked to the Dutch government have publicly warned about all of
this](https://www.dutchnews.nl/2026/04/digid-takeover-by-us-firm-is-a-security-risk-top-official-says/).

Several Dutch MPs warned about a scenario where the US
could "[pull the plug" on DigiD](https://nltimes.nl/2026/04/22/parliament-wants-govt-take-digid-away-solvinity-us-takeover-happens).

Whether that exact scenario is technically realistic in a dramatic Hollywood sense is debated. Governments tend to
present these systems as segmented, controlled, encrypted, and sovereign. [DigiD itself does remain owned by the Dutch
state](https://www.digid.nl/en/solvinity).

But infrastructure dependence is rarely binary. Modern dependency tends to appear in the form of support contracts,
specialised operational knowledge, supply chain access, privileged maintenance channels, proprietary tooling, and
emergency response dependence.

Infrastructure control is less "off switch" and more "you now need permission, updates, expertise, licences,
cooperation, and legal alignment from another jurisdiction".

Strategically, that lands rather differently.

## Can citizens refuse DigiD

In practice, mostly no.

Dutch residents can sometimes avoid DigiD for specific interactions by using physical appointments, paper forms, or
alternative authentication methods. But many government and semi-public services increasingly assume DigiD
participation.

The structural picture is:

- DigiD is becoming functionally mandatory
- participation in society increasingly depends on it
- there is no fully equivalent citizen-controlled alternative

That creates a democratic tension. People are effectively compelled into a centralised digital identity ecosystem while
having very little influence over procurement, hosting, jurisdiction, or architecture decisions.

A [recent survey](https://www.iamexpat.nl/expat-info/dutch-news/87-dutch-residents-would-stop-using-digid-if-us-takeover-goes-through)
found that many Dutch residents would stop using DigiD if the takeover proceeds, while most also admitted they cannot
realistically function without it.

Which is modern digital governance in one sentence: you are free to opt out, provided you also opt out of existence.

## What else this surfaces

Beyond privacy, there are broader structural issues.

### National resilience

Critical infrastructure increasingly depends on foreign firms across cloud, identity, email, productivity suites, DNS,
hosting, and cyber defence tooling. DigiD is not isolated; it sits inside a wider European dependency stack.

One dependency is manageable. Twenty interconnected ones start to look like strategic vulnerability.

### Legal opacity

Cross-border jurisdiction gets murky fast. Which law prevails during conflict? Who audits access? What secrecy
obligations exist? Can Dutch authorities even know about foreign access requests?

This is one reason [privacy groups and academics have been asking for transparency about the review
process](https://www.universiteitleiden.nl/en/in-the-media/2026/01/experts-call-for-openness-on-digid-sale-to-us-tech-company).

### Democratic accountability

Citizens can vote out ministers. They cannot vote out multinational infrastructure providers.

Once critical systems are deeply outsourced, accountability tends to fragment. Government blames contractor. Contractor
blames legal obligations. Regulator says "not our competence". Procurement office says "continuity". Parliament says "
concerning". Everyone writes strongly worded PDFs.

Meanwhile the dependency remains.

### Security concentration

Centralised digital identity systems are inherently attractive targets, whether to nation states, ransomware groups,
espionage actors, or insider threats. Even if the takeover introduces no immediate compromise, concentration of identity
infrastructure creates systemic risk.

If DigiD fails, large parts of Dutch administration wobble at once: taxes, healthcare access, pensions, municipal
services, legal systems.

This is
why [critics keep classifying it as vital infrastructure](https://waag.org/en/article/call-action-digid-must-not-fall-american-hands/).

### Strategic contradiction

Perhaps the most awkward part is the contradiction itself.

The Netherlands and the EU publicly advocate strategic autonomy, European cloud ecosystems, reduced US dependency, and
sovereign digital infrastructure.

At the same time, practical procurement decisions often continue reinforcing US dependence, because American firms tend
to be large, technically mature, already integrated, hard to replace quickly, and sometimes cheaper in the short term.

So the state says, in effect, "we need digital sovereignty," and then [signs another extension because replacing the
infrastructure quickly is operationally terrifying](https://nltimes.nl/2026/04/25/dutch-cabinet-extends-digid-contractor-contract-despite-us-takeover-concerns).

Which is not uniquely Dutch. Europe has been discovering that rebuilding sovereign infrastructure after decades of
outsourcing is rather like deciding to grow your own vegetables after paving over the garden in 2004.

## What it comes down to

The engine room is still rented. Two trajectories sit on the table for European states: keep extending the lease while
writing strongly worded PDFs about sovereignty, or accept the operational cost of rebuilding what was paved over. Both
are expensive. Only one of them ends with the keys in the right hands.

Either trajectory is also a choice the citizens being routed through DigiD did not get to make. That part travels with
whichever option wins.

