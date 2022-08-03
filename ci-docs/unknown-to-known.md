---
title: Prilagodite svoje izkušnje s podatki o znanih in neznanih uporabnikih
description: Vključite podatke o prej neznanih uporabnikih, ko poznate njihovo identiteto.
ms.date: 07/07/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: ff99721bef0004bc8cae1ec14ff9df16cbb0682e
ms.sourcegitcommit: ece8ff732490ecd3b3421ab273f331e6fd46a7f7
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/19/2022
ms.locfileid: "9173827"
---
# <a name="personalize-your-experiences-with-data-about-known-and-unknown-users"></a>Prilagodite svoje izkušnje s podatki o znanih in neznanih uporabnikih

Upravljanje podatkov o strankah ni nov izziv, vendar postaja vse težje, ko uporabniki krmarijo po različnih digitalnih kanalih, ki jih ponujajo blagovne znamke. Uporabnik, ki je znan (preverjen) na enem kanalu, postane neznan (nepreverjen) na drugem, če ni prijavljen. Pogosto je težava v tem, da nepreverjeni (neznani) uporabniki nimajo skupnega ID-ja. Lahko bi ga uporabili za povezovanje pomembnih atributov profilov in ustvarjanje enotnih profilov strank. Customer Insights pomaga rešiti to težavo tako, da zaužije podatke iz metod sledenja v vaših izvornih sistemih. Konsolidirani neznani in znani profili nudijo organizacijam popoln vpogled v posodobljene profile in njihove zgodovinske transakcije, vedenja in demografske podatke. Gre celo korak dlje z zagotavljanjem ločljivosti identitete, ki vam omogoča poenotenje dejavnosti strank na več kanalih, vključno z vašim spletnim mestom, nakupom v trgovini, programi zvestobe itd.

## <a name="sample-scenario"></a>Vzorčni scenarij

Pomislimo na verigo kavarn, ki ima široko bazo strank, ki kupujejo kavo in hrano v trgovinah ter naročajo izdelke prek spleta. Spletni obiskovalci med brskanjem po izdelkih pogosto niso overjeni, zaradi česar so "neznani uporabniki". Veriga kavarn težko zagotovi prilagojene ponudbe in izkušnje, če so uporabniki neznani. Po drugi strani pa se stranke lahko prijavijo v svoj račun in postanejo "znani uporabniki" podjetja tako, da se pridružijo sistemu zvestobe, kar posledično omogoča bolj personalizirane izkušnje. Customer Insights lahko verigi kavarn pomaga pridobiti vpogled v znane in prej neznane uporabnike.

S Customer Insights lahko podjetje združi profile strank s podatki o dejavnostih iz nepreverjenih (neznanih) sej, potem ko se uporabnik prijavi in postane znan. Veriga kavarn lahko prenese podatke iz drugih podatkovnih virov z uporabo vgrajenih povezovalnikov v Customer Insights, da združi identitete strank iz različnih kanalov.

## <a name="prerequisites"></a>Zahteve

- Spletni podatki se zbirajo in vsebujejo "ID obiskovalcev" za vse obiskovalce.
- Spletni podatki vsebujejo "preverjene ID-je uporabnikov" za prijavljene obiskovalce. Ti ID-ji so povezani s sistemom zvestobe.
- Podatki o dogodkih visoke vrednosti, kot sta »Ogled izdelka« in »Blagajna«, so definirani in vključeni v izvorne podatke skupaj s časovnim žigom dogodka in ID-jem dogodka.

Naslednja tabela prikazuje poenostavljen primer, kako bi lahko zajeli spletne dogodke z visoko vrednostjo.

|ID dogodka|EventTimeStamp|Uporabniško ime|LoyaltyID|Ime dogodka|
|--|--|--|--|--|
|1|07-23-2022 10:00:00|abc123|--|Pogled izdelka|
|2|07-23-2022 10:05:00|abc123|707|Prijava zvestobe|
|3|07-23-2022 10:10:00|abc123|707|Dokončanje nakupa|
|4|07-23-2022 10:20:00|xyz789|--|Pogled izdelka|

## <a name="data-ingestion"></a>Uvoz podatkov

Podatki o strankah lahko izvirajo iz vašega spletnega mesta kot podatki o dogodkih in so lahko shranjeni v vaših lastnih storitvah za analizo podatkov ali tretjih oseb. Spletni podatki vsebujejo znane in neznane uporabnike, če ima spletno mesto tok preverjanja pristnosti, ki se integrira s storitvijo preverjanja pristnosti. Na primer sistem e-trgovine, ki od uporabnikov zahteva, da zagotovijo svoje popolne podatke za dokončanje nakupne transakcije. Ali sistem zvestobe, ki zahteva avtentikacijo za potrditev veljavnega prejemnika nagradnih popustov.

Podatki o dogodkih v našem zgornjem primeru vsebujejo različne ID-je profila znanih in neznanih uporabnikov. Pri dogodku 1 in 4 sta uporabnika neznana, pri dogodku 2 in 3 pa se uporabnik z ID-jem abc123 prijavi v program zvestobe.

:::image type="content" source="media/website-data-source.png" alt-text="Viri podatkov, vključno s spletno stranjo Contoso.":::

Za več informacij o razpoložljivih možnostih za vnos podatkov glejte [Pregled podatkovnih virov](data-sources.md).

## <a name="data-unification"></a>Poenotenje podatkov

Zbliževanje neznanih identitet z znanimi identitetami pomaga omogočiti personalizacijo na podlagi vedenja uporabnikov, ne glede na stanje njihovega profila (znan ali neznan). Prilagojena vsebina za vse uporabnike strankam pomaga hitro priti do najbolj ustreznih izdelkov ali storitev, ki jih v tistem trenutku zanimajo.

Ker so nekateri uporabniki v naših podatkih znani, lahko uporabimo Customer Insights, da te podatke združimo s profilom uporabnika. Za več informacij o poenotenju profilov strank glejte [Pregled poenotenja podatkov](data-unification.md).

1. Izberite izvorna polja iz spletne podatkovne entitete. Uporabite podatke profila, ki so shranjeni v vaših spletnih podatkih, in izberite polja, ki predstavljajo ID-je z demografskimi podatki.

   :::image type="content" source="media/website-source-fields.png" alt-text="Izvorna polja za splet vir podatkov.":::

1. Dodajte pravila za združevanje podvojenih zapisov. Za spletne podatke izberite najbolj zapolnjene podatke.

1. Konfigurirajte pravila in pogoje tekme. Podatki o dogodkih spletnih profilov v tem primeru se bodo na ID-jih ujemali s profili iz drugih podatkovnih virov, ki vsebujejo informacije o strankah. Nastavite pravila natančnega ujemanja za ID-je kot ločena pravila z vsako od drugih entitet profila, ki imajo ustrezen primarni ključ ali ujemanje ID-ja. V primeru so podatki o profilu spletnega dogodka uporabljeni kot zadnja ujemajoča se entiteta, tako da se najprej združijo drugi podatki o profilu.
   1. Ne preverjam **Vključite vse zapise** ustvari poenotene profile za znane uporabnike in vključuje njihove ustrezne ID-je neznanih uporabnikov. Koristno je v scenarijih, ko si želite ogledati pretekle vedenjske dejavnosti znanih uporabnikov, ko so bili še neznani.
   1. Preverjanje **Vključi vse zapise** ustvari ločene zapise profila za neznane uporabnike. Neznani uporabniki dobijo edinstven ID stranke. V prihodnosti, ko je znani profil povezan s podatki o profilu spletnih dogodkov, si bo mogoče ogledati pot na novo znanega uporabnika in jo uporabiti za personalizacijo tudi na podlagi preteklih neznanih vedenjskih podatkov.

:::image type="content" source="media/website-match-rule.png" alt-text="Pravilo ujemanja za entiteto spletnega mesta vir podatkov.":::

## <a name="get-insights"></a>Pridobi vpoglede

Če so profili strank ustvarjeni za neznane in znane uporabnike, se lahko uporabijo podatki o spletnih dogodkih visoke vrednosti [aktivnosti](activities.md). Te dejavnosti je mogoče uporabiti za ustvarjanje več vpogledov. Na primer, stranke, ki so obiskale spletno stran pred šestimi meseci (ko so bile še neznane), ali stranke, ki nimajo ID-ja zvestobe, nikoli niso dokončale blagajne.

:::image type="content" source="media/website-known-unknown.png" alt-text="Posnetek zaslona strani stranke z znanimi in neznanimi strankami.":::

[Obogatiti](enrichment-hub.md) vaše podatke, gradnjo [ukrepe](measures.md), in ustvarite [segmenti](segments.md) za nadaljnjo aktivacijo.

Ustvarite lahko na primer segmente znanih uporabnikov, ki so si ogledali nekatere izdelke, vendar nikoli niso dokončali nakupa.

Za več informacij glejte [Pregled segmentov](segments.md).

## <a name="activate-insights"></a>Aktivirajte vpoglede

Obstaja več načinov za izvoz vaših podatkov in ukrepanje na podlagi temeljnih vpogledov.

Za več informacij glejte [Pregled izvoza](export-destinations.md).
