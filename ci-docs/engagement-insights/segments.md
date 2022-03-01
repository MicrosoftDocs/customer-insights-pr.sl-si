---
title: Ogled in ustvarjanje segmentov
description: Kako ustvariti, urediti in izbrisati segmente in kje jih uporabiti.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: cedcd58373428dd35ba29ce8fdd00007257f8fa59b0d25bc584b4e832df13604
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036168"
---
# <a name="view-and-create-segments"></a>Ogled in ustvarjanje segmentov

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Segmenti vam omogočajo prepoznavanje podmnožice obiskovalcev na podlagi značilnosti ali interakcij na spletnem mestu. Segmenti vam omogočajo uporabo filtrov in analizo teh podmnožic. Analiza vam lahko pomaga preučiti trende v vašem podjetju in se nanje odzvati. 

:::image type="content" source="media/segments-page.png" alt-text="Posnetek zaslona aplikacije za vpoglede v interakcije, ki prikazuje seznam obstoječih segmentov v delovnem prostoru.":::

## <a name="view-segments"></a>Ogled segmentov

1. V levem podoknu za krmarjenje izberite **Podatki**. 

1. Izberite zavihek **Segmenti** za ogled seznama vseh segmentov v delovnem prostoru. 

## <a name="create-a-segment"></a>Ustvarjanje segmenta

Segmenti so sestavljeni iz pravil in pogojev, ki so povezani z logičnimi operatorji. Pogoji uporabljajo filtre za izbrano razsežnost. Vsak segment lahko uporabi do pet razsežnosti.

Spodnji primer prikazuje segment z dvema pogojema v enem pravilu. Filtrira vse dogodke na spletnem mestu, kjer je uporabljen brskalnik Chrome in operacijski sistem iOS ali Android.

:::image type="content" source="media/segment-sample.png" alt-text="Primeri segmentov z dvema pogojema v pravilu za filtriranje dogodkov na spletnem mestu.":::

Ta razdelek opisuje, kako ustvariti *prazen segment* od začetka.

1. Odprite **Podatki** > **Segmenti**.

1. Izberite **Nov segment**.

1. V razdelku **Knjižnica virov** izberite atribut, po katerem želite filtrirati. Trenutno lahko ustvarite le segmente na podlagi razsežnosti.

1. Izberite operator in vrednost za izbrani atribut. Podprte so naslednje operacije.
   - **je**: zahteva natančno ujemanje za vključitev vrednosti. Uporablja **je enako** za eno vrednost oz. **kateri koli od** za vključitev več vrednosti.
   - **ni**: zahteva natančno ujemanje za izključitev vrednosti. Uporablja **je enako** za eno vrednost oz. **kateri koli od** za vključitev več vrednosti.
   - **se začne z**: niz, s katerim se začnejo ujemajoče se vrednosti.
   - **se konča z**: niz, s katerim se končajo ujemajoče se vrednosti.
   - **vsebuje**: niz, vključen v ujemajoče se vrednosti.

1. Če želite v skupino dodati več pogojev, lahko uporabite dva logična operaterja. Predvideni atributi se upoštevajo pri uporabi operatorjev nabora.
   - Operator **IN**: oba pogoja morata biti izpolnjena kot del postopka segmentacije. Ta možnost je najbolj uporabna, če določite pogoje v različnih entitetah.
   - Operator **ALI**: izpolnjen mora biti kateri koli od pogojev kot del postopka segmentacije. Ta možnost je najbolj uporabna, če določite več pogojev za isto entiteto.

1. Izberite **Shrani** in poimenujte segment. 

Segment bo naveden na strani Segmenti in ga lahko uporabite za vsa poročila in lijake v delovnem prostoru.

## <a name="use-a-segment-in-a-report-or-funnel"></a>Uporaba segmenta v poročilu ali lijaku

Segmente lahko uporabite za poročilo ali lijak, da jih filtrirate glede na pogoje v segmentu. Vendar segmentov ne morete uporabiti v poročilu o uporabi v realnem času.

:::image type="content" source="media/segment-reports-filter.png" alt-text="Poročilo o ogledih strani z razširjenim spustnim seznamom, v katerem lahko izberete segmente, ki jih želite uporabiti.":::

Če želite uporabiti segment, odprite poročilo ali lijak. Izberite **Dodaj pogoj** in **Filtriraj po segmentih**. Na seznamu izberite segment, ki ga želite uporabiti. Segment bo uporabljen v poročilu. Če grafikon ne podpira segmenta, se prikaže napaka.
 
V poročilu ali lijaku lahko uporabite *do tri segmente*.

## <a name="edit-a-segment"></a>Urejanje segmenta

1. Odprite **Podatki** > **Segmenti**.
1. Na seznamu izberite segment, da ga odprete. 
1. Po potrebi spremenite ali dodajte vrednosti.
1. Če želite uporabiti spremembe, izberite **Shrani**.

## <a name="change-the-name-of-a-segment"></a>Sprememba imena segmenta

1. Odprite **Podatki** > **Segmenti**.
1. Na seznamu segmentov izberite **Več [...]**. 
1. Na spustnem seznamu izberite možnost **Uredi ime**.
1. Vnesite novo ime in izberite **Preimenuj**.

## <a name="delete-a-segment"></a>Brisanje segmenta

1. Odprite **Podatki** > **Segmenti**.
1. Na seznamu segmentov izberite **Več [...]**. 
1. Na spustnem seznamu izberite možnost **Izbriši**.
1. Izberite **Izbriši**, da potrdite izbiro.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
