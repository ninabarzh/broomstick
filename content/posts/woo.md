---
title: "Een transparantiewet die vindbaarheid eist"
date: 2026-06-06
draft: false
tags:
  - systems thinking
  - organisational dynamics
  - security
  - woo
description: "De Wet open overheid vraagt de staat openbaar te maken wat de staat niet altijd kan vinden. Een blik op waarom de eis aan het verkeerde eind van het systeem aangrijpt, met een vergelijk naar detectiewerk."
cover:
  image: "/images/woo.png"
  alt: "A single weary civil servant at a cluttered government desk, buried under towering stacks of paper documents and redaction folders, frantically rubber-stamping and blacking out pages. In the background, an empty pristine filing system labelled 'intake' sits untouched and gathering dust."
  relative: false
---

Er is een gewoonte in detection engineering die een organisatie tijd kost om af te leren. Een team kijkt naar de
waarschuwingen, de dashboards en de dekkingsrapporten, en beschouwt die als de plek waar detectie gebeurt.
[Dat is niet zo](https://blue.tymyrddin.dev/docs/counter/). Het is de plek waar detectie zichtbaar wordt. Het werk
dat bepaalt of er iets te zien valt, gebeurde veel eerder en veel stiller, toen iemand koos wat er gelogd werd. Zonder
vastgelegde gebeurtenis genereer je geen waarschuwing. De prijs van een ontbrekende log betaal je pas tijdens een
incident, wanneer blijkt dat het spoor nooit heeft bestaan.

De [Wet open overheid](https://wetten.overheid.nl/BWBR0045754/2026-02-20) heeft eenzelfde vorm, en die analogie
verklaart meer over waarom departementen ermee worstelen dan welke verklaring ook in termen van archiveren of
compliance.

## Vindbaarheid laat zich niet voorschrijven

De Woo verving in 2022 de oudere WOB en hield haar centrale belofte overeind: een burger mag om overheidsinformatie
vragen en ontvangt die informatie, tenzij er een grond is om te weigeren. Dat verzoekrecht kent geen overgangsrecht en
kan dus over oude besluitvorming gaan. Een verzoek dat vandaag binnenkomt kan een dossier van jaren terug raken. Daar
komt bij wat de WOB niet had: een plicht om bepaalde categorieën informatie actief openbaar te maken zonder dat iemand
erom vraagt. Het gaat om
[Zeventien categorieën](https://pgwoo.nl/home/hoofdstuk-3-openbaarmaking-uit-eigen-beweging/artikel-3-3-actieve-openbaarmaking-van-categorieen-informatie/),
die stapsgewijs per koninklijk besluit verplicht worden. En daarnaast,
langs een eigen beleidslijn, de beslisnota: de ambtelijke notitie waarin de afwegingen onder een besluit van een
minister of staatssecretaris staan. Daar zit de moeite: een staat kan niet openbaar maken wat zij niet kan vinden, en
geen wet kan vindbaarheid voorschrijven.

## Twee lussen, één knoop

![Abstracte tweelussenstructuur: vastlegging voedt reconstrueerbaarheid voedt openbaarmaking, met een balancing loop op de uitgang en een reinforcing loop die de ingang uitholt](/images/01abstract.png#center)

Hoeveel iemand vastlegt op het moment van besluiten bepaalt hoe reconstrueerbaar het besluit later is. En
reconstrueerbaarheid bepaalt hoeveel er aan de uitgang openbaar kan worden. Vastlegging voedt reconstrueerbaarheid en
die voedt openbaarmaking. De wet grijpt aan op de laatste schakel, de openbaarmaking.

Op zichzelf werkt dat. Lage openbaarmaking wekt externe druk: een Woo-verzoek, een Kamervraag of een bevinding van de
inspectie. Die druk trekt inzet naar de zichtbare laag: lakteams, publicatieportalen, openbaarmakingsprocessen. De inzet
verhoogt de openbaarmaking. Dat is een balancing loop, het type dat zichzelf corrigeert. Dat is wat de wet bedoelt. De
gemarkeerde relatie in de figuur is dat meer openbaarmaking de druk verlaagt. Dat sluit de loop.

Het probleem zit in de tweede lus, die een knoop deelt met de eerste. Aandacht is eindig. De inzet (mankracht, tijd,
geld) die naar openbaarmaking (de zichtbare laag) gaat, komt uit dezelfde pot die anders naar vastlegging (ingang) zou
gaan. Meer inzet op openbaarmaking betekent minder aandacht voor vastlegging, lagere reconstrueerbaarheid, lagere
openbaarmaking, meer druk en weer meer inzet. Dat is een reinforcing loop. Hij werkt precies op de plek waar de
balancing loop zou moeten corrigeren. Een departement kan de balancing loop niet harder laten lopen zonder de
reinforcing loop mee te trekken. Aandacht (focus) is eindig en de druk zit op de uitgang, niet op de ingang.

Reconstrueerbaarheid is in de figuur als wolk getekend en niet als ovaal. Het is geen grootheid die het systeem geneigd
is te meten. Haar meten zou vereisen dat een departement het oorspronkelijke besluit en de gronden ervan bijhoudt in een
vorm die het later kan bevragen. En dat is juist wat erodeert wanneer inzet naar de uitgang vloeit. Het systeem kan heel
scherp zien hoeveel het openbaar heeft gemaakt. Maar het kan niet makkelijk zien hoeveel van wat het besloot nog
terughaalbaar is. Dat ontbreken van die maat is mede waarom de reinforcing loop ongezien blijft.

![Woo-instantie van dezelfde structuur: vastleggen van besluit en gronden, reconstrueerbaarheid van besluitvorming, actieve openbaarmaking, Woo- en toezichtdruk, en inzet op openbaarmaking als gedeelde knoop](/images/02woo.png#center)

De Woo-instantie is de abstracte structuur met de ingevulde labels: vastleggen van het besluit en de gronden op het
moment van besluiten, de reconstrueerbaarheid van hoe een besluit tot stand kwam, de omvang van de actieve
openbaarmaking, de Woo- en toezichtdruk, en de inzet op openbaarmaking als de knoop waar beide lussen elkaar raken.

![Detection-instantie van dezelfde structuur: telemetrie, reconstrueerbaarheid van het event, dekking van waarschuwingen (alerts), incident- en auditdruk, en inzet op tunen als gedeelde knoop](/images/03detection.png#center)

De detection-instantie heeft dezelfde topologie: telemetrie aan de ingang, reconstrueerbaarheid van wat er gebeurde (de
wolk), dekking van waarschuwingen aan de uitgang, incident- en auditdruk, en inzet op tunen als de gedeelde knoop. De
vertrouwde reflex wanneer een audit een gat vindt, is meer regels schrijven en meer dashboards bouwen. Dat is inzet op
de zichtbare laag. Het is dezelfde lus, maar dan in operationele kleren.

## De macht blijft buiten schot

Hier houdt de structurele analyse op neutraal te zijn. Het is de moeite waard om voorzichtig te zijn met de volgorde.
Het mechanisme hierboven werkt, of iemand het nu bedoeld heeft of niet. Maar zodra het werkt, is de plek waar de wet de
druk aanlegt een keuze.

Een vastleggingsplicht aan de ingang geldt voor de persoon die beslist, op het moment dat hij beslist. Een
openbaarmakingsplicht aan de uitgang geldt voor een latere ambtenaar, vaak een andere, die moet vinden en vrijgeven wat
wel of niet is vastgelegd. De vastleggingsplicht grijpt in op het moment van machtsuitoefening. De openbaarmakingsplicht
grijpt pas achteraf in op de administratie. Een wet die transparantie vraagt door op de uitgang aan te grijpen, kiest
het punt dat de uitoefening van macht het minst verstoort. Dat de eis aan het verkeerde eind van het systeem landt voor
het voortbrengen van de gewenste eigenschap, is niet alleen een technisch feit. Het is ook een feit over wie de wet
ontziet.

Ik wil dit niet overdrijven tot intentie. Het punt is structureel, geen uitspraak over motieven. Maar de structuur treft
niet iedereen even zwaar. En die asymmetrie opmerken is iets anders dan alleen de lussen zien.

## Verloren blijft verloren

![Interventievariant: het aangrijpingspunt verplaatst naar de ingang, de inzet voedt de vastlegging, en de reinforcing loop R is daarmee onderbroken.](/images/04intervention.png#center)

Beide lussen zijn vatbaar voor interventie. Een departement kan de balancing loop morgen al harder laten lopen: meer
capaciteit (inzet) voor openbaarmaking, meer portalen, meer mensen. Het kan de reinforcing loop onderbreken door het
aangrijpingspunt naar de ingang te verplaatsen. Dan voedt de inzet de vastlegging in plaats van haar leeg te trekken.
Beide interventies liggen binnen handbereik.

Aan het vastleggen van gisteren valt niets meer te doen. De schakel van vastlegging naar reconstrueerbaarheid loopt
alleen vooruit in de tijd. Wat een departement gisteren niet heeft vastgelegd, halen beide lussen niet terug. Telemetrie
die niet is verzameld, is er gewoon niet. Een besluitvormingsspoor dat niet is vastgelegd op het moment van besluiten,
is achteraf niet te reconstrueren zonder de reconstructie zelf verdacht te maken. De lussen beschrijven wat een systeem
nog kan beïnvloeden. Over een verleden dat nooit is opgeschreven, zeggen ze niets.

De wet erkent dit zelf, maar schuin. De actieve openbaarmakingsplicht
[geldt niet met terugwerkende kracht](https://pgwoo.nl/home/hoofdstuk-10-slotbepalingen/artikel-10-2a-overgangsrecht-bestaande-documenten/):
zij geldt alleen voor documenten
die zijn opgesteld of ontvangen nadat de plicht voor het bestuursorgaan inging. De wetgever vraagt het oude bestand dus
niet alsnog actief naar buiten. Dat lijkt een praktische overgangsmaatregel, maar het is ook een stilzwijgende toegift.
Je kunt niet verplichten openbaar te maken wat niet vindbaar is vastgelegd. Dus stelt de wet het verleden vrij in plaats
van het op te eisen. Het verzoekrecht kent die vrijstelling niet en kan oude besluitvorming wel raken. Daar bijt de
reconstrueerbaarheid: een verzoek over een dossier van jaren terug stuit op wat toen wel of niet is vastgelegd. Geen
openbaarmakingsproces aan de uitgang verandert daar iets aan.

Het compliance-kader doet alsof het onhaalbare haalbaar is: hard werken tot het verleden terugkomt. Maar niemand neemt
dat serieus. Wat wel klopt, is dat een deel van het verleden structureel weg is. Het nuttige is om dat als ontbrekend
te registreren in plaats van een plausibele versie te fabriceren. Een departement dat kan zeggen welke periodes van
zijn eigen besluitvorming niet meer reconstrueerbaar zijn, doet iets preciezers en nuttigers dan een departement dat
een openbaarmaking produceert over een verslag dat er nooit echt was.

## Dezelfde lus elders

Dit is hetzelfde mechanisme als in [de stabiliteit van disfunctie](/posts/dysfunction/), maar dan vanuit een andere
hoek. Aanpassen aan een probleem is goedkoper dan de oorzaak wegnemen. Aanpassen kan lokaal, maar correctie vraagt om
coördinatie. Openbaarmaking onder druk is aanpassing aan slechte vindbaarheid. Ze absorbeert het symptoom, één verzoek
tegelijk, zonder de vastleggingspraktijk te raken die het symptoom voortbrengt. De wolk rond reconstrueerbaarheid is
hetzelfde type als die rond de verschoven baseline: ongemeten, omdat meten zou betekenen dat het systeem iets vasthoudt
waarvoor het niet wordt beloond.

Wie ooit een verouderd systeem heeft moeten vervangen terwijl het oude bleef storen, kent de lus van binnenuit. Energie
en tijd gaan zitten in het blussen van brandjes in het oude systeem. Dus komt het nieuwe later en moet het oude langer
mee. Het symptoom van vandaag trekt de inzet weg van de oorzaak van morgen. Die aandacht komt uit dezelfde eindige
voorraad.

Niets hiervan zegt dat de wet verkeerd is. Actieve openbaarmaking is een redelijke eis aan een staat. De observatie is
alleen preciezer: een eis aan de uitgang kan geen eigenschap voortbrengen die aan de ingang ontstaat. Druk alleen dicht
dat gat niet. Wat het wel kan dichten, is veranderen wat een ambtenaar vastlegt op het moment dat zij besluit. En dat is
de enige plek in de lus waar bijna niemand kijkt.
