---
title: Uporaba virov podatkov za vključitev podatkov
description: Naučite se uvoziti podatke iz različnih virov.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
---

# <a name="data-sources-overview"></a>Pregled virov podatkov



Zmogljivost vpogledov v občinstvo v storitvi Dynamics 365 Customer Insights se poveže s podatki iz širokega nabora virov. Povezovanje z vir podatkov se pogosto imenuje postopek *zaužitje podatkov*. Po zaužitju podatkov lahko jih lahko [poenotite](data-unification.md) in jih uporabite.

## <a name="add-a-data-source"></a>Dodajanje vira podatkov

Oglejte si podrobne članke, kako dodati vir podatkov, odvisno od možnosti, ki jo izberete.

Dodate lahko naslednje vire podatkov:

- [Power Query konektorji](connect-power-query.md)
- [Common Data Model](connect-common-data-model.md)
- [Microsoft Dataverse jezero](connect-dataverse-managed-lake.md)

> [!NOTE]
> Če uporabljate preizkusno različico, razdelek z načini uvoza vključuje a **Knjižnica podatkov Customer Insights** možnost. Izberite to možnost, da izberete vzorčni nabor podatkov, ki je na voljo za različne panoge. Za več informacij glejte [Dynamics 365 Customer Insights sojenje](../trial-signup.md).

## <a name="add-data-from-on-premises-data-sources"></a>Dodajanje podatkov iz virov podatkov na mestu uporabe

Uvažanje podatkov iz virov podatkov na mestu uporabe v vpogledih občinstva je podprto na podlagi podatkovnih tokov storitve Microsoft Power Platform. Tokove podatkov lahko omogočite v Customer Insights z [zagotavljanje Microsoft Dataverse URL okolja](create-environment.md) pri postavljanju okolja.

Viri podatkov, ki so ustvarjeni po povezovanju a Dataverse okolje z uporabo Customer Insights [Power Platform tokovi podatkov](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) privzeto. Za podatkovne tokove je prek prehoda za podatke podprta povezljivost na mestu uporabe. Vire podatkov, ki so obstajali pred a., lahko odstranite in znova ustvarite Dataverse okolje je bilo povezano [z uporabo podatkovnih prehodov na mestu uporabe](/data-integration/gateway/service-gateway-app).

Prehodi za podatke iz obstoječega okolja storitve Power BI ali Power Apps bodo vidni v storitvi Customer Insights, kjer jih lahko znova uporabite. Na strani z viri podatkov se nahajajo povezave do okolja Microsoft Power Platform, kjer si lahko ogledate prehode za podatke na mestu uporabe ter jih konfigurirate.

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
