---
title: When the browser looks back
date: 2026-04-17
tags: [privacy, platforms, surveillance, LinkedIn, browser extensions, normalisation]
description: "Browser extension scanning, anti-scraping claims, and the slow normalisation of client-side surveillance disguised as security plumbing."
draft: false
---

LinkedIn loads JavaScript that probes for installed browser extensions — thousands of them, including competitors' 
sales tools, grammar checkers, and religious or political plugins. LinkedIn acknowledges this, but frames it as 
anti-scraping and abuse prevention.

The question is not whether extension detection happens. It is how the results are used and stored?

So the situation is **not** *“hidden conspiracy script discovered”*, it is *“known technique used aggressively enough 
that it has triggered class actions”*.

On BrowserGate specifically, it sits inside the evidential chain rather than outside it. The controversy exists because 
independent technical reporting and legal filings are converging on similar descriptions of behaviour, even if they 
differ in interpretation.

## BrowserGate signal

At [browsergate.eu](https://browsergate.eu/), the signal quality is uneven. Some material is technical 
reporting, some is advocacy framing, and some is light on verification. That mix is typical in early-stage platform 
disputes. Strong claims tend to arrive before consensus catches up.

What is solid at this point is fairly straightforward.

Extension probing at scale is happening, but it does not present itself as a single discrete action. It appears more 
like a background pattern of checks that becomes visible only when aggregated and observed over time. It is tied to 
identity-linked profiling on LinkedIn’s side, which is where discomfort begins to accumulate rather than announce 
itself. LinkedIn frames it as anti-abuse enforcement, and in isolation that framing is familiar. Most large platforms 
describe intrusive signals in security terms because that is where they are easiest to justify.

What remains open is not whether the mechanism exists, but how it behaves once it has done its initial job. Whether 
signals are discarded after real-time risk scoring, or whether they are retained and folded into longer-term 
behavioural profiles. That distinction separates short-lived fraud prevention from persistent inference about user 
tooling and behaviour.

This is where the broader discussion around it entered the LinkedIn feed.

## Discussion on it in the LinkedIn feed

Ivan L.’s post drew on existing reporting and news coverage about LinkedIn’s extension scanning practices. It did 
not introduce new technical findings, but instead summarised and reframed the publicly reported material into a 
more direct, conversational interpretation of its implications. And strangely, it ended with 

*"How do you manage browser extensions in your org? Or..do you manage?
P.S. If my profile disappears from Linkedin tomorrow - you know what happened...".*

I thought he was trying to be funny. *I drafted a reply about the difference between transient risk signals and 
persistent behavioural profiles, and the usual scope-creep argument, but specific to extension telemetry.*

The button to post my comment did not work, and on reload the post disappeared.

Not dramatically. No announcement, no visible enforcement trace. Just a refresh, and the absence of something that had 
been there moments before. Eerie. Then the profile followed a similar pattern, not reliably present either.

At that point, the interesting part became not the disappearance itself although my brain was racing to make 
possible connections. Platforms do that constantly. The interesting part is how routine the mechanism feels. Content 
appears, gets reviewed, and sometimes vanishes without explanation that survives outside the system.

## Browser-level signals signal infrastructurisation (not a real word)

That is where a shift sits.

Not in whether LinkedIn is doing something novel, but in how unremarkable it has become that browser-level signals, 
behavioural scoring, and enforcement decisions operate in the same machinery. Nothing about it announces itself 
any more. It just behaves like infrastructure.

And infrastructure rarely needs to explain itself to the people inside it.
