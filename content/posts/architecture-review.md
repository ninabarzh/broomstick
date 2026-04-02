---
title: "Architecture reviews that approve instead of challenge"
date: 2026-04-02
description: "A look at how technical, emotional, and political factors shape architecture reviews."
tags:
  - architecture
  - software architecture
  - security architecture
  - tech leadership
  - systems thinking
  - risk management
  - organisational dynamics
  - IT-governance
draft: false
---

Architecture reviews exist to catch problems before they become expensive. In practice, most reviews catch a different 
set of problems from the ones they were designed to find, and miss a different set from the ones that will eventually 
cause trouble.

This is not because the reviewers lack competence. It is because most architecture reviews are not designed to produce 
understanding. They are designed to produce alignment and distribute accountability. Once that is the function, the 
outcome is predictable.

## A review that produces endorsement rather than understanding

An architecture review is a room full of people with different stakes in the design.

The architect has a professional investment in it. Managers have already made commitments that depend on it. Engineers 
have opinions about feasibility that may conflict with timelines. Security has concerns that may require rework that 
nobody has planned for.

These are not neutral positions. They shape what can be said.

Most reviews ask for candid challenge while making that challenge professionally costly. The result is a process that 
records attendance, produces action items on safe topics, and quietly converges on endorsement. The substantive 
concerns are present, but they are not expressed in a way that forces resolution.

## What happens instead of honest engagement

Under these conditions, people do what the system allows.

The technical participant produces a precise and increasingly detailed account of the design that never quite 
addresses the concern that was raised. Questions about delivery risk are answered with explanations of technical 
correctness. These are not the same thing, but the latter is easier to defend and harder to challenge directly.

The reviewer who raises a concern sees it reflected in the next version of the design. The wording acknowledges the 
issue. The design does not change in the way intended. In the next review, the concern is marked as addressed. 
Challenging that status risks being seen as obstructive.

The manager agrees that the concern matters. Nothing changes. Addressing it would require revisiting a prior 
commitment, and the incentives in the room are not aligned with that outcome.

These are not individual failures of honesty. They are the expected output of a process that rewards agreement and 
penalises disruption.

## What the review misses as a result

The concerns most likely to cause problems are also the ones least likely to survive this process.

They are uncomfortable because they require changing something significant. They are expressed indirectly because 
direct expression carries cost. They are acknowledged and deferred rather than resolved.

The review closes. The design proceeds. The problem appears later, during implementation, in production, or in an 
incident. What was deferred becomes expensive.

This is not an exception. It is the normal outcome of a review that functions as a governance checkpoint rather than 
a genuine examination of whether the design will work.

## The function most reviews actually serve

Many architecture reviews exist to distribute accountability rather than to improve the design.

A room full of people has seen the proposal. Questions have been asked. Concerns have been noted. Decisions have been 
minuted. When problems emerge later, they are no longer owned by a single person.

If this is the real function, the behaviour in the room makes sense. The goal is not to surface the most difficult 
problems, but to avoid being the person who blocked progress or took sole responsibility.

Any attempt to improve reviews that ignores this underlying function will produce better looking meetings with the 
same outcomes.

## What changes when the conditions change

A review that is intended to find problems requires different conditions.

The most important is separation between review and approval. If a review is expected to endorse a design that has 
already been agreed, it cannot also function as a mechanism for challenging that design. Where organisations cannot 
or will not separate these activities, the limits of the review should be made explicit. Otherwise, it becomes a ritual 
that implies scrutiny without enabling it.

Concerns need to be raised without being treated as obstruction or as a personal challenge. This is not achieved by 
stating a norm once. It requires consistent demonstration that raising a difficult issue is expected and useful.

Architects need to be able to acknowledge that a concern is valid and that the design needs to change without this 
being treated as failure. Architectural error is normal. Error caught in review is cheap. Error suppressed because 
the conditions did not allow it is expensive.

These are not process tweaks. They change what the review is for.

## The facilitator’s role

A review with an external facilitator who has no direct stake in the design behaves differently.

A facilitator can ask the questions participants tend to avoid: what concern has not been said, what would need to be 
true for this design to fail, what is most uncertain here. These are ordinary questions, but they are structurally 
difficult for participants with stakes in the outcome to ask of each other.

A facilitator can improve the conditions in the room. They cannot override the incentives around it. If the 
organisation does not want certain answers, those answers will remain difficult to surface regardless of who asks 
the question.

## The system around the room

The review does not exist in isolation.

Timelines, funding decisions, and prior commitments shape what is possible long before the review takes place. By the 
time a design reaches formal review, some decisions are already effectively locked in. Expecting the review to surface 
and resolve those constraints is unrealistic.

If the upstream system rewards speed, certainty, and adherence to plan, the review will reflect those priorities. It 
will not compensate for them.

## What this means in practice

Most organisations already have architecture reviews that perform exactly the function they are set up to perform.

They create alignment, distribute accountability, and allow work to proceed. They do not reliably surface the problems 
that matter most.

The question is not whether the review looks rigorous. It is whether it is designed to make difficult truths visible 
and actionable.

If it is not, the risks are still there. They are simply deferred, waiting for a more expensive moment to appear.

For a deeper look at how technical, emotional, and political factors shape architecture work, see [The human layers](https://purple.tymyrddin.dev/docs/systems-architecture/the-human-layers)
