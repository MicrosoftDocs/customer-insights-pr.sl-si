---
title: Ustvarjanje in upravljanje okolij
description: Naučite se, kako se prijaviti za storitev in kako upravljati okolja.
ms.date: 11/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 65c6a68f550c2873ec30c6ac54f1752d880ce12c
ms.sourcegitcommit: fb9f118b4e16b5aabb3e503463efca21718f5d72
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/12/2021
ms.locfileid: "7799655"
---
# <a name="manage-environments"></a>Upravljanje okolij

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

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

## <a name="connect-to-microsoft-dataverse"></a>Povežite se z Microsoft Dataverse
   
The **Microsoft Dataverse** korak vam omogoča povezavo Customer Insights z vašim Dataverse okoljem.

Uporabiti [gotovi modeli predvidevanje](predictions-overview.md#out-of-box-models), konfigurirajte skupno rabo podatkov z Dataverse. Lahko pa omogočite vnos podatkov iz virov podatkov na mestu uporabe, pri čemer navedete URL okolja Microsoft Dataverse, ki ga upravlja vaša organizacija. Izberite **Omogoči skupno rabo podatkov** deliti izhodne podatke Customer Insights s podatkovnim jezerom, ki ga upravlja Dataverse.

:::image type="content" source="media/dataverse-data-sharing.png" alt-text="Možnosti konfiguracije za omogočanje skupne rabe podatkov z Microsoft Dataverse.":::

> [!NOTE]
> Storitev Customer Insights ne podpira naslednjih primerov skupne rabe podatkov.
> - Če shranite vse podatke v svoj Azure Data Lake Storage, ne boste mogli omogočiti skupne rabe podatkov s podatkovnim jezerom, ki ga upravlja Dataverse.
> - Če omogočite skupno rabo podatkov z Dataverse, ne boste mogli [ustvariti predvidene ali manjkajoče vrednosti v entiteti](predictions.md).

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

- Viri podatkov iz mape Common Data Model in podatkovnega jezera, ki ga upravlja Dataverse. Te vire podatkov boste morali ustvariti ročno z istim imenom kot v izvornem okolju.

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
