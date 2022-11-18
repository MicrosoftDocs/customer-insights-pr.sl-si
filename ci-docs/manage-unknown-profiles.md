---
title: Upravljajte neznane profile s Customer Insights
description: Delajte z neznanimi profili strank, ki so ustvarjeni in upravljani v Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: andtapia
ms.author: andreatapia
manager: shellyha
ms.openlocfilehash: 0e12f64a22b93d117009fb8aee76d02a7583e699
ms.sourcegitcommit: 24627d53dcdf607baaab1cc3c299a3584c386173
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/15/2022
ms.locfileid: "9776841"
---
# <a name="manage-unknown-profiles-with-customer-insights"></a>Upravljajte neznane profile s Customer Insights

Uporabniki interneta so na spletu pogosto neznani ali anonimni. Celo najbolj zvesti kupci se lahko zdijo "neznani", če niso prijavljeni v različnih napravah. Pri številnih blagovnih znamkah so znani ali preverjeni uporabniki manjšina kljub naraščajočim pričakovanjem strank glede personalizacije. Glede na to, da je prihodnost piškotkov tretjih oseb pod vprašajem, je upravljanje uporabniških nastavitev na podlagi podatkov prve osebe ključnega pomena za doseganje personaliziranih izkušenj.

Nepozabna personalizacija je odvisna od tega, kako dobro poznate svojo stranko in Customer Insights vam pri tem pomaga s sledenjem vsem strankam.  Ni vam treba omejiti ali ustaviti uporabe podatkov, zbranih na začetku dejavnosti strank. Customer Insights vam omogoča, da prinesete svoje podatke, da ustvarite profil stranke za neznane uporabnike. Ta profil lahko nato uporabite za nadaljnja dejanja, kljub manjkajočim kontaktnim podatkom. Uvozite lastne podatke iz virov, kot so splet, mobilni ali sistemi CRM, v Customer Insights, da nenehno bogatite profile strank. Ko poenotite več interakcij, [obrnite *neznano* stranka v a *znan* stranka](unknown-to-known.md).

## <a name="sample-scenario"></a>Vzorčni scenarij

Recimo, da uporabnik uporablja svojo mobilno napravo za brskanje po vašem spletnem mestu e-trgovine. Spletno mesto dodeli obiskovalcu "mobile_guest123" kot edinstven identifikator in začnete zbirati vedenjske aktivnosti na podlagi njihove spletne dejavnosti. Na primer, katere strani so obiskali, koliko časa so preživeli na teh straneh ali katere povezave so kliknili. Ne poznate njihovega imena ali e-poštnega naslova, vendar ti podatki lahko pomagajo blagovnim znamkam pridobiti smiselne vpoglede v tega določenega uporabnika. Po drugi strani pa lahko te vpoglede uporabite naslednjič, ko uporabnik obišče spletno mesto. Izvedite poizvedbo Customer Insights za »mobile_guest123«, da pridobite seznam segmentov uporabnika, kot so »organsko«, »mobilne stranke prednaročila«, »stranke z visoko vrednostjo« itd., ali pridobite profil za ustvarjanje prilagojenih spletnih izkušenj. Podatke lahko tudi izvozite v kateri koli aktivacijski sistem, da storite enako.

## <a name="prerequisites"></a>Zahteve

- Vnesite podatke prve osebe v Customer Insights
- Vsaka entiteta ima edinstven ID, ki je nastavljen kot primarni ključ
- Vsaka entiteta s primarnim ključem za personalizacijo je poenotena
- Sistem za upravljanje vsebine vašega spletnega mesta lahko uporablja API-je (za spletno personalizacijo na podlagi neposredne komunikacije s Customer Insights)

Naslednja tabela prikazuje poenostavljen primer, kako bi lahko zajeli spletne dogodke z visoko vrednostjo.

|ID dogodka|EventTimeStamp|Uporabniško ime|PrimaryKey|Ime dogodka|
|--|--|--|--|--|
|1|09-15-2022 9:00:00|abc123|ID piškotka1|Pogled izdelka|
|2|09-18-2022 10:05:00|abc123|ID piškotka1|Pogled izdelka|
|3|09-18-2022 10:10:00|abc123|ID piškotka1|Dodaj v voziček|
|4|09-21-2022 09:05:00|abc123|ID piškotka1|Pogled izdelka|

## <a name="data-ingestion"></a>Uvoz podatkov

Za več informacij o razpoložljivih možnostih za vnos podatkov glejte [Pregled podatkovnih virov](data-sources.md).

## <a name="data-unification"></a>Poenotenje podatkov

Za več informacij o poenotenju profilov strank glejte [Pregled poenotenja podatkov](data-unification.md).

## <a name="get-insights"></a>Pridobi vpoglede

[Obogatiti](enrichment-hub.md) vaše podatke, gradnjo [ukrepe](measures.md), in ustvarite [segmenti](segments.md) za nadaljnjo aktivacijo.

Ustvarite lahko na primer segmente neznanih uporabnikov, ki so brskali po istih straneh izdelkov, vendar nikoli niso dokončali nakupa.

## <a name="activation"></a>Aktiviranje

S svojimi podatki v Customer Insights in vašimi vpogledi pripravljenimi za delo, lahko uporabite Customer Insights za personalizacijo:

1. Uporabi [OData API](apis.md) za pridobitev članstva v segmentu ali profila stranke Za več primerov glejte [Primeri poizvedb OData za API-je Customer Insights](odata-examples.md).

1. [Izvozi](export-destinations.md) vaše podatke v vaše aktivacijske sisteme.

Primer: Neznani uporabnik večkrat obišče spletno stran in obišče strani z izdelki za različne modele usnjenih čevljev. S temi podatki, ki so na voljo v Customer Insights, lahko neznanega uporabnika vključite v segment ljudi, ki jih zanimajo usnjeni čevlji. Uporabite ta segment za obveščanje o prilagajanju gradnje vašega spletnega mesta za obiskovalce, ki se vračajo. Ob naslednjem obisku stran prepozna neznanega uporabnika in mu lahko ponudi 10% kupon na usnjene čevlje.

[!INCLUDE [footer-include](includes/footer-banner.md)]
