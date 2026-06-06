---
title: "Een transparantiewet die om vindbaarheid vraagt"
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

Er is een gewoonte in detection engineering management die een organisatie tijd kost om af te leren. Een team kijkt naar
de waarschuwingen, de dashboards, de dekkingsrapporten en behandelt ze als de plek waar detectie gebeurt.
[Dat is niet zo](https://blue.tymyrddin.dev/docs/counter/). Het is de plek waar detectie zichtbaar wordt. Het werk dat
bepaalt of er überhaupt iets te zien valt, gebeurde veel eerder en veel stiller toen iemand koos wat er gelogd werd. Op
een event dat nooit is vastgelegd valt geen alert te schrijven. De detectie aan de uitgang reikt niet verder
dan de telemetrie die iemand aan de ingang heeft ingericht en niemand voelt de prijs van een ontbrekende log entry op
het moment dat de log niet wordt geschreven. Die prijs komt later, tijdens een incident, wanneer blijkt dat het te
reconstrueren spoor nooit heeft bestaan.

De [Wet open overheid](https://wetten.overheid.nl/BWBR0045754/2026-02-20) heeft dezelfde vorm, en het zo bekijken
verklaart meer over waarom departementen ermee worstelen dan welke verklaring ook die in termen van archiveren of
compliance is gesteld.

## Wat de wet eigenlijk vraagt

De Woo verving de oudere WOB in 2022 en hield haar centrale belofte overeind, dat een burger om overheidsinformatie kan
vragen en die ontvangt zolang er geen grond is om te weigeren. Dat verzoekrecht kent geen overgangsrecht en kan dus over
oude besluitvorming gaan: een verzoek dat vandaag binnenkomt kan een dossier van jaren terug raken. Daar bovenop kwam
iets wat de WOB niet had: een plicht om bepaalde categorieën informatie actief openbaar te maken zonder dat iemand erom
vraagt. [Zeventien categorieën](https://pgwoo.nl/home/hoofdstuk-3-openbaarmaking-uit-eigen-beweging/artikel-3-3-actieve-openbaarmaking-van-categorieen-informatie/),
die stapsgewijs per koninklijk besluit verplicht worden. En daarnaast, langs een eigen
beleidslijn, [de beslisnota](https://www.informatiehuishouding.nl/projecten/openbaarmaking-en-informatiehuishouding), de
ambtelijke notitie waarin de afwegingen onder een besluit van een minister of staatssecretaris staan. Beide plichten,
de actieve en die op verzoek, zijn waar de moeite zit, want een staat kan niet openbaar maken wat zij niet kan vinden,
en geen wet kan vindbaarheid voorschrijven. Het is een eigenschap die een departement eerder heeft opgebouwd, of niet.

Zo leest de wet als een transparantiewet en gedraagt zich als een vindbaarheidsprobleem. De vermomming is niet
toevallig en daar kom ik op terug. Eerst het mechanisme.

## Het mechanisme

De keten loopt in één richting. Hoeveel iemand vastlegt op het moment van besluiten bepaalt hoe reconstrueerbaar het
besluit later is en reconstrueerbaarheid bepaalt hoeveel er aan de uitgang openbaar kan worden. Vastlegging voedt
reconstrueerbaarheid voedt openbaarmaking. De wet grijpt aan op de laatste schakel, de openbaarmaking, en probeert die
te bewegen.

![Abstracte tweelussenstructuur: vastlegging voedt reconstrueerbaarheid voedt openbaarmaking, met een balancing loop op de uitgang en een reinforcing loop die de ingang uitholt](/images/01abstract.png#center)

Op zichzelf werkt dat aangrijpen. Lage openbaarmaking wekt externe druk, een Woo-verzoek, een Kamervraag, een bevinding
van de inspectie. De druk trekt inzet naar de zichtbare laag, lakteams, publicatieportalen, openbaarmakingsprocessen. De
inzet verhoogt de openbaarmaking. Dat is een balancing loop, het type dat zichzelf corrigeert, en het is wat de wet
bedoelt. De gemarkeerde relatie in de figuur, waar meer openbaarmaking de druk verlaagt, sluit hem.

De moeite zit in de tweede lus, die een knoop deelt met de eerste. Aandacht is eindig. De inzet die de balancing loop op
de zichtbare laag stort, komt uit dezelfde voorraad die anders naar vastlegging aan de ingang zou gaan. Meer inzet op
openbaarmaking, minder aandacht voor vastlegging, lagere reconstrueerbaarheid, lagere openbaarmaking, meer druk, weer
meer inzet. Dat is een reinforcing loop en hij loopt op precies de knoop waar de correctie van afhangt. Een departement
kan de balancing loop niet harder laten lopen zonder de reinforcing loop mee te trekken, zolang aandacht eindig is en de
druk op de uitgang zit in plaats van op de ingang.

Reconstrueerbaarheid is als wolk getekend en niet als ovaal, omdat het geen grootheid is die het systeem geneigd is te
meten. Haar meten zou vereisen dat een departement het oorspronkelijke besluit en de gronden ervan op record houdt in
een vorm die het later kan bevragen en dat is juist wat inzet die naar de uitgang vloeit erodeert. Het systeem kan
heel scherp zien hoeveel het openbaar heeft gemaakt. Het kan niet makkelijk zien hoeveel van wat het besloot nog
terughaalbaar is en het ontbreken van die maat is mede waarom de reinforcing loop ongezien loopt.

![Woo-instantie van dezelfde structuur: vastleggen van besluit en gronden, reconstrueerbaarheid van besluitvorming, actieve openbaarmaking, Woo- en toezichtdruk, en inzet op openbaarmaking als gedeelde knoop](/images/02woo.png#center)

De Woo-instantie is de abstracte structuur met de labels ingevuld. Vastleggen van het besluit en de gronden op het
moment van besluiten, de reconstrueerbaarheid van hoe een besluit tot stand kwam, de omvang van de actieve
openbaarmaking, de Woo- en toezichtdruk, en de inzet op openbaarmaking als de knoop waar beide lussen elkaar raken.

![Detection-instantie van dezelfde structuur: telemetrie, reconstrueerbaarheid van het event, dekking van waarschuwingen (alerts), incident- en auditdruk, en inzet op tunen als gedeelde knoop](/images/03detection.png#center)

En de detection-instantie, dezelfde topologie weer. Telemetrie aan de ingang, reconstrueerbaarheid van wat er gebeurde
als de wolk, dekking van waarschuwingen (alerts) aan de uitgang, incident- en auditdruk, inzet op tunen als de gedeelde
knoop. De
vertrouwde reflex wanneer een audit een gat vindt is meer regels schrijven en meer dashboards bouwen, en dat is inzet op
de zichtbare laag. Het is dezelfde lus in operationele kleren.

## Waarom de vermomming niet toevallig is

Hier houdt de structurele analyse op neutraal te zijn en het is de moeite waard om voorzichtig te zijn met de volgorde.
Het
mechanisme hierboven geldt of iemand het nu bedoeld heeft of niet. Maar zodra het geldt, is de plek waar de wet de druk
aanlegt zelf een keuze en die keuze is leesbaar.

Een vastleggingsplicht aan de ingang zou degene binden die besluit op het moment dat zij besluit, terwijl het besluit
nog leeft en de inzet aanwezig is. Een openbaarmakingsplicht aan de uitgang bindt een latere ambtenaar, vaak een andere,
die moet vinden en vrijgeven wat wel of niet is vastgelegd. De eerste raakt de macht waar zij wordt uitgeoefend. De
tweede raakt een administratieve functie stroomafwaarts ervan. Een wet die om transparantie vraagt door op de uitgang
aan te grijpen heeft het aangrijpingspunt gekozen dat de uitoefening van macht het minst verstoort en het resultaat
openheid genoemd. Dat de eis aan het verkeerde eind van het systeem landt voor het voortbrengen van de eigenschap die
zij wil, is niet alleen een technisch feit. Het is ook een feit over wie de regeling spaart.

Ik wil dit niet overdrijven tot intentie. Het punt is structureel, geen bewering over iemands motief. Maar de structuur
is niet symmetrisch in wie zij iets kost en die asymmetrie opmerken is iets anders dan de lussen opmerken.

## Wat verloren is, is verloren

![Interventievariant: het aangrijpingspunt verplaatst naar de ingang, de inzet voedt de vastlegging, en de reinforcing loop R is daarmee onderbroken.](/images/04intervention.png#center)

Op beide lussen valt in te grijpen. Een departement kan de balancing loop morgen harder laten lopen: meer lakcapaciteit,
meer portalen, meer mensen op openbaarmaking. Het kan de reinforcing loop onderbreken door het aangrijpingspunt naar de
ingang te verplaatsen, zodat de inzet de vastlegging voedt in plaats van haar leeg te trekken. Beide ingrepen liggen
binnen bereik van wie besluit ze te doen.

Aan het vastleggen van gisteren valt niets meer te doen. De schakel van vastlegging naar reconstrueerbaarheid loopt
alleen vooruit in de tijd. Wat een departement gisteren niet heeft vastgelegd, halen beide lussen niet terug, niet
langzaam en niet uiteindelijk. Telemetrie die niet verzameld is, is er gewoon niet. Een besluitvormingsspoor dat niet is
vastgelegd op het moment van besluiten, is achteraf niet te reconstrueren zonder de reconstructie zelf verdacht te
maken. De lussen beschrijven wat een systeem nog kan beïnvloeden. Over een verleden dat nooit is opgeschreven zeggen ze
niets, want er is niets waar een lus op kan aangrijpen.

De wet erkent dit zelf, schuin. De actieve openbaarmakingsplicht heeft eerbiedigende werking: zij geldt
[niet voor documenten die zijn opgesteld of ontvangen](https://pgwoo.nl/home/hoofdstuk-10-slotbepalingen/artikel-10-2a-overgangsrecht-bestaande-documenten/)
voordat de plicht voor het bestuursorgaan inging. De wetgever vraagt het oude bestand dus niet alsnog actief naar
buiten. Dat leest als een praktische overgangsmaatregel, maar het is ook een stilzwijgende toegift: je kunt niet
verplichten openbaar te maken wat niet op een vindbare manier is vastgelegd, dus stelt de wet het verleden vrij in
plaats van het op te eisen. Het verzoekrecht kent die vrijstelling niet en kan oude besluitvorming wel raken, en juist
daar bijt de reconstrueerbaarheid: een verzoek over een dossier van jaren terug stuit op wat toen wel of niet is
vastgelegd, en geen openbaarmakingsproces aan de uitgang verandert daar iets aan.

De conclusie die het compliance-kader trekt is onhaalbaar, hard werken tot het verleden terugkomt. Wat wel klopt is dat
een deel van het verleden structureel weg is en het nuttige is dat als weg te markeren in plaats van een plausibele
versie te fabriceren. Een departement dat kan zeggen welke periodes van zijn eigen besluitvorming niet meer
reconstrueerbaar zijn, doet iets preciezers en iets nuttigers dan een departement dat een nette openbaarmaking
produceert over een record dat er nooit echt was.

## Waar dit thuishoort

Dit is hetzelfde mechanisme als dat in [de stabiliteit van disfunctie](/posts/dysfunction/), vanuit een andere hoek
bekeken. Aanpassen aan een probleem is goedkoper dan de oorzaak ervan wegnemen, en aanpassen kan lokaal terwijl
correctie coördinatie vraagt. Openbaarmaking onder druk is aanpassing aan slechte vindbaarheid. Ze absorbeert het
symptoom, één lakbeurt tegelijk, zonder de vastleggingspraktijk te raken die het symptoom voortbracht. De wolk om
reconstrueerbaarheid is hetzelfde soort wolk als die om de verschoven baseline in dat stuk: ongemeten, omdat haar meten
zou betekenen dat het systeem iets vasthoudt waarvoor het niet wordt beloond.

Wie ooit een verouderd systeem heeft moeten vervangen terwijl het bleef storen, kent de lus van binnenuit: de tijd gaat
op aan het brandjes blussen in het oude systeem, dus het nieuwe komt later, dus het oude moet langer mee. Het 
symptoom van vandaag trekt de inzet weg van de oorzaak van morgen, en de aandacht die dat kost komt uit dezelfde 
eindige voorraad.

Niets hiervan zegt dat de wet verkeerd is in wat zij wil. Actieve openbaarmaking is een redelijke eis aan een staat. De
observatie is smaller en, denk ik, nuttiger dan een oordeel: een eis aan de uitgang van een systeem kan
geen eigenschap voortbrengen die aan de ingang ontstaat en druk dicht het gat tussen die twee niet.
Wat het wel dicht, als iets het dicht, is veranderen wat een ambtenaar vastlegt op het moment dat zij
besluit, en dat is de enige plek in de lus waar bijna niemand kijkt.
