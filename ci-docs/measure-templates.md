---
title: Ustvarite mere iz predlog
description: Določite mere z uporabo predlog za pogoste primere uporabe.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: 6dc7fce78d10ba91de4b2abf54c6c6ab1c919d3a
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170793"
---
# <a name="create-measures-from-templates"></a>Ustvarite mere iz predlog

Uporabite vnaprej določene predloge pogosto uporabljenih [ukrepe](measures.md) da jih ustvarite. Predloge temeljijo na preslikanih podatkih iz entitete *Poenotena dejavnost*. Prepričajte se, da ste konfigurirali [dejavnosti strank](activities.md), preden ustvarite ukrep iz predloge.

Predloge meritev so podprte samo v okoljih za **posamezne stranke**. Če želite ustvariti mere po meri ali ustvariti mere za B-to-B, glejte [Uporabite graditelj mer](measure-builder.md).

Razpoložljive predloge ukrepov:
- Povprečna vrednost transakcije (ATV)
- Skupna vrednost transakcije
- Povprečni dnevni prihodek
- Povprečni mesečni prihodek
- Povprečni letni prihodek
- Število transakcij
- Prislužene točke zvestobe
- Izkoriščene točke zvestobe
- Stanje točk zvestobe
- Življenjska doba dejavne stranke
- Trajanje članstva v programu zvestobe
- Čas od zadnjega nakupa

## <a name="build-a-new-measure-using-a-template"></a>S pomočjo predloge sestavite novo mero

1. Pojdi do **Ukrepi**.

1. Izberite **Novo** in nato **Izberi predlogo**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Posnetek zaslona spustnega menija pri ustvarjanju nove mere z oznako na predlogi.":::

1. Poiščite predlogo, ki ustreza vašim potrebam, in izberite **Izberi predlogo**.

1. Preglejte zahtevane podatke in izberite **Začetek**, če imate na voljo vse podatke.

1. Izberite **Uredi podrobnosti** poleg imena mere. Vnesite ime za mero. Po želji dodajte [oznake](work-with-tags-columns.md#manage-tags) po meri.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Pogovorno okno za urejanje podrobnosti.":::

1. Izberite **Dokončano**.

1. V **Nastavite časovno obdobje** razdelku določite časovni okvir podatkov. Če želite, da nova mera pokrije celoten nabor podatkov, izberite možnost **Ves čas**, ali pa se odločite, da se mera osredotoči na **Določeno časovno obdobje**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Posnetek zaslona, ki prikazuje razdelek časovnega obdobja pri konfiguriranju ukrepa iz predloge.":::

1. V naslednjem razdelku izberite **Dodaj podatke**, če želite izbrati dejavnosti in preslikati ustrezne podatke iz vaše entitete *Poenotena dejavnost*.

    1. Korak 1 od 2: v razdelku **Vrsta dejavnosti** izberite vrsto entitete, ki jo želite uporabiti. Za **dejavnosti**, izberite entitete, ki jih želite preslikati, in nato izberite **Naslednji**.
    1. Korak 2 od 2: izberite atribut v entiteti *Poenotena dejavnost* za komponento, ki jo zahteva formula. Za povprečno vrednost transakcije je to na primer atribut, ki predstavlja vrednost transakcije. Za **Časovni žig dejavnosti**, izberite atribut iz *Enotna dejavnost* entiteta, ki predstavlja datum in čas dejavnosti.
    1. Izberite **Shrani**.

    Ko je preslikava podatkov uspešna, se prikaže stanje **Popolna** ter ime preslikanih dejavnosti in prikaz atributov.

1. Izberite **Teči** za izračun rezultatov ukrepa. Izberite **Shrani osnutek** če želite obdržati trenutno konfiguracijo in zagnati ukrep pozneje. The **Ukrepi** prikazi strani.

## <a name="next-step"></a>Naslednji korak

Za ustvarjanje uporabite obstoječe ukrepe [segment strank](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
