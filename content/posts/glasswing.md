---
title: "The Glasswing problem"
date: 2026-04-25
description: "The framing was unmistakable. We have built something dangerous. We are choosing not to release it. Be grateful that we are the ones who built it. Why both halves of that framing deserve more scrutiny than they have received, and why the genuinely interesting story, the structural one, has been almost entirely buried under coverage of the headline numbers."
tags:
  - AI Security
  - Cybersecurity
  - zero-day
  - Glasswing
  - responsible disclosure
draft: false
cover:
  image: "/images/monolith.png"
  alt: "A colossal cracked black monolithic slab" 
  caption: "This image is not a butterfly"
  relative: false
---
#AISecurity #Cybersecurity #ZeroDay #ProjectGlasswing #ResponsibleDisclosure
On 7 April 2026, Anthropic announced two things at once. The first was a new frontier model called Claude Mythos 
Preview. The second was [Project Glasswing](https://www.anthropic.com/project/glasswing), a coalition of twelve 
technology and finance companies that would receive 
[controlled access to that model](https://venturebeat.com/technology/anthropic-says-its-most-powerful-ai-cyber-model-is-too-dangerous-to-release), 
with everyone else, including paying API customers, locked out indefinitely.

The [accompanying blog posts from Anthropic's red team](https://red.anthropic.com/2026/mythos-preview/) made a 
remarkable claim: Mythos Preview, given an isolated container and a vague prompt, had autonomously discovered 
thousands of zero-day vulnerabilities across "every major operating system and every major web browser": a 27-year-old 
denial-of-service bug in OpenBSD's TCP stack, a 17-year-old remote code execution flaw in FreeBSD's NFS server, fully 
weaponised end-to-end. A 16-year-old vulnerability in FFmpeg's H.264 codec that had survived every fuzzer and every 
human reviewer to look at the code since 2010. In Mozilla Firefox alone, the model surfaced 271 zero-days, shipped as 
fixes in Firefox 150, the largest single batch of security fixes in the browser's history.

## The numbers, briefly

Before getting to what could be wrong with the framing, the underlying capability seems real and worth taking seriously.

Anthropic's own technical post is careful in places that the marketing summary is not. The team ran Mythos Preview 
against the OSS-Fuzz corpus, roughly a thousand open-source repositories, using a stripped-down agentic harness: 
launch a container, prompt the model to find a security vulnerability, let it work. The model reads source, forms 
hypotheses, runs the binary, attaches debuggers, and produces a bug report with a proof-of-concept. No specialised 
scaffolding, no fine-tuning, no custom prompts. Anthropic explicitly notes that the cybersecurity capabilities were 
not trained for. They emerged as a side effect of general improvements in code reasoning and agentic autonomy. The 
same improvements that make the model better at writing patches make it better at writing exploits. 
Worth keeping in mind.

On the headline benchmark, turning identified vulnerabilities into working exploits in Firefox's JavaScript shell, 
Mythos apparently achieves a 72.4% conversion rate, with register control in another 11.6% of attempts. In one 
demonstrated case, the model was reported to write an exploit chaining four separate vulnerabilities into a JIT heap 
spray that escaped both the renderer and OS sandboxes. That is the kind of work that, until recently, only a 
handful of humans on the planet could do, and most of them charge by the hour.

So: the capability is probably real. The question is what to do with that observation, and Anthropic's answer, 
Project Glasswing with twelve members, one hundred million dollars in usage credits, and four million in donations 
to open-source security organisations, is more revealing than it first appears.

## Small models can do a lot of this already

Within days of the Mythos announcement, AISLE, a security firm that has been running its own AI vulnerability 
discovery system for over a year, 
[published a quiet but devastating response](https://aisle.com/blog/ai-cybersecurity-after-mythos-the-jagged-frontier). 
They took the specific bugs Anthropic had showcased, isolated the relevant code, and ran it through small, cheap, 
open-weights models. Eight out of eight models detected the flagship FreeBSD NFS exploit, including one with 
3.6 billion active parameters costing eleven cents per million tokens. A [5.1B-parameter open model](https://github.com/EleutherAI/pythia) recovered the 
core chain of the 27-year-old OpenBSD bug. On a basic security reasoning task, small open models outperformed most 
frontier models from every major lab.

AISLE was careful not to claim Mythos is not capable. It almost certainly is, especially on the exploitation side, 
where chaining four vulnerabilities into a sandbox escape is genuinely frontier work. The claim was narrower and 
harder to wave away: the *discovery* side of the problem, looking at code and saying "this is a stack buffer 
overflow with remote-code-execution potential", is broadly accessible right now, in models you can run on your laptop. 
The exclusivity Anthropic implies around Mythos is real for the highest-end exploitation work and likely substantially 
overstated for everything else.

[Tom's Hardware put it more bluntly](https://www.tomshardware.com/tech-industry/artificial-intelligence/anthropics-latest-ai-model-identifies-thousands-of-zero-day-vulnerabilities-in-every-major-operating-system-and-every-major-web-browser-claude-mythos-preview-sparks-race-to-fix-critical-bugs-some-unpatched-for-decades): 
claims of "thousands" of severe zero-days rest on a much smaller number of manually reviewed cases, around 198 by 
their count. The 271 Firefox bugs are real and shipped. The "thousands" figure is partly a model-output count, 
not a count of independently verified vulnerabilities, and the gap between those two things in the AI security world 
is larger than press releases typically admit.

There is also the [structural critique from Forrester](https://www.forrester.com/blogs/project-glasswing-the-10-consequences-nobodys-writing-about-yet/). 
Glasswing surfaced vulnerabilities that were 16 and 27 years 
old in projects maintained by small volunteer teams while remediation capacity in open source does not 
scale with it. It remains human, finite, underpaid, and largely voluntary.

The framing of Mythos as a uniquely dangerous artefact requiring a coalition treaty to govern 
starts to wobble once you accept that the capability is diffusing fast and broadly. If a [3.6B-parameter open model](https://github.com/EleutherAI/pythia) 
can spot the same FreeBSD bug, the question of who has access to Mythos specifically is less consequential than who 
has access to last year's open-weights checkpoint and a copy of the FreeBSD source tree. The latter group is, 
roughly, anyone with an internet connection and an afternoon.

## The timing

Anthropic announced Project Glasswing on 7 April. The same week, the company disclosed an annualised revenue run 
rate above thirty billion dollars, up from nine billion at the end of 2025, announced a 
[multi-gigawatt compute deal with Google and Broadcom](https://www.anthropic.com/news/google-broadcom-partnership-compute), 
and [had been working toward an IPO since 2025](https://marketwise.com/investing/anthropics-ipo-get-set-for-it-to-light-up-an-already-scorching-ai-industry/). 
A high-profile, government-adjacent cybersecurity programme with blue-chip partners (AWS, Apple, Microsoft, Google, JPMorgan Chase, 
the Linux Foundation) is exactly the kind of narrative that burnishes a public-offering prospectus.

This isn't a gotcha. Strategic self-interest and genuine security value can coexist; restricted access really does 
make adversarial distillation harder, really does give defenders a head start, really is what a responsible lab would 
do if it believed its own capability claims. The point is only that "we built something too dangerous to release" 
carries different weight when the alternative would have been releasing it commercially into a market where 
competitors are pricing similar capability at substantially lower margins.

It's also worth noting that the announcement landed in a slightly less than pristine context. 
[News of Mythos first leaked in March](https://cybersecuritynews.com/anthropic-claude-mythos/) when draft 
documentation was inadvertently stored in a publicly accessible cache through human error. Days later, 
[Anthropic accidentally exposed](https://arstechnica.com/ai/2026/03/entire-claude-code-cli-source-code-leaks-thanks-to-exposed-map-file/) 
nearly 2,000 source code files and over half a million lines of code from Claude Code for 
about three hours through a separate misconfiguration. Already in October 2025, security researchers documented 
that Claude Code would [arbitrarily ignore user-configured deny rules for file access](https://github.com/anthropics/claude-code/issues/8961) 
with inconsistent behaviour, sometimes blocking a denied file and other times reading or modifying it without permission. 
Then in April 2026, a second, more specific flaw was publicly disclosed: [Claude Code silently stops enforcing deny 
rules when a command contains more than fifty subcommands](https://www.cryptika.com/critical-claude-code-flaw-silently-bypasses-developer-configured-security-rules/). 
A developer who blocks `rm` will see it blocked when run alone, but that same `rm` command will run unrestricted when 
chained after fifty harmless statements. This second issue has since been formally addressed by Anthropic in 
[Claude Code version 2.1.90](https://github.com/anthropics/claude-code/releases/tag/v2.1.90), while the earlier 
inconsistent permissions behaviour remains unresolved in the [linked GitHub thread](https://github.com/anthropics/claude-code/issues/8961).

The optics of an AI security lab having operational security incidents in the run-up to announcing a security 
initiative are something the press has been generous in not dwelling on. Glass houses, etc.

None of this invalidates the underlying capability. It does suggest the announcement is doing rhetorical work that 
the technical post is not, and that the line between "responsible disclosure of capability" and "controlled product 
launch with a security framing" is blurrier than the framing wants to admit.

## What is new, and why it breaks more than it fixes

Set the framing aside. Even if you take Anthropic's restraint at face value, and there are reasons to, since they are 
visibly forgoing revenue, the more interesting story is what AI vulnerability discovery does to a security ecosystem 
that was already creaking before any of this started.

A few numbers, from sources outside the Anthropic announcement.

[CVE volume increased 35% between 2024 and 2025](https://www.cve.org/About/Metrics), and that figure undercounts the 
actual discovery rate because not every bug earns a CVE. As of March 2026, the 
[NVD carried a backlog of 30,000 unanalysed vulnerabilities](https://www.kiteworks.com/cybersecurity-risk-management/data-layer-security-nvd-mythos/). 
[Google's M-Trends 2026 report](https://cloud.google.com/blog/topics/threat-intelligence/m-trends-2026/) estimates 
the mean time to exploit newly disclosed vulnerabilities at *negative seven days*: exploitation typically occurs 
before a patch exists. In the same month Anthropic announced Glasswing, 
[HackerOne suspended new submissions to its Internet Bug Bounty programme after AI-generated reports](https://www.darkreading.com/application-security/ai-led-remediation-crisis-prompts-hackerone-pause-bug-bounties), 
a mix of genuine discoveries and low-quality submissions, overwhelmed both triage capacity and remediation across 
the open-source ecosystem.

Read those numbers in the order they appear. The system was already in distress. Then AI-augmented discovery showed up.

Here's the structural problem nobody wants to look at directly. Anthropic's own data point is that [less than 1% of 
the vulnerabilities Mythos has discovered have been patched](https://red.anthropic.com/2026/mythos-preview/). 
They have adopted a 90+45-day disclosure timeline (ninety days for the maintainer to ship a fix, plus forty-five days 
before publishing technical details) and use SHA-3 commitment hashes to prove possession of bug details without 
revealing them. This is well-designed by the standards of human-paced disclosure. It is also, as Anthropic's own 
red team admits, probably inadequate. 

The Cloud Security Alliance (CSA), 
[in an emergency briefing produced with SANS Institute and over 250 CISOs](https://labs.cloudsecurityalliance.org/mythos-ciso/), 
concluded that "current patch cycles, response processes, and risk metrics were not built for this environment," 
warning that "the time between disclosure and weaponisation is compressing toward zero". Industry-standard windows 
were calibrated for a world where individual researchers found vulnerabilities at the speed of human attention. 
Mythos finds them at the speed of an agentic loop.

The 16-year-old FFmpeg bug and the 27-year-old OpenBSD bug were both found in projects maintained by small volunteer 
teams. FFmpeg's core maintainer team can be counted on one hand. Open source in general is 
[famously security-focused AND famously under-funded](https://fossforce.com/2026/02/sudo-heartbleed-and-the-lessons-we-still-havent-learned/). 
Anthropic's four-million-dollar donation to open-source security organisations is genuine and welcome, 
and it is also a rounding error against the remediation capacity that an industrialised vulnerability discovery 
pipeline implies. Discovery scales with compute. Remediation scales with humans. The gap between those two curves 
is the next decade of open-source security.

This is the part of the Forrester analysis that is closest to right: Mythos turns vulnerability management from a 
discovery problem into a maintenance-capacity problem. The bottleneck is no longer "who can find the bug" but 
"who is qualified to fix it without introducing a regression, and how do we pay them". Without a shift in where the 
money goes, critical open-source projects risk replaying 
[the COBOL problem](https://www.metaintro.com/blog/cobol-developer-shortage-legacy-systems-career-opportunity-2026) at 
speed: indispensable code, no sustainable maintenance model, growing technical debt that can no longer be ignored 
because an AI agent will surface it on demand for anyone who asks.

## Glasswing as a treaty

The most useful frame for what Project Glasswing actually is comes from outside Anthropic's own materials: it's not a 
product launch, it's closer to a treaty. Twelve organisations chosen for two qualities: they own enough critical 
infrastructure that broad zero-day discovery in their products serves the public good, and they have the institutional 
capacity to manage their own ecosystem of disclosures responsibly. Microsoft can patch its own products at scale 
and help downstream maintainers cope. So can Apple, Google, the Linux Foundation. JPMorgan Chase is the slightly 
weirder member of the list, and worth thinking about as a signal: financial-sector critical infrastructure is now 
considered comparable in priority to operating systems and browsers.

This treaty framing has two implications most coverage missed.

First, the coalition is deliberately pre-political. There is no government in it. There is no international body 
governing membership. The Linux Foundation is the only member without a profit motive, and it is a US-based 501(c)(6). 
Anthropic has stated an intention to eventually transition governance to "an independent, third-party body 
coordinating cybersecurity projects across private and public sectors", which is the kind of phrase that means 
"we haven't figured this out yet". The current structure works because twelve organisations can coordinate by phone. 
It is not a structure that scales to fifty, or to participants outside the US/Western tech sphere, or to 
nation-state actors with their own AI capabilities and their own ideas about disclosure norms.

Second, Glasswing is openly temporary. Anthropic has not committed to keeping Mythos restricted; they've committed to 
not releasing *this* model commercially while their competitors catch up. 
[OpenAI classified GPT-5.3-Codex as "High Cybersecurity Capability"](https://itecsonline.com/post/gpt-5.3-codex-released) 
under their own Preparedness Framework in February 2026, the first model any major 
lab explicitly labelled that way, and has since released GPT-5.4-Cyber through a similar restricted-access pilot 
called [Trusted Access for Cyber](https://healsecurity.com/openai-expands-cyber-defense-program-with-gpt-5-4-cyber-access-for-trusted-organizations/), 
with ten million dollars in API credits for vetted defenders. Google has 
[Big Sleep](https://thehackernews.com/2025/07/google-ai-big-sleep-stops-exploitation.html) and 
[CodeMender](https://deepmind.google/blog/introducing-codemender-an-ai-agent-for-code-security/) doing 
internal vulnerability discovery and patching, with seventy-two security fixes already upstreamed to open-source 
projects. AISLE found twelve out of twelve CVEs in the [January 2026 OpenSSL coordinated release](https://securityaffairs.com/187445/security/openssl-issued-security-updates-to-fix-12-flaws-including-remote-code-execution.html).

This is an industry-level structural shift, not a one-company event. The interesting analytical question is not 
"is Mythos as dangerous as Anthropic says" but "what happens in eighteen months when every frontier lab has a 
Mythos-class model and the capability has diffused into the open-weights ecosystem at the level AISLE has already 
demonstrated".

## What defenders can actually do

The forward-looking part of this is less dramatic than the announcement and more useful. A few things follow 
reasonably directly from the trajectory.

The traditional patch-cycle assumption (find a bug, ninety days, ship a fix) is over. Google's "negative seven days" 
mean-time-to-exploit number is not an artefact of measurement; it's the structural state of the world when both 
attackers and defenders have access to LLM-augmented discovery. Defensive playbooks built around the assumption 
that exploitation comes after disclosure may need rewriting around the assumption that exploitation comes before 
disclosure. This is uncomfortable because it implies that compensating controls (runtime detection, segmentation, 
exploit mitigation hardening, monitoring) matter more than patch latency, and most organisations have invested the 
opposite way for the last decade. Awkward.

Vulnerability triage capacity, not vulnerability discovery, is the binding constraint. A team set up to handle a 
thousand findings per quarter, whose scanner vendor integrates 
[AI-augmented discovery](https://checkmarx.com/blog/stop-manual-triaging-start-agentic-fixing/) and starts surfacing ten 
thousand, does not have a security improvement; it has an unprioritised pile that creates [legal liability through 
documentation](https://thehackernews.com/2026/03/what-boards-must-demand-in-age-of-ai.html). 
[ArmorCode's framing of contextual risk scoring](https://www.armorcode.com/blog/reduce-risk-at-enterprise-scale-from-alert-fatigue-to-strategic-security) 
as a way to prevent "AI-scale discovery" from becoming "AI-scale noise" is essentially correct, even allowing for 
the vendor pitch. [The contextual layer](https://www.upguard.com/blog/context-gap-time-lost-to-investigation) 
(what asset is this on, what data does it touch, what compensating controls exist) becomes the load-bearing component 
of the security programme.

The combination of AI agents and traditional SAST tools matters more than either in isolation. 
[A 2026 study](https://browse-export.arxiv.org/abs/2602.05868) found 
that Semgrep's per-sample assessment accuracy against expert judgement was 65%, and CodeQL's was 61%. Aggregate 
numbers looked fine; per-sample accuracy told a different story. Coding agents on a twenty-dollar-a-month subscription 
will surface things the paid scanners miss, and vice versa. Anyone running one without the other has gaps they cannot 
see, and those gaps are only going to widen [as both layers improve at different rates](https://bsg.tech/blog/ai-appsec-agentic-security-tools-2026/).

For open-source maintainers specifically, the math is harder. The realistic entry points right now are programmes 
like [Anthropic's Claude for Open Source](https://dataconomy.com/2026/03/30/anthropic-offers-free-claude-max-access-to-open-source-developers/) 
(qualifying threshold around 5,000 GitHub stars or 1M monthly NPM downloads) 
and [Google's CodeMender outreach](https://deepmind.google/blog/introducing-codemender-an-ai-agent-for-code-security/) 
to maintainers of critical projects. Neither programme reaches the long tail of 
small but security-critical projects, and the long tail is where the 16- and 27-year-old bugs were found. The 
question of how to fund security work on packages that twelve people maintain in their spare time but that secure 
a third of the internet has been live for a decade. AI vulnerability discovery is what makes it [impossible to keep 
deferring](https://securitybrief.co.uk/story/linux-foundation-secures-usd-12-5m-for-ai-security).

## Where this leaves us

Two things, held together a bit uncomfortably.

The first is that Anthropic deserves credit for visible restraint. Building a model with significant offensive 
capability and choosing not to ship it commercially is unusual behaviour in a competitive AI market, and it's worth 
acknowledging as such even if the restraint is also commercially convenient. The Project Glasswing structure is a 
serious attempt at a difficult problem, and the alternatives (release it, or quietly use it internally) would both 
have been worse. The hundred million dollars in usage credits is a real subsidy of defensive work, and the four 
million in donations is a real if inadequate gesture toward maintainer capacity.

The second is that the framing of the announcement obscures more than it reveals. The capability is not as exclusive 
to Mythos as the announcement implies; small open-weights models recover much of the discovery side at trivial cost. 
The disclosure architecture is well-designed for human pacing and inadequate for AI pacing, and Anthropic's own 
red team says so. The remediation bottleneck, the part of the system that actually closes vulnerabilities once they 
are found, is structurally underfunded in a way that no twelve-organisation coalition can fix. And the treaty model 
that Glasswing represents is openly temporary, scaling poorly, and pre-political in a way that won't survive the 
next eighteen months of capability diffusion.

The honest summary is something like: the technical capability is real, the announcement is doing more 
rhetorical work than the technical post supports, and the genuinely interesting questions (what disclosure norms 
look like at AI pace, how open-source maintenance gets funded when discovery is industrialised, what happens when 
nation-state actors have their own Mythos-equivalents) have barely been engaged with in the public conversation.

Project Glasswing is a starting point, in roughly the way Anthropic itself describes it. The thing worth watching is 
not the coalition. It's what fills the space around it.

*If you write about AI security and want to argue with any of this, the most interesting disagreements are probably about where the bottleneck actually sits (discovery, triage, or remediation) and what the right policy response looks like at each layer. I don't have settled views on the third question and would like to.*

