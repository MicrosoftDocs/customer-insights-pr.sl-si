---
title: Uporaba virov podatkov za vključitev podatkov
description: Naučite se uvoziti podatke iz različnih virov.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: a720641f7499fc71ff5bceeba48d296c51f77242
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643973"
---
# <a name="overview-about-data-sources"></a>Pregled virov podatkov

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Zmogljivost vpogledov v občinstvo v storitvi Dynamics 365 Customer Insights se poveže s podatki iz širokega nabora virov. Povezovanje z vir podatkov se pogosto imenuje postopek *zaužitje podatkov*. Po zaužitju podatkov lahko jih lahko [poenotite](data-unification.md) in jih uporabite.

## <a name="add-a-data-source"></a>Dodajanje vira podatkov

Glejte podrobne članke o tem, kako dodati vir podatkov, odvisno od tega, katero možnost izberete.

Vir podatkov lahko dodate na tri glavne načine:

- [S pomočjo številnih priključkov Power Query](connect-power-query.md)
- [Iz mape Common Data Model](connect-common-data-model.md)
- [Iz svojega jezera storitve Common Data Service](connect-common-data-service-lake.md)

> [!NOTE]
> Podatkov iz virov podatkov na mestu uporabe še ne morete dodati.

## <a name="review-ingested-data"></a>Pregled zaužitih podatkov

Videli boste ime vsakega zaužitega vira podatkov, njegovo stanje in čas, ko so bili podatki za ta vir nazadnje osveženi. Seznam virov podatkov lahko razvrstite po vseh stolpcih.

> [!div class="mx-imgBorder"]
> ![Vir podatkov je dodan](media/configure-data-datasource-added.png "Vir podatkov je dodan")

|Stanje  |Opis  |
|---------|---------|
|Uspelo   |Vir podatkov je bil uspešno vključen, če je čas omenjen v stolpcu **Osveženo**.
|Ni začeto   |Vir podatkov še nima vključenih podatkov ali je še v načinu osnutka.         |
|Osveževanje    |Uvažanje podatkov je v teku. Ta postopek lahko prekličete tako, da v stolpcu **Dejanja** izberete **Ustavi osveževanje**. Ustavitev osveževanja vira podatkov bo povrnjena na zadnje stanje osveževanja.       |
|Neuspelo     |Pri uvozu podatkov je prišlo do napak.         |

Izberite **Osveži stanje** za pregled več podrobnosti o stanju osveževanja, vključno s podrobnostmi o napakah in posodobitvami nadaljnjih postopkov.

Nalaganje podatkov lahko traja nekaj časa. Po uspešni osvežitvi je mogoče uvožene podatke pregledati na strani **Entitete**. Za več informacij glejte [Entitete](entities.md).

## <a name="refresh-a-data-source"></a>Osveževanje vira podatkov

Vire podatkov lahko osvežite po samodejnem urniku ali ročno na zahtevo. 

Izberite **Skrbnik** > **Sistem** > [**Načrtovanje**](system.md#schedule-tab) za konfiguriranje načrtovanih osvežitev vseh vključenih virov podatkov.

Če želite osvežiti vir podatkov na zahtevo, sledite tem korakom:

1. Pri vpogledih v občinstvo izberite **Podatki** > **Viri podatkov**.

2. Izberite navpične tri pike poleg vira podatkov, ki ga želite osvežiti, in izberite **Osveži** s spustnega seznama.

3. Vir podatkov se zdaj sproži za ročno osvežitev. Če osvežite vir podatkov, boste posodobili tako shemo entitet kot tudi podatke za vse entitete, določene v viru podatkov.

4. Izberite **Ustavi osveževanje**, če želite preklicati obstoječo osvežitev, in se bo vir podatkov vrnil na zadnje stanje osveževanja.

## <a name="delete-a-data-source"></a>Brisanje vira podatkov

1. Pri vpogledih v občinstvo izberite **Podatki** > **Viri podatkov**.

2. Izberite navpične tri pike poleg vira podatkov, ki ga želite odstraniti, in na spustnem meniju izberite **Izbriši**.

3. Potrdite izbris.
