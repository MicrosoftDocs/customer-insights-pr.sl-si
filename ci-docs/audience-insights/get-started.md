---
title: Uvod v možnost vpogledov v občinstvo v storitvi Dynamics 365 Customer Insights
description: Pregled vpogledov v občinstvo pomaga virom za hiter začetek.
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 2776b2292560f9ea61a06d2b1b7bc7811d35c860
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353747"
---
# <a name="get-started-with-dynamics-365-customer-insights-audience-insights-capability"></a>Uvod v možnost vpogledov v občinstvo s storitvijo Dynamics 365 Customer Insights

Vpogledi v občinstvo pomagajo, da bolje razumete svoje stranke. Povežite podatke iz različnih virov glede transakcij, vedenja in opazovanja, da ustvarite popoln pregled strank. S temi vpogledi omogočite izkušnje in procese, osredotočene na stranko. Poenotenje in razumevanje podatkov o strankah ter njihova uporaba za inteligentne vpoglede in dejanja.

## <a name="step-1-create-an-environment"></a>1. korak: Ustvarjanje okolja

Za začetek morate najprej ustvariti okolje za delo. Če je vaša organizacija že kupila licenco, glejte razdelek [Ustvarjanje okolja](create-environment.md). Če želite začeti preskus za vpoglede v občinstvo, glejte [Nastavitev preskusnega okolja](../trial-signup.md). 

## <a name="step-2-explore-audience-insights"></a>2. korak: Raziskovanje vpogledov v občinstvo

Ko se prvič prijavite v vpoglede v občinstvo, lahko konfigurirate nastavitve in raziščete izdelek.

1. [Vpišite se v vpoglede v občinstvo](https://home.ci.ai.dynamics.com) z uporabo svojega Microsoftovega uporabniškega računa za storitev Azure Active Directory (AAD).

1. [Spremenite okolje](manage-environments.md#switch-environments) za ogled predstavitvenih podatkov in [raziščite vpoglede v občinstvo](home.md).

##  <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>3. korak: Vnos, poenotenje in nastavitev odnosov za vaše podatke

Poenoteni profili so osnova za pridobivanje vpogledov in ukrepanje v zvezi s podatki. Vnesite podatke iz različnih virov in zaženite postopek poenotenja podatkov, da združite poenotene profile. Določite odnose med uvoženimi entitetami, uporabite funkcije obogatitve za dodajanje informacij v profile. 

1. Vnesite podatke tako, da ustvarite vire podatkov iz več možnosti. Izbirajte med [Power Query konektorji](connect-power-query.md), a [Mapa skupnega podatkovnega modela](connect-common-data-model.md), ali [Microsoft Dataverse](/dynamics365/customer-insights/audience-insights/connect-dataverse-managed-lake). 

1. Zaženite [postopek poenotenja podatkov](data-unification.md) tako, da greste skozi [zemljevid](map-entities.md) in omogočite [ujemanje](match-entities.md) in [spajanje](merge-entities.md) faz.

1. Spoznajte [entitete, ki jih sistem ustvari](entities.md), in ustvarite [odnose med uvoženimi entitetami](relationships.md).
    
## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>4. korak: Izboljšajte poenotene profile s predvidevanji, dejavnostmi in merami

Z nastavljenimi poenotenimi profili lahko izboljšate svoje podatke in še povečate informacije, ki jih ponujajo.

1. V razširjeni knjižnici ponudnikov obogatitve izberite [obogatitev svojih podatkov o strankah](enrichment-hub.md).

1. Uporabite [v naprej pripravljene modele](predictions-overview.md) za napoved verjetnosti izgube ali pričakovanih prihodkov.

1. [Konfigurirajte dejavnosti](activities.md) na podlagi uvoženih podatkov in ponazorite interakcije s svojimi strankami v kronološki časovnici. 

1. [Ustvarite mere](measures.md) za merjenje svojih poslovnih ciljev in KPI-jev.
 
## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>5. korak: Ustvarite segmente in aktivirajte podatke z različnimi možnostmi izvoza

Zdaj, ko so vaši podatki popolni in vsebujejo širok obseg informacij o vaših strankah, je čas, da poiščete načine za ukrepanje v zvezi s temi podatki. 

1. [Ustvarite segmente](segments.md), podmnožice vaše baze strank, da zagotovite, da so vaša dejanja ustrezna za ciljne stranke.

1. Brskajte po razširjenem katalogu [možnosti izvoza](export-destinations.md), kjer lahko uporabite podatke o strankah. Podatke lahko na primer uporabite za upravljanje promocij in stik z digitalnim trženjem.

1. Preglejte možnosti integracije, na primer z [neposredno povezavo z vpogledi v interakcije](../engagement-insights/integrate-audience-insights-engagement-insights.md) ali z drugimi aplikacijami Dynamics 365 z [dodatkom za kartico stranke](customer-card-add-in.md).  


[!INCLUDE[footer-include](../includes/footer-banner.md)]