---
title: "Agile, where it fits and where it doesn't"
subtitle: "Two axes, not one"
description: "The choice between iteration and anticipation is not about project size. It turns on how much is unknown and how much a mistake costs, two independent axes that place any piece of work somewhere it was always going to sit."
draft: false
date: 2026-06-04T08:00:00.000Z
tags:
  - agile
  - software engineering
  - uncertainty
  - systems thinking
cover:
  image: "/images/uncertainty_consequence_quadrant.png"
  alt: "Quadrant mapping uncertainty against consequence, with adaptation favoured at high uncertainty and anticipation at high consequence" 
  caption: "A 2x2 matrix mapping software work onto two axes: uncertainty (vertical, low at bottom to high at top) and consequence (horizontal, low at left to high at right). Top left, high uncertainty and low consequence: startup and experimental products, internal tools, online services, where adaptation pays. Top right, high uncertainty and high consequence: exploratory work that cannot fail safely, the hard middle. Bottom left, low uncertainty and low consequence: routine business systems, reporting, internal CRUD, where either approach works. Bottom right, low uncertainty and high consequence: aircraft control, signalling, infrastructure, safety systems, where anticipation pays."
  relative: false
---

Most engineering disciplines accept that method follows from context. Nobody expects a bridge engineer, a documentary
director, and a trauma surgeon to share a planning model, and nobody finds the difference remarkable. Software is one of
the few fields where people go looking for a single methodology and then try to apply it to everything in sight.

Agile is the most successful instance of that search, which makes it an awkward thing to argue about. The useful
question is not whether it is good or bad. It is what kind of work it was meant for, and that turns out to depend on two
things that have nothing to do with how much anyone likes the method.

## Reaction to

The early movement grew out of projects that spent months producing plans before any working software existed, by which
point the plans no longer matched what anyone had learned. The insight underneath the reaction was modest. When the 
shape of what is being built is not yet known, learning is part of the building, and short iterations tend to beat 
elaborate prediction.

That is an adaptation strategy. It is not a productivity strategy, not a management framework, and not a claim about how
teams ought to treat one another, though it has since been pressed into service as all three.

## Two axes

The variable that does the work here is not project size. A large project is not automatically a poor fit, and a small
one is not automatically a good one. Two things seem to govern the choice, and they pull in different directions.

The first is uncertainty: how much of the work is genuinely unknown at the start. A payroll system, aircraft
certification paperwork, a medical device compliance dossier: the requirements are largely settled before anyone writes
code. A consumer product, an early startup, an exploratory research tool: the requirements are partly a guess, and
discovery is part of delivery.

The second is consequence: what it costs when something is wrong and reaches the world. A failed feature in an internal
tool is an inconvenience. A defect in infusion pump firmware is not. The two axes are independent. Uncertainty can be high
while consequence is low, the natural home of iterative work, and low while consequence is high, the natural home of
anticipation.

Where uncertainty dominates and feedback is cheap, learning while building usually wins. Where consequence dominates and
feedback is slow or irreversible, thinking before building tends to win. Most real work sits somewhere between and leans
one way.

## Iteration earns its place

Iterative approaches do well when the requirements are honestly unknown, when a mistake can be corrected quickly, when a
failure is awkward rather than catastrophic, and when the architecture can absorb revision without falling over. Online
services, internal tooling, and experimental products tend to meet most of these conditions at once. Learning from
production works because production is a cheap and fast teacher and the cost of being wrong for a week is small.

## Where it starts to strain

The failure mode is not scale. It is that reality becomes expensive to revise, and that expense comes in at least three
forms.

The first is harm. In a safety critical system the bottleneck is not how fast the code gets written, it is how the code is proven
correct before it touches anyone. A defect found after deployment in railway signalling or aircraft control
or heart monitoring may already have done its damage, so learning from production is no longer available as a primary
strategy. The feedback the iterative model relies on is exactly the feedback that cannot be waited for.

The second is lag. When the loop between a decision and its observable result runs in months or years, as in
pharmaceuticals or nuclear work, the correction can be cheap in principle and still useless in practice, because it
arrives long after the decision it was meant to inform. The assumption of rapid feedback quietly stops holding.

The third is reversal. Deep infrastructure, power grids and telecom backbones and water systems, is not unsafe to revise
so much as costly to revise, because the architecture is long-lived and tightly coupled and a wrong early choice
propagates through everything built on top of it. So the cheap move is to get the architecture roughly right before
committing, which pushes the design work earlier, into anticipation.

None of this makes anticipation superior. It marks out a different region of the same two axes. A social media feature
and a heart monitor are not arguments for opposing philosophies. They are points at opposite corners of one space.

## The debate that misses it

Framed as Agile versus Waterfall, the argument is close to empty, because organisations that function at all
already run hybrids: iterative delivery inside planned architectural boundaries, short-cycle implementation inside slow
regulatory frameworks, long-term design wrapped around short-term adaptation. The genuine question for any given piece
of work is not which camp wins but where prediction ends and learning begins, and that line moves with the work.

Pure anticipation is rare. Pure adaptation is rare. Almost everything worth building combines the two, and the
practitioners who seem dogmatic about one usually turn out, on inspection, to be doing some quiet amount of the other.
The disagreement, when there is a real one, is over proportions rather than principles: how much can be settled
up front, and how much has to be left open and found out.

So treating either pole as universally correct is the mistake. Agile is valuable where discovery dominates. Planning
becomes valuable where consequence dominates. The practical question is not whether to prefer iteration or planning. It
is how much of a system one can afford to find out the hard way.