---
title: Obogatitev z neodvisnimi obogatitvami HERE Technologies
description: Splošne informacije o neodvisni obogatitvi HERE Technologies.
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668698"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Obogatitev profilov strank v sodelovanju z družbo HERE Technologies (predogled)

HERE Technologies je podjetje z lokacijsko platformo, ki ponuja lokacijsko usmerjene podatke in storitve. S storitvami za obogatitev podatkov podjetja HERE Technologies lahko z normalizacijo naslova, ekstrakcijo zemljepisne širine in dolžine in še več zagotovite natančnejše razumevanje lokacije svojih strank.

## <a name="prerequisites"></a>Zahteve

Za konfiguracijo obogatitve HERE Technologies morajo biti izpolnjeni naslednji predpogoji:

- Imate aktivno naročnino HERE Technologies. Če želite naročnino, se lahko [prijavite tukaj](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) ali neposredno [stopite v stik z družbo HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you). [Preberite več o obogatitvi lokacije HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Imate ključ API za HERE Technologies.

- Imate [skrbniška](permissions.md#administrator) dovoljenja.

## <a name="configuration"></a>Konfiguracija

1. Pomaknite se na možnost **Podatki** > **Obogatitev**.

1. Izberite **Obogatitev podatkov** na ploščici HERE Technologies.

   > [!div class="mx-imgBorder"]
   > ![Ploščica HERE Technologies](media/HERE-tile.png "Ploščica HERE Technologies")

1. Vnesite aktiven **ključ API za HERE Technologies**. Preberite in podajte soglasje za **Zasebnost podatkov in skladnost** tako, da potrdite polje **Strinjam se**. 

1. Potrdite oba vnosa z izbiro možnosti **Povezovanje s HERE**.

1. Izberite **Dodajanje podatkov** in izberite, ali želite polja preslikati na primarni in/ali sekundarni naslov. Za oba naslova lahko določite preslikavo polj (na primer domači in poslovni naslov) in obogatite profile za oba naslova posebej. Izberite **Naprej**.

1. Določite, katera polja iz vaših poenotenih profilov naj bodo uporabljena za iskanje ustreznih podatkov o lokaciji družbe HERE Technologies. Polji **Ulica 1** in **Poštna številka** sta obvezni za izbrani primarni in/ali sekundarni naslov. Za večjo natančnost ujemanja lahko dodate več polj.

   > [!div class="mx-imgBorder"]
   > ![Stran za konfiguracijo obogatitve HERE Technologies](media/enrichment-HERE-configuration.png "Stran za konfiguracijo obogatitve HERE Technologies")

1. Izberite **Uporabi** za dokončanje preslikave polja.

## <a name="enrichment-results"></a>Rezultati obogatitve

Če želite začeti postopek obogatitve, izberite **Zaženi** v ukazni vrstici. Sistem lahko obogatitev samodejno zažene tudi kot del [načrtovane osvežitve](system.md#schedule-tab). Čas obdelave bo odvisen od velikosti podatkov o vaših strankah in odzivnega časa API-ja družbe HERE Technologies.

Po končanem postopku obogatitve lahko podatke o na novo obogatenih profilih strank pregledate v možnosti **Moje obogatitve**. Poleg tega boste našli čas zadnje posodobitve in število obogatenih profilov.

Do podrobnega prikaza vsakega obogatenega profila lahko dostopate tako, da izberete **Ogled obogatenih podatkov**.

## <a name="next-steps"></a>Naslednji koraki

Nadgradite svoje obogatene podatke o strankah. Ustvarite [Segmente](segments.md), [Mere](measures.md) in pa [izvozite podatke](export-destinations.md), da svojim strankam zagotovite prilagojeno izkušnjo.

## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v HERE Technologies, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da HERE Technologies izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš skrbnik za Dynamics 365 Customer Insights lahko to obogatitev kadar koli odstrani in s tem prekini uporabo te funkcije.
