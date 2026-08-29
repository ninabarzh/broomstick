---
title: "Rule by list"
description: "A volunteer server collective in Milan is placed on a United States terrorism list. Italy is not asked."
date: 2026-08-28
draft: false
tags: [ "Autistici/Inventati", "sanctions", "sovereignty", "governance", "infrastructure", "privacy", "EU" ]
---

On 3 March 2001, around ten people in a Milan hacklab assembled a server from hardware a bank was getting rid of and
scavenged parts. The least experienced person present was put at the keyboard so that everyone would understand what
was being built. The machine was named Paranoia. On its second day, an inverted firewall rule instructed it to reject
every connection not originating from itself, and for a while the server could talk only to the server. (*Red: This
is, to be fair, the most secure configuration known to computing, and also the least useful.*) The collective printed
the mistake on a T-shirt. The story is told in the collective's
own book [+KAOS](/archive/kaos-book-2017.pdf).

On 26 August 2026, the United States Department of
State [designated that collective](https://www.state.gov/releases/office-of-the-spokesperson/2026/08/designation-of-autistici-inventati-as-a-specially-designated-global-terrorist),
Autistici/Inventati, a Specially Designated Global Terrorist under Executive Order 13224, and the Treasury's Office of
Foreign Assets
Control [added it to the Specially Designated Nationals list](https://home.treasury.gov/news/press-releases/sb0616),
alongside Palestine Action and Masar Badil in the same action. The distance between the two events is twenty-five years
of a small, unpaid, consensus-run group providing email, hosting, mailing lists, blogs and chat to people who did not
want to route their speech through corporations or states. The
collective [denies every allegation](/archive/cavallette-statement-20260826.html) in the government statements. The
statements themselves, read closely, contain something more interesting than the allegations: a theory of what a
communications provider is, and a very accurate map of what a communications provider depends on.

## Listing

A designation is not a prosecution. Nobody has been charged. No court has been asked to find anything. There is no
Italian proceeding, and Italian law has no role in the matter, a
point [Italian commentary](https://pasqualepillitteri.it/en/news/12997/usa-autistici-inventati-global-terrorist-sanctions)
picked up within a day. What exists is a signature on an executive instrument, and three legal consequences that follow
from it: any property of the listed entity under US jurisdiction is frozen; US persons and companies are prohibited from
providing or receiving funds, goods or services involving it; and breaching that prohibition carries civil and criminal
penalties for the US party. OFAC's own [FAQ on Executive Order 13224](https://ofac.treasury.gov/faqs/812) carries a prohibition on dealing and the penalties.
The penalties fall on the bank, the registrar, the host, the donor, not on the listed entity, which is by construction
outside reach. (*Red: Nobody is penalised for being on the list. People are penalised for standing next to it.*)

OFAC issued [Counter Terrorism General License 36](https://ofac.treasury.gov/media/936791/download?inline=), permitting
transactions needed to wind down existing relationships. It expires at 04:01 UTC on 25 September 2026. After
that, any US-linked institution still connected to Autistici/Inventati is exposed. Foreign institutions are not bound by
the prohibition, but since a [2019 amendment](https://home.treasury.gov/news/press-releases/sm772) every SDGT listing
carries secondary-sanctions exposure for foreign financial institutions that knowingly facilitate significant
transactions with the designated entity, and that is enough. A compliance department in Milan, Amsterdam or Frankfurt
weighs the cost of legal advice against the cost of closing an account, and the account closes. (*Red: A compliance
department is an organ evolved to feel fear on behalf of an institution that cannot, and it does the job very well.*)
Over-compliance is not a side effect of the instrument. It is the instrument.

That is the whole mechanism. It seems slight when set out plainly, and it is exactly this slightness that makes the case
hard to read from the advocacy pieces, which write about it as though it were a raid.

## Two readings

The State
Department's [fact sheet](https://www.state.gov/releases/office-of-the-spokesperson/2026/08/designation-of-autistici-inventati-as-a-specially-designated-global-terrorist)
describes encrypted chat and email, web hosting, video conferencing, streaming and anonymity tools, and asserts that
these were "specifically designed to support the operations of far-left terrorist networks". The evidence offered in
the two statements is that communiqués and publications attributed to a range of groups, from European antifascist
cells to the PKK, passed through A/I infrastructure or were hosted on Noblogs. Nothing in the public statements claims
that the collective wrote those texts, chose targets, moved money or weapons, or knew of any act before it occurred. The
theory does not need any of that. Provision is treated as participation. An email account becomes co-authorship of
every message sent from it.

Set that theory against the architecture. After Italian police obtained covert access to A/I's server at a commercial
hosting
provider [on 15 June 2004](/archive/statewatch-italy-police-access-200507.html),
an operation the collective [discovered a year later](https://edri.org/our-work/edrigramnumber3-13backdoor/) by reading
a footnote in [someone else's case file](/archive/autistici-short-history-20251029.html), it rebuilt. Plan R*, from October 2005, distributed encrypted data and services
across machines in several countries, with public-facing nodes designed to be replaceable. Alongside that came a policy
of holding as little as possible: no subscriber identities, minimal logs, encrypted disks, and repeated instruction to
users not to trust the provider with their safety. When Norwegian
police [copied a server's drives in November 2010](/archive/statewatch-norway-italy-seizure-201012.html)
at Italian request, looking for the owner of one mailbox, the disks yielded nothing identifying and services were
restored elsewhere within hours.

The collective, in other words, engineered away precisely the control the designation attributes to it. It cannot read
the mail because it built a system in which it cannot read the mail. One reading in circulation puts the consequence
sharply: the charge, read structurally, amounts to not having surveilled. A
provider that chose to protect its users' privacy is being treated as though it concealed their crimes, and the absence
of a capability is being read as intent.

So the first reading, the reading of what A/I controls, appears to be wrong on the engineering.

The second reading is about what A/I depends on, and that one is correct. Plan R* answers the question "what happens
when a machine disappears" and answers it well. It does not answer "what happens when a bank closes the account", "what
happens when the registry suspends the domain", "what happens when the certificate authority declines to renew", or
"what happens when the transit provider's legal team reads a Treasury press release". (*Red: Nobody, it seems, thought
to ask the bank.*) Those relationships were never in the threat model, or were in it and accepted as unavoidable. A
server collective can put its disks in five countries and
still have its name in a US registry (.org is [administered from Reston, Virginia](https://pir.org/who-we-are/)), its
trust chain rooted in US-based authorities, its donations passing through US-based processors, and its bandwidth bought
from companies with US subsidiaries. Twenty-five years of removing single points of failure at the hardware layer left
the institutional layer largely as found. The Sabot Media
piece [republished by the collective](/archive/cavallette-sabot-repost-p2-20260827.html) lists the exposed layers plainly:
banking, donations, domains, data-centre contracts, bandwidth, certificates, software dependencies.

The designation does not attack the servers. It attacks the joints. Whoever drafted it understood the dependency graph
of an "autonomous" provider better than the provider's own architecture documents did, because the architecture
documents were about a different kind of attacker.

## Sovereignty

Territorial sovereignty says that Italy decides whether an Italian association is criminal. Italy has decided nothing
and has not been asked. The listing reaches an entity with no US presence through the things that entity cannot avoid
touching: dollar clearing, the naming system, the trust system, the handful of companies through which most of the
world's traffic and payments pass. Legality in Europe and viability in Europe have come apart. The first still belongs
to Rome; the second now depends on Washington.

This is not a novel observation about the dollar. Sanctions have shaped European banking behaviour for two decades, and
the
EU's [Blocking Statute](https://finance.ec.europa.eu/eu-and-world/open-strategic-autonomy/extraterritoriality-blocking-statute_en),
updated in 2018 to shield European companies trading with Iran, showed how little a regulation can do against a
compliance department's risk appetite:
the [Court of Justice](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=CELEX:62020CJ0124) reads the prohibition
broadly, and in the same judgment holds that an operator may drop a listed customer without giving reasons, though it
may then have to prove in court that it was not complying with the US measures. What is new here is the object. The
reach is being used not against a bank or a shipping company but against a publishing platform for political speech,
hosted in an EU member state, operating within that state's law.

The EU has had a digital sovereignty agenda for a decade. Cases like this one show whether the phrase describes
anything. The initial response has been silence, and silence is itself a decision: it establishes as working precedent
that a US executive listing applies inside the Union by default. The PKK citation in the designation makes objection
harder, since the PKK is on
the [EU's own terrorism list](https://www.consilium.europa.eu/en/policies/sanctions-against-terrorism/) and
has [litigated its listing](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=CELEX:62014TJ0316(01)) for years
without being removed, so any European official raising the case would need to argue proportionality and process rather
than the underlying category. Proportionality arguments are slow, and the licence expires on 25
September. [Beniamino Irdi's reading](https://decode39.com/16319/autistici-inventati-case-sets-a-new-counterterrorism-precedent-irdi-says/),
that the material-support logic is being applied to infrastructure openly for the first time, suggests the precedent is
the point.

The question also arrives from below. In a private conversation within a day of the listing, a Dutch provider,
ideologically kin to A/I and formally unconnected, asked whether it would be next. That is the sovereignty question in
its practical form: not whether Brussels can protest, but whether a Dutch bank reads a Washington list, and it does.

## Governance

The shift on display is from law to list. A prosecution needs a charge, a forum, a defence, a standard of proof and a
route of appeal. A designation needs a signature and a press release. (*Red: It is the difference between a trial and a
rumour with letterhead.*) Enforcement is then outsourced to private intermediaries who each draw their boundary a
little wider than the law requires, because uncertainty resolved by exclusion costs less than uncertainty resolved by
counsel. The listed party has no forum in which to be heard, and the intermediaries who cut it off have no obligation to
explain themselves. The result is a form of governance that is dispersed, deniable and largely invisible: no officer in
the server room, no order to show, only a series of accounts that quietly stop working. (*Red: Nobody kicks the door
in. The door just stops recognising the key.*)

None of this machinery is new. It has been used
against [charities](https://charityandsecurity.org/designation-process/us_harities_designated_shut_down_by_treasury/),
[hawala networks](https://home.treasury.gov/news/press-releases/po770) and individuals since 2001, and the
civil-liberties objections to it are [well documented](https://www.justsecurity.org/125072/fto-sdgt-antifa/).
Applying it to a communications provider is a widening, not an invention, and the widening has a specific direction:
away from money, towards speech. Treasury's own press
release [insists](https://home.treasury.gov/news/press-releases/sb0616) that the United States does not sanction
political speech, citing its FAQ 1190, a paragraph away from the one that lists a hosting provider.

There is a smaller point about legibility. A/I has no coordinator, no spokesperson, no leadership, no payroll and no
voting; it decides by consensus on mailing lists that every participant can read, as
its [manifesto](/archive/autistici-manifesto-20260826.html) sets out. A state
that governs by list needs a name to write on the list and finds this kind of structure suspicious on its face, since it
has no obvious place to apply pressure and no individual to hold responsible. The designation's language, with its "
cadre of radical hackers", supplies the missing organisational chart by assertion. What the collective describes as an
absence of hierarchy, the designation describes as concealment of one. The same move that reads no-logging as
obstruction reads no-leader as conspiracy. (*Red: Bureaucracies have long regarded the absence of someone to shout at
as a form of insolence.*)

## Fascism

The word carries a great deal of weight in the material around this case and less in the event itself. What the
designation does, precisely and in writing, is treat antifascism as a marker of terrorism. It names the collective's
antifascist and antimilitarist politics, its practice of selecting projects compatible with those politics, and its
hosting of antifascist groups, and presents these as elements of the case. It sits inside a stated programme:
a [September 2025 executive order](https://www.whitehouse.gov/presidential-actions/2025/09/designating-antifa-as-a-domestic-terrorist-organization/)
naming "Antifa" a domestic terrorist 
organisation, [National Security Presidential Memorandum 7](https://www.whitehouse.gov/presidential-actions/2025/09/countering-domestic-terrorism-and-organized-political-violence/)
on political violence "under the umbrella of self-described 'anti-fascism'", and
the [November 2025 designation](https://www.state.gov/releases/office-of-the-spokesperson/2025/11/designations-of-antifa-ost-and-three-other-violent-antifa-groups)
of four European groups in Germany, Italy and Greece, the first time the foreign-terrorist machinery had been pointed at
that movement. For the people involved the resonance is not abstract: the Italian episodes in A/I's history run through
the G8 in Genoa, the Diaz school and the Bolzaneto barracks, for which the European Court of Human
Rights [found Italy in breach of the prohibition on torture](https://www.ejiltalk.org/a-new-case-on-torture-in-europe-cestaro-v-italy/) in
2015 and [again in 2017](https://unipd-centrodirittiumani.it/en/news/european-court-of-human-rights-italy-condemned-three-times-for-inhumane-and-degrading-treatment),
and the investigation behind the 2010 seizure, [triggered by graffiti](/archive/autistici-short-history-20251029.html) aimed at a neo-fascist organisation.
Criminalising the opposition to a thing while leaving the thing itself untouched has historically been a reliable tell
of where a state's sympathies lie.

Whether the correct noun is fascism, authoritarian legalism, or one of the other terms in circulation is partly a matter
of taxonomy and partly a matter of temperament. The features on the record are easier to agree on: political dissent
reclassified as a security threat; executive action without judicial process; enforcement through institutional fear
rather than police force; and a foreign reach that domestic institutions in Europe do not, so far, resist. Those
features do not require a mass movement, uniforms or a leader cult, and can coexist with elections, courts and a free
press that reports on them. It may be more useful to name the features than to argue over the noun, if only because the
features can be checked against the next case and the noun cannot.

## Setting in motion

Most of what the listing sets in motion does not touch A/I at all.

Intermediary protection changes shape. European and US law have for a generation held that a host or conduit is not
responsible for what passes through it, provided it acts when notified; in the EU this runs from the e-Commerce
Directive into [Articles 4 to 6 of the Digital Services Act](https://dsa-library.com/chapter/2/),
with [Article 8](https://dsa-library.com/article/8/) forbidding general monitoring obligations. A designation does not engage with that framework; it steps around it. No notice, no
takedown, no finding of knowledge. If hosting plus political affinity plus a refusal to log is sufficient, then
encrypted mail providers in Switzerland and Germany, a [comparable collective in the United States](https://riseup.net),
Tor relay operators, Matrix and Mastodon administrators, VPN companies and community archives all sit inside the same
template, distinguished only by whether a given administration dislikes their users. Most would never be listed. The
point is that nothing in the law now says they cannot be.

Privacy-preserving design becomes a suspect choice. The fact sheet presents anonymity and encryption as features built
to support operations. Once that reading exists in an official document, larger providers acquire a reason to add
identity verification, keep more logs and decline projects that look like this one, not because they are required to but
because compliance prefers not to be a test case. A possible drift is that users leave small trusted infrastructure for
commercial platforms that are easier to subpoena and map. That is a surveillance gain obtained without decrypting
anything. And for users out of the frying pan into the fire.

The sanctions instrument acquires a new purpose. OFAC was built for terrorist finance, narcotics and hostile states.
Pointing it at a volunteer publishing platform converts it into a tool against speech, with an enforcement radius that
runs through bank fear rather than any statute. Other states have done comparable things, with foreign-agent
registers, "undesirable organisation" lists and blocking regimes. The novelty is the dollar system doing it, which means
the reach is honoured in Europe whether or not Europe agrees.

Domestic groups become reachable through foreign infrastructure. The designation lists Rose City Antifa, resistance to
the Atlanta police-training centre and Jane's Revenge alongside the PKK and Hamas. Listing a foreign provider is one way
to reach domestic movements that the executive cannot easily designate directly, since there is no
domestic-terrorist-organisation designation in US law, a
point [CrimethInc](https://crimethinc.com/2026/08/27/us-government-designates-host-of-noblogsorg-a-global-terrorist)
made the day after: make their communications infrastructure untouchable and their supporters legally uncertain. Anyone
building tools those movements use could in principle be read as providing
"technological support". Sanctions counsel advising US non-profits were
already [warning](https://www.arnoldporter.com/en/perspectives/blogs/enforcement-edge/2025/12/precedent-setting-antifa-related-foreign-terrorist-designations)
about that exposure after the November designations.

And the people who chose this infrastructure because commercial platforms were unsafe for them, writers, organisers,
researchers and NGO staff in hostile environments, become collateral damage. Sources hesitate to write to an address. 
Archives go offline. The record of what happened in Genoa in 2001, part of which escaped through the media centre this
collective helped run, gets harder to reach.

## 25 September

The honest hedge is that all of this depends on repetition. A single listing that the collective outlasts, with European
providers quietly routing around US dependencies and European institutions saying nothing, ends up as a footnote in the
history of sanctions overreach. A second and a third listing turn it into doctrine. Which of those happens is not
visible from here.

What is visible is the shape of the test. The wind-down licence expires at 04:01 UTC on 25 September 2026. Between
now and then, every institution with a relationship to A/I decides whether to keep it, and most of those decisions will
be taken by people who have never heard of Plan R* and have no interest in the difference between a provider and a user.
(*Red: They will have a form. The form will not have a box for it.*) The servers will very probably still be running
on 26 September. The question is whether anything can still reach them, pay for them, or trust their certificates. A
quarter-century of preparing for a machine to disappear meets an attacker who has no interest in the machine.

The first server locked itself out on its second day, able to speak only to itself. The collective found that funny
enough to wear. The listing amounts to an attempt to recreate the condition from the outside, for a whole network, by
persuading everyone else to stop connecting. Whether that works is not, in the end, a question about architecture. It is
a question about who else is standing on the same joints, and whether they notice in time. Stay updated via 
[Circe](https://circex.org/it/news).

---

*Seven of the sources linked above are served from this site rather than from where they were originally published. The
collective's own site and its blog have been down since the listing, and archive.org (note the .org) copies can
be withdrawn on request, so the short history, the manifesto, the statement of 26 August, the Sabot Media repost and
the +KAOS book are local copies of archive.org captures (29 October 2025 for the history page, 26 to 28 August 2026 for
the rest). The two Statewatch articles are local copies as well, the 2010 one from a capture of December 2012, since
the live page has since shrunk to its first paragraph. Stylesheets and images were copied alongside; analytics scripts,
share widgets and licensed web fonts were removed; the text was not touched. A piece about designated and potential 
other to-be-designated entities and joints giving way seemed unwise to be written standing on them.*
