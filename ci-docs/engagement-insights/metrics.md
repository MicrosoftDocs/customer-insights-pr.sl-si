---
title: Ogled in ustvarjanje metrik
description: Ustvarjanje, urejanje in brisanje metrik.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 97189168e0f5586aad8be8089a1f9e27893c2115c7e805ddaab1efc00e11b860
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034289"
---
# <a name="view-and-create-metrics"></a>Ogled in ustvarjanje metrik

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Metrike pomagajo razumeti vedenje vaših obiskovalcev. Združujejo lastnosti dogodkov in merijo statistiko in uspešnost vaših spletnih lastnosti.  

Recimo, da na svojem spletnem mestu vodite tržno promocijo. Z metrikami lahko sledite številu posameznih obiskovalcev ali uporabnikov, ki so obiskali vaše spletno mesto v času trajanja promocije. Analiza metrik vam pomaga bolje razumeti ciljno skupino vašega spletnega mesta. Kombiniranje metrik z [razsežnostmi](dimensions.md) na [poročilu po meri](custom-reports.md) vam omogoča merjenje vedenja za razumevanje uporabnikov. Obiskovalce lahko na primer ločite v kategorijo novih in povratnih obiskovalcev, da ugotovite razlike v zanimanju in nameri med skupinama.

## <a name="view-metrics"></a>Ogled metrik

Vpogledi v interakcije vključujejo pogosto uporabljene združitve lastnosti dogodkov kot sistemske metrike: 

- Obiskovalci
- Obiski
- Ogledi strani
- Kliki

Te sistemske metrike temeljijo na obstoječih lastnostih dogodkov v osnovnih dogodkih.

1. V levem podoknu za krmarjenje izberite **Podatki**. 
1. Izberite zavihek **Metrike** za ogled seznama vseh metrik v delovnem prostoru. 
   > [!NOTE]
   > Sistemsko ustvarjene metrike so na voljo samo za branje. Ne morete jih spremeniti ali izbrisati. Ustvarite in urejate lahko le metrike po meri.

## <a name="create-a-metric"></a>Ustvarjanje metrike

Skrbniki okolja in delovnega prostora lahko ustvarjajo metrike. Lastnosti dogodka je treba poslati v delovni prostor, preden ustvarite metriko. Ustvarite lahko metrike na podlagi lastnosti dogodka, ki jih pošljejo osnovni dogodki, ali pa uporabite spletni SDK, da [pošljete lastnosti dogodka po meri](advanced-SDK-implementation.md).

1. Odprite **Podatki** > **Meritve**.
1. Izberite **Nova metrika**.

   :::image type="content" source="media/new-metric.png" alt-text="Dodajanje metrike za dogodek.":::

1. Za formatiranje izberite vrsto podatkov **Celo število** ali **Dvojno**. Celo število mora biti celo število. Za »Dvojno« lahko izbirate med enim in tremi decimalnimi mesti.
1. V podoknu **Knjižnica virov** poiščite lastnost dogodka, na podlagi katere bo izdelana meritev.
1. Izberite **znak plus (+)** poleg lastnosti, da jo uporabite v formuli. Formulo lahko ustvarite samo na podlagi ene lastnosti. 
1. Izberite eno od naslednjih združenih funkcij. 

   - Vsota: aritmetični seštevek vseh vrednosti 
   - Povprečje: povprečje vseh vrednosti
   - Število: skupno število vrednosti
   - Število različnih vrednosti: skupno število različnih vrednosti

   Po določitvi metrike se prikaže predogled dejavnosti metrike za zadnjo uro.

1. Izberite **Shrani**. 
1. Vnesite ime za metriko in izberite **Shrani**.

Traja lahko do eno minuto, preden lahko metriko uporabite za [ustvarjanje poročil po meri](custom-reports.md).

## <a name="edit-a-metric"></a>Urejanje metrike

1. Odprite **Podatki** > **Meritve**.
1. Na seznamu izberite metriko.
1. Sprememba definicije metrike
1. Izberite **Shrani**.

## <a name="change-the-name-of-a-metric"></a>Sprememba imena metrike

1. Odprite **Podatki** > **Meritve**.
1. Izberite **Več [...]** pri posamezni metriki in izberite **Uredi ime**.
1. Spremenite ime. 
1. Izberite **Preimenuj**.

## <a name="delete-a-metric"></a>Brisanje metrike

1. Odprite **Podatki** > **Meritve**.
1. Izberite **Več [...]** pri posamezni metriki in izberite **Izbriši**.

   :::image type="content" source="media/delete-metric.png" alt-text="Brisanje metrike za dogodek.":::

1. Izberite možnost **Izbriši**, da pordite izbris.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
