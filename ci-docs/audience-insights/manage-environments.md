---
title: Ustvarjanje in upravljanje okolij
description: Naučite se, kako se prijaviti za storitev in kako upravljati okolja.
ms.date: 07/22/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: e3f99f8f151aea5f120084382babd5e46e109545a4f63aafc51c3ecb1400cc33
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034197"
---
# <a name="manage-environments"></a>Upravljanje okolij

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>Zamenjava okolja

V zgornjem desnem kotu strani izberite kontrolnik **Okolje**, če želite spremeniti okolje.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Posnetek zaslona kontrolnika za preklapljanje med okolji.":::

Če ste skrbnik, lahko [ustvarite](get-started-paid.md) in upravljate okolja.

## <a name="edit-an-existing-environment"></a>Urejanje obstoječega okolja

Uredite lahko določene podatke obstoječih okolij.

1.  V glavi aplikacije izberite izbirnik **Okolje**.

2.  Izberite ikono za **urejanje**.

3. V polju **Uredi okolje** lahko posodobite **prikazno ime** okolja, vendar pa ne morete spremeniti **regije** ali **tipa**.

4. Če je okolje konfigurirano za shranjevanje podatkov v shrambi Azure Data Lake Storage, lahko posodobite **Ključ računa**. Vendar pa ne morete spremeniti možnosti **Ime računa** ali imena razdelka **Vsebnik**.

5. Po želji lahko povezavo, ki temelji na ključu računa posodobite ter zamenjate s povezavo, ki temelji na virih ali na naročnini. Po nadgradnji ne morete povrniti ključa kupca po posodobitvi. Za več informacij glejte [Povezovanje vpogledov v občinstvo in računa Azure Data Lake Storage Gen2 z glavnim imenom storitve Azure](connect-service-principal.md). Ob posodobitvi povezave ne morete spremeniti podatkov **vsebnika**.

6. Izbirno lahko zagotovite URL okolja Microsoft Dataverse pod možnostjo **Konfiguriranje skupne rabe podatkov s storitvijo Microsoft Dataverse in omogočanje dodatnih zmogljivosti**. Te zmogljivosti vključujejo skupno rabo podatkov z aplikacijami in rešitvami na podlagi storitve Microsoft Dataverse, uvoz podatkov iz podatkovnih virov na mestu uporabe ali uporabo [napovedi](predictions.md). Izberite možnost **Omogoči skupno rabo podatkov** za skupno rabo izhodnih podatkov Customer Insights s storitvijo Microsoft Dataverse Managed Data Lake.

   > [!NOTE]
   > - Skupna raba podatkov s storitvijo Microsoft Dataverse Managed Data Lake trenutno ni podprta, če vse podatke shranjujete v shrambi Azure Data Lake Storage.
   > - [Predvidevanje manjkajočih vrednosti v entiteti](predictions.md) in vdelana poročila PowerBI v vpogledih v občinstvo (če je omogočeno v vašem okolju) trenutno niso podprta, če omogočite skupno rabo podatkov s podatkovnim jezerom, ki ga upravlja Microsoft Dataverse.

   Ko omogočite izmenjavo podatkov z okoljem Microsoft Dataverse, se bo zagnala popolna osvežitev vaših virov podatkov in drugih postopkov. Če se postopki trenutno izvajajo, ne boste videli možnosti za omogočanje skupne rabe podatkov s storitvijo Microsoft Dataverse. Počakajte, da se ti postopki končajo ali jih prekličete, da omogočite izmenjavo podatkov. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Možnosti konfiguracije za omogočanje skupne rabe podatkov s storitvijo Microsoft Dataverse.":::
   
   Ko zaženete postopke, na primer uvoz podatkov ali ustvarjanje segmenta, bodo v zgoraj navedenem računu za shranjevanje ustvarjene ustrezne mape. Podatkovne datoteke in datoteke model.json bodo ustvarjene in dodane v zadevne podmape, odvisno od postopka, ki ga izvajate.

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
- Viri podatkov iz mape Common Data Model in shrambe Data Lake, ki jo upravlja Dataverse. Te vire podatkov boste morali ustvariti ročno z istim imenom kot v izvornem okolju.

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
