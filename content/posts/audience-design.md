---
title: "Audience design"
subtitle: "On the right kind of boring, and the readers it politely shows out"
description: "Some writing filters its readers on purpose. Some by accident. Some by committee. The line between obscurity and design sits closer to honesty than to secrecy."
date: 2026-05-14
draft: false
tags:
  - "writing"
  - "documentation"
  - "security culture"
  - "audience design"
  - "obscurity"
  - "tedium as a filter"
  - "public writing"
  - "threat modelling"
cover:
  image: "/images/audience.png"
  alt: "A figure at a small desk in a high-ceilinged reading room, reading with the quiet satisfaction of someone who has found exactly the book they wanted; through the tall windows, crowds of other figures drift past, half-dissolving into a cheerful drizzle, their attention already elsewhere. The reader is entirely unbothered." 
  relative: false
---

A friend asked whether the proof-of-concept I had sketched on [a docs page](https://purple.tymyrddin.dev/docs/admin-surface/sos) was worth
actually building. I said no, for the usual reasons, and also because the page in
question had been written in the specific style of a document that does not want to be
read. A four-layer architecture diagram without the diagram. Ingestion, storage, correlation, presentation.
Bullet lists of API names with the dispiriting authority of a railway timetable. It
reads like a tender response written by a tender response.

That was the point. Most readers close the tab around the third bullet of the first
section, where the page introduces a graph database called Neo4j with the offhand
confidence of someone who has never had to explain it at a dinner party. Beyond this
point lies a country no casual reader returns from.

What I had not quite noticed, while writing the thing, was that I had chosen my reader
without asking permission. Not the topic. The reader. And once you notice that, the
world starts looking subtly different, in the way it does after someone explains what
a quantity surveyor actually does for a living.

## Mechanics

Every piece of writing filters its readers. This is not a profound observation, in
the way that gravity is not a profound observation. It is mostly true, mostly
ignored, and occasionally embarrassing to people who pretend otherwise.

Vocabulary filters. Length filters. The first sentence filters more than the rest of
the document put together, although the second sentence, if it is long and contains
the word "methodological", can be relied upon to clear out the survivors. What
changes is whether the filter is deliberate, accidental, or the work of a committee
that did not realise it was making one.

Most writing about security assumes a single binary: public or classified, openness
or secrecy, transparent or controlled. The interesting axis sits elsewhere, sulking.
You can publish a document and still not be legible to most of the people who could
open it. You can leave it in the open and let the prose do the work of keeping the
wrong readers out, the way a really good Latin inscription on a public building does.

A vivid essay invites readers in. A four-layer architecture diagram politely shows
them the door, holds their coat, and hopes they had a nice time. Both are public.
Both are honest about what they are. The difference is who finishes reading, and
whether they did it on purpose.

## Survivors

A page that reads like a tender response filters by patience, not by intent. This is
worth being clear about, because patience and intent are different things, and one
of them is considerably rarer.

The bored hobbyist with three browser tabs open does not stay. The journalist on
deadline does not stay. The undergraduate looking for a thesis hook does not stay.
The retired engineer who genuinely wants the dependency graph between Dutch defence
infrastructure and civilian utilities, and is willing to read seven pages of dry
architecture to get to the interesting bit, does stay. He may also email you. He has thoughts.

So does a patient state actor, who has been patient for a living since before
patience was fashionable. Tedium is not a defence against funded adversaries; it is
a defence against incidental ones. That is a smaller defence than it sometimes
looks. It is also not nothing. Most attention is incidental; most of the people who
could amplify a finding never finish reading, and most of the rest assume someone
else already has.

It works best when the underlying claim is one you are willing to make available to
someone who reads the whole page carefully, and unwilling to make available to
someone who reads only the introduction and the bit with the missing diagrams. Which,
depressingly, describes a surprising amount of writing about infrastructure.

## Precedents

Academic prose does this constantly, and has done since roughly the invention of
academic prose. Legal documents do it by accident, then by habit, then by tradition,
then by a kind of nineteenth-century institutional inertia that has by now acquired
something close to the legal status of a person. Terms of service do it
deliberately, although the goal there is to filter out anyone with the will to argue
rather than anyone with the will to understand, which are different filters
operating on entirely different muscles.

The pattern is older than the web. The web just made it cheaper. Where once you had
to print and bind the Boring Bit and then post it to forty-six addresses, you can
now upload it once and let the internet do the filtering for you, which it does with
the impartial enthusiasm of a small dog at a checkpoint.

Reflective essays do the opposite. They are designed to lower the activation energy
of attention, to pull a reader in further than they intended to go, the way a really
comfortable chair in a bookshop will pull a customer in further than they intended
to go and keep them there until the staff start, very slowly, turning out the
lights.

Both modes are legitimate. The dishonest move is to write reflective prose about
something better served by tedium, or to write tedious prose about something the
reader genuinely had a right to follow without first qualifying as a chartered
accountant.

## Neighbours

If you write about systems, you are choosing whose attention to invite. This is
true whether you admit it or not. The same set of facts can become an essay or an
architecture diagram, and the choice between them is not about correctness; it is
about who you want to talk to next, and which conversation you are prepared to have
when they arrive.

Sometimes the answer is the essay. Sometimes the answer is the architecture
diagram, sometimes the code. Sometimes, the answer is both or all three, on adjacent pages, with the essay quietly
linking to the diagram for the readers who care enough to keep going. This is the
shape most worth sitting with, because it is the only one that is honest about the
existence of the filter at all.

It does not pretend the diagram is for everyone, in the patronising way that public
consultations sometimes pretend they are for everyone. It does not pretend the
essay is the whole story, in the comfortable way that [a good essay](/posts/perhaps/) can sometimes
make a reader forget the diagram exists. It just lets readers self-sort, and trusts
that the people who needed the diagram will find their way to it, the way moths
find their way to streetlamps, and patient state actors find their way to graph
databases.

Full disclosure: this one was designed for the friend who asked, and rather more
for me. Most reflective writing is. It just does not usually say so.

The ones who close the tab were never the audience.

They were the weather.