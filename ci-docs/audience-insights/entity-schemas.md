---
title: Sheme entitet Customer Insights v rešitvi Common Data Model
description: Delo z entitetami v rešitvi Common Data Model.
ms.date: 04/17/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2cf01029ef6b64fe566022d09ce65bca3603189c
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643928"
---
# <a name="entity-schemas-in-common-data-model"></a>Sheme entitet v rešitvi Common Data Model

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

[Common Data Model](https://docs.microsoft.com/common-data-model/) je deklarativna specifikacija in opredelitev standardnih entitet, ki predstavljajo pogosto uporabljane koncepte in dejavnosti po poslovnih in storilnostnih aplikacijah. Ta model se širi tudi na podatke opazovanj in analitične podatke. Common Data Model zagotavlja dobro opredeljene, modularne in razširljive poslovne entitete – kot so kupec, poslovna enota, primer, stik, možna stranka, priložnost in izdelek – ter interakcije z dobavitelji, delavci in strankami – kot so dejavnosti in pogodbe o ravni storitve. Vsakdo lahko nadgradi in razširi definicije Common Data Model, da zajame dodatne poslovne zamisli.

To je model podatkov v skupni rabi, ki aplikacijam in integratorjem podatkov omogoča lažje sodelovanje z zagotavljanjem enotne definicije podatkov. Common Data Model vključuje bogat sistem metapodatkov s standardnimi entitetami, odnosi, hierarhijami, lastnostmi in drugim. Izvira iz aplikacij Dynamics 365 in je storitvi GitHub odprtokodni model z več kot 260 standardnimi entitetami. Velik sistem notranjih in zunanjih partnerjev prispeva industrijske koncepte v Common Data Model.

Danes več sistemov in platform uporablja Common Data Model, vključno podatkovni toki Power BI in podatkovne storitve Azure. Model je že podprt v storitvah Common Data Service, Dynamics 365, Power Apps, Power BI in prihodnjih podatkovnih storitvah Azure, in neposredno pridobiva vrednost za [Open Data Initiative](https://www.microsoft.com/open-data-initiative).

## <a name="customer-insights-entity-schemas"></a>Sheme entitet Customer Insights

Da bi vzpostavili popoln pregled stranke in poskrbeli za razpoložljivost modelov Customer Insights v rešitvi Common Data Model za razširljivost, smo objavili naslednje sheme entitet:

| Entiteta | Opis |
|---------|---------|
|[CustomerActivity](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | Dejavnost, ki jo izvaja uporabnik in ima opazovalno vrednost za poslovanje. |
|[CustomerProfile](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | Oseba ali organizacija, ki je opravljala poslovno dejavnost ali ima potencial za vključitev v poslovno dejavnost. |
|[MeasureDefinition](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Definicija dogodkov KPI, razdeljenih na nič ali več dimenzij (npr. mesečno aktivni uporabniki, skupna poraba stranke, povprečni stroški pridobitve stranke) |
|[Segment](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Določa skupino članov s skupnimi lastnostmi. |
|[SegmentMembership](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Člani, ki sodelujejo v določenem segmentu. |

Za več informacij glejte dokumentacijo o [shemah entitet Customer Insights v Common Data Model](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Prikaz entitet z uporabo orodja Common Data Model Entity Navigator

Entitete si lahko ogledate v orodju [Common Data Model Entity Navigator](https://microsoft.github.io/CDM/). Izberite gumb **Naloži iz storitve GitHub!** in se pomaknite na **foundationCommon** > **crmCommon** > **solutions** > **customerInsights**, kjer boste našli seznam entitet Customer Insights in njihove definicije.
> [!div class="mx-imgBorder"]
> ![CDM Entity Navigator prikazuje entiteto CustomerActivity](media/CDM-entity-navigator.png "CDM Entity Navigator prikazuje entiteto CustomerActivity")
