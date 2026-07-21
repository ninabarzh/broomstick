---
title: "The phrase survived. The definition did not."
description: "On defence in depth, and what the phrase originally defined: real depth means each successful compromise changes the attacker's problem."
tags: [ "defence-in-depth", "security-architecture", "ot-security", "engineering-claims" ]
draft: false
date: 2026-07-21
cover:
  image: "/images/language-defence-in-depth.png"
  alt: "Cross-section illustration of a medieval castle's concentric defences seen from above at a slight angle: moat, outer wall, gatehouse, courtyard, inner keep"
  relative: false
---

Consider a medieval castle. It is tempting to imagine that its security rested on the thickness of its walls, and that a
besieging army faced essentially one problem, repeated: get past the stone. But that is not how a defended position
worked, and the people who built them knew it.

A castle was arranged so that every successful advance exposed the attacker to a new disadvantage. The moat forced
engineering work under fire. The wall forced escalade or breach, both slow, both loud, both costly in men. The gatehouse
compressed the attackers into a killing corridor where their numbers stopped helping them. The courtyard beyond it was
overlooked from every side, so that taking the gate meant standing in the open beneath defenders who had been waiting
for exactly this. And the inner keep meant that even total success outside its walls bought the attacker another siege,
on worse ground, with a depleted force.

None of these layers existed because someone believed more layers were better. Each one changed the geometry of the
attack. Each imposed a cost. Each bought time. Each forced the attacker into conditions the defender had chosen. The
position was designed around a single organising question: what does each successive layer force the attacker to do?

That is the principle of defence in depth, though not yet the name. The phrase is a twentieth-century one, from the
industrial battlefields where armies gave up the single trench line for successive defensive zones. The castle had been
building the idea into stone for centuries before anyone thought to name it.

Cybersecurity borrowed [the
phrase](https://www.ncsc.gov.uk/collection/operational-technology/secure-rf-communications/principle-9). It quietly
forgot the definition.

## Layers are not the point

The phrase has become something people recognise rather than examine. They say it approvingly, in architecture reviews
and audit responses and vendor decks, and very rarely ask the question the military origin would have asked first. What
does each successive layer force the attacker to do? If the answer is nothing, there aren't layers. There are
decorations.

Multiple controls do not automatically create depth. Depth exists only when successive controls satisfy conditions that
turn out to be surprisingly demanding. They need to be independent, so that the failure of one does not imply the
failure of the next. They need to be differently vulnerable, so that the technique which defeated the first is useless
against the second. They benefit from being able to detect the failure of what came before them, because a layer that
cannot tell it is now the front line behaves as though it is still safely in the rear. And each one needs to force new
attacker effort: new tooling, new access, new noise, new risk of discovery.

Measured against those conditions, a great deal of what passes for depth thins out considerably. A firewall behind
another firewall is not necessarily depth; if both fall to the same misconfiguration class, they are one layer drawn
twice. Two antivirus products are rarely depth; they tend to share signature economics, evasion techniques, and blind
spots. Three identity systems that all ultimately defer to the same [Active Directory
forest](https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/plan/appendix-a--reviewing-key-ad-ds-terms) are
certainly not depth. They are one point of failure with three logos.

Depth is about changing the attacker's problem. It is not about enlarging the architecture diagram. The two can look
identical from the defender's side of the drawing, which is rather the difficulty.

## Military doctrine cared about cost

It is worth going back to the origin, which is more recent and more specific than the castle. The modern doctrine took
shape on the Western Front, in the German [defence organised in depth](https://edoc.hu-berlin.de/handle/18452/16336)
that gave up the forward line for a system of belts and counterattacks, so that every metre the attacker took cost him
more than the last. It contains an assumption that cybersecurity has been reluctant to inherit. Military defence assumes
that every layer will eventually fail. Not might. Will. The wall is going to be breached, on a long enough siege, and
the doctrine is entirely comfortable with this, because the question was never "can this wall hold forever?" The
question was "what happens after it doesn't?"

In a well-designed position, every successful attack becomes harder than the one before it. The attacker who takes the
outer wall has spent men, time, and equipment to arrive somewhere worse: overlooked, channelled, further from resupply,
and facing defenders who now know exactly where he is. Success is supposed to be expensive, and each success more
expensive than the last, not merely a milestone passed on the way to the objective. And expense, in the doctrine's
accounting, was never only casualties: it was time, ammunition, logistics, information surrendered, fatigue accumulated,
morale worn thin.

This is precisely where many cyber architectures quietly fail, and the failure has a recognisable shape. Once one
credential is compromised, everything after it trusts it. The attacker who phishes a session does not encounter a new
problem at the next layer; the next layer greets the stolen token as an old friend. Authentication was the wall, and
behind the wall the courtyard turns out to be furnished, well-lit, and unguarded, on the theory that anyone standing in
it presumably belongs there. The remaining layers become scenery: present, catalogued, compliant, and irrelevant to the
path actually being walked.

The military designer would call this a position with a strong outer work and nothing behind it, and would not call it
deep, however many structures appeared on the plan.

## Interaction beats accumulation

Organisations [inventory controls](https://purple.tymyrddin.dev/docs/audits/iso27001/gear-depot/). Attackers [experience
systems](https://red.tymyrddin.dev/docs/through/evasion/notes/attack-chain/). These are not two views of the same
object; they are different objects.

An inventory is additive. Each control is assessed on its own terms, found adequate, and counted. The list grows, and
the growth feels like progress, because in an inventory it is. But an attack path is not experienced as a list. It is
experienced as a system, and systems have the awkward property that their behaviour emerges from interaction rather than
accumulation. Ten excellent controls can combine into one weak system, if they share assumptions, trust each other's
outputs, or all stand behind the same authentication event. Three modest controls can combine into a genuinely resilient
one, if each fails differently and each failure is visible to the others.

Interaction is what does the work. Not count. Security architectures have emergent properties. Control catalogues do
not, and a catalogue is what most depth claims are actually describing.

## Negative space

If there is a single question that separates real depth from its portrait, it might be this one, asked of the whole
architecture at once: what assumptions do all the layers share?

Not what does each layer defend against. What do they all rest on? The answers, in most environments, arrive quickly and
are uncomfortable. A shared identity provider. Shared DNS. Shared administrators, whose workstations touch everything. A
shared cloud tenant. Shared monitoring, and shared logging, so that the system's ability to notice its own compromise
travels through [one pipeline](https://blue.tymyrddin.dev/docs/diy/server/runbooks/centralised-logging/). A [shared
supply chain](https://blue.tymyrddin.dev/docs/ot/incidents/havex/). A shared time source, which is a stranger dependency
than it first appears, since so much of authentication and correlation silently assumes the clocks agree. And, least
visible of all, shared thinking: the same threat model, held by the same people, embedded in every layer they designed.

Because no individual control owns these assumptions, no individual control assessment tends to discover them. These
common dependencies are the negative space of the architecture, the part no diagram draws, and they flatten the apparent
depth into a single point of failure. Ten layers resting on one substrate have the depth of the substrate. The castle
analogy holds here too, unkindly: it does not much matter how many walls stand between the attacker and the keep if
every wall is keyed to the same gate, guarded by the same garrison, and built on the same foundation the attacker has
learned to undermine. Depth disappears not because any layer is weak, but because everything rests on one thing, and the
attacker has found it.

## Defence in depth versus bureaucracy in depth

Many organisations, asked to demonstrate depth, proudly present a stack. MFA. EDR. SIEM. SOAR. DLP. CASB. PAM. XDR. The
list grows year-on-year, each acronym its own procurement, its own dashboard, its own line in the audit response. It
reads as formidable. It is certainly expensive.

Then the attacker [steals a session
cookie](https://www.ncsc.gov.uk/news/star-blizzard-continues-spear-phishing-campaigns), and most of the stack quietly
becomes irrelevant. Not defeated; nothing so dramatic. Simply not consulted. The MFA already happened, upstream of the
theft. The identity layer sees a valid token. The alerting layers see a user doing user things. The attack proceeds
along a path that intersects perhaps two of the eight acronyms, and neither of those two knows anything is wrong.

The architecture was layered. The attack path wasn't. That is the whole distinction, and it suggests a name for what has
actually been built in many of these environments. Not defence in depth. Bureaucracy in depth: an arrangement in which
every control is present and individually defensible, and in which the attacker's experience is nonetheless of moving
through open country. The layers satisfy the auditor. The attacker meets a different building.

## OT remembered something

There is one corner of the field where the original meaning survived, largely because it was never imported through
cybersecurity at all. Industrial systems did not set out to implement defence in depth. They arrived at it as a
by-product of how engineering has always handled dangerous processes, and the principle they arrived at can be stated in
one line: OT never relied on copies of the same protection. It relied on different physical realities.

Each thing standing between a compromised control system and a disaster exists in a different domain, obeys different
rules, and fails for different reasons. The networks are genuinely apart, not merely logically adjacent. The [safety
instrumented system](https://red.tymyrddin.dev/docs/in/ot/notes/safety/) runs its own logic on its own hardware,
designed by people who assumed the basic process control would fail and planned for the day it did. The mechanical
interlock holds regardless of what any computer believes; it fails as metal, not as software. The analogue gauge reports
the pressure actually in the pipe, and the operator watching it is entitled, indeed expected, to distrust the screens.
Behind all of it, the emergency shutdown exists to [bring the process to a safe
state](https://blue.tymyrddin.dev/docs/ot/incidents/triton/) even when everything upstream is lying.

The consequence is exactly the property that layered cyber stacks can lack. The interlock does not care that the SIS was
bypassed. The operator does not care that the alarm server is compromised, because the gauge is analogue and the pipe is
audibly wrong. An attacker who defeats one of these arrives at the next facing a genuinely new problem, often in a
different discipline entirely, which is a very expensive kind of progress.

That is what the military people meant. It survived in OT because process safety engineers never trusted metaphors in
the first place. They [counted failure modes](https://www.icheme.org/media/12368/4-lopa-introduction.pdf).

## A depth test

The whole argument reduces to four checks.

1. If this layer fails, what genuinely new problem appears for the attacker?
2. If the answer is "none", there isn't another layer.
3. If the answer is "the same problem again", there also isn't another layer.
4. If defeating the next layer takes the same capability that defeated this one, the two are probably one layer, drawn
   twice.

Run against a real architecture, the test tends to shorten the list of layers considerably. Whatever survives is the
depth.

## Keeping the layers, misplacing the cost

None of this is an argument that the phrase is wrong. "Defence in depth" captured a real piece of engineering insight,
and for a while it did useful work: it pushed organisations past the fantasy of the single perfect control. The trouble 
began when the metaphor started to be taken more seriously than the engineering underneath it, at which point "depth"
quietly came to mean "quantity", and the organising question was misplaced.

Defence in depth was never an instruction to accumulate controls. It was an instruction to make every success more
expensive than the last. Depth is not measured by how many controls appear on the architecture diagram. It is measured
by how many new problems the attacker encounters after the first one fails.

Somewhere along the way, we kept the layers and misplaced the cost. The layers were always the easy part.
