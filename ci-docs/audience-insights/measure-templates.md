---
title: Ustvarite mere iz predlog
description: Določite ukrepe z uporabo predlog za običajne primere uporabe.
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
ms.openlocfilehash: eeabd889f7b694f8d809894169a3cdc068acc340
ms.sourcegitcommit: 9ef2cf99b847e7bd8f890f83d84b3a4045aaf8cc
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/01/2022
ms.locfileid: "8529421"
---
# <a name="use-a-template-to-build-a-measure"></a>Uporaba predloge za izdelavo ukrepa

Uporabite lahko vnaprej določene predloge, ki se pogosto uporabljajo [ukrepe](measures.md) jih ustvariti. Podrobni opisi predlog in vodena izkušnja vam pomagajo pri učinkovitem ustvarjanju ukrepov. Predloge temeljijo na preslikanih podatkih iz entitete *Poenotena dejavnost*. Prepričajte se, da ste konfigurirali [dejavnosti strank](activities.md), preden ustvarite ukrep iz predloge.

Če želite ustvariti meritve po meri, glejte [Uporabite graditelj meril za ustvarjanje ukrepov iz nič](measure-builder.md).

# <a name="individual-consumers-b-to-c"></a>[Posamezni potrošniki (prodaja strankam)](#tab/b2c)

Razpoložljive predloge ukrepov: 
- Povprečna vrednost transakcije (ATV)
- Skupna vrednost transakcije
- Povprečni dnevni prihodek
- Povprečni letni prihodek
- Število transakcij
- Prislužene točke zvestobe
- Izkoriščene točke zvestobe
- Stanje točk zvestobe
- Življenjska doba dejavne stranke
- Trajanje članstva v programu zvestobe
- Čas od zadnjega nakupa

## <a name="build-a-new-measure-using-a-template"></a>Z uporabo predloge ustvarite novo mero

1. Pojdi do **Ukrepi**.

1. Izberite **Novo** in nato **Izberi predlogo**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Posnetek zaslona spustnega menija pri ustvarjanju nove mere z oznako na predlogi.":::

1. Poiščite predlogo, ki ustreza vašim potrebam, in izberite **Izberi predlogo**.

1. Preglejte zahtevane podatke in izberite **Začetek**, če imate na voljo vse podatke.

1. Izberite **Uredite podrobnosti** poleg Ime mere. Navedite ime za ukrep. Po želji dodajte [oznake](work-with-tags-columns.md#manage-tags) po meri.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Pogovorno okno Uredi podrobnosti.":::

1. Izberite **Dokončano**.

1. V razdelku **Nastavi časovno obdobje** določite časovni okvir podatkov, ki jih želite uporabiti. Če želite, da nova mera pokrije celoten nabor podatkov, izberite možnost **Ves čas**, ali pa se odločite, da se mera osredotoči na **Določeno časovno obdobje**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Posnetek zaslona, ki prikazuje razdelek časovnega obdobja pri konfiguriranju ukrepa iz predloge.":::

1. V naslednjem razdelku izberite **Dodaj podatke**, če želite izbrati dejavnosti in preslikati ustrezne podatke iz vaše entitete *Poenotena dejavnost*.

    1. Korak 1 od 2: v razdelku **Vrsta dejavnosti** izberite vrsto entitete, ki jo želite uporabiti. Za **Dejavnosti** izberite entitete, ki jih želite preslikati.
    1. Korak 2 od 2: izberite atribut v entiteti *Poenotena dejavnost* za komponento, ki jo zahteva formula. Za povprečno vrednost transakcije je to na primer atribut, ki predstavlja vrednost transakcije. Za **Časovni žig dejavnosti** izberite atribut iz entitete poenotene dejavnosti, ki predstavlja datum in čas dejavnosti.
   
1. Ko je preslikava podatkov uspešno zaključena, se prikaže stanje **Dokončano** skupaj z imenom preslikanih dejavnosti in atributov.

1. Zdaj lahko izberete **Zaženi**, da izračunate rezultate ukrepa. Če jih želite pozneje prilagoditi, izberite **Shrani osnutek**.

# <a name="business-accounts-b-to-b"></a>[Poslovni računi (podjetja podjetjem)](#tab/b2b)

Ta funkcija je na voljo samo za mere, ustvarjene v okoljih s posameznimi strankami kot primarno ciljno občinstvo.

---
