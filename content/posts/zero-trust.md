---
title: "The trouble with calling it zero trust"
date: 2026-07-20
draft: false
description: "The engineering claim behind zero trust is modest and sound. The name is neither. On what happens when a technical term borrows an ordinary word, and organisations organise around the metaphor."
tags:
  - security
  - trust
  - language
  - organisations
  - OT
  - zero-trust
cover:
  image: "/images/language-zero-trust.png"
  alt: "A walled medieval city at dusk seen from slightly above, gates standing open, lantern-lit lanes, guild banners hanging from timbered houses, small figures greeting one another at the gate and leaning from windows to watch a lone stranger in the lane. One long section of the city wall has been replaced by an incongruous row of sleek modern turnstiles and a faint blue-glowing server cabinet."
  relative: false
---

A medieval city was never secured by its wall alone. It had guilds that vouched for their members, letters of
introduction carried from town to town, gate guards who knew faces, innkeepers who noticed accents, and neighbours who
registered a stranger in the lane before any official did. The wall was one instrument among many, and arguably not the
most effective one. What kept the city safe was a dense weave of overlapping trust relationships, most of them informal,
all of them cheap (in financial terms).

Trust may be one of civilisation's least expensive technologies. It lets people coordinate without drafting a contract
for every interaction, a transaction cost in the sense [Coase](https://doi.org/10.1111/j.1468-0335.1937.tb00002.x) gave
the term. Societies with high levels of it appear to spend less on verification, oversight, and enforcement, and to get
more done with the savings.
[Fukuyama](https://www.academia.edu/8928126/Trust_The_Social_Virtues_and_the_Creation_of_Prosperity_by_Francis_Fukuyama)
built his account of national prosperity on that observation. Organisations function for the same reason: colleagues
routinely extend each other credit, admit mistakes, lend judgement, and occasionally bend procedure because reality
insists. Verification is the expensive alternative, and complete verification is impossible, which is why trust exists
at all: every functioning organisation chooses, mostly unconsciously, where verification ends and trust begins. Security
architectures can move that boundary. They cannot eliminate it. If a consultant walked into a boardroom and proposed
eliminating trust from the organisation, the proposal would be recognised at once as absurd, and probably as sinister.

The curious thing about "zero trust" is that it appears to propose exactly that.

Except it doesn't. The word trust is carrying at least two meanings here, and the distance between them is where
everything interesting in this story happens.

## What the phrase was meant to do

The term has an author and a birthday. John Kindervag, then an analyst at Forrester Research, published [*No More Chewy
Centers: Introducing The Zero Trust Model of Information
Security*](https://media.paloaltonetworks.com/documents/Forrester-No-More-Chewy-Centers.pdf) in September 2010. The
title refers to an old joke in the field: that networks were built like a certain chocolate sweet, hard and crunchy on
the outside, soft and chewy in the middle. The perimeter was fortified; everything behind it was assumed benign.
Kindervag's diagnosis was that this trust model was broken at the root. Firewalls had a trusted interface and an
untrusted interface, and the labels were doing work the underlying reality could not support. Packets, he observed, are
not the kind of thing trust applies to.

He was not the first to notice. The Jericho Forum, a mostly European group of corporate security officers, had been
arguing since 2004 that the perimeter was already dissolving under the weight of outsourcing, mobility, and
intercompany connectivity, and that survival lay in what they
called [de-perimeterisation](https://collaboration.opengroup.org/jericho/commandments_v1.2.pdf). And the engineering
world caught up in its own way when Google published
the [BeyondCorp papers](https://research.google/pubs/beyondcorp-a-new-approach-to-enterprise-security/) from 2014
onwards, describing how the company was moving its internal applications off a privileged network. Access decisions
would rest on who the user was and what state their device was in, rather than on where the request came from. In
2020, NIST attempted to fence the term formally
in [Special Publication 800-207](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-207.pdf), defining
zero trust architecture in terms of resources, requests, and continuous evaluation.

Strip the branding away and the engineering claim is almost disappointingly modest. Network location is not an identity
claim; it is an accident of topology. A packet arriving from the corporate LAN inherits the credibility of the LAN,
which is to say the credibility of whichever forgotten device was compromised last. So: don't authenticate the cable.
Authenticate the requester. Check the device. Do it per request, not per morning.

That is sensible, and it was arguably overdue. It is also a claim about routing and credentials, roughly as ideological
as a recommendation to stop accepting photocopied passports. So why does the phrase read like a manifesto?

## The name had an author too

A comfortable answer would be that a modest engineering idea was corrupted in transit, that vendors and executives took
an innocent technical term and inflated it into a philosophy of suspicion. That answer is too kind, and the founding
document itself is a witness against it.

*No More Chewy Centers* does not build its case on misconfigured routers. Its examples are people, chief among them an
insider at a firm supplying software to credit bureaus, who sold tens of thousands of customer records over two years,
undetected, from a position of trust. The report's argument moves freely between packets and people, listing malicious
insiders in trusted positions among the reasons the old model fails, and dismissing "trust but verify" as a useless buzz
phrase. In the years since, Kindervag has repeatedly described trust itself as a vulnerability, a human sentiment that
has no rightful place in digital systems. One can read that charitably, as a compressed way of saying that trust
decisions belong at the identity layer rather than the network layer. Charitable or not, the name was not an engineering
label that escaped the lab. It looks chosen for its reach. "Zero trust" fits on a slide and stirs the blood.
"Location-independent request authentication" does neither, and would have sold no reports.

Technical terms do not stay inside RFCs. Executives, boards, auditors, and journalists read them literally, and then
organise around the metaphor. The phrase did not accidentally invite expansive readings. It invited them from the moment
it was coined, and it went on doing so in rooms its coiner never controlled.

## The name escapes engineering

Once the phrase reaches the boardroom, a natural inference presents itself. If trusting networks turned out to be
dangerous, perhaps trusting employees is dangerous too. The inference is invalid, but it is not stupid; it is what the
words say. And so a second family of products arrives wearing the badge: user behaviour analytics, insider risk scoring,
keystroke and screen monitoring, sentiment analysis of internal chat. Some of this has a foothold in NIST's
specification and some of it has none. Its trust algorithm does take historical behaviour patterns as an input, and the
document names insider threat directly. But its interest in behaviour stays tied to the access decision. It does not
reach for keystrokes, screen contents, or whether Marieke in finance seems disgruntled this quarter. Nothing in the
architecture required that. The name licensed it.

The industry's favourite "castle and moat" slide quietly redraws history. It depicts a wall and a gate, then invites a
laugh at their inadequacy. What disappears are the guilds, the letters of introduction, the reputations, the neighbours
whose watchfulness made the city function in the first place. The slide removes trust from the picture, then sells the
omission back as insight.

![Castle and moat](/images/language-moat-castle.png)

## Trust is infrastructure too

Bruce Schneier's argument in [Liars and Outliers](https://www.schneier.com/books/liars-and-outliers) is that security
is not the opposite of trust but its enabling condition: the whole apparatus of locks, laws, and reputations exists so
that strangers can cooperate at scale. On that reading, strip the trust out and there is less left for security to
protect. Onora O'Neill made
the adjacent point about institutions in her [2002 Reith Lectures](https://www.bbc.co.uk/programmes/p00ghvd8): regimes
of ever-increasing accountability and audit, introduced in the name of restoring trust, tend instead to corrode it,
replacing professional judgement with defensive compliance.

Both observations bear directly on the surveilled organisation. The behaviours security actually depends on are
voluntary and fragile. Someone admits they clicked the link. Someone mentions that the contractor's questions felt off.
Someone escalates an uncertainty they could have quietly ignored, or stays late to help a colleague recover a mistake
that would otherwise surface in an audit. Every one of these runs on psychological safety, and psychological safety is
difficult to sustain when one's keystrokes are being scored for risk. An organisation that signals institutional
distrust of its people tends to receive, in return, exactly the information flow it has priced in: none.

There seems to be an inversion. The more an organisation works at removing interpersonal trust, the more
weight its technical controls carry, since they now operate without the human early-warning system around them. And the
more weight the controls carry, the less gracefully the organisation degrades when they fail, which they eventually do.
Distrust is not a free upgrade. It is a transfer of load onto the most brittle part of the structure.

## Identity is negotiated

Identity systems tend to assume identity is crisp: one person, one credential, one continuous session of unambiguous
intent. Real organisations are not like that, and everyone in them knows
it. [Weinberg](https://purple.tymyrddin.dev/docs/foundations/problem-solving/secrets-of-consulting/#it-s-always-a-people-problem)
would have recognised the shape at once: a people problem wearing a technical costume.

A nurse borrows a colleague's terminal mid-emergency because logging out and back in costs ninety seconds the patient
does not have. A maintenance account is shared because the vendor shipped it that way in 2009 and the machine has
never once been offline long enough to change it. An engineer fixing something at three in the morning is using
whatever access still works. A consultant is covering a role she does not formally hold, with everyone's blessing and
no one's paperwork. These are not violations that happen to occur; they are trust behaviours humans have negotiated,
continuously and mostly well, using context the policy engine cannot see. The architecture classifies them as attacks
not because the architecture is stupid but because context is not easily computable, and humility sits better with that
limit than enforcement does.

## What the plant already knew

Operational technology is where the abstraction finally collides with physics. An industrial site contains controllers
that cannot perform authentication at all, safety loops that cannot tolerate the latency of a policy decision point,
deterministic timing that a dropped handshake would violate, and equipment considerably older than any framework now
assessing it. Per-request verification is not resisted there out of conservatism. It is resisted because the request is
a valve, and the valve cannot wait.

More interesting than what the plant lacks is what it has. Engineers on a site do not trust each other because of
network identity. They trust presence: who is physically standing at the cabinet. Presence is itself a security control.
They trust competence, demonstrated over years. They trust professional reputation, which travels between sites faster
than any credential, and operational judgement, which is why the person who has run the unit for two decades gets
believed at 3:00. These are genuine trust mechanisms with genuine verification built in, and they are primary structure.

The OT world even had its own vocabulary before the slogan
arrived. [IEC 62443](https://purple.tymyrddin.dev/docs/audits/iec62443/) organises a plant into zones and conduits: regions of
comparable trust with controlled channels between them, a gradient rather than a zero. That is not an industrial
peculiarity. It is the model most organisations run without writing down, and one sector happened to standardise. Zero
trust arriving in these environments as "add another gateway" proposes zeroing a gradient that was already doing useful
work.

## A category mistake

The phrase joins two different things under one word. There is epistemic trust: I have evidence that this request is
genuine, this credential valid, this device in a known state. And there is social trust: I believe this person will act
competently and honestly, the expectation that Diego Gambetta and his contributors spent [a
volume](https://www.researchgate.net/publication/242591079_Trust_Making_and_Breaking_Cooperative_Relations) dissecting
as a quiet condition of cooperative life. The first is a property of claims and can, in principle, be verified per
request. The second is a property of relationships and cannot, because it is precisely the willingness to proceed
without full verification. It is what stands in where evidence runs out, which in any real organisation is most of the
time.

Engineers hear a claim about evidence. Everyone else hears a claim about a relationship. Both readings are reasonable,
which is the whole problem.

Zero trust, as engineering, addresses only the first. Its readers, being human, hear the second. The boardroom inference
and the surveillance products it licensed both follow from collapsing these two meanings into a single marketing phrase.
And the founding report, which built its case around a human insider, shows the collapse was present at the christening
rather than introduced in transit. That is the category mistake, and it has been compounding ever since.

## Recovering the precision

None of this argues for abandoning the architecture. The engineering insight survives perfectly well once the two trusts
are prised apart again. A security architecture can verify requests all day without teaching an organisation to distrust
itself. The discipline is small and unglamorous: noticing, before a trust relationship is removed, which kind of trust
it is, what work it is currently doing, and what will carry that load once the boundary between verification and trust
has moved.

The architecture never asked anyone to stop trusting people. It asked them to stop trusting IP addresses. Somewhere
between the research note and the boardroom, those became the same sentence. A city that tore down its guilds because
the wall had failed would not be more secure. It would merely be alone, inside a very well-authenticated gate.

## Sources

- Kindervag, J., [*No More Chewy Centers: Introducing The Zero Trust Model of Information
  Security*](https://media.paloaltonetworks.com/documents/Forrester-No-More-Chewy-Centers.pdf), Forrester Research,
  September 2010.
- Jericho Forum, [*Jericho Forum Commandments*](https://collaboration.opengroup.org/jericho/commandments_v1.2.pdf), The
  Open Group, 2007.
- Ward, R. and Beyer,
  B., ["BeyondCorp: A New Approach to Enterprise Security"](https://www.usenix.org/system/files/login/articles/login_dec14_02_ward.pdf),
  *;login:*, USENIX, December 2014.
- Rose, S., Borchert, O., Mitchell, S. and Connelly, S., [*Zero Trust
  Architecture*](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-207.pdf), NIST Special Publication
  800-207, August 2020.
- Schneier, B., [*Liars and Outliers: Enabling the Trust That Society Needs to
  Thrive*](https://www.schneier.com/books/liars-and-outliers), Wiley, 2012.
- O'Neill, O., [*A Question of Trust: The BBC Reith Lectures 2002*](https://www.bbc.co.uk/programmes/p00ghvd8),
  Cambridge University Press, 2002.
- Gambetta, D. (ed.), [*Trust: Making and Breaking Cooperative Relations*](https://www.researchgate.net/publication/242591079_Trust_Making_and_Breaking_Cooperative_Relations), Basil
  Blackwell, 1988.
- Fukuyama, F., [*Trust: The Social Virtues and the Creation of
  Prosperity*](https://www.academia.edu/8928126/Trust_The_Social_Virtues_and_the_Creation_of_Prosperity_by_Francis_Fukuyama), Free Press, 1995.
- Coase, R. H., [*The Nature of the Firm*](https://doi.org/10.1111/j.1468-0335.1937.tb00002.x), *Economica*, Vol. 4,
  No. 16, November 1937.
- IEC 62443-3-2, [*Security for industrial automation and control systems*](https://purple.tymyrddin.dev/docs/audits/iec62443/), Ty Myrddin, 2025
- Weinberg, G. M., [*The Secrets of Consulting*](https://leanpub.com/thesecretsofconsulting), Dorset House, 1985.