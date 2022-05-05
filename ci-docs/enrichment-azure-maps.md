---
title: Obogatitev profilov strank s podatki o lokaciji iz storitve Zemljevidi Azure
description: Splošne informacije o obogatitvi proizvajalca storitve Zemljevidi Azure.
ms.date: 08/31/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 6a1c3791076a7dda4531664ca88632f7f1b914e3
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643008"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Obogatitev profilov strank s storitvijo Zemljevidi Azure (predogledna različica)

Storitev Zemljevidi Azure ponuja podatke in storitve, osredotočene na lokacijo, za zagotavljanje izkušenj na podlagi geoprostorskih podatkov z vgrajenim obveščanjem o lokaciji. Storitve obogatitve podatkov v storitvi Zemljevidi Azure izboljšajo natančnost podatkov o lokaciji vaših strank. Prinaša zmogljivosti, kot so normaliziranje naslovov ter ekstrahiranje zemljepisne širine in dolžine v storitev Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Zahteve

Če želite konfigurirati obogatitev podatkov v storitvi Zemljevidi Azure, morajo biti izpolnjeni naslednji pogoji:

- Imeti morate aktivno naročnino na storitev Zemljevidi Azure. Če se želite naročiti, se lahko [prijavite ali pridobite brezplačno preskusno različico](https://azure.microsoft.com/services/azure-maps/).

- Na voljo morate imeti [povezavo](connections.md) za storitev Zemljevidi Azure *ali* pa [skrbniško](permissions.md#admin) dovoljenje in aktivni ključ API za storitev Zemljevidi Azure.

## <a name="configure-the-enrichment"></a>Konfiguriranje obogatitve

1. Pomaknite se na možnost **Podatki** > **Obogatitev**. 

1. Izberite možnost **Obogatitev podatkov** na ploščici **Lokacija**.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Ploščica za storitev Zemljevidi Azure.":::

1. Na spustnem seznamu izberite možnost [povezava](connections.md). Če povezava za storitev Zemljevidi Azure ni na voljo, se obrnite na skrbnika. Če ste skrbnik, lahko [konfigurirate povezavo za storitev Zemljevidi Azure](#configure-the-connection-for-azure-maps). 

1. Izberite **Naprej**, da potrdite izbiro.

1. Izberite **Nabor podatkov o strankah**, ki ga želite obogatiti s podatki o lokaciji iz storitve Zemljevidi Azure. Izberete lahko entiteto **Stranka**, da obogatite vse svoje poenotene profile strank, ali izberite entiteto segmenta, da obogatite samo profile strank v tem segmentu.

    :::image type="content" source="media/enrichment-azure-maps-configuration-customer-data-set.png" alt-text="Posnetek zaslona izbire nabora podatkov o strankah.":::

1. Izberite, ali želite preslikati polja na primarni in/ali sekundarni naslov. Določite lahko preslikavo polj za oba naslova in ločeno obogatite profile za oba naslova, na primer za domači in službeni naslov. Izberite **Naprej**.

1. Določite, katera polja iz vaših poenotenih profilov morajo biti uporabljena za iskanje ujemajočih se podatkov o lokaciji iz storitve Zemljevidi Azure. Polji **Ulica 1** in **Poštna številka** sta obvezni za izbrani primarni ali sekundarni naslov. Za večjo točnost ujemanja lahko dodate več polj.

   :::image type="content" source="media/enrichment-azure-maps-configuration.png" alt-text="Stran za konfiguracijo obogatitve storitve Zemljevidi Azure.":::

1. Izberite možnost **Naprej**, da dokončate preslikavo polj.

1. Ocenite, ali želite spremeniti **Dodatne nastavitve**. Te so na voljo za največjo prilagodljivost pri obravnavi naprednih primerov uporabe, vendar bodo privzete vrednosti v večini primerov ustrezne:
   - **Vrsta naslovov**: Nastavljeno je privzeto vedenje, da obogatitev vrne najboljše ujemanje naslova, tudi če je naslov nepopoln. Če želite pridobit samo popolne naslove, na primer naslove, ki vključujejo hišno številko, počistite vsa potrditvena polja razen **Naslovi točke**. 
   - **Jezik**: Naslovi so privzeto vrnjeni v jeziku regije, kateri pripada naslov. Če želite uporabiti standardiziran jezik naslova, v spustnem meniju izberite jezik. Na primer, če izberete **angleščina**, bo vrnjeno **Kopenhagen, Danska**, namesto **København, Danska**.

1. Navedite ime obogatitve.

1. Preglejte svojo izbiro in nato izberite **Shrani obogatitev**.

## <a name="configure-the-connection-for-azure-maps"></a>Konfiguriranje povezave za storitev Zemljevidi Azure

Za konfiguriranje povezav morate biti skrbnik v storitvi Customer Insights. Pri konfiguriranju obogatitve izberite možnost **Dodaj povezavo** ali pa odprite razdelek **Skrbnik** > **Povezave** ter v ploščici storitve Zemljevidi Azure izberite **Nastavitev**.

1. V polje **Prikazno ime** vnesite ime povezave.

1. Navedite veljaven ključ API za storitev Zemljevidi Azure.

1. Preberite in podajte soglasje za **Zasebnost podatkov in skladnost** tako, da potrdite polje **Strinjam se**.

1. Izberite možnost **Potrdi** za potrditev konfiguracije.

1. Po zaključku potrjevanja izberite možnost **Shrani**.

:::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Stran za konfiguracijo povezave za storitev Zemljevidi Azure.":::

## <a name="enrichment-results"></a>Rezultati obogatitve

Če želite začeti postopek obogatitve, izberite **Zaženi** v ukazni vrstici. Sistem lahko obogatitev samodejno zažene tudi kot del [načrtovane osvežitve](system.md#schedule-tab). Čas obdelave bo odvisen od velikosti vaših podatkov o strankah in odzivnega časa API-ja.

Ko je postopek obogatitve končan, lahko pregledate podatke o novo obogatenih profilih strank v razdelku **Moje obogatitve**. Poleg tega boste našli čas zadnje posodobitve in število obogatenih profilov.

Do podrobnega prikaza vsakega obogatenega profila lahko dostopate tako, da izberete **Ogled obogatenih podatkov**.

## <a name="next-steps"></a>Naslednji koraki

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

S tem ko dovolite, da storitev Dynamics 365 Customer Insights podatke prenese storitvi Zemljevidi Azure, omogočite prenos podatkov zunaj omejitve skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo tovrstne podatke prenesel skladno z vašimi navodili, vendar ste vi odgovorni za to, da storitev Zemljevidi Azure izpolni morebitne obveznosti glede zasebnosti ali varnosti. Za več informacij pojdite na [Microsoftova izjava o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš skrbnik za Dynamics 365 Customer Insights lahko to obogatitev kadar koli odstrani in s tem prekini uporabo te funkcije.

[!INCLUDE [footer-include](includes/footer-banner.md)]
