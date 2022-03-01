---
title: Vnos in omejitve podatkov v realnem času
description: Splošne informacije o zmožnostih v realnem času pri vpogledih v občinstvo.
ms.date: 10/27/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00a72e6a67e33c8e70ccc6139c5e62020f9d3e1
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689195"
---
# <a name="real-time-data-ingestion-preview"></a>Uvoz podatkov v realnem času (predogled)

Funkcije v skoraj realnem času vam omogočajo, da si v nekaj sekundah ogledate najnovejše interakcije, ki so jih vaše stranke opravile z vašimi izdelki in storitvami.

[Načrtovane osvežitve](system.md#schedule-tab) vključujejo veliko število zapisov in več zapletenih postopkov. Najprej se podatki izvlečejo iz vira podatkov. Nato se podatki poenotijo in obogatijo z dodatnimi informacijami. Vsak posamezen postopek lahko traja od nekaj minut do nekaj ur.

Funkcija v realnem času zagotavlja podatke takoj za porabo, dokler naslednje načrtovano osveževanje ne izvleče teh podatkov iz vira podatkov.

Posodobitve v realnem času imajo čas poteka, po katerem ne preglasijo vrednosti iz vira podatkov:

- Posodobitve profilov bodo shranjene 4 ure
- Dejavnosti bodo shranjene 30 dni

Te vrednosti so parametri klicev API-jev, ki jih lahko spremenite. Njihov cilj je zagotoviti, da vaši izvorni podatki ostanejo vaš vir resnice. Če želite, da so posodobitve v realnem času vključene dlje časa, jih morate dodati v vir podatkov, da bodo vzete med naslednjo načrtovano osvežitvijo.

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a>Posodobitev polj poenotenih profilov strank v realnem času

Posodobljeni profili se bodo v nekaj sekundah prikazali v pogledu kartice stranke ali kateri koli drugi vizualizaciji.

Ker postopki v realnem času potekajo po poenotenju podatkov, veljajo le za poenotene profile strank. Posledično se spremembami profilov v realnem času ne bodo posodobile mere, članstva v segmentu ali obogatitve.

### <a name="limitations"></a>Omejitve

- Profile strank lahko posodabljate, vendar jih ne morete ustvariti ali izbrisati.
- Izvažanje posodobitev v realnem času v zunanje sisteme, kot je Power BI, trenutno ni na voljo.

## <a name="real-time-creation-of-activities"></a>Ustvarjanje dejavnosti v realnem času

API v realnem času vam omogoča objavo nove dejavnosti iz vašega izvornega sistema (posamezen izvorni zapis) v poenotenem profilu stranke. Nova dejavnost bo v nekaj sekundah na voljo kot poenotena dejavnost na časovnici poenotenega profila stranke. Časovnico lahko vidite v pogledu kartice stranke ali kateri koli drugi integraciji časovne osi, ki ste jo konfigurirali.

> [!NOTE]
>
> - Dejavnosti so nespremenljive. Ko so ustvarjene, se ne spremenijo.
> - Trenutno segmenti in mere ne bodo posodobljeni glede na novo dejavnost.
> - Dejavnosti, dodane samo prek API-ja v realnem času, se ne izvozijo in ne bodo prikazane v storitvi PowerBI.

Obstajata dva načina za povezavo z API-jem v realnem času:

- [posredni](#connect-via-the-dynamics-365-customer-insights-connector), pri čemer se uporabi [povezovalnik storitve Dynamics 365 Customer Insights](https://docs.microsoft.com/connectors/customerinsights/)
- [neposredni](#connect-directly-to-the-real-time-api), pri čemer se uporabi koda

Za oba načina veljajo naslednje zahteve:

- Okolje Customer Insights
- Poenoteni profili strank
- Konfigurirane in izvedene dejavnosti
- Dovoljenja sodelavcev in skrbnikov za preverjanje pristnosti vašega računa

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a>Povezovanje prek povezovalnika storitve Dynamics 365 Customer Insights

API v realnem času lahko uvozi podatke iz namenskega povezovalnika Power Platform, [povezovalnika storitve Dynamics 365 Customer Insights](https://docs.microsoft.com/connectors/customerinsights/), brez potrebe po pisanju in uvajanju kakršne koli kode.    
Povezovalnik lahko izvaja enaka dejanja v realnem času kot API. Za izboljšane povezovalnika potrebujete veljavno licenco. Za več informacij glejte razdelek [Pogosta vprašanja o licenciranju za Power Apps in Power Automate](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).

- Power Platform [Power Apps in/ali Power Automate](https://docs.microsoft.com/connectors/)
- [Logične aplikacije storitve](https://docs.microsoft.com/azure/connectors/apis-list) Azure

Za podrobnosti o ustvarjanju tokov glejte [dokumentacijo za Power Automate](https://docs.microsoft.com/power-automate/).

## <a name="connect-directly-to-the-real-time-api"></a>Povezovanje neposredno z API-jem v realnem času

Zmožnosti v realnem času lahko uporabite tako, da sestavite svoj prodajni lijak in se neposredno povežete z API-jem v realnem času.    
Dejavnost lahko objavite v obliki svojega izvornega sistema ali v obliki zapisa UnifiedActivity. Obliko zapisa lahko pridobite tako, da z API-jem pokličete /api/instances/{instanceId}/manage/entities/UnifiedActivity.

Podrobnosti tega API-ja, vključno s parametri in odzivi, najdete v razdelku **EntityData** pri [sklicu za API-je za Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Če želite več informacij, glejte razdelek [Delo z API-ji za Customer Insights](apis.md).

## <a name="understand-your-real-time-usage-with-telemetry"></a>Razumevanje uporabe v realnem času s telemetrijo

Pridobite pregled obsega zahtev za API v realnem času in informacije o težavah, s katerimi se sistem lahko srečuje. [Dostopate lahko do telemetrije v realnem času](system.md#api-usage-tab) tako, da se pomaknete v razdelek **Skrbnik** > **Sistem** > **Uporaba API-ja**. V tabeli **Postopki** vrstice za postopke API, ki uporabljajo metode v realnem času, vsebujejo gumb za ogled uporabe API-ja v realnem času. Gumb je vizualiziran s simbolom daljnogleda. Izberite gumb, da odprete stransko podokno s podrobnostmi o uporabi za sprotno uporabo API-ja v trenutnem okolju.

Uporabite izbirnik **Združi po**, da izberete, kako najbolje predstaviti interakcije v realnem času na časovnici z obsegom od zadnjih 24 ur do zadnjih 30 dni. Podatke lahko združite po metodi API-ja, določenem imenu entitete (uvožena entiteta), avtorju ustvarjanja (vir dogodka), rezultatu (uspeh ali neuspeh) ali kodah napak. Podatki so na voljo kot grafikon zgodovine in kot tabela.
