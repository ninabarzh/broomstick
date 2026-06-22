---
title: "The nuclear delusion"
subtitle: "Why treating AI like a bomb keeps Europe dependent"
date: 2026-06-22
tags:
  - AI governance
  - cybersecurity
  - European sovereignty
  - export controls
  - threat modeling
  - AI policy
  - Mythos
  - Glasswing
draft: false
---

The nuclear analogy is at the moment the most popular frame for thinking about advanced AI, and it is the most 
comfortable one for the people who built the bomb metaphor's home institutions. It carries an implicit theory of 
control: states hold the technology, deterrence holds the states, and a small club of capable powers manages the rest 
of the world's exposure. That theory has a long pedigree and a familiar cast. It also, for Europe, leads somewhere 
worth noticing before the door closes.

What follows is an argument that the analogy is not just imperfect but load-bearing in a way that works against European
interests. The frame produces a politics of gatekeeping, and the gate is held in Washington.

## The analogy

The nuclear comparison gets three things right, which is why it persists. AI is dual-use. Some of its applications carry
catastrophic potential. And it appears to call for governance of a kind that markets do not supply on their own. None of
that is in dispute here.

The bend shows up at the mechanics. Nuclear weapons are state-controlled and capital-intensive, gated by access to
fissile material and the industrial base to enrich it. Frontier AI is built inside private companies, and its most
dangerous capabilities, as the past three months have shown, can emerge as a byproduct of general improvement rather
than a deliberate weapons programme. Attribution diverges too. A missile launch has a signature; a poisoned training set
or an extracted model does not. Deterrence assumes the actor can be found and that the actor fears retaliation. With AI
the actor may be a research group, a contractor, or a Discord server, and the harm may be invisible until after it
lands.

This is a part of the problem the analogy cannot absorb. Su and Jia (2025) and Khlaaf and Myers West (2025) both work
this seam from different directions, the first on the structural mismatch between non-proliferation logic and software,
the second on how defence-grade risk thresholds get quietly relaxed once a capability is framed as inevitable. The frame
is not neutral. It selects for certain policies and rules out others, and the ones it selects tend to centralise.

## April 2026

On 7 April 2026, Anthropic announced [Claude Mythos Preview](https://www.anthropic.com/glasswing) and declined to
release it. That second fact is the more interesting one. The model was described as having found thousands of
high-severity vulnerabilities across every major operating system and web browser, and the company's response was not a
product launch but a containment programme.

The numbers that survive scrutiny are worth stating carefully, because the loose ones have already started circulating.
The UK [AI Security Institute](https://www.aisi.gov.uk/blog/our-evaluation-of-claude-mythos-previews-cyber-capabilities)
ran its own evaluation and found that on expert-level capture-the-flag tasks, which no model could complete before April
2025, Mythos Preview succeeded 73 per cent of the time. AISI also built a 32-step corporate-network attack simulation it
calls "The Last Ones", estimated to take a human team around 20 hours. Mythos Preview is the first model to complete it
end to end, in 3 of its 10 attempts, averaging 22 of 32 steps across all runs. The next best model managed 16.

On exploit generation, Anthropic's
own [Firefox benchmark](https://www.tomshardware.com/tech-industry/artificial-intelligence/anthropics-latest-ai-model-identifies-thousands-of-zero-day-vulnerabilities-in-every-major-operating-system-and-every-major-web-browser-claude-mythos-preview-sparks-race-to-fix-critical-bugs-some-unpatched-for-decades)
reported the model converting identified vulnerabilities into working shell exploits 72.4 per cent of the time within
the Firefox JavaScript engine, with register control in a further 11.6 per cent. On the CyberGym
vulnerability-reproduction benchmark, the Glasswing page puts Mythos at 83.1 per cent against 66.6 per cent for the
next-best Anthropic model. The figure is the company's own, so it is worth holding as a claim rather than an independent
finding, but it sits close to the 83 per cent first-attempt rate
the [ECB](https://thenextweb.com/news/ecb-banks-cybersecurity-ai-mythos-elderson) cited when it called European banks
in.

The concrete discoveries are easier to verify than the rates.
Mozilla [patched](https://www.securityweek.com/claude-mythos-finds-271-firefox-vulnerabilities/) 271 vulnerabilities
surfaced by an early Mythos build in Firefox 150, though only around 40 reached CVE status and three were credited to
Claude in the advisory, which suggests most were lower-severity or hardening issues rather than 271 exploitable holes.
Anthropic's [own disclosure](https://www.helpnetsecurity.com/2026/04/08/anthropic-claude-mythos-preview-identify-vulnerabilities/)
describes a 27-year-old remote-crash bug in OpenBSD, a 16-year-old flaw in FFmpeg that automated tooling had reportedly
hit five million times without catching, and a 17-year-old remote code execution vulnerability in the FreeBSD NFS
server, CVE-2026-4747, which the company says it exploited to unauthenticated root with no human involvement after the
prompt.

The capability, on this evidence, is not marketing. What turned it into a political question almost immediately was not the
capability itself but the framing around it: what got shared, and with whom.

## Left outside the room

[Project Glasswing](https://www.anthropic.com/glasswing) is the containment programme. By Anthropic's account it
launched with twelve partners: Amazon Web Services, Anthropic, Apple, Broadcom, Cisco, CrowdStrike, Google, JPMorgan
Chase, the Linux Foundation, Microsoft, Nvidia, and Palo Alto Networks. A further group of more than 40 organisations
was given access to scan critical and open-source infrastructure. The company says it committed up
to $100M in usage credits and $4M in donations, $2.5M to Alpha-Omega and OpenSSF through the Linux Foundation and $1.5M
to the Apache Software Foundation.

Read the membership list as a map of where decisions sit. Eleven of the twelve are US corporations. The Linux
Foundation, the single non-profit, is US-based. The coalition is, by design, pre-political: no governments, no
international body, no treaty. That design has an honest rationale, which is speed. A dozen organisations can coordinate
by phone. What coordinates by phone does not scale to a continent, and it does not have a seat for anyone who was not in
the room at the start.

Europe was not in the room. By early May
the [Eurogroup](https://yellow.com/news/eurogroup-mythos-access-anthropic-banks) was raising access as an agenda item,
with no European government, regulator, or bank on the list. Spain's economy minister Carlos Cuerpo told reporters
before a Eurogroup meeting that the model could find vulnerabilities or backdoors across institutions in every sector,
not finance alone, and pressed for a European response. By late May
the [talks had stalled](https://hipertextual.com/inteligencia-artificial/europa-claude-mythos-temor-sistema-bancario/).
Christine Lagarde, speaking for the ECB, framed the asymmetry plainly: a capability available only to US firms divides
the playing field, and the ECB was
left [studying defences](https://www.globalbankingandfinance.com/ecb-studying-defences-against-mythos-powered-attacks-lagarde/)
against a model it could not see.

The detail that sharpens the point is that access was never actually controlled the way the programme implied. A Discord
group reportedly [obtained Mythos](https://www.sourcetrail.com/javascript/unauthorized-discord-access-to-anthropics-claude-mythos-triggers-fresh-ai-security-fears/)
through a third-party vendor and held it for around two weeks. So the operative distinction was never capable hands
versus incapable hands. European banks could not get in; an unauthorised chat group could. The gate was real for allies
and porous for whoever found the side door.

It is worth being precise about which complaint this is, because two are running close together. One is about autonomy:
Europe does not control a capability its own infrastructure depends on. The other is about security: that dependence
turns into exposure the moment the capability can be withdrawn, or selectively granted, by parties Europe does not
answer to. The first is uncomfortable. The second is the one with teeth, and the Discord episode is where it shows,
because the same arrangement that locked allied banks out left a side door open to whoever found it. A dependence
relationship reads as a sovereignty grievance right up until the access can be cut unilaterally, at which point it is a
security problem.

The gap that Glasswing does not close is the structural one. Discovery scales with compute. Remediation scales with
humans. Those two curves diverge, and the divergence is most of the next decade of open-source security. A temporary
credit commitment from one company does not bend the second curve, and it leaves the question of who funds the
maintainers exactly where it was.

## A European PoC (one of many already)

It is worth being modest about what this section can carry. Vulnforge is a proof of concept, not a Mythos competitor,
and treating it as one would repeat the overclaiming this essay is trying to avoid.

What it demonstrates is narrow and, I think, sufficient. It runs local, AI-assisted vulnerability scanning on ordinary
workstations using open-weights models. Nothing is sent to a US vendor; no third party logs what was investigated. The
pipeline keeps a tamper-evident record, so a finding can be traced to exactly what produced it. The operating principle
is that the model proposes and the code disposes: suggestions are checked by execution in an isolated environment rather
than trusted on the model's say-so. No cloud bill, no API key, no vendor dependency.

What it does not do is scale to Mythos-level capability or arrive production-ready. Claiming otherwise would be a
category error. The point it makes is about direction, not parity. The architecture Europe would need (local models,
auditable pipelines, no dependency on a gatekeeper) is buildable on hardware that already exists. Europe is not starting
from zero. Whether it scales depends on investment, and investment depends on whether the strategic frame treats this as
a priority or a hobby.

## US response: gatekeeping in two acts

The American policy response over June reads, from a European vantage, less like governance than like the management of
an export asset.

[Executive Order 14409](https://www.govinfo.gov/content/pkg/FR-2026-06-05/pdf/2026-11415.pdf), signed 2 June 2026 and
published in the Federal Register on 5 June, established a classified benchmarking process to decide when a model is a 
"covered frontier model", and a voluntary framework under which developers may give the government up to 30 days of
pre-release access before sharing a model with other trusted partners. It directed the Attorney General to prioritise
enforcement against AI-enabled computer crime under
the [existing statutes](https://regulations.justia.com/regulations/fedreg/2026/06/05/2026-11415.html), and set up a
voluntary AI cybersecurity clearinghouse through Treasury. What the order pointedly did not do, and says so in its own
text, is create any mandatory licensing, pre-clearance, or permitting regime. The mechanism is voluntary, classified,
and routed through national-security agencies. It is a framework for the US government to see frontier models first, not
a framework for governing them in the open.

Ten days later the second act removed any ambiguity about who counts as a partner. On 12 June the Commerce Department's
Bureau of Industry and Security issued
an [export control directive](https://fortune.com/2026/06/13/anthropic-disables-fable-mythos-export-controls-national-security-threat/)
ordering Anthropic to suspend access to Fable 5 and Mythos 5 for any foreign national, whether outside the United States
or inside it, including Anthropic's own non-citizen employees. Because nationality could not be filtered in real time
across cloud platforms,
Anthropic [disabled both models](https://www.aljazeera.com/news/2026/6/13/us-orders-anthropic-to-disable-ai-models-for-all-foreign-nationals)
for everyone. The stated justification was thin: a reference to a jailbreak, with no detailed written support, which
Anthropic characterised as a narrow misunderstanding and which at least
one [security researcher](https://www.techpolicy.press/did-the-us-government-just-set-an-ai-export-precedent-by-blocking-mythos/)
described as defensive research rather than a jailbreak at all.

There is a coherent case for the American position, and the essay is weaker if it pretends otherwise. A frontier model
that can build working exploits across every major system is, from Washington's vantage, not obviously different in kind
from advanced cryptography, missile guidance, or lithography tools, all of which sit under export control without anyone
calling it a betrayal of allies. A state that treats decisive cyber capability as a strategic asset will guard it like
one. The argument is rational on its own terms. It is also, for Europe, beside the point, because a rationale that is
sound from Washington does not make the resulting dependence any less of a problem for Frankfurt. The two can both be
true: the United States is acting in a defensible national interest, and that interest leaves European infrastructure
dependent on a switch it does not hold.

For Europe the content of the dispute is almost beside the point. A precedent is the message. A single directive, by
letter, can switch off access for every non-American on earth, allies included, with no notice and no recourse. The
export-control kill switch moved from theory to demonstrated fact in an afternoon. Whatever the merits of this
particular case, the capability now exists and has been used.

## Where the nuclear frame falls short for Europe

Deterrence is the load-bearing element of the nuclear settlement, and the version that holds it up depends on conditions
that AI does not reliably supply. Mutually assured destruction needs clear attribution, a survivable second strike,
broadly rational actors, and early warning. AI compromise sits closer to the opposite on each: attribution is often
impossible, a compromise can be invisible rather than survivable, the actors include corporations and non-state groups
whose incentives are not the duelist's, and sabotage carries no radar signature. None of that means deterrence vanishes.
It may survive in altered forms: deterrence by denial, the threat of economic retaliation, liability regimes, sanctions
on states that harbour malicious actors. What it suggests is narrower and harder to wave away: classical nuclear
deterrence does not transfer cleanly, and a policy that imports it wholesale inherits assumptions the environment has
already removed.

The arms-race shape is different too. Nuclear competition was a duel between a small number of states. The AI version is
closer to a free-for-all, with private labs, states, and criminal actors all in the field, and the private sector
dominant. Khlaaf and Myers West note that the overwhelming share of activity sits with private actors, which is
precisely the population the state-centric frame is least equipped to govern. The same authors track how risk thresholds
once reserved for defence systems get stretched or waved through once a capability is cast as existential and therefore
urgent. The existential register, in their reading, does some of the work of accelerating deployment rather than
restraining it.

There is also a quieter loss buried in the analogy. Nuclear weapons stayed under state control. The AI capability that
prompted all of this sits inside a company, and that company has been making decisions that are geopolitical in everything but name: who gets access, when to switch
it off, how to read a government letter. Anthropic did not seek that role,
and the export directive arguably forced its hand. The structural fact remains: decisions affecting European security
are being taken inside an American firm and an American agency, and the nuclear frame has no vocabulary for that because
under the nuclear frame it could not happen.

## Where the analysis points

I am wary of ending on a five-point plan, because the genre tends to launder uncertainty into confidence. So take these
as directions that the preceding analysis seems to support, rather than a programme anyone has costed.

The first is to stop modelling AI policy on non-proliferation. The frame imports assumptions (state control, working
deterrence, clear attribution) that do not hold, and it produces gatekeeping as a reflex. A frame that started from
decentralised development, private-sector dominance, and weak attribution would generate different instincts, and most
of them would point toward building capacity rather than negotiating for access to someone else's.

The second is that capacity has to be built rather than requested. The Mythos episode is a fairly clean demonstration
that asking does not work: Europe asked, the talks stalled, and an export directive then settled the matter. Vulnforge
is not the answer, but it points at the shape of one, local models, auditable pipelines, no dependency on a gatekeeper,
and that shape is fundable.
Mistral's [reported work](https://www.amlintelligence.com/2026/05/news-mistral-developing-cybersecurity-ai-model-for-european-banks-lacking-mythos-access/)
on a cybersecurity model for European banks suggests the market sees the same gap.

The third concerns who get regulated. The AI Act reaches further than its borders on paper: it binds providers placing
a model on the EU market and, through its output-based trigger, third-country providers whose model output is used in
the Union. A model trained in California and queried from a terminal in Frankfurt is, on the face of the text, in scope.
The gap is not jurisdiction but leverage. Asserting authority over a model whose weights, compute, and off-switch all
sit in the United States is a different thing from being able to act on that authority, particularly once the relevant
use falls into the national-security domain the Act largely steps back from. The territorial instinct behind the Act
assumed a thing that could be localised and held to account where it operated, and the Mythos episode is a fairly direct
demonstration of what happens when neither condition holds. If frontier labs now make decisions with security
consequences for other jurisdictions, the regulatory object may need to be the lab itself, treated closer to critical
infrastructure than to an ordinary vendor. That is a harder thing to do to a foreign company, which is part of why
building a domestic one is not a separate question from regulating the others.

The last is that red lines only function if someone draws and enforces them. The US has not stated clearly what an AI
red line is, and the export directive suggests the line is wherever national-security discretion decides it is on a
given Friday. Europe articulating its own standards, for what is acceptable and what is not, would at least make the
boundary legible, which is a precondition for it meaning anything.

## The choice, held open

By this point the question has quietly changed shape. It is no longer whether the nuclear analogy is accurate, which is
the argument the title invites and the least interesting one available. A frame can be broadly accurate and still be the
wrong thing to build a policy on, because a frame does not only describe, it selects. It rules some responses in and
others out, and the ones it favours here tend to centralise: a small club of capable powers, a gate, and a hand on the
gate that belongs to someone else. The question worth asking is whether Europe wants the arrangements that frame tends
to produce, now that the past three months have shown what they look like in operation.

The nuclear frame offers Europe a settled story with a fixed place in it: customer, not partner. The protection on offer
is a deterrence built for a different problem, and the seat on offer is in a club Europe did not join. The events of
April through June did not break that frame so much as reveal what accepting it costs. Access can be granted and revoked
by people Europe does not elect, on grounds Europe is not shown, at a speed that leaves no room to respond.

Whether the alternative, the slow and expensive work of building capacity, is one Europe will actually choose is
genuinely open. It is easier to keep asking. The question the Mythos episode leaves is only whether the asking has
finally produced enough evidence about its own futility to change the behaviour, or whether the comfort of the old frame
outlasts the proof that it no longer fits.
