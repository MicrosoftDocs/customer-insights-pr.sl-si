---
title: Prenos podatkov v realnem času (predogled)
description: Splošne informacije o zmožnostih v realnem času pri vpogledih v občinstvo.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 138704445d52df3336af6af60420f0bd0ee0c639
ms.sourcegitcommit: a8e99cf8b23ccc00d76c1dee22afd808a160a5c8
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/22/2022
ms.locfileid: "8464130"
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

- [posredni](#connect-via-the-dynamics-365-customer-insights-connector), pri čemer se uporabi [povezovalnik storitve Dynamics 365 Customer Insights](/connectors/customerinsights/)
- [neposredni](#connect-directly-to-the-real-time-api), pri čemer se uporabi koda

Za oba načina veljajo naslednje zahteve:

- Okolje Customer Insights
- Poenoteni profili strank
- Konfigurirane in izvedene dejavnosti
- Dovoljenja sodelavcev in skrbnikov za preverjanje pristnosti vašega računa

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a>Povezovanje prek povezovalnika storitve Dynamics 365 Customer Insights

API v realnem času lahko uvozi podatke iz namenskega povezovalnika Power Platform, [povezovalnika storitve Dynamics 365 Customer Insights](/connectors/customerinsights/), brez potrebe po pisanju in uvajanju kakršne koli kode.    
Povezovalnik lahko izvaja enaka dejanja v realnem času kot API. Za izboljšane povezovalnika potrebujete veljavno licenco. Za več informacij glejte razdelek [Pogosta vprašanja o licenciranju za Power Apps in Power Automate](/power-platform/admin/powerapps-flow-licensing-faq).

- Power Platform [Power Apps in/ali Power Automate](/connectors/)
- [Logične aplikacije storitve](/azure/connectors/apis-list) Azure

Za podrobnosti o ustvarjanju tokov glejte [dokumentacijo za Power Automate](/power-automate/).

## <a name="connect-directly-to-the-real-time-api"></a>Povezovanje neposredno z API-jem v realnem času

Zmožnosti v realnem času lahko uporabite tako, da sestavite svoj prodajni lijak in se neposredno povežete z API-jem v realnem času.    
Dejavnost lahko objavite v obliki svojega izvornega sistema ali v obliki zapisa UnifiedActivity. Obliko zapisa lahko pridobite tako, da z API-jem pokličete /api/instances/{instanceId}/manage/entities/UnifiedActivity.

Podrobnosti tega API-ja, vključno s parametri in odzivi, najdete v razdelku **EntityData** pri [sklicu za API-je za Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Če želite več informacij, glejte razdelek [Delo z API-ji za Customer Insights](apis.md).

## <a name="understand-your-real-time-usage-with-telemetry"></a>Razumevanje uporabe v realnem času s telemetrijo

Pridobite pregled obsega zahtev za API v realnem času in informacije o težavah, s katerimi se sistem lahko srečuje. Lahko [dostopate do telemetrije v realnem času](system.md#api-usage-tab). 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
