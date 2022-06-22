---
title: Uporaba virov podatkov za vključitev podatkov
description: Naučite se uvoziti podatke iz različnih virov.
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: overview
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: e22977107565a0b28b74f41576a1c7ccc74f6dc1
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011769"
---
# <a name="data-sources-overview"></a>Pregled virov podatkov

Dynamics 365 Customer Insights zagotavlja povezave za prenos podatkov iz širokega nabora virov. Povezovanje z vir podatkov se pogosto imenuje postopek *zaužitje podatkov*. Po zaužitju podatkov lahko [poenotiti](data-unification.md), ustvarite vpoglede in aktivirajte podatke za ustvarjanje prilagojenih izkušenj.

## <a name="add-data-sources"></a>Dodajanje virov podatkov

Vire podatkov lahko priložite ali uvozite v Customer Insights. Na spodnjih povezavah so navodila za dodajanje podatkovnih virov.

**Priložite vir podatkov**

Če imate podatke pripravljene v eni od Microsoftovih podatkovnih storitev Azure, se lahko Customer Insights preprosto poveže z vir podatkov, ne da bi morali znova vnesti podatke. Izberite eno od teh možnosti:
- [Azure Data Lake Storage(datoteke csv ali parket v mapi Common Data Model)](connect-common-data-model.md)
- [Azure Synapse Analytics(Baze podatkov o jezerih)](connect-synapse.md)
- [Microsoft Dataverse podatkovno jezero](connect-dataverse-managed-lake.md)

**Uvozite in preoblikujte**

Če uporabljate lokalne vire podatkov, Microsoft ali podatke tretjih oseb, uvozite in preoblikujte podatke z uporabo Power Query konektorji.
- [Power Query konektorji](connect-power-query.md)

## <a name="review-data-sources"></a>Preglejte vire podatkov

Če je bilo vaše okolje konfigurirano za uporabo pomnilnika Customer Insights in uporabljate lokalne vire podatkov, uporabite Power Platform tokovi podatkov. Z Power Platform podatkovnih tokov, si lahko ogledate vire podatkov v skupni rabi in vire podatkov, ki jih upravljajo drugi. The **Viri podatkov** stran navaja vire podatkov v treh razdelkih:
- **V skupni rabi** : Viri podatkov, ki jih lahko upravljajo vsi skrbniki Customer Insights. Power Platform pretokov podatkov, lastnega računa za shranjevanje in pripenjanja na a Dataverse -upravljano podatkovno jezero so primeri skupnih virov podatkov.
- **Upravljam jaz** :Power Platform tokovi podatkov, ki jih ustvarite in upravljate samo vi. Drugi skrbniki Customer Insights si lahko samo ogledajo te tokove podatkov, ne pa jih urejajo, osvežujejo ali brišejo.
- **Upravljajo drugi** :Power Platform tokovi podatkov, ki so jih ustvarili drugi skrbniki. Lahko si jih samo ogledate. V njem je naveden lastnik toka podatkov, na katerega se lahko obrnete za kakršno koli pomoč.
> [!NOTE]
> Vse entitete si lahko ogledajo in uporabljajo drugi uporabniki. Medtem ko so viri podatkov v lasti uporabnika, ki jih je ustvaril, lahko entitete, ki nastanejo pri zaužitju podatkov, uporablja vsak uporabnik Customer Insights.

Če vaše okolje ne uporablja Power Platform pretoki podatkov, **Viri podatkov** stran vsebuje le seznam vseh virov podatkov. Brez prikaza razdelkov.

Pojdi do **Podatki** > **Viri podatkov** če si želite ogledati ime vsakega zaužitega vir podatkov, njegovo stanje in zadnjič osveževanje podatkov za ta vir. Seznam virov podatkov lahko razvrstite po vseh stolpcih.

:::image type="content" source="media/configure-data-datasource-added.png" alt-text="Vir podatkov je dodan.":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Nalaganje podatkov lahko traja nekaj časa. Po uspešni osvežitvi je mogoče uvožene podatke pregledati na strani **Entitete**. Za več informacij glejte [Entitete](entities.md).

## <a name="refresh-data-sources"></a>Osveževanje virov podatkov

Vire podatkov lahko osvežite po samodejnem urniku ali ročno na zahtevo. [Lokalni viri podatkov](connect-power-query.md#add-data-from-on-premises-data-sources) osveževati po lastnih urnikih, ki so nastavljeni med vnosom podatkov. Za priložene vire podatkov zaužitje podatkov porabi najnovejše podatke, ki so na voljo od tega vir podatkov.

Pojdi do **Admin** > **sistem** > [**Urnik**](system.md#schedule-tab) da konfigurirate sistemsko načrtovano osveževanje vaših prevzetih podatkovnih virov.

Če želite osvežiti vir podatkov na zahtevo, sledite tem korakom:

1. Pojdite na **Podatki** > **Viri podatkov**.

1. Izberite navpično elipso (&vellip;) poleg vir podatkov, ki ga želite osvežiti in izberite **Osveži** s spustnega seznama. Vir podatkov se zdaj sproži za ročno osvežitev. Če osvežite vir podatkov, se posodobijo tudi shema entitet in podatki za vse entitete, določene v viru podatkov.

1. Izberite **Ustavi osveževanje**, če želite preklicati obstoječo osvežitev, in se bo vir podatkov vrnil na zadnje stanje osveževanja.

## <a name="delete-a-data-source"></a>Brisanje vira podatkov

Vir podatkov lahko izbrišete le, če se podatki ne uporabljajo pri nobeni obdelavi, kot so poenotenje, vpogledi, aktivacije ali izvozi.

1. Pojdite na **Podatki** > **Viri podatkov**.

2. Izberite navpično elipso (&vellip;) poleg vir podatkov, ki ga želite odstraniti, in izberite **Izbriši** iz spustnega menija.

3. Potrdite izbris.


[!INCLUDE [footer-include](includes/footer-banner.md)]
