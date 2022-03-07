---
title: Obogatitev z neodvisno obogatitvijo HERE Technologies
description: Splošne informacije o neodvisni obogatitvi HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 1b46e8913c6d288b93cdf32e195b5e9387916e70
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230402"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Obogatitev profilov strank v sodelovanju z družbo HERE Technologies (predogled)

HERE Technologies je podjetje z lokacijsko platformo, ki ponuja lokacijsko usmerjene podatke in storitve. S storitvami za obogatitev podatkov podjetja HERE Technologies lahko z normalizacijo naslova, ekstrakcijo zemljepisne širine in dolžine in še več zagotovite natančnejše razumevanje lokacije svojih strank.

## <a name="prerequisites"></a>Zahteve

Za konfiguracijo obogatitve HERE Technologies morajo biti izpolnjeni naslednji predpogoji:

- Imate aktivno naročnino HERE Technologies. Če želite naročnino, se lahko [prijavite tukaj](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) ali [se obrnete neposredno na družbo HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you). [Preberite več o obogatitvi lokacije HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- [Povezava](connections.md) HERE je na voljo, *do nje pa lahko dostopate tudi* s pomočjo dovoljenja [skrbnika](permissions.md#administrator) in ključa vmesnika API družbe HERE Technologies.

## <a name="configure-the-enrichment"></a>Konfiguriranje obogatitve

1. Pomaknite se na možnost **Podatki** > **Obogatitev**. 

1. Na ploščici za HERE Technologies izberite možnost **Obogatitev podatkov** in izberite možnost **Začetek**.

   > [!div class="mx-imgBorder"]
   > ![Ploščica HERE Technologies.](media/HERE-tile.png "Ploščica HERE Technologies")

1. Na spustnem seznamu izberite možnost [povezava](connections.md). Če ni na voljo nobena povezava, se obrnite na skrbnika. Če ste skrbnik, lahko vzpostavite povezavo z izbiro možnosti **Dodaj povezavo**. Na spustnem seznamu izberite možnost **HERE Technologies**. 

1. Izberite možnost **Poveži z družbo HERE Technologies** za potrditev izbire.

1.  Izberite možnost **Naprej** in izberite **nabor podatkov o stranki**, ki ga želite obogatiti s podatki o lokaciji podjetja HERE Technologies. Izberete lahko entiteto **Stranka**, da obogatite vse vaše profile strank, ali entiteto segmenta, da obogatite samo profile strank, ki jih vsebuje ta segment.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Posnetek zaslona izbire nabora podatkov o strankah.":::

1. Izberite, ali želite polja preslikati na primarni in/ali sekundarni naslov. Za oba naslova lahko določite preslikavo polj in obogatite profile za vsak naslov posebej. Gre za primere, ko je na primer na voljo domač in poslovni naslov. Izberite **Naprej**.

1. Določite, katera polja iz vaših poenotenih profilov naj bodo uporabljena za iskanje ustreznih podatkov o lokaciji družbe HERE Technologies. Polji **Ulica 1** in **Poštna številka** sta obvezni za izbrani primarni in/ali sekundarni naslov. Za večjo natančnost ujemanja lahko dodate več polj.

   > [!div class="mx-imgBorder"]
   > ![Stran za konfiguracijo obogatitve HERE Technologies.](media/enrichment-HERE-configuration.png "Stran za konfiguracijo obogatitve HERE Technologies")

1. Izberite možnost **Naprej**, da dokončate preslikavo polj.

1. Navedite ime obogatitve. 

1. Po pregledu svoje izbire izberite možnost **Shrani obogatitev**.

## <a name="configure-the-connection-for-here-technologies"></a>Konfigurirajte povezavo za HERE Technologies. 

Za konfiguriranje povezav morate biti skrbnik. Pri konfiguriranju obogatitve izberite možnost **Dodaj povezavo** *ali* odprite razdelek **Skrbnik** > **Povezave** in na ploščici HERE Technologies izberite možnost **Nastavitev**.

1. Vnesite ime povezave v polje za **prikazno ime**.

1. Navedite veljaven ključ za API HERE Technologies.

1. Preglejte in podajte soglasje, tako da v razdelku **Zasebnost in skladnost podatkov** izberete možnost **Strinjam se**.

1. Izberite možnost **Potrdi** za potrditev konfiguracije.

1. Po zaključku potrjevanja izberite možnost **Shrani**.

   > [!div class="mx-imgBorder"]
   > ![Stran za konfiguriranje povezave z družbo HERE technologies.](media/enrichment-HERE-connection.png "Stran za konfiguriranje povezave z družbo HERE technologies")

## <a name="enrichment-results"></a>Rezultati obogatitve

Če želite začeti postopek obogatitve, izberite **Zaženi** v ukazni vrstici. Sistem lahko obogatitev samodejno zažene tudi kot del [načrtovane osvežitve](system.md#schedule-tab). Čas obdelave bo odvisen od velikosti podatkov o vaših strankah in odzivnega časa API-ja družbe HERE Technologies.

Po končanem postopku obogatitve lahko podatke o na novo obogatenih profilih strank pregledate v možnosti **Moje obogatitve**. Poleg tega boste našli čas zadnje posodobitve in število obogatenih profilov.

Do podrobnega prikaza vsakega obogatenega profila lahko dostopate tako, da izberete **Ogled obogatenih podatkov**.

## <a name="next-steps"></a>Naslednji koraki

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v HERE Technologies, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da HERE Technologies izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš skrbnik za Dynamics 365 Customer Insights lahko to obogatitev kadarkoli odstrani, s čimer je uporaba te funkcije prekinjena.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
