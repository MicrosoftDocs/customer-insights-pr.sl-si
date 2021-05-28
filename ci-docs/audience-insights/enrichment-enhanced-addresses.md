---
title: Obogatitev izboljšave naslova
description: Z Microsoftovimi modeli obogatite in uravnotežite podatke o naslovih za profile strank.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 07271d491460764f2c738e760e41c3492f2b6de9
ms.sourcegitcommit: 27f9dd837304ef9fc00f055a6e900fbf6fce1429
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/30/2021
ms.locfileid: "5965598"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Obogatitev profilov strank z izboljšanimi naslovi

Naslovi v vaših podatkih so lahko nestrukturirani, nepopolni ali napačni. Uporabite Microsoftove modele za uravnoteženje in obogatitev naslovov v [obliki Common Data Model](/common-data-model/schema/core/applicationcommon/address) za boljšo natančnost in vpoglede.

## <a name="how-we-enhance-addresses"></a>Kako izboljšujemo naslove?

Naš model gre skozi dvostopenjski postopek za izboljšanje naslova. Najprej razčleni naslov, da prepozna njegove komponente, in jih postavi v strukturirano obliko. Nato z umetno inteligenco popravimo, dopolnimo in standardiziramo vrednosti v naslovu.

### <a name="example"></a>Primer

Podatki o naslovih so lahko v nestandardni obliki in vsebujejo napake v črkovanju. Model lahko odpravi te težave in ustvari dosledne naslove v poenotenih profilih strank.

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a>Omejitve

Izboljšani naslovi delujejo samo z vrednostmi, ki že obstajajo v uvoženih podatkih o naslovih. Model ne izvaja naslednjega: 

1. Ne preveri, ali je naslov veljaven.
2. Ne preveri, ali je katera od vrednosti, na primer poštne številke ali imena ulic, veljavna.
3. Ne spremeni vrednosti, ki jih ne prepozna.

Model za izboljšanje naslovov uporablja tehnike, ki temeljijo na strojnem učenju. 100-odstotna natančnost ni zagotovljena, čeprav uporabljamo visok prag zanesljivosti, ko model spremeni vhodno vrednost, tako kot pri katerem koli modelu, ki temelji na strojnem učenju.

## <a name="supported-countries-or-regions"></a>Podprte države ali regije

Trenutno podpiramo obogatitev naslovov v teh državah ali regijah: 

- Avstralija
- Kanada
- Združeno kraljestvo
- Združene države

Naslovi morajo vsebovati vrednost države/regije. Ne obdelujemo naslovov za države ali regije, ki niso podprte, in naslovov, ki nimajo nobene države ali regije.

## <a name="configure-the-enrichment"></a>Konfiguriranje obogatitve

1. Pomaknite se na možnost **Podatki** > **Obogatitev**.

1. Izberite **Obogatitev podatkov** na ploščici **Izboljšani naslovi**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Posnetek zaslona ploščice Izboljšani naslovi.":::

1. Izberite možnost **Nabor podatkov o stranki** in izberite entiteto, ki vsebuje naslove, ki jih želite obogatiti. Izberete lahko entiteto *Stranka* za obogatitev naslovov v vseh vaših profilih strank ali pa entiteto segmenta za obogatitev naslovov samo v profilih strank v tem segmentu.

1. Izberite način oblikovanja naslovov v naboru podatkih. Izberite **Naslov z enim atributom**, če naslovi v vaših podatkih uporabljajo eno samo polje. Izberite **Naslov z več atributi**, če naslovi v vaših podatkih uporabljajo več kot eno podatkovno polje.

   > [!NOTE]
   > Država/regija je obvezna tako v naslovu z enim kot z več atributi. Naslovi, ki ne vsebujejo veljavnih ali podprtih vrednosti držav/regij, ne bodo obogateni

1.  Preslikajte polja z naslovi iz vaše poenotene entitete stranke.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Stran za preslikavo polja z izboljšanim naslovom.":::

1. Izberite možnost **Naprej**, da dokončate preslikavo polj.

1. Navedite ime obogatitve in izhodne entitete.

1. Po pregledu svoje izbire izberite možnost **Shrani obogatitev**.

## <a name="enrichment-results"></a>Rezultati obogatitve

Če želite začeti postopek obogatitve, izberite **Zaženi** v ukazni vrstici. Sistem lahko obogatitev samodejno zažene tudi kot del [načrtovane osvežitve](system.md#schedule-tab). Čas obdelave je odvisen od velikosti podatkov o stranki.

Po končanem postopku obogatitve lahko podatke o na novo obogatenih profilih strank pregledate v možnosti **Moje obogatitve**. Poleg tega boste našli čas zadnje posodobitve in število obogatenih profilov.

Do podrobnega prikaza vsakega obogatenega profila lahko dostopate tako, da izberete **Ogled obogatenih podatkov**.

## <a name="next-steps"></a>Naslednji koraki

Nadgradite svoje obogatene podatke o strankah. Ustvarite [Segmente](segments.md), [Mere](measures.md) in pa [izvozite podatke](export-destinations.md), da svojim strankam zagotovite prilagojeno izkušnjo.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
