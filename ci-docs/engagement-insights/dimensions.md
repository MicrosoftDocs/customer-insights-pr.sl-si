---
title: Ogled in ustvarjanje razsežnosti
description: Kako ustvariti, urediti in izbrisati razsežnosti.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 136da1e1265c7087d861712d34d011b09cb60ad5
ms.sourcegitcommit: 565637f49cbdd05a82f42784f594c19cac299140
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623652"
---
# <a name="view-and-create-dimensions"></a>Ogled in ustvarjanje razsežnosti

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Razsežnost je atribut dogodka, ki lahko opiše, filtrira ali združuje podatke. Če na svojem spletnem mestu izvajate marketinško promocijo, lahko z razsežnostmi razvrstite obiskovalce po novih uporabnikih in povratnikih.  

Vpogledi v interakcije vključujejo vnaprej pripravljene (OOB) dimenzij za lastnosti dogodka. Primeri vključujejo:

- Ime brskalnika
- Ime strani
- Model naprave
- Operacijski sistem
- Država/regija

## <a name="view-dimensions"></a>Ogled razsežnosti

Razsežnosti temeljijo na obstoječih lastnostih dogodkov. Ko za vpogled v interakcijo uporabite kodo za sledenje, se samodejno ustvarijo sistemske razsežnosti.

1. V levem podoknu za krmarjenje izberite **Podatki**. 
1. Izberite **Razsežnosti**, da si ogledate seznam vseh razsežnosti v delovnem prostoru. 
   > [!NOTE]
   > Sistemsko ustvarjene razsežnosti so na voljo samo za branje. Ne morete jih urejati. Ustvarjate in urejate lahko samo razsežnosti po meri.

## <a name="create-a-dimension"></a>Ustvarjanje dimenzije

Poleg sistemsko ustvarjenih razsežnosti lahko skrbniki okolja in delovnega prostora ustvarjajo tudi razsežnosti po meri. Razsežnosti po meri temeljijo na privzetih lastnostih osnovnih dogodkov ali pa lahko uporabljajo [lastnosti dogodka po meri](advanced-SDK-implementation.md).

1. Odprite **Podatki** > **Razsežnosti**.
1. Izberite **Nova dimenzija**.

   :::image type="content" source="media/add-dimension.png" alt-text="Dodajte dimenzijo dogodku.":::

1. V podoknu **Ustvarjanje razsežnosti** izberite lastnost, na kateri bo temeljila razsežnost. Na seznamu lastnosti bodo prikazane vse lastnosti v delovnem prostoru, ki niso dodeljene razsežnosti.
   
   :::image type="content" source="media/create-new-dimension.png" alt-text="Ustvarite novo dimenzijo.":::
      
3. Vnesite ime v polje **Ime prikaza**. Po želji lahko dodate tudi **opis**.
4. Izberite možnost **Ustvari**, da shranite razsežnost. Preden lahko uporabite razsežnost v [poročilu po meri](custom-reports.md) ali [segmentu](segments.md), lahko traja do eno minuto. 

## <a name="edit-a-dimension"></a>Urejanje razsežnosti

Ime in opis razsežnosti lahko spremenite. Urejate lahko samo dimenzije, ki jih ustvarijo uporabniki, ne morete pa urejati dimenzij sistema.


1. Odprite **Podatki** > **Razsežnosti**.
1. Izberite razsežnost, ki jo želite izbrisati.
1. V podoknu **Urejanje razsežnosti** posodobite razsežnost.
1. Če želite shraniti spremembe, izberite **Uporabi**.

## <a name="delete-a-dimension"></a>Brisanje dimenzije

Izbrišete lahko samo razsežnosti, ki jih ustvarijo uporabniki, ne morete pa odstraniti sistemskih razsežnosti.

Brisanje razsežnosti je trajno. Poročila in segmenti, ki uporabljajo izbrisano razsežnost, ne bodo več delovali. 

1. Odprite **Podatki** > **Razsežnosti**.
1. Izberite razsežnost, ki jo želite izbrisati.
1. V podoknu **Urejanje razsežnosti** izberite **Brisanje razsežnosti**.

   :::image type="content" source="media/delete-dimension.png" alt-text="Izbrišite dimenzijo za dogodek.":::

1. Vnesite **POTRDI IZBRIŠI** (z velikimi črkami), da potrdite brisanje. 
1. Izberite **Izbriši**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
