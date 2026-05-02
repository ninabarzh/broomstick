---
title: "Is your threat model already behind?"
subtitle: "The dangerous model is the one that still looks professional"
description: "Most organisations have a historical artefact where a threat model used to be. The gap between the environment people believe they are defending and the one that actually exists widens quietly through ordinary organisational behaviour."
draft: false
date: 2026-05-02
tags:
  - threat-modelling
  - risk-management
  - security
  - audit
  - infosec
  - compliance
---

Most organisations think they have a threat model.

What they usually have is a historical artefact: a snapshot of how the environment looked on the day several people sat 
in a room with diagrams, coffee, and varying levels of optimism.

The session happens. Assets are mapped. Threats are identified. Risks are scored. A document is produced. The document 
is reviewed, approved, uploaded somewhere nobody voluntarily visits, and occasionally resurrected during audits or 
post-incident archaeology.

At the time it was written, it may even have been accurate.

Then the organisation changed.

That is the part many security programmes quietly fail to account for. Threat modelling is often treated as a project 
milestone rather than an operational activity. Something completed, rather than something maintained. The result is 
a widening gap between the environment people believe they are defending and the environment that actually exists.

## Drift happens quietly

The drift rarely arrives dramatically. Nobody announces: “Good news everyone, we have accidentally invalidated the threat model.”

Instead, it accumulates through ordinary organisational behaviour.

A business unit adopts a SaaS platform because procurement was taking too long. A cloud integration is expanded to 
support a new workflow. A vendor receives broader access because the temporary exception became permanent through the 
ancient administrative ritual known as “nobody revisited it”. An acquired company arrives carrying infrastructure 
held together by undocumented dependencies and hope.

Each individual decision appears reasonable in isolation. Collectively, they alter the attack surface.

The original threat model does not know this.

More importantly, the organisation often does not realise the model no longer reflects reality. The diagrams still 
look reassuringly official. The risk register still contains tidy entries with colour-coded severity ratings. 
Leadership still believes there is visibility over the environment because visibility existed at some point in the past.

This creates a particularly dangerous condition in security: confident misunderstanding.

An outdated threat model does not merely omit risk. It distorts decision-making. Resources are allocated against yesterday’s architecture. Defensive controls are prioritised around assumptions attackers have already moved beyond. Reviews confirm protections around systems that no longer represent the primary exposure.

## Attackers adapt faster than governance

Three or four years ago, many organisations barely considered QR-code phishing campaigns, adversary-in-the-middle frameworks intercepting authentication flows, or attackers routing operations through legitimate cloud infrastructure to blend into normal enterprise traffic. Those techniques are now common enough to bore incident responders.

Attack methods evolve continuously because attackers are not constrained by governance cycles, annual reviews, or the thrilling spectacle of waiting three months for cross-departmental approval to update a spreadsheet.

Defenders often are.

A static threat model defending a dynamic environment gradually becomes less useful while still appearing authoritative. Nobody worries about a clearly broken model. The dangerous model is the one that still looks professional.

## Practice beats the archived version

The useful distinction is between threat modelling as an output and threat modelling as an operational practice.

An output is finite. It is produced, reviewed, and archived. A practice evolves alongside the organisation itself.

In a maintained approach, changes to the environment trigger reassessment. New integrations. Infrastructure migrations. Acquisitions. Significant incidents. Discovery of undocumented dependencies. Major workflow changes. These events do not wait politely for the annual review cycle, and neither does the attack surface.

The review itself does not need to recreate the original workshop every time. Most of the work is narrower and more practical.

- What changed in the environment?
- Which trust relationships expanded?
- Which assumptions are no longer true?
- [What attack paths exist now](https://purple.tymyrddin.dev/docs/threat-modelling/attack-path-mapping) that did not exist six months ago?
- What techniques are attackers using now that the current model barely acknowledges?

The organisations that keep their models closest to reality are usually not the ones producing the most polished diagrams. They are the ones treating the model as something operational: updated after incidents, adjusted after architectural changes, questioned after unexpected findings, and revisited whenever reality diverges from documentation.

That sounds obvious when written down. So does backing up data. Organisations still discover both only after a bad week.

## The people who know where the bodies are buried

The most accurate understanding of attack paths rarely sits entirely with the people formally running the threat modelling exercise.

It sits with the engineer who knows two systems communicate in ways absent from the architecture diagrams. The operations administrator who knows a “temporary” firewall exception has existed since several prime ministers ago. The analyst who has spent months watching authentication abuse against externally exposed services. The infrastructure team quietly carrying technical debt nobody wants to discuss in steering meetings.

When these people are excluded, the resulting threat model develops fictional completeness. The map looks coherent because the missing terrain never made it onto the page.

The gaps are usually mundane rather than exotic. An undocumented connection. Excessive inherited permissions. A monitoring blind spot everyone assumed another team covered. A partner integration extending further into the environment than originally intended.

Threat modelling sessions that include operational staff uncover these findings constantly.

Those sessions also reveal something else: attackers are often using the environment more realistically than the organisation itself understands it.

Many threat models still describe attackers as 
[abstract external entities](https://purple.tymyrddin.dev/docs/threat-modelling/adversary-persona-workshop) interacting 
neatly with bounded systems. Real attackers move through inherited trust relationships, shared identity providers, 
forgotten integrations, unmanaged cloud assets, and administrative shortcuts accumulated over years of operational 
compromise.

They use the organisation the way the organisation actually works, not the way the diagrams say it works.

## Surprise is a useful metric

A healthy threat modelling process produces surprises.

Not constant chaos. Not paranoia. Just enough friction to expose assumptions that had quietly hardened into accepted truth.

One of the clearest warning signs in security is a review process that never uncovers anything unexpected. A threat model that only confirms the existing picture is no longer exploring the environment. It is protecting the assumptions already embedded inside it.

Security programmes often mistake stability for understanding. A stable model may simply mean nobody has looked closely enough to disturb it.

A usual question after a review is: ***“Is the model complete?”***

A more useful question to add is: ***“What did we learn that we did not know before?”***

If the answer is “nothing”, the organisation has stopped looking in the places where uncomfortable answers live.
