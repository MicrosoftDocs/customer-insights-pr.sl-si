---
title: Izvoz podatkov storitve Customer Insights v storitev AdRoll
description: Preberite o konfiguraciji povezave s storitvijo AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697094"
---
# <a name="connector-for-adroll-preview"></a>Povezovalnik za storitev AdRoll (predogledna različica)

Izvozite segmente poenotenih profilov strank v storitev AdRoll in jih uporabite za oglaševanje. 

## <a name="prerequisites"></a>Zahteve

-   Imate [račun za AdRoll](https://www.adroll.com/) in ustrezne skrbniške poverilnice.
-   Imate [konfigurirane segmente](segments.md) pri vpogledih v občinstvo.
-   Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.

## <a name="connect-to-adroll"></a>Vzpostavljanje povezave s storitvijo AdRoll

1. Izberite **Skrbnik** > **Cilji za izvoz**.

1. V razdelku **AdRoll** izberite **Nastavi**.

1. Dajte svojemu cilju izvoza prepoznavno ime v polju **Prikazno ime**.

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Konfiguracijsko podokno za povezavo s storitvijo AdRoll":::

1. Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.

1. Izberite možnost **Poveži**, da inicializirate povezavo s storitvijo AdRoll.

1. Izberite **Preverjanje pristnosti s storitvijo AdRoll** in vnesite svoje skrbniške poverilnice za AdRoll. 

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Vnesite **ID oglaševalca AdRoll** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).

1. Izberite **Naslednji** za nastavitev izvoza.

## <a name="configure-the-connector"></a>Konfiguracija povezovalnika

1. V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje v poenotenem profilu strank, ki predstavlja e-poštni naslov stranke. Segmente je treba izvoziti v storitev AdRoll.

1. Izberite segmente, ki jih želite izvoziti. Izberite segment z vsaj 100 člani. Manjših segmentov ni mogoče izvoziti. Poleg tega je največja velikost segmenta za izvoz 250.000 članov na izvoz. 

1. Izberite **Shrani**.

## <a name="export-the-data"></a>Izvoz podatkov

Lahko [izvozite podatke na zahtevo](export-destinations.md). Izvoz se bo zagnal tudi z vsakim [načrtovanim osveževanjem](system.md#schedule-tab).

## <a name="known-limitations"></a>Znane omejitve

- V storitev AdRoll lahko ob vsakem izvozu izvozite do 250.000 profilov.
- V storitev AdRoll ne morete izvoziti segmentov z manj kot 100 profili. 
- Izvoz v storitev AdRoll je omejen na segmente.
- Izvoz do 250.000 profilov v storitev AdRoll lahko traja do 10 minut. 
- Število profilov, ki jih lahko izvozite v storitev AdRoll, je odvisno in omejeno glede na vašo pogodbo s storitvijo AdRoll.

## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v storitev AdRoll, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da storitev AdRoll izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).

Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.
