---
title: Izboljšanje podatkov o podjetju
description: Obogatite in normalizirajte podatke podjetja z Microsoftovimi modeli.
ms.date: 04/22/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6aa38afa7f92b512d19b4967fc1652b5e43ad094
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642988"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Obogatitev profilov podjetij z izboljšanimi podatki o podjetju

Uporabite Microsoftove modele in zbrane podatke podjetja, da popravite, dopolnite in standardizirate profile vašega podjetja. Uporabili bomo [Format skupnega podatkovnega modela](/common-data-model/schema/core/applicationcommon/account) za boljšo natančnost in vpoglede.

Lahko tudi [izboljšati podatke podjetja o virih podatkov](data-sources-enrichment.md) izboljšati natančnost ujemanja v procesu poenotenja podatkov. 

Za javna podjetja v Združenih državah so na voljo informacije, kot so prihodki, borzni podatki, industrija in drugo.  

## <a name="how-we-enhance-company-data"></a>Kako izboljšamo podatke o podjetju

Naš model gre skozi postopek v dveh korakih za izboljšanje profila podjetja. Prvič, normalizira ime podjetja. Na primer *Microsoft Corp* bo popravljeno in standardizirano *Microsoft Corporation*. Poskuša najti ujemanje v Microsoftovih zbranih podatkih podjetja. Če najdemo ujemanje, obogatimo profil podjetja z informacijami iz naših zbranih podatkov podjetja, vključno z imenom podjetja.


### <a name="example"></a>Primer

Podatki o vašem podjetju morda niso v standardizirani obliki in vsebujejo črkovalne napake. Model poskuša odpraviti te težave in ustvariti dosledne informacije.

```Input
Microsft
```

```Output
- AccountName: Microsoft Corporation
- MainPhoneNumber: 8006427676
- Website: https://www.microsoft.com/
- Street1: One Microsoft Way
- City: Redmond
- StateOrProvince: Washington
- County: King
- ZipOrPostalCode: 98052
- CountryOrRegion: United States
```

## <a name="limitations"></a>Omejitve

Pri izboljšanih podatkih obstaja nekaj omejitev. Model ne podpira elementov na spodnjem seznamu.

1.  Potrdite identiteto podjetja. Ne preverjamo, ali je vhod obstoječa organizacija ali ali podjetje uporablja izhod kot svoje standardno ime.
2.  Celovito pokrivajte podjetja po vsem svetu. Microsoftovi zbrani podatki o podjetju imajo globalno pokritost, vendar ponujajo največjo pokritost v Avstraliji, Kanadi, Združenem kraljestvu in Združenih državah.
3.  Standardizirajte naslove podjetij po vsem svetu. Trenutno podpiramo standardizacijo naslovov v teh državah ali regijah: Avstralija, Kanada, Francija, Nemčija, Italija, Japonska, Združeno kraljestvo in Združene države.
4.  Zagotavljamo točnost ali svežino podatkov. Ker se poslovne informacije pogosto spreminjajo, ne moremo zagotoviti, da so predloženi izboljšani podatki podjetja vedno točni ali posodobljeni.

## <a name="configure-the-enrichment"></a>Konfiguriranje obogatitve

1. Pomaknite se na možnost **Podatki** > **Obogatitev**.

1. Izberite **Obogatite moje podatke** na **Izboljšani podatki o podjetju** ploščice.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Ploščica za obogatitev v središču za obogatitev za podatke o podjetju.":::

1. Izberite možnost **Nabor podatkov o stranki** in izberite entiteto, ki vsebuje naslove, ki jih želite obogatiti. Izberete lahko entiteto *Stranka* za obogatitev naslovov v vseh vaših profilih strank ali pa entiteto segmenta za obogatitev naslovov samo v profilih strank v tem segmentu.

1. Izberite, katere vrste polj iz profilov vašega podjetja naj se uporabljajo za ujemanje z Microsoftovimi zbranimi podatki o podjetju. Ta izbira vpliva na polja za preslikavo, do katerih imate dostop v naslednjem koraku.

1.  Preslikajte polja podjetja iz vaše enotne stranke. Več ključnih identifikatorjev in polj preslikate, večja je verjetnost za višjo stopnjo ujemanja.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Korak preslikave podatkov pri konfiguraciji obogatitve podjetja.":::

1. Izberite možnost **Naprej**, da dokončate preslikavo polj.

1. Navedite ime obogatitve in izhodne entitete.

1. Po pregledu svoje izbire izberite možnost **Shrani obogatitev**.

## <a name="enrichment-results"></a>Rezultati obogatitve

Če želite začeti postopek obogatitve, izberite **Zaženi** v ukazni vrstici. Sistem lahko obogatitev samodejno zažene tudi kot del [načrtovane osvežitve](system.md#schedule-tab). Čas obdelave je odvisen od velikosti podatkov o stranki.

Po končanem postopku obogatitve lahko podatke o na novo obogatenih profilih strank pregledate v možnosti **Moje obogatitve**. Poleg tega boste našli čas zadnje posodobitve in število obogatenih profilov.

Vzorec obogatenih podatkov si lahko ogledate v **Obogaten predogled strank** ploščice. Izberite **Poglej več** in izberite **Podatki** zavihek za dostop do podrobnega pogleda vsakega obogatenega profila.

### <a name="overview-card"></a>Pregledna kartica

Pregledna kartica prikazuje podrobnosti o kritju obogatitve. 

* **Podjetja obdelana in spremenjena** : Število uspešno obogatenih profilov podjetij strank.

* **Podjetja obdelana in nespremenjena** : število profilov podjetij strank, ki so bili prepoznani, vendar nespremenjeni. To se običajno zgodi, ko so vhodni podatki veljavni in jih z obogatitvijo ni mogoče izboljšati.

* **Podjetja niso obdelana in nespremenjena** : Število profilov podjetij strank, ki niso bili prepoznani. To se običajno zgodi za vhodne podatke, ki so neveljavni ali jih obogatitev ne podpira.

## <a name="next-steps"></a>Naslednji koraki

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
