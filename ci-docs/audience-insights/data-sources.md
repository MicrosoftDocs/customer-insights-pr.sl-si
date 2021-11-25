---
title: Uporaba virov podatkov za vključitev podatkov
description: Naučite se uvoziti podatke iz različnih virov.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 27cbd0346b1219c7812f4b90327dd27b645c2b8e
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732175"
---
# <a name="data-sources-overview"></a>Pregled virov podatkov

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Zmožnost občinstvo vpogledov v Dynamics 365 Customer Insights se povezuje s podatki iz širokega nabora virov. Povezovanje z vir podatkov se pogosto imenuje postopek *zaužitje podatkov*. Po zaužitju podatkov lahko jih lahko [poenotite](data-unification.md) in jih uporabite.

## <a name="add-a-data-source"></a>Dodajanje vira podatkov

Glejte podrobne članke o tem, kako dodati vir podatkov, odvisno od tega, katero možnost izberete.

Vir podatkov lahko dodate na tri glavne načine:

- [S pomočjo številnih priključkov Power Query](connect-power-query.md)
- [Iz mape Common Data Model](connect-common-data-model.md)
- [Iz vašega Microsoft Dataverse jezera](connect-dataverse-managed-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a>Dodajanje podatkov iz virov podatkov na mestu uporabe

Prenos podatkov iz virov podatkov na mestu uporabe v občinstvo Insights je podprt na podlagi tokov podatkov Microsoft Power Platform. Tokove podatkov lahko v storitvi Customer Insights omogočite z [zagotavlja URL okolja Microsoft Dataverse](create-environment.md) pri postavljanju okolja.

Viri podatkov, ki so ustvarjeni po povezovanju okolja Dataverse s Customer Insights, bodo uporabljeni [Power Platform tokovi podatkov](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) privzeto. Za podatkovne tokove je prek prehoda za podatke podprta povezljivost na mestu uporabe. Odstranite in ponovno ustvarite vire podatkov, ki so obstajali, preden je bilo okolje Dataverse povezano z [uporabite podatkovne prehode na mestu uporabe](/data-integration/gateway/service-gateway-app).

Podatkovni prehodi iz obstoječega okolja Power BI ali Power Apps bodo vidni in jih lahko znova uporabite v Customer Insights. Stran z viri podatkov prikazuje povezave do okolja Microsoft Power Platform, kjer si lahko ogledate in konfigurirate podatkovne prehode na mestu uporabe.

## <a name="review-ingested-data"></a>Pregled zaužitih podatkov

Videli boste ime vsakega zaužitega vira podatkov, njegovo stanje in čas, ko so bili podatki za ta vir nazadnje osveženi. Seznam virov podatkov lahko razvrstite po vseh stolpcih.

> [!div class="mx-imgBorder"]
> ![Vir podatkov je dodan.](media/configure-data-datasource-added.png "Vir podatkov je dodan")

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

Nalaganje podatkov lahko traja nekaj časa. Po uspešni osvežitvi je mogoče uvožene podatke pregledati na strani **Entitete**. Za več informacij glejte [Entitete](entities.md).

## <a name="refresh-a-data-source"></a>Osveževanje vira podatkov

Vire podatkov lahko osvežite po samodejnem urniku ali ročno na zahtevo. 

Izberite **Skrbnik** > **Sistem** > [**Načrtovanje**](system.md#schedule-tab) za konfiguriranje načrtovanih osvežitev vseh vključenih virov podatkov.

Če želite osvežiti vir podatkov na zahtevo, sledite tem korakom:

1. Pri vpogledih v občinstvo izberite **Podatki** > **Viri podatkov**.

2. Izberite navpične tri pike poleg tistega vira podatkov, ki ga želite osvežiti, in na spustnem seznamu izberite **Osveži**.

3. Vir podatkov se zdaj sproži za ročno osvežitev. Če osvežite vir podatkov, se posodobijo tudi shema entitet in podatki za vse entitete, določene v viru podatkov.

4. Izberite **Ustavi osveževanje**, če želite preklicati obstoječo osvežitev, in se bo vir podatkov vrnil na zadnje stanje osveževanja.

## <a name="delete-a-data-source"></a>Brisanje vira podatkov

1. Pri vpogledih v občinstvo izberite **Podatki** > **Viri podatkov**.

2. Izberite navpične tri pike poleg tistega vira podatkov, ki ga želite odstraniti, in v spustnem meniju izberite **Izbriši**.

3. Potrdite izbris.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
