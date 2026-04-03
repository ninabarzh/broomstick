---
title: "Ghost hunting"
date: 2026-04-05
description: "A detection rule is a bet. It says that if an attacker does something in a given environment, the rule will fire. That bet rests on an understanding of attacker behaviour at the time the rule was written. That understanding was incomplete then and has been drifting ever since."
tags:
  - detection engineering
  - soc
  - purple team
  - threat intelligence
  - DFIR
  - risk factors
  - resilience
  - IT-governance
draft: false
---

Most organisations are aware of this. Very few act on it. The result is a detection posture that looks busy, looks 
measured, and quietly fails in the places that matter.

This is where breaches tend to settle in and make themselves comfortable.

## A library of yesterday’s attacks

Detection engineering is usually reactive. Something happens, a technique is identified, a rule is written. Over time 
this builds a library of detections that reflects what has already been seen, filtered through whatever incidents and 
intelligence happened to reach the team.

That library feels like coverage. It is not, it is a historical record.

Attackers are not limited to what has already been observed. They are limited by what is blocked and what still works. 
Once a technique becomes reliably detectable, its value drops. Tooling shifts, tradecraft adapts, the rules remain.

Many detection libraries are quietly well tuned to techniques that serious attackers moved away from some time ago.

## The illusion of coverage

Operationally, everything looks fine. Rules fire, alerts are triaged, dashboards show activity, coverage maps neatly 
to frameworks.

This is where programmes drift into performance rather than protection.

Coverage often becomes a counting exercise. A technique is marked as covered because a rule exists. Whether that rule 
would actually fire in this environment, against a current variant of that technique, is another question. It is also 
the one that tends to be skipped.

This is less a tooling problem and more an incentives problem. It is easier to show that a rule exists than to show 
that it works.

## Static rules, adaptive adversaries

Most detection logic encodes assumptions about how attacks look. Those assumptions age quickly.

Living off the land techniques blend into normal system activity. A PowerShell command that looks routine on one 
endpoint is lateral movement on another. Signature logic struggles because the behaviour is not obviously malicious 
in isolation.

Identity based attacks bypass the idea of a technical entry point. If an attacker logs in through a legitimate 
authentication flow, there may be no exploit, no malware, no clear boundary crossing. If detection assumes compromise 
starts at the perimeter, it tends to miss what happens inside identity systems.

Cloud native attacks make this worse. Activity stays within provider infrastructure, using legitimate APIs and 
short-lived resources. Network indicators fade away, logging is partial or misconfigured, and the attack carries on 
regardless.

None of this is particularly new. What is new is how often detection still assumes the opposite.

## Detection as a drifting model

A more useful frame is to treat detection as a model of how the environment can be attacked, expressed as rules 
and correlations.

Like any model, it has blind spots. It reflects the data it was built on. It tends to overfit to past incidents and 
degrade as conditions change.

Left alone, it drifts in a predictable direction. It becomes better at recognising what it already understands and 
worse at seeing anything else. Confidence increases while actual coverage quietly shrinks.

A quiet SOC is not always a sign of control. Sometimes it is a sign that the model is no longer looking in the right places.

## Building against what has not yet been seen

Closing this gap means moving from reactive detection to proactive modelling.

Threat intelligence is an obvious input, though it often ends up as commentary rather than material. Reports are read, 
summarised, and filed away. Less often are they translated into detection logic before those techniques appear locally.

The information is not scarce. Campaign reports describe tooling and behaviour, malware repositories contain 
recent samples, sector advisories surface patterns early. The constraint tends to be the absence of a process that 
turns that information into something testable in the local environment.

Many programmes stop at awareness. Detection only improves when that awareness is turned into something that can fail.

## Testing the model, not trusting it

If detection is a model, it benefits from being tested against reality.

[Purple team exercises](https://purple.tymyrddin.dev/docs/making-of/purple-team/readiness) can do this when treated as 
experiments rather than demonstrations. Running a technique in the actual environment, with existing logging and 
controls, answers questions that documentation cannot.

Does anything fire. If so, what? If not, why not? Is the activity visible at all. If it is visible, is it 
distinguishable from normal behaviour.

This is where the uncomfortable gaps tend to appear. Not only missing rules, but missing telemetry, 
fragile assumptions, and logic that works nicely until it meets real conditions.

The detection gap that matters is often the one where nothing fires and nothing looks wrong.

## Detection posture

A detection posture that keeps up is less about accumulating rules and more about maintaining, challenging, and 
occasionally discarding them.

Rules are reviewed against changes in attacker behaviour, not only after incidents. Coverage mapping is useful when 
it is backed by validation in practice. Techniques are tested in the environment they are meant to protect, not only 
in controlled setups.

Old rules that detect techniques no longer in use, or that produce noise without signal, are worth questioning. 
They tend to hide gaps elsewhere rather than provide value.

Metrics shift away from activity and towards effectiveness. Not how many alerts were processed, but which techniques 
can be detected with some confidence and which remain invisible.

It is less tidy than a dashboard full of reassuring colours. It is also closer to reality.

## The cost of not doing this

Maintaining [detection as a living model](https://purple.tymyrddin.dev/docs/making-of/soc/detection) takes effort. Time, discipline, and a willingness to question assumptions all 
come into play.

The alternative has its own cost.

It produces systems that are visibly busy and functionally blind. It produces incidents where the relevant data 
existed, the rule existed, and neither connected in time to matter.

If detection only fires on behaviour that is already understood, it is not detecting attackers. It is documenting 
history.
