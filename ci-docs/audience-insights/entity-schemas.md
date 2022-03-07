---
title: Sheme entitet Customer Insights v rešitvi Common Data Model
description: Delo z entitetami v rešitvi Common Data Model.
ms.date: 08/13/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: f0af2a6d8a90ff01ea9d4eeb29f34113261fd0d4
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231077"
---
# <a name="entity-schemas-in-common-data-model"></a>Sheme entitet v rešitvi Common Data Model



[Common Data Model](/common-data-model/) je deklarativna specifikacija in opredelitev standardnih entitet, ki predstavljajo pogosto uporabljane koncepte in dejavnosti po poslovnih in storilnostnih aplikacijah. Ta model se širi tudi na podatke opazovanj in analitične podatke. Common Data Model zagotavlja dobro opredeljene, modularne in razširljive poslovne entitete – kot so kupec, poslovna enota, primer, stik, možna stranka, priložnost in izdelek – ter interakcije z dobavitelji, delavci in strankami – kot so dejavnosti in pogodbe o ravni storitve. Vsakdo lahko nadgradi in razširi definicije Common Data Model, da zajame dodatne poslovne zamisli.

To je model podatkov v skupni rabi, ki aplikacijam in integratorjem podatkov omogoča lažje sodelovanje z zagotavljanjem enotne definicije podatkov. Common Data Model vključuje bogat sistem metapodatkov s standardnimi entitetami, odnosi, hierarhijami, lastnostmi in drugim. Izvira iz aplikacij Dynamics 365 in je storitvi GitHub odprtokodni model z več kot 260 standardnimi entitetami. Velik sistem notranjih in zunanjih partnerjev prispeva industrijske koncepte v Common Data Model.

Common Data Model danes uporablja več sistemov in platform, vključno s podatkovnimi tokovi Power BI in podatkovnimi storitvami Azure. Podprt je že v Microsoft Dataverse, Dynamics 365, Power Apps, Power BI in prihajajočih podatkovnih storitvah Azure, ki neposredno razmejujejo vrednost za iniciativo [Pobuda za odprte podatke](https://www.microsoft.com/open-data-initiative).

## <a name="customer-insights-entity-schemas"></a>Sheme entitet Customer Insights

Da bi vzpostavili popoln pregled stranke in poskrbeli za razpoložljivost modelov Customer Insights v rešitvi Common Data Model za razširljivost, smo objavili naslednje sheme entitet:

| Entiteta | Opis |
|---------|---------|
|[CustomerActivity](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | Dejavnost, ki jo izvaja uporabnik in ima opazovalno vrednost za poslovanje. |
|[CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | Oseba ali organizacija, ki je opravljala poslovno dejavnost ali ima potencial za vključitev v poslovno dejavnost. |
|[MeasureDefinition](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Definicija dogodkov KPI, razdeljenih na nič ali več dimenzij (npr. mesečno aktivni uporabniki, skupna poraba stranke, povprečni stroški pridobitve stranke) |
|[Segment](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Določa skupino članov s skupnimi lastnostmi. |
|[SegmentMembership](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Člani, ki sodelujejo v določenem segmentu. |

Za več informacij glejte dokumentacijo o [shemah entitet Customer Insights v Common Data Model](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Prikaz entitet z uporabo orodja Common Data Model Entity Navigator

Entitete si lahko ogledate v orodju [Common Data Model Entity Navigator](https://microsoft.github.io/CDM/). Izberite entiteto v razdelku Application Insights, da dobite seznam entitet Customer Insights in njihove definicije.
> [!div class="mx-imgBorder"]
> ![Orodje za krmarjenje po entitetah CDM prikazuje entiteto CustomerActivity.](media/CDM-entity-navigator.png "CDM Entity Navigator prikazuje entiteto CustomerActivity")


[!INCLUDE[footer-include](../includes/footer-banner.md)]
