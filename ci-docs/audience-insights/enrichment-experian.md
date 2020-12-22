---
title: Obogatitev z neodvisnimi obogatitvami Experian
description: Splošne informacije o neodvisni obogatitvi Experian.
ms.date: 09/17/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 60fc49734e54740e83b47a7028be216a0eb81e49
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668833"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Obogatitev profilov strank z demografskimi podatki podjetja Experian (predogled)

Družba Experian je vodilna v svetu pri kreditnem poročanju o potrošniških in podjetjih ter tržnih storitvah. S storitvami za obogatitev podatkov družbe Experian lahko globlje razumete svoje stranke tako, da svoje profile strank obogatite z demografskimi podatki, kot so velikost gospodinjstva, dohodek in drugo.

## <a name="prerequisites"></a>Zahteve

Za konfiguracijo storitve Experian je treba izpolnjevati naslednje predpogoje:

- Imate aktivno naročnino za Experian. Če želite naročnino, [se obrnite neposredno na Experian](https://www.experian.com/marketing-services/contact). [Več informacij o obogatitvi podatkov Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).
- Imate ID uporabnika, ID stranke in številko modela za svoj račun za zaščiten promet (ST) z omogočenim SSH, ki ga je za vas ustvaril Experian.
- Imate dovoljenja [skrbnika](permissions.md#administrator) pri vpogledih v občinstvo.

## <a name="configuration"></a>Konfiguracija

1. Pojdite v **Podatki** > **Obogatitev** in izberite zavihek **Odkrivanje**.

1. Izberite **Obogatitev podatkov** na ploščici storitve Experian.

   > [!div class="mx-imgBorder"]
   > ![Ploščica storitve Experian](media/experian-tile.png "Ploščica storitve Experian")

1. Izberite **Začetek** in vnesite ID uporabnika, ID stranke in številko modela za svoj račun Experian Secure Transport. Preberite in podajte soglasje za **Zasebnost podatkov in skladnost** tako, da potrdite polje **Strinjam se**. Potrdite vse vnose z izbiro **Uporabi**.

## <a name="map-your-fields"></a>Preslikajte polja

1. Izberite **Dodajte podatke** in izberite svoje identifikatorje ključev med možnostmi **Ime in naslov**, **E-pošta** ali **Telefon**, ki jih želite poslati v Experian za razreševanje identitete.

   > [!TIP]
   > Več atributov identifikatorjev ključev, poslanih Experianu, bo verjetno povzročilo višjo stopnjo ujemanja.

1. Izberite **Naslednji** in preslikajte ustrezne atribute iz vaše enotne entitete stranke za izbrana polja identifikatorja ključa.

1. Izberite **Dodaj atribut** za preslikavo dodatnih atributov, ki bi jih radi poslali Experianu.

1.  Izberite **Shrani** za dokončanje preslikave polj.

   > [!div class="mx-imgBorder"]
   > ![Preslikave polja Experian](media/experian-field-mapping.png "Preslikave polja Experian")

## <a name="enrichment-results"></a>Rezultati obogatitve

Če želite začeti postopek obogatitve, izberite **Zaženi** v ukazni vrstici. Sistem lahko obogatitev samodejno zažene tudi kot del [načrtovane osvežitve](system.md#schedule-tab). Čas obdelave bo odvisen od velikosti podatkov o strankah in postopkov obogatitve, ki jih je za vaš račun nastavil Experian.

Po končanem postopku obogatitve lahko podatke o na novo obogatenih profilih strank pregledate v možnosti **Moje obogatitve**. Poleg tega boste našli čas zadnje posodobitve in število obogatenih profilov.

Do podrobnega prikaza vsakega obogatenega profila lahko dostopate tako, da izberete **Ogled obogatenih podatkov**.

## <a name="next-steps"></a>Naslednji koraki

Nadgradite svoje obogatene podatke o strankah. Ustvarite [Segmente](segments.md), [Mere](measures.md) in pa [izvozite podatke](export-destinations.md), da svojim strankam zagotovite prilagojeno izkušnjo.

## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v Experian dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Experian izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš skrbnik za Dynamics 365 Customer Insights lahko to obogatitev kadar koli odstrani in s tem prekini uporabo te funkcije.
