---
title: Uvod v rešitev Dynamics 365 Customer Insights
description: Pregled Customer Insights pomaga virom za hiter začetek.
ms.reviewer: v-wendysmith
ms.author: mhart
author: m-hartmann
ms.date: 04/12/2022
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 1c925110f40319df77940d1c32f24a99504d6ec6
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011999"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Uvod v rešitev Dynamics 365 Customer Insights

Vpogled v stranke vam lahko pomaga graditi globlje razumevanje vaših strank. Povežite podatke iz različnih virov glede transakcij, vedenja in opazovanja, da ustvarite popoln pregled strank. S temi vpogledi omogočite izkušnje in procese, osredotočene na stranko. Poenotenje in razumevanje podatkov o strankah ter njihova uporaba za inteligentne vpoglede in dejanja.

## <a name="step-1-create-an-environment"></a>1. korak: Ustvarjanje okolja

Najprej ustvarite okolje za delo. Če je vaša organizacija že kupila licenco, glejte razdelek [Ustvarjanje okolja](create-environment.md). Če želite začeti preskus za Customer Insights, glejte [Nastavite poskusno okolje](trial-signup.md).

## <a name="step-2-explore-customer-insights"></a>2. korak: Raziščite vpoglede strank

Ko se prvič prijavite v Customer Insights, konfigurirajte nastavitve in raziščite izdelek.

1. [prijavite se v Customer Insights](https://home.ci.ai.dynamics.com) z uporabo vašega Microsofta Azure Active Directory (AAD) uporabniški račun.

1. Spremenite okolje, da si ogledate demo podatke in [raziščite vpogled v stranke](home.md).

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>3. korak: Vnos, poenotenje in nastavitev odnosov za vaše podatke

Poenoteni profili so osnova za pridobivanje vpogledov in ukrepanje v zvezi s podatki. Vnesite podatke iz različnih virov in zaženite postopek poenotenja podatkov, da združite poenotene profile. Podajte Odnosi med zaužitimi entitetami in uporabite funkcije obogatitve za dodajanje informacij v profile.

1. Vnesite podatke tako, da ustvarite vire podatkov iz več možnosti. Izbirajte med [Azure Data Lake Storage, vključno s skupnim podatkovnim modelom](connect-common-data-model.md),[Azure Synapse Analytics](connect-synapse.md),[Microsoft Dataverse](connect-dataverse-managed-lake.md), oz [Power Query konektorji](connect-power-query.md).

1. Zaženite [proces poenotenja podatkov](data-unification.md) z identifikacijo [izvorna polja](map-entities.md), odstranjevanje [dvojniki](remove-duplicates.md),[ujemanje pogojev](match-entities.md), in [povezovalna polja](merge-entities.md).

1. Spoznajte [entitete, ki jih sistem ustvari](entities.md), in ustvarite [odnose med uvoženimi entitetami](relationships.md).

## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>4. korak: Izboljšajte poenotene profile s predvidevanji, dejavnostmi in merami

Z nastavljenimi enotnimi profili izboljšajte svoje podatke in dodatno povečajte informacije, ki jih ponujajo.

1. V razširjeni knjižnici ponudnikov obogatitve izberite [obogatitev svojih podatkov o strankah](enrichment-hub.md).

1. Uporabite [v naprej pripravljene modele](predictions-overview.md) za napoved verjetnosti izgube ali pričakovanih prihodkov.

1. [Konfigurirajte dejavnosti](activities.md) na podlagi uvoženih podatkov in ponazorite interakcije s svojimi strankami v kronološki časovnici.

1. [Ustvarite mere](measures.md) za merjenje svojih poslovnih ciljev in KPI-jev.

## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>5. korak: Ustvarite segmente in aktivirajte podatke z različnimi možnostmi izvoza

Zdaj, ko so vaši podatki popolni in vsebujejo širok nabor informacij o vaših strankah, poiščite načine za ukrepanje glede teh podatkov.

1. [Ustvarite segmente](segments.md), podmnožice vaše baze strank, da zagotovite, da so vaša dejanja ustrezna za ciljne stranke.

1. Brskajte po razširjenem katalogu [možnosti izvoza](export-destinations.md), kjer lahko uporabite podatke o strankah. Podatke lahko na primer uporabite za upravljanje promocij in stik z digitalnim trženjem.

1. Preglejte možnosti integracije, na primer v druge aplikacije Dynamics 365 z [Dodatek za kartico stranke](customer-card-add-in.md).  


[!INCLUDE [footer-include](includes/footer-banner.md)]
