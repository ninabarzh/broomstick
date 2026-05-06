---
title: "The administrative attack surface"
subtitle: "Reading military infrastructure like an attacker, and other awkward moments in modern security culture"
description: "A personal reflection on systems thinking, public infrastructure exposure, adversarial analysis and the uneasy relationship institutions have with people who notice operational dependencies."
date: 2026-05-06
draft: false
tags:
  - "critical infrastructure"
  - "systems thinking"
  - "operational security"
  - "infrastructure exposure"
  - "security governance"
  - "adversarial analysis"
  - "OT security"
  - "resilience"
  - "bureaucratic entropy"
  - "open source intelligence"
  - "public sector security"
  - "dependency chains"
  - "compliance versus reality"
  - "security culture"
  - "strategic vulnerability"
---

A few days after sending an application to the Dutch Ministry of Defence for a senior cyber and information security
advisory role, I read an NRC article about publicly accessible details of Dutch military infrastructure.

Not leaked documents. Not espionage. Not shadowy dead drops in rainy parking garages.

Public websites. Pipeline routes. Radar dependencies. Cable maps. Technical drawings. Backup systems.
Segmentation details. Power feeds. Coordinates.

Bits of information scattered across agencies, permits, infrastructure registries, environmental datasets and planning
portals like breadcrumbs dropped by a committee convinced that nothing bad ever happens in spreadsheets.

The article follows an ex-military technician who pieces together vulnerabilities in Dutch defence infrastructure
simply by combining publicly available information. Not hacking. Not breaching. Just looking. Correlating.
Thinking operationally.

In other words: systems thinking.

## Shift

And while reading it, I had the uncomfortable thought: *Perhaps it is better if I do not get the job.*

I surprised myself with that thought. Not because the article was wrong. Quite the opposite. The problem is that I
immediately understood the reasoning. Not the “destroy infrastructure” part. The dependency part.

If you work long enough in security, infrastructure, telecoms, OT, distributed systems or architecture, you stop
seeing systems as isolated objects. You start seeing dependency chains, operational assumptions, trust boundaries,
maintenance realities, failure cascades and single points of failure wearing fluorescent safety jackets.

You stop asking: *“What does this system do?”*

You start asking: *“What does this system depend on, quietly, without anyone noticing?”*

That shift changes everything.

## Waterfall

**A radar is no longer a radar.** It becomes a layered arrangement of dependencies: power supply, cooling, maintenance
windows, procurement chains, segmented networks, contractor access, backup duration, physical access paths and
monitoring assumptions. Each part necessary, none sufficient on its own, all quietly holding each other in place.

**A military fuel pipeline is not a pipe.** It is timing and pressure, logistics and repair capacity, redundancy and
response coordination, stretched across geography, institutions and bureaucracy that rarely meet in one place at once.

**Modern infrastructure is rarely defeated by cinematic sabotage.**
It usually dies of correlations.

One agency publishes permits. Another publishes environmental maps. A contractor uploads technical drawings. A utility
operator exposes cable metadata. A procurement system lists component models. An environmental review includes backup
generators. A planning objection embeds security layouts.

Nothing is leaked. Nothing is obviously wrong.

And yet someone can stand in a wet Frisian field with a smartphone and enough context to see how the pieces connect into
something operationally meaningful.

That is the actual story. Not secrecy versus openness. Not journalists versus government. Not “hackers”.

The real shift sits elsewhere.

Modern bureaucracies tend to classify information individually, while attackers tend to read systems collectively.

Those are not the same way of seeing.

And the awkward part is that this is also, quietly, how security architecture works.

You think in dependencies. You look for constraints. You follow how failure might propagate rather than how intention
was written down. You assume that diagrams simplify, and that infrastructure behaves differently once it is under
pressure, connected, or combined with other systems.

## Back to the application.

The Ministry of Defence vacancy talked about security frameworks, oversight, cloud, AI, policy development and
strategic advisory work. Reasonable enough. Necessary, even.

But after reading the article I found myself wondering whether institutions genuinely want people who think this way,
or whether they merely like the idea of them existing somewhere abstract and well supervised.

Everyone says they want “out of the box thinking” until someone quietly points at the box’s fuel supply, external
contractors, maintenance dependencies and single shared conduit.

Then suddenly the room develops a passionate commitment to process.

The strange thing is that none of this requires paranoia.

Only systems literacy.

You do not need classified access to identify many modern vulnerabilities. You need patience, context, technical
curiosity and the ability to combine boring documents that were never meant to be read together.

That is partly why the line between architecture, intelligence analysis and security engineering has become
increasingly blurry.

The attack surface is no longer merely technical.

It is administrative.

And this is where things become philosophically awkward for democratic societies.

## Awkward

Open societies publish things because openness serves legitimate purposes: planning, accountability, environmental
review, public participation, interoperability, safety regulation and coordination.

But modern states also depend on highly interconnected infrastructure whose vulnerabilities emerge through aggregation.

Each individual publication may appear harmless. The system-level picture may not be.

That is not hypocrisy. It is structural tension.

And structural tensions are rarely solved by pretending one side does not exist.

So yes, perhaps it is better if I do not get the job.

Or perhaps the opposite is true.

Perhaps organisations responsible for critical infrastructure and national resilience increasingly need people who
are capable of reading systems the way attackers do, without becoming attackers themselves.

People who understand that security is rarely about dramatic secrets and far more often about operational assumptions
quietly accumulating in public view.

People who know that resilience is not a policy document. It is behaviour under stress.

The uncomfortable possibility is that modern societies need this kind of thinking quite badly.

The even more uncomfortable possibility is that they may not always like the people who do it.
