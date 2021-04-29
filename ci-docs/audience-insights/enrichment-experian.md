---
title: Obogatitev z neodvisnimi obogatitvami Experian
description: Splošne informacije o neodvisni obogatitvi Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896393"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Obogatitev profilov strank z demografskimi podatki podjetja Experian (predogled)

Družba Experian je vodilna v svetu pri kreditnem poročanju o potrošniških in podjetjih ter tržnih storitvah. S storitvami za obogatitev podatkov družbe Experian lahko globlje razumete svoje stranke tako, da svoje profile strank obogatite z demografskimi podatki, kot so velikost gospodinjstva, dohodek in drugo.

## <a name="prerequisites"></a>Zahteve

Za konfiguracijo storitve Experian je treba izpolnjevati naslednje predpogoje:

- Imate aktivno naročnino za Experian. Če želite naročnino, [se obrnite neposredno na Experian](https://www.experian.com/marketing-services/contact). [Več informacij o obogatitvi podatkov Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Skrbnik je že konfiguriral povezavo s storitvijo Experian *oziroma* imate vi [skrbniška](permissions.md#administrator) dovoljenja. Potrebujete tudi ID uporabnika, ID stranke in številko modela za račun storitve Secure Transport (ST) z omogočenim protokolom SSH, ki ga je za vas ustvaril Experian.

## <a name="configure-the-enrichment"></a>Konfiguriranje obogatitve

1. Pojdite v **Podatki** > **Obogatitev** in izberite zavihek **Odkrivanje**.

1. Izberite **Obogatitev podatkov** na ploščici storitve Experian.

   > [!div class="mx-imgBorder"]
   > ![Ploščica storitve Experian](media/experian-tile.png "Ploščica storitve Experian")
   > 

1. Na spustnem seznamu izberite [povezavo](connections.md). Če ni na voljo nobena povezava, se obrnite na skrbnika. Če ste skrbnik, lahko vzpostavite povezavo tako, da izberete možnost **Dodaj povezavo** in na spustnem meniju izberete možnost Experian. 

1. Izberite možnost **Poveži z Experian** za potrditev izbire povezave.

1.  Izberite možnost **Naprej** in izberite **nabor podatkov o stranki**, ki ga želite obogatiti z demografskimi podatki podjetja Experian. Izberete lahko entiteto **Stranka**, da obogatite vse vaše profile strank, ali entiteto segmenta, da obogatite samo profile strank, ki jih vsebuje ta segment.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Posnetek zaslona izbire nabora podatkov o strankah.":::

1. Izberite možnost **Naprej** in določite, katero vrsto polj iz vaših poenotenih profilov je treba uporabiti za iskanje ustreznih demografskih podatkov iz Experiana. Zahtevano je vsaj eno od naslednjih polj: **Ime in naslov**, **Telefon** ali **E-poštni naslov**. Za večjo natančnost ujemanja lahko dodate do dve dodatni polji. Ta izbira vpliva na polja za preslikavo, do katerih imate dostop v naslednjem koraku.

    > [!TIP]
    > Več atributov identifikatorjev ključev, poslanih Experianu, bo verjetno povzročilo višjo stopnjo ujemanja.

1. Izberite možnost **Naprej**, da začnete preslikavo polj.

1. Določite, katero vrsto polj iz vaših poenotenih profilov je treba uporabiti za iskanje ustreznih demografskih podatkov iz Experiana. Obvezna polja so označena.

1. Navedite ime obogatitve in izhodne entitete.

1. Po pregledu svoje izbire izberite možnost **Shrani obogatitev**.

## <a name="configure-the-connection-for-experian"></a>Konfiguriranje povezave z Experian 

Za konfiguriranje povezav morate biti skrbnik. Pri konfiguriranju obogatitve izberite možnost **Dodaj povezavo** *ali* odprite razdelek **Skrbnik** > **Povezave** in na ploščici Experian izberite možnost **Nastavitev**.

1. Izberite **Začetek**.

1. Vnesite ime povezave v polje za **prikazno ime**.

1. Vnesite veljaven ID uporabnika, ID stranke in številko modela za svoj račun Experian Secure Transport.

1. Preberite in podajte soglasje za **Zasebnost podatkov in skladnost** tako, da potrdite polje **Strinjam se**.

1. Izberite možnost **Potrdi** za potrditev konfiguracije.

1. Po zaključku potrjevanja izberite možnost **Shrani**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Podokno za konfiguriranje povezave z Experianom.":::

## <a name="enrichment-results"></a>Rezultati obogatitve

Če želite začeti postopek obogatitve, izberite **Zaženi** v ukazni vrstici. Sistem lahko obogatitev samodejno zažene tudi kot del [načrtovane osvežitve](system.md#schedule-tab). Čas obdelave bo odvisen od velikosti podatkov o strankah in postopkov obogatitve, ki jih je za vaš račun nastavil Experian.

Po končanem postopku obogatitve lahko podatke o na novo obogatenih profilih strank pregledate v možnosti **Moje obogatitve**. Poleg tega boste našli čas zadnje posodobitve in število obogatenih profilov.

Do podrobnega prikaza vsakega obogatenega profila lahko dostopate tako, da izberete **Ogled obogatenih podatkov**.

## <a name="next-steps"></a>Naslednji koraki

Nadgradite svoje obogatene podatke o strankah. Ustvarite [Segmente](segments.md), [Mere](measures.md) in pa [izvozite podatke](export-destinations.md), da svojim strankam zagotovite prilagojeno izkušnjo.

## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v Experian dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Experian izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš skrbnik za Dynamics 365 Customer Insights lahko to obogatitev kadar koli odstrani in s tem prekini uporabo te funkcije.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
