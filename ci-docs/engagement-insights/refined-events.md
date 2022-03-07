---
title: Ustvarjanje in spreminjanje dogodkov
description: Kako ustvariti in spreminjati dogodke.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: dbafa2231daa82c34ee2ec8292111575e95af675
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228223"
---
# <a name="create-and-modify-events"></a>Ustvarjanje in spreminjanje dogodkov

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dogodek je podatek, ki predstavlja vedenje uporabnika, kot je dejavnost na spletnem mestu.

- *Osnovni* dogodek zabeleži, ko si uporabnik ogleda stran (dogodek ogleda) ali stopi v interakcijo z vsebino (dogodek dejanja).
- *Izboljšan* dogodek je navidezen pogled osnovnega dogodka. Izboljšane dogodke določite z odstranjevanjem in dodajanjem lastnosti ali s filtriranjem dogodkov na podlagi vrednosti lastnosti.

## <a name="prerequisites"></a>Zahteve

Če želite pridobiti dogodke, najprej povežite podatke svoje spletne strani z vpogledi v interakcije z izrezkom kode. Za več informacij glejte [Nameščanje spletnega kompleta za razvoj programske opreme na spletno mesto](instrument-website.md).

 :::image type="content" source="media/new-events-connect-data.png" alt-text="Najprej povežite svoje podatke.":::

## <a name="create-refined-events"></a>Ustvarjanje dogodkov, ki so natančneje določeni

Uporabite izboljšane dogodke, da zmanjšate obseg osnovnega dogodka za [izvoz](export-events.md) ali odstranite lastnosti, ki niso potrebne za izpostavljenost.

> [!NOTE]
> Ko na spletno mesto dodate spletni komplet za razvoj programske opreme, si lahko ogledate osnovne dogodke in ustvarite dogodke, ki so natančneje določeni. 

Za ogled osnovnih dogodkov:

1. V levem podoknu za krmarjenje izberite **Podatki**.

1. Izberite **Dogodki** za ogled seznama vseh dogodkov v delovnem prostoru.

    :::image type="content" source="media/data-events.png" alt-text="Ogled dogodkov.":::

Če želite iz osnovnega dogodka ustvariti dogodek, ki je natančneje določen: 

1. Odprite **Podatki** > **Dogodki** in izberite **+ Novi dogodki** na vrhu zaslona.

1. V pogovornem oknu **Novi dogodki** izberite **Ustvarjanje dogodkov, ki so natančneje določeni** in nato **Naprej**.
   
     :::image type="content" source="media/new-events-wizard.png" alt-text="Novi čarovnik za dogodke.":::
     
1. V pogovorno okno **Novi dogodki** vnesite naslednje podatke:

   - Izberite dogodek v spustnem meniju **Osnovni dogodki**.
   - Vnesite ime v besedilno polje za **prikazno ime izboljšanih dogodkov**.
   - Po želji posodobite predlagano **dejansko ime** brez uporabe presledkov.

1. Izberite možnost **Ustvari** za uporabo nastavitev.

Dogodek, ki je natančneje določen, se zdaj prikaže v vašem seznamu **Dogodki**.

### <a name="edit-event-name"></a>Urejanje imena dogodka

Lahko spremenite ime in lastnosti osnovnega dogodka ali dogodka, ki je natančneje določen.

1. Odprite razdelek **Podatki** > **Dogodki**. 

1. Izberite **Več [...]** za dogodek in nato **Uredi ime**.
    
     :::image type="content" source="media/create-refined-events-options.png" alt-text="Možnosti za ustvarjanje izboljšanih dogodkov.":::

3. Posodobite ime dogodka in izberite možnost **Preimenuj**.

### <a name="view-the-details-of-a-refined-event"></a>Oglejte si podrobnosti o dogodku, ki je natančneje določen:

1. V seznamu **Dogodek** izberite svoj osnovni dogodek ali dogodek, ki je natančneje določen. 

1. Izberite **Dodajanje in odstranjevanje lastnosti** na vrhu zaslona, da odprete podokno **Urejanje lastnosti**. 

     :::image type="content" source="media/add-remove-properties.png" alt-text="Dodajanje in odstranjevanje lastnosti.":::

1. S potrditvenimi polji izberite lastnosti, ki jih želite prikazati, in tiste, ki jih želite skriti. 

   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Urejanje lastnosti za izboljšane dogodke.":::

1. Izberite **Potrdi**, da uporabite svojo izbiro, nato pa izberite **Shrani**.


### <a name="edit-selected-properties-for-a-refined-event"></a>Urejanje izbranih lastnosti za dogodek, ki je natančneje določen

1. Odprite razdelek **Podatki** > **Dogodki** in izberite izboljšane dogodke, da odprete podroben pogled.
1. Izberite **Dodajanje in odstranjevanje lastnosti**. 
1. Uredite izbor potrditvenih polj.
1. Izberite **Potrdi** in potem **Shrani** za uporabo sprememb.

Za informacije o izvozu dogodkov glejte [Izvoz dogodkov](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
