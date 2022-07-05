---
title: Obogatite profile podjetij z izboljšanimi podatki o podjetju
description: Obogatite in normalizirajte podatke podjetja z Microsoftovimi modeli.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 131ef3d1e123628779609ddec368cfef8f4d607e
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054268"
---
# <a name="enrich-company-profiles-with-enhanced-company-data"></a>Obogatite profile podjetij z izboljšanimi podatki o podjetju

Uporabite Microsoftove modele in zbrane podatke podjetja, da popravite, dopolnite in standardizirate profile vašega podjetja. Uporabili bomo [Format skupnega podatkovnega modela](/common-data-model/schema/core/applicationcommon/account) za boljšo natančnost in vpoglede.

Lahko tudi [izboljšati podatke podjetja o virih podatkov](data-sources-enrichment.md) izboljšati natančnost ujemanja v procesu poenotenja podatkov.

Za javna podjetja v Združenih državah so na voljo informacije, kot so prihodki, borzni podatki, industrija in drugo.  

## <a name="how-we-enhance-company-data"></a>Kako izboljšamo podatke o podjetju

Naš model gre skozi postopek v dveh korakih za izboljšanje profila podjetja. Prvič, normalizira ime podjetja. Na primer *Microsoft Corp* bo popravljeno in standardizirano *Microsoft Corporation*. Poskuša najti ujemanje v Microsoftovih zbranih podatkih podjetja. Če najdemo ujemanje, obogatimo profil podjetja z informacijami iz naših zbranih podatkov o podjetju, vključno z imenom podjetja.

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

Model ne izvaja naslednjega:

- Potrdite identiteto podjetja. Ne preverjamo, ali je vhod obstoječa organizacija ali ali podjetje uporablja izhod kot svoje standardno ime.
- Celovito pokrivajte podjetja po vsem svetu. Microsoftovi zbrani podatki o podjetju imajo globalno pokritost, vendar ponujajo največjo pokritost v Avstraliji, Kanadi, Združenem kraljestvu in Združenih državah.
- Standardizirajte naslove podjetij po vsem svetu. Trenutno podpiramo standardizacijo naslovov v teh državah ali regijah: Avstralija, Kanada, Francija, Nemčija, Italija, Japonska, Združeno kraljestvo in Združene države.
- Zagotavljamo točnost ali svežino podatkov. Ker se poslovne informacije pogosto spreminjajo, ne moremo zagotoviti, da so predloženi izboljšani podatki podjetja vedno točni ali posodobljeni.

## <a name="configure-the-enrichment"></a>Konfiguriranje obogatitve

1. Pojdite v **Podatki** > **Obogatitev** in izberite zavihek **Odkrivanje**.

1. Izberite **Obogatite moje podatke** na **Izboljšani podatki o podjetju** ploščice.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Ploščica za obogatitev v središču za obogatitev za podatke o podjetju.":::

1. Preglejte pregled in nato izberite **Naslednji**.

1. Izberite **Stranka nabor podatkov** in izberite profil ali segment, ki ga želite obogatiti. The *Stranka* entiteta obogati vse vaše profile strank, medtem ko segment obogati le profile strank, ki jih vsebuje ta segment.

1. Izberite vrsto polj iz profilov vašega podjetja, ki jih želite uporabiti za ujemanje z Microsoftovimi zbranimi podatki o podjetju. Ta izbira vpliva na polja za preslikavo, do katerih imate dostop v naslednjem koraku.

1. Izberite **Naprej**.

1. Preslikajte polja vašega podjetja na podatke o podjetju iz Microsofta. Za večjo natančnost ujemanja dodajte več polj.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Korak preslikave podatkov pri konfiguraciji obogatitve podjetja.":::

1. Izberite možnost **Naprej**, da dokončate preslikavo polj.

1. Zagotovite a **ime** za obogatitev in **Izhodna entiteta**.

1. Po pregledu svoje izbire izberite možnost **Shrani obogatitev**.

1. Izberite **teci** za začetek procesa obogatitve ali blizu vrnitve na **Obogatitve** stran.

## <a name="view-enrichment-results"></a>Oglejte si rezultate obogatitve

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

### <a name="overview-card"></a>Pregledna kartica

The **Pregled sprememb strank** ploščica prikazuje podrobnosti o pokritosti obogatitve

- **Podjetja obdelana in spremenjena** : Število uspešno obogatenih profilov podjetij strank.
- **Podjetja obdelana in nespremenjena** : število profilov podjetij strank, ki so bili prepoznani, vendar nespremenjeni. To se običajno zgodi, ko so vhodni podatki veljavni in jih z obogatitvijo ni mogoče izboljšati.
- **Podjetja niso obdelana in nespremenjena** : število profilov podjetij strank, ki niso bili prepoznani. To se običajno zgodi za vhodne podatke, ki so neveljavni ali jih obogatitev ne podpira.

## <a name="next-steps"></a>Naslednji koraki

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
