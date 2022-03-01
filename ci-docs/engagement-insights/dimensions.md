---
title: Ogled in ustvarjanje razsežnosti
description: Kako ustvariti, urediti in izbrisati razsežnosti.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b575c5e84197d76f53a722bac60c5af928c917f9671720ede1de38c4a7478be4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034017"
---
# <a name="view-and-create-dimensions"></a>Ogled in ustvarjanje razsežnosti

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Razsežnost je atribut dogodka, ki lahko opiše, filtrira ali združuje podatke. Če na svojem spletnem mestu izvajate marketinško promocijo, lahko z razsežnostmi razvrstite obiskovalce po novih uporabnikih in povratnikih.  

Vpogledi v interakcijo vključujejo vnaprej pripravljene razsežnosti za lastnosti dogodka. Primeri vključujejo:

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
1. Izberite **Dodaj razsežnost**.

   :::image type="content" source="media/add-dimension.png" alt-text="Dodajte dimenzijo dogodku.":::

1. V podoknu **Ustvarjanje razsežnosti** izberite lastnost, na kateri bo temeljila razsežnost. Na seznamu lastnosti bodo prikazane vse lastnosti v delovnem prostoru, ki niso dodeljene razsežnosti.
1. Vnesite ime v polje **Ime prikaza**. Po želji lahko dodate tudi opis.
1. Izberite možnost **Ustvari**, da shranite razsežnost. Preden lahko uporabite razsežnost v [poročilu po meri](custom-reports.md) ali [segmentu](segments.md), lahko traja do eno minuto. 

## <a name="edit-a-dimension"></a>Urejanje razsežnosti

Ime in opis razsežnosti lahko spremenite.

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
