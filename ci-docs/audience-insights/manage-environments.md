---
title: Ustvarjanje in upravljanje okolij
description: Naučite se, kako se prijaviti za storitev in kako upravljati okolja.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 8251cac9f95455b61eb0300b6c72cd4ab2969591
ms.sourcegitcommit: 3807202283dd116a30f900a163d8141db621e5a8
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 01/28/2022
ms.locfileid: "8046353"
---
# <a name="manage-environments"></a>Upravljanje okolij



## <a name="switch-environments"></a>Zamenjava okolja

V zgornjem desnem kotu strani izberite kontrolnik **Okolje**, če želite spremeniti okolje.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Posnetek zaslona kontrolnika za preklapljanje med okolji.":::

Če ste skrbnik, lahko [ustvarite](create-environment.md) in upravljate okolja.

## <a name="edit-an-existing-environment"></a>Urejanje obstoječega okolja

Uredite lahko določene podatke obstoječih okolij.

1.  V glavi aplikacije izberite izbirnik **Okolje**.

2.  Izberite ikono za **urejanje**.

3. V polju **Urejanje okolja**, lahko posodobite nastavitve okolja.

Za več informacij o nastavitvah okolja glejte [Ustvarjanje novega okolja](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Vzpostavljanje povezave s programom Microsoft Dataverse
   
Korak **Microsoft Dataverse** vam omogoča, da povežete Customer Insights s svojim okoljem Dataverse.

Če želite uporabiti [pripravljene modele predvidevanja](predictions-overview.md#out-of-box-models), konfigurirajte skupno rabo podatkov z okoljem Dataverse. Ali pa omogočite uvoz podatkov iz virov podatkov na mestu uporabe, ki zagotavljajo URL za okolje Microsoft Dataverse, ki ga upravlja vaša organizacija. Izberite možnost **Omogoči skupno rabo podatkov** za skupno rabo izhodnih podatkov Customer Insights z upravljanim jezerom podatkov Dataverse.

> [!IMPORTANT]
> Vpogled v stranke in Dataverse morajo biti v isti regiji, da omogočite skupno rabo podatkov.

:::image type="content" source="media/dataverse-data-sharing.png" alt-text="Možnosti konfiguracije za omogočanje skupne rabe podatkov s storitvijo Microsoft Dataverse.":::

> [!NOTE]
> Storitev Customer Insights ne podpira naslednjih primerov skupne rabe podatkov.
> - Če vse podatke shranite v svojo shrambo Azure Data Lake Storage, ne boste mogli omogočiti skupne rabe podatkov z upravljanim jezerom podatkov Dataverse.
> - Če omogočite skupno rabo podatkov s storitvijo Dataverse, ne boste mogli [ustvariti predvidenih ali manjkajočih vrednosti v entiteti](predictions.md).

## <a name="copy-the-environment-configuration"></a>Kopiranje konfiguracije okolja

Ko ustvarite novo okolje, lahko izberete kopiranje konfiguracije iz obstoječega okolja. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Posnetek zaslona možnosti nastavitev v nastavitvah okolja.":::

Prikazan bo seznam vseh razpoložljivih okolij iz vaše organizacije, od koder lahko kopirate podatke.

Kopirane so naslednje konfiguracijske nastavitve:

- Vključeni/uvoženi viri podatkov
- Konfiguracija poenotenja podatkov (preslikava, ujemanje, spajanje)
- Segmenti
- Mere
- Odnosi
- Dejavnosti
- Kazalo za iskanje in filtre
- Izvoz ciljev
- Načrtovano osveževanje
- Obogatitve
- Upravljanje modelov
- Dodelitve vloge

Naslednji podatki *niso* kopirani:

- Profili strank
- Poverilnice virov podatkov. Za vsak vir podatkov boste morali zagotoviti poverilnice in ročno osvežiti vire podatkov.

- Viri podatkov iz mape Common Data Model in upravljanega jezera podatkov Dataverse. Te vire podatkov boste morali ustvariti ročno z istim imenom kot v izvornem okolju.

Ko kopirate okolje, boste videli potrditveno sporočilo, da je bilo ustvarjeno novo okolje. Izberite **Na vire podatkov**, da prikažete seznam virov podatkov.

Vsi viri podatkov bodo prikazovali stanje **Zahtevane poverilnice**. Uredite vire podatkov in vnesite poverilnice, da jih osvežite.

:::image type="content" source="media/data-sources-copied.png" alt-text="Seznam virov podatkov, ki so bili kopirani in potrebujejo preverjanje pristnosti.":::

Ko osvežite vire podatkov, se pomaknite na možnost **Podatki** > **Poenoti**. Tukaj so na voljo nastavitve iz izvornega okolja. Po potrebi jih uredite ali izberite **Zagon**, da zaženete proces poenotenja podatkov in ustvarite poenoteno entiteto stranke.

Ko je poenotenje podatkov dokončano, odprite možnost **Mere** in **Segmenti**, da ju prav tako osvežite.

## <a name="reset-an-existing-environment"></a>Ponastavitev obstoječega okolja

Če želite izbrisati vse konfiguracije in odstraniti vključene podatke, lahko kot administrator okolje ponastavite v prazno stanje.

1.  V glavi aplikacije izberite izbirnik **Okolje**. 

2.  Izberite okolje, ki ga želite ponastaviti, nato pa tri pike (**...**). 

3. Izberite možnost **Ponastavi**. 

4.  Če želite potrditi brisanje, vnesite ime okolja in izberite **Ponastavi**.

## <a name="delete-an-existing-environment"></a>Brisanje obstoječega okolja

Kot skrbnik lahko izbrišete okolja, katerih skrbnik ste.

1.  V glavi aplikacije izberite izbirnik **Okolje**.

2.  Izberite okolje, ki ga želite ponastaviti, nato pa tri pike (**...**). 

3. Izberite možnost **Izbriši**. 

4.  Če želite potrditi izbris, vnesite ime okolja in izberite **Izbriši**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
