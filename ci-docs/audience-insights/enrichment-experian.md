---
title: Obogatitev z neodvisno obogatitvijo Experian
description: Splošne informacije o neodvisni obogatitvi Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: efa26fa82a950063e074a4ab930ed95383c55334
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376712"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Profile strank obogatite z demografskimi podatki iz storitve Experian (predogled)

Experian je vodilno podjetje v svetu na področju poročanja o potrošniških in poslovnih kreditih in na področju trženjskih storitev. S pomočjo storitev za obogatitev podatkov Experian lahko poglobite razumevanje svojih strank, in sicer tako, da njihove profile obogatite s pomočjo demografskih podatkov, kot so velikost gospodinjstva, dohodek itd.

## <a name="prerequisites"></a>Zahteve

Da bi lahko konfigurirali Experian, morate izpolnjevati naslednje predpogoje:

- Imeti morate aktivno naročnino na Experian. Če se želite naročiti, [se obrnite neposredno na Experian](https://www.experian.com/marketing-services/contact). [Več informacij o obogatitvi podatkov Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Povezavo Experian je konfiguriral skrbnik, *v nasprotnem primeru* pa imate [skrbnikovo](permissions.md#admin) dovoljenje vi. Potrebujete tudi ID uporabnika, ID stranke in številko modela za račun storitve Secure Transport (ST) z omogočeno funkcijo SSH, ki ga je za vas ustvaril Experian.

## <a name="supported-countriesregions"></a>Podprte države/regije

Obogatitev profilov strank trenutno omogočamo samo v ZDA.

## <a name="configure-the-enrichment"></a>Konfiguriranje obogatitve

1. Pojdite v **Podatki** > **Obogatitev** in izberite zavihek **Odkrivanje**.

1. Izberite možnost **Obogatitev mojih podatkov** na ploščici Experian.

   > [!div class="mx-imgBorder"]
   > ![Ploščica Experian.](media/experian-tile.png "Experian tile")
   > 

1. Na spustnem seznamu izberite možnost [povezava](connections.md). Če ni na voljo nobena povezava, se obrnite na skrbnika. Če ste skrbnik, lahko vzpostavite povezavo tako, da izberete možnost **Dodaj povezavo** in na spustnem seznamu izberete Experian. 

1. Za potrditev izbire povezave zberite možnost **Poveži z Experian**.

1.  Izberite možnost **Naprej**, nato pa možnost **Nabor podatkov o strankah**, ki jih želite obogatiti z demografskimi podatki iz storitve Experian. Izberete lahko entiteto **Stranka**, da obogatite vse vaše profile strank, ali entiteto segmenta, da obogatite samo profile strank, ki jih vsebuje ta segment.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Posnetek zaslona izbire nabora podatkov o strankah.":::

1. Izberite možnost **Naslednji** in določite, katera vrsta polj iz vaših poenotenih profilov mora biti uporabljena za iskanje ujemajočih se demografskih podatkov iz storitve Experian. Zahtevano je vsaj eno od naslednjih polj: **Ime in naslov**, **Telefon** ali **E-poštni naslov**. Za večjo natančnost ujemanja lahko dodate do dve dodatni polji. Ta izbira vpliva na polja za preslikavo, do katerih imate dostop v naslednjem koraku.

    > [!TIP]
    > Več atributov identifikatorja ključa, poslanih storitvi Experian, lahko doprinese višjo stopnjo ujemanja.

1. Izberite možnost **Naprej**, da začnete preslikavo polj.

1. Določite, katera polja iz vaših poenotenih profilov morajo biti uporabljena za iskanje ujemajočih se demografskih podatkov iz storitve Experian. Obvezna polja so označena.

1. Navedite ime obogatitve in izhodne entitete.

1. Po pregledu svoje izbire izberite možnost **Shrani obogatitev**.

## <a name="configure-the-connection-for-experian"></a>Konfigurirajte povezavo za Experian 

Za konfiguriranje povezav morate biti skrbnik. Pri konfiguriranju obogatitve izberite možnost **Dodaj povezavo** *ali možnost* **Skrbnik** > **Povezave** ter izberite **Nastavi** na ploščici storitve Experian.

1. Izberite **Začetek**.

1. Vnesite ime povezave v polje za **prikazno ime**.

1. Vnesite veljaven ID uporabnika, ID stranke in številko modela za svoj račun Secure Transport v storitvi Experian.

1. Preglejte in podajte soglasje, tako da v razdelku **Zasebnost in skladnost podatkov** izberete možnost **Strinjam se**.

1. Izberite možnost **Potrdi** za potrditev konfiguracije.

1. Po zaključku potrjevanja izberite možnost **Shrani**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian podokno konfiguracije povezave.":::

## <a name="enrichment-results"></a>Rezultati obogatitve

Če želite začeti postopek obogatitve, izberite **Zaženi** v ukazni vrstici. Sistem lahko obogatitev samodejno zažene tudi kot del [načrtovane osvežitve](system.md#schedule-tab). Čas obdelave bo odvisen od velikosti vaših podatkov o strankah in od postopkov obogatitve, ki jih je za vaš račun vzpostavil Experian.

Po končanem postopku obogatitve lahko podatke o na novo obogatenih profilih strank pregledate v možnosti **Moje obogatitve**. Poleg tega boste našli čas zadnje posodobitve in število obogatenih profilov.

Do podrobnega prikaza vsakega obogatenega profila lahko dostopate tako, da izberete **Ogled obogatenih podatkov**.

## <a name="next-steps"></a>Naslednji koraki

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

S tem ko dovolite, da Dynamics 365 Customer Insights podatke prenese storitvi Experian, omogočite prenos podatkov zunaj omejitve skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo take podatke prenesel skladno z vašimi navodili, vendar ste vi odgovorni za to, da Experian izpolnjuje morebitne obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš skrbnik za Dynamics 365 Customer Insights lahko to obogatitev kadarkoli odstrani, s čimer je uporaba te funkcije prekinjena.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
