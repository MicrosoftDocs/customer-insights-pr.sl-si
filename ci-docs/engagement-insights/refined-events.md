---
title: Ustvarjanje in spreminjanje izboljšanih dogodkov
description: Preberite več o tem, kako ustvariti in spreminjati izboljšane dogodke.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 0344bac5f4d43df853309f43c94d95f962937f77c936ed7305c5de4a08835f04
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034794"
---
# <a name="create-and-modify-refined-events"></a>Ustvarjanje in spreminjanje izboljšanih dogodkov

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]


Dogodek je podatek, ki predstavlja vedenje uporabnika, kot je dejavnost na spletnem mestu.

- *Osnovni* dogodek zabeleži, ko si uporabnik ogleda stran (dogodek ogleda) ali stopi v interakcijo z vsebino (dogodek dejanja).
- *Izboljšan* dogodek je navidezen pogled osnovnega dogodka. Izboljšane dogodke določite z odstranjevanjem in dodajanjem lastnosti ali s filtriranjem dogodkov na podlagi vrednosti lastnosti.

Uporabite izboljšane dogodke, da zmanjšate obseg osnovnega dogodka za [izvoz](export-events.md) ali odstranite lastnosti, ki niso potrebne za izpostavljenost.

## <a name="create-refined-events"></a>Ustvarjanje izpopolnjenih dogodkov

Obstajajo trije načini za ustvarjanje izboljšanega dogodka iz osnovnega dogodka. 

1. Odprite razdelek **Podatki** > **Dogodki** in izberite eno od naslednjih možnosti:
    - Izberite **Novi dogodki** in nato **Ustvarjanje izboljšanih dogodkov**.
    - Izberite osnovni dogodek, da odprete podroben pogled, in v zgornjem meniju izberite **Ustvarjanje izboljšanih dogodkov**.
    - Izberite **Več [...]**, da odprete bližnjico do osnovnega dogodka. Nato izberite **Ustvarjanje izboljšanih dogodkov**.
    
    :::image type="content" source="media/create-refined-events-options.png" alt-text="Možnosti za ustvarjanje izboljšanih dogodkov.":::

1. V pogovornem oknu **Ustvarjanje izboljšanih dogodkov** vnesite naslednje podatke:

- Izberite dogodek na spustnem meniju **Osnovni dogodki**, če ustvarjate nov dogodek.
- Vnesite ime v besedilno polje za **prikazno ime izboljšanih dogodkov**.
- Po želji posodobite predlagano **dejansko ime** brez uporabe presledkov.

3. Izberite možnost **Ustvari** za uporabo nastavitev.

1. V podrobnem pogledu vašega izboljšanega dogodka izberite **Dodajanje in odstranjevanje lastnosti**, da odprete podokno **Urejanje lastnosti**. 

1. S potrditvenimi polji izberite lastnosti, ki jih želite prikazati, in tiste, ki jih želite skriti. 
   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Urejanje lastnosti za izboljšane dogodke.":::

1. Izberite možnost **Potrdi**, da uporabite svoj izbor.

1. Če želite shraniti konfiguracijo, izberite **Shrani**.

## <a name="edit-refined-events"></a>Urejanje izboljšanih dogodkov

Spremenite lahko ime in lastnosti izboljšanega dogodka.

### <a name="edit-event-name"></a>Urejanje imena dogodka

1. Odprite razdelek **Podatki** > **Dogodki**. 
1. Izberite **Več [...]** za dogodek in nato **Uredi ime**.
1. Posodobite ime dogodka in izberite možnost **Preimenuj**.

### <a name="edit-selected-properties"></a>Urejanje izbranih lastnosti

1. Odprite razdelek **Podatki** > **Dogodki** in izberite izboljšane dogodke, da odprete podroben pogled.
1. Izberite **Dodajanje in odstranjevanje lastnosti**. 
1. Uredite izbor potrditvenih polj.
1. Izberite **Potrdi** in potem **Shrani** za uporabo sprememb.

Za informacije o izvozu dogodkov glejte [Izvoz dogodkov](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
