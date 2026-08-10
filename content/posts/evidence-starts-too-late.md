---
title: The evidence starts too late
description: Security work runs on records. Alerts, tickets, risk registers, audit evidence. Give that work to a model rather than an analyst and the model gets the records. Not the walk past a cabinet nobody has opened in years, or the handwritten label nobody can account for.
tags:
  - systems thinking
  - organisational dynamics
  - AI
  - security
draft: false
date: 2026-08-10T12:00:00+02:00
---

[The hinge](../the-hinge/) ended with a person doing the comparing: for example, an analyst who takes what the systems
report, holds it against what is actually happening, and decides which of the two to believe. Route around that job in
one place and it reappears in another.

So the obvious next proposal: give the comparing to a model. Let it read the alerts, the tickets, the risk register and
the audit evidence, and make the call. It reads faster, never tires, never has a bad Tuesday, and holds more in one
context window than a shift of analysts holds in a year.

The question is what happens to the work when the analyst is gone and the model has the job.

The claim is narrow. Not that models lack context. Not that intuition is magic. Not that the current generation falls
short, an argument with an expiry date printed on the box. The claim is positional: what gets noticed is settled
before the model has anything to read. A model works with records, evidence, telemetry and other representations of
what has happened. Whatever was never observed, recorded or instrumented before the model receives its input is absent
from its world.

## What gets into the record

In an information security management system, things that happen become things the organisation can record, review and
act on. Asset inventories, risk registers, vendor questionnaires, audit evidence, telemetry, control documentation and
incident records all do this in different ways.

An engineer walking a rack room finds a fibre patched into a port decommissioned last year, notices the label is
handwritten, remembers the same thing in another room in March, and cannot place who would have done it. What reaches
the organisation's records is a change ticket: port 14 disabled, patch removed, closed.

The ticket is true. The handwriting, the March echo and the inability to place it had nowhere to go, because no field on
the form was asking.

The asset inventory has the same boundary. A configuration management database is accurate about everything that was
onboarded, which is the point. The box zip-tied inside a cabinet on a plant floor, a programmable logic controller
installed by a contractor during a shutdown eleven years ago and never entered anywhere, is not misrepresented. It is
unrepresented.

A model reading the inventory can recognise that inventories of this kind are incomplete, estimate likely gaps, and
recommend a discovery scan. All useful. All downstream. The model can reason about missing assets as a known class of
problem. Whether the scan ever reaches this cabinet was settled years earlier by somebody else. What the model cannot
do is find this particular box before somebody has put it in its field of view. That requires the floor: the walk past
the cabinet.

## Before anything was measured

The risk register moves the boundary further upstream. Somebody, at some meeting, decided that a thing counted as a
risk, described it, and entered it. A model can score the wording, probably more consistently than the committee ever
managed, and rank the register beautifully.

The thing that never became a risk is not ranked low. It is not ranked.

A model fed threat intelligence, sector taxonomies and the processed incidents of a thousand other organisations can
propose risks the register never contained, and anyone who has watched it happen may reasonably think the omission
problem has been solved.

It has not. The proposals come from other organisations' records, from what they saw once it had been turned into
shareable information. The model can widen the range of distinctions available to the organisation. What it cannot
supply is the risk in this organisation that nobody has yet noticed, named or recorded.

A committee member may half-recognise it from something glimpsed in a corridor, and still not be able to phrase it.

## The Tuesday night shift

Certification scales the problem up.

An auditor reviews evidence: policies, tickets, screenshots, exports, records of records. A model can chew through the
packet superbly, cross-reference every clause, and find every inconsistency between the access policy and the
joiners-movers-leavers log.

The packet is an account of the organisation's controls. The Tuesday night shift is elsewhere.

The operator who has learned which alarm on which line means a loose sensor rather than an intruder does not escalate.
That is also how a real intrusion gets waved through, by an attacker who has learned the same pattern. There is no
ticket, no exception record, no incident report. The auditor cannot review a decision that left no evidence. The model
cannot process evidence that does not exist.

## When judgement is still forming

An analyst can escalate with nothing more than: "This bothers me and I cannot yet say why."

Not mysticism. A mismatch between what is perceived and what can so far be said. Sometimes that is the first sign of
an intrusion. Sometimes it is simply a distinction arriving before its vocabulary, the March echo the engineer had
nowhere to file. No special faculty was involved there either, only several weak observations that had not yet become
something the form could hold.

"I closed it, but I did not like it" is not a conclusion. It is evidence about the state of the comparison, and it
travels by handover, by tone, by somebody saying it out loud on a bridge call. The ticket says closed. A judgement that
shows itself unfinished can be picked up by the next shift. One that arrives finished gets filed.

A model can give the same fluent surface either way.

"Benign administrative activity consistent with expected patterns" can be the conclusion of a sound inference or a
confabulated one. The trouble is not the error rate. Errors can be counted. The trouble is that the output need not
carry any sign that the judgement behind it was unfinished.

Interpretability does not automatically hand that sign back. Attribution scores and reasoning traces are further
outputs, instrumented by somebody and read by somebody, creating another place where judgement is required.

## The agent with hands

The strongest objection has hands. A model doing the comparing no longer just receives reports. It runs the runbooks
itself: queries the SIEM, pulls endpoint telemetry, launches scans, reads back years of tickets. Surely that is
different. Surely the model is now observing the estate.

It is collecting.

An agent gathering its own data is still gathering data through instruments somebody configured. What is queryable was
fixed before the agent arrived: which systems were onboarded, which fields were retained, how data was normalised, which
collectors were deployed, which protocols they can parse.

The segment that was never logging does not appear in the agent's world as a blind spot. It does not appear. It is the
cabinet again, at network scale.

A person can find the silence itself odd, an absence conspicuous against an expectation the telemetry never carried.
An agent told to check coverage checks the coverage inventory, which is another record. It can confirm that every
segment in the inventory reaches the SIEM. Whether the inventory lists every segment is the same question again, one
level up.

## Where the job goes

Automating the triage desk moves the job somewhere else.

The analyst leaves. Judgement reappears as whoever assembles the context each alert arrives with, whoever decides what the
model never sees, whoever samples what it closed, whoever decides when auto-closure stops being believed.

Nothing vanished.

The judgement now watches dashboards about model behaviour instead of anything about the estate. Nobody stopped judging.
The work was scattered into positions with worse sightlines.

## Stocking, not occupying

None of this argues the model out of the room.

[Variety](https://purple.tymyrddin.dev/docs/foundations/system-effectiveness/ashby) can be engineered around a
regulator as well as inside one, and a model amplifies well: clusters alerts, correlates tickets, drafts timelines,
digests intelligence, widens what one analyst can attend to in a shift. Variety only helps with distinctions the
system can make, though. A model can supply more distinctions from the records it receives. It cannot supply one the
organisation has given it no way to make.

That is the case for putting the model around the job, and the case against giving it the job. It is an enormous stock
of distinctions borrowed from other organisations' records. That is not where a situation's own distinctions get made.

Sampling the discard pile tests how the model distinguishes: what it auto-closed, where it repeatedly failed to tell two
things apart, what its confidence looked like just before it was wrong.

Manufacturing events tests the record: whether the organisation's instrumentation can represent what actually
happened. Red teaming, read this way, is not only about proving that a defence can be beaten. It creates events that
test whether the records, alerts and controls can capture what happened. Does the trace survive? Does anything fire?
Does the silence get heard?

Giving the job to a model answers the throughput question, and can widen the record besides. The comparing is what is
left when the available evidence has done all it can.

The model receives the world after somebody has already decided what to observe, what to record and what to discard.

Keeping a person in that job was never the sentimental option. It is what the job has always been.
