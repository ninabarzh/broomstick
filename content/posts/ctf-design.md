---
title: "CTFs that teach solving CTFs"
date: 2026-04-03
description: "Learning is mostly implicit unless something forces it into the open. Most people running CTFs will recognise that they skip this, usually under time pressure."
tags:
  - CTF
  - Infosec training
  - education
  - threat simulation
  - skill development
  - learning by doing
  - security awareness
  - offensive security
draft: false
cover:
  image: "/images/ctfs.png"
  alt: "Six digital screens floating independently in a creative, messy workspace." 
  caption: ""
  relative: false 
---

Capture the Flag (CTF) exercises are one of the better formats security learning has produced. Participants can work at 
their own pace, choose what to engage with, encounter real obstacles, and get immediate feedback when something works or 
does not. For learning technical skills, this is close to ideal.

Most CTFs do not deliver on this potential. Not because they are badly designed, but because they are designed to do 
something else. Many optimise for engagement, competition, or recruitment. In that context, teaching people to solve 
CTF challenges is not a failure. It is the goal.

The problem starts when these outcomes are mistaken for learning.

## Optimising for the flag rather than the learning

A CTF challenge designed around finding a flag rewards the participant who reaches the solution fastest, by whatever 
route works. A challenge designed around developing a technique is structured so that the path to the solution builds 
understanding of how that technique actually works.

These are different activities.

A participant who finds a shortcut has practised finding shortcuts. They have not necessarily developed a model of the 
vulnerability. When they encounter a variation in a real environment, the shortcut is not available.

This gap between solving and understanding is the gap between confidence and capability. Completing a CTF often feels 
like learning. Sometimes it is. Often it is familiarity with a particular set of patterns.

## Realism is a constraint, not a cure

A common response is to make challenges more realistic. This helps, but it is not a free improvement.

A[ sanitised challenge teaches a clean version of a technique](https://github.com/tymyrddin/power-and-light-sim). That 
is useful, especially for beginners. [A more realistic proof of concept](https://github.com/tymyrddin/ics-simlab) 
forces the participant to deal with ambiguity, partial information, and failure modes. That is also 
useful, especially for more experienced practitioners.

The two serve different purposes.

Too much abstraction and participants learn moves without understanding context. Too much realism and participants 
spend their time navigating noise rather than building a mental model. The design problem is not to maximise realism, 
but to place it deliberately.

Realistic does not mean complex. It means close enough to actual behaviour that the participant’s understanding is 
tested rather than confirmed.

## Skill level changes the answer

A beginner does not need a realistic environment. They need clarity. A well-constructed, slightly contrived challenge 
can teach a concept cleanly and quickly.

An experienced practitioner needs something else. They need variation, failure modes, and context. Without that, they 
are rehearsing what they already know.

Most CTFs flatten this distinction. The same challenge set is presented to participants with very different levels 
of experience. The result is predictable. Beginners are overwhelmed or rely on walkthroughs. Experienced participants 
optimise for speed and pattern recognition.

Neither group is learning as much as they could.

## The cost of no debrief

The most common failure mode is not the challenge design. It is what happens after.

A CTF that ends when scoring closes has delivered an experience. The learning remains implicit. Participants know what 
they did, but not necessarily why it worked, what it means about the vulnerability class, or how it applies elsewhere.

The debrief is where this becomes explicit.

What was surprising about how the technique behaved. What would have caused it to fail. What signals it produced from 
a defensive perspective. What the participant now understands that they did not before.

This requires time, preparation, and facilitation. It is usually the first thing cut.

Without it, the CTF produces memory rather than capability.

## Competition shapes behaviour

Leaderboards and time pressure are effective. They drive engagement. They also change what participants optimise for.

If the goal is to win, the fastest path to the flag is the correct strategy. If the goal is to learn, the path that 
builds understanding is the correct strategy. These are often in conflict.

You can mitigate this. Reward writeups as well as solutions. Design challenges where understanding is the fastest path. 
Introduce pauses that force reflection. But once you introduce competition, you have biased the system.

You cannot fully optimise for both competition and learning. You can only choose where to place the emphasis.

## What this means for design

A CTF that is intended to teach needs to make its priorities explicit.

If the goal is engagement or recruitment, then fast, solvable, satisfying challenges are the right design. There is 
nothing wrong with that. Not to be confused with deep learning.

If the goal is capability, trade-offs follow. Fewer challenges, more time per challenge, deliberate variation in 
realism, and a structured debrief. The competition element may need to be reduced rather than refined.

The format is not neutral. It shapes behaviour. Treating it as a container for good content misses the point.

## Where platforms like Root-Me and TryHackMe fit

Platforms such as [Root-Me](https://www.root-me.org/Barzh) and 
[TryHackMe](https://tryhackme.com/p/Nina.Barzh?tab=badges) sit at different points on this spectrum.

Root-Me tends towards challenge-based learning with a strong emphasis on solving discrete problems. It is good at 
building pattern recognition (and intuition) and exposing participants to a wide range of techniques. It leans closer 
to the “solve the challenge” end, which makes it effective for [exploration and practice](https://red.tymyrddin.dev/docs/through/buffer-overflow/root-me/), but variable in how much it 
builds deeper understanding without [additional reflection](https://red.tymyrddin.dev/docs/through/buffer-overflow/notes/).

TryHackMe is more structured. It guides participants through [scenarios with explanations and progression paths](https://red.tymyrddin.dev/docs/through/buffer-overflow/thm/). 
This supports learning more directly, particularly for beginners, by making the intended technique explicit. The 
trade-off is that guided environments can reduce the need to struggle, which is where some learning happens.

Neither approach is wrong. They optimise for different things.

Used deliberately, both are valuable. Used as a substitute for each other, they leave gaps. A participant who only 
uses guided paths may lack resilience when structure disappears. A participant who only solves challenges may lack a 
clear mental model of what they are doing.

## What it looks like when it works

A CTF that is working produces participants who are surprised by what they encounter. Not overwhelmed, but forced to 
update their understanding.

It also produces a debrief where participants can explain what they learned, not just what they solved.

That usually takes longer than planned. That is not a problem. It is the signal that something useful happened.

If a CTF runs smoothly, fits neatly into its timebox, and produces a clean leaderboard, it has probably optimised for 
the competition.

If it runs slightly over, generates discussion, and leaves some challenges partially solved but well understood, it 
may have optimised for learning.

For the learning conditions that make this work, see 
[CTFs as learning environments](https://purple.tymyrddin.dev/docs/foundations/montessori/ctf-value).
