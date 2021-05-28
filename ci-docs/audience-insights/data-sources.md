---
title: Uporaba virov podatkov za vključitev podatkov
description: Naučite se uvoziti podatke iz različnih virov.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3c0b4690e18285aa37eef481b3cfac951884ead6
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085550"
---
# <a name="data-sources-overview"></a>Pregled virov podatkov

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Zmogljivost vpogledov v občinstvo v storitvi Dynamics 365 Customer Insights se poveže s podatki iz širokega nabora virov. Povezovanje z vir podatkov se pogosto imenuje postopek *zaužitje podatkov*. Po zaužitju podatkov lahko jih lahko [poenotite](data-unification.md) in jih uporabite.

## <a name="add-a-data-source"></a>Dodajanje vira podatkov

Glejte podrobne članke o tem, kako dodati vir podatkov, odvisno od tega, katero možnost izberete.

Vir podatkov lahko dodate na tri glavne načine:

- [S pomočjo številnih priključkov Power Query](connect-power-query.md)
- [Iz mape Common Data Model](connect-common-data-model.md)
- [Iz svojega jezera storitve Common Data Service](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a>Dodajanje podatkov iz virov podatkov na mestu uporabe

Uvoz podatkov iz virov podatkov na mestu uporabe v vpogledih v občinstvo je podprt na podlagi podatkovnih tokov iz storitve Power Platform. Podatkovne tokove lahko omogočite v storitvi Customer Insights, in sicer tako, da med nastavitvijo okolja [navedete URL povezave za okolje Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization).

Za vire podatkov, ustvarjene ob vzpostavitvi povezave med okoljem storitve Dataverse in storitvijo Customer Insights, se privzeto uporabljajo [podatkovni tokovi iz storitve Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Za podatkovne tokove je prek prehoda za podatke podprta povezljivost na mestu uporabe. Odstranite vire podatkov, ki so obstajali pred vzpostavitvijo povezave z okoljem Dataverse za [uporabo prehodov za podatke na mestu uporabe](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md), in jih znova ustvarite.

Prehodi za podatke iz obstoječega okolja storitve Power BI ali Power Apps bodo vidni v storitvi Customer Insights, kjer jih lahko znova uporabite. Na strani z viri podatkov je prikazana povezava do okolja Power Platform, kjer si lahko ogledate prehode za podatke na mestu uporabe in jih konfigurirate.

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

Če si želite ogledati več podrobnosti, izberite vrednost stolpca **Stanje** katerega koli vira podatkov. V podoknu **Podrobnosti o napredku** razširite možnost **Viri podatkov**. Izberite možnost **Prikaži podrobnosti** za pregled več podrobnosti o stanju osveževanja, vključno s podrobnostmi o napakah in posodobitvami nadaljnjih postopkov.

Nalaganje podatkov lahko traja nekaj časa. Po uspešni osvežitvi je mogoče uvožene podatke pregledati na strani **Entitete**. Za več informacij glejte [Entitete](entities.md).

## <a name="refresh-a-data-source"></a>Osveževanje vira podatkov

Vire podatkov lahko osvežite po samodejnem urniku ali ročno na zahtevo. 

Izberite **Skrbnik** > **Sistem** > [**Načrtovanje**](system.md#schedule-tab) za konfiguriranje načrtovanih osvežitev vseh vključenih virov podatkov.

Če želite osvežiti vir podatkov na zahtevo, sledite tem korakom:

1. Pri vpogledih v občinstvo izberite **Podatki** > **Viri podatkov**.

2. Izberite navpične tri pike poleg vira podatkov, ki ga želite osvežiti, in izberite **Osveži** s spustnega seznama.

3. Vir podatkov se zdaj sproži za ročno osvežitev. Če osvežite vir podatkov, se posodobijo tudi shema entitet in podatki za vse entitete, določene v viru podatkov.

4. Izberite **Ustavi osveževanje**, če želite preklicati obstoječo osvežitev, in se bo vir podatkov vrnil na zadnje stanje osveževanja.

## <a name="delete-a-data-source"></a>Brisanje vira podatkov

1. Pri vpogledih v občinstvo izberite **Podatki** > **Viri podatkov**.

2. Izberite navpične tri pike poleg vira podatkov, ki ga želite odstraniti, in na spustnem meniju izberite **Izbriši**.

3. Potrdite izbris.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
