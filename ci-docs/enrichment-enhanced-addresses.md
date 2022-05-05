---
title: Obogatitev naslova (vsebuje video)
description: Z Microsoftovimi modeli obogatite in uravnotežite podatke o naslovih za profile strank.
ms.date: 01/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
searchScope:
- ci-data-sources-enrichment
- ci-data-sources-enrichment-details
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: b4fef3b5e30e1cac4e5cb4401498f2f0981a409e
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643005"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Obogatitev profilov strank z izboljšanimi naslovi

Naslovi v vaših podatkih so lahko nestrukturirani, nepopolni ali napačni. Uporabite Microsoftove modele za uravnoteženje in obogatitev naslovov v [obliki Common Data Model](/common-data-model/schema/core/applicationcommon/address) za boljšo natančnost in vpoglede.

Lahko tudi [obogatite naslove na virih podatkov](data-sources-enrichment.md) izboljšati natančnost ujemanja v procesu poenotenja podatkov. 

## <a name="how-we-enhance-addresses"></a>Kako izboljšujemo naslove?

Naš model gre skozi dvostopenjski postopek za izboljšanje naslova. Najprej razčleni naslov, da prepozna njegove komponente, in jih postavi v strukturirano obliko. Nato s pomočjo umetne inteligence popravimo, dopolnimo in standardiziramo vrednosti v naslovu.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWNewo]

### <a name="example"></a>Primer

Podatki o naslovu so lahko v nestandardni obliki in lahko vsebujejo napake v črkovanju. Model lahko odpravi te težave in ustvari dosledne naslove v poenotenih profilih strank.

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

Model za izboljšanje naslovov uporablja tehnike, ki temeljijo na strojnem učenju. Čeprav je naša stopnja zanesljivosti, ko gre spremembo vhodne vrednosti modela, visoka, 100-odstotna natančnost – tako kot pri vseh modelih, ki temeljijo na strojnem učenju – ni zagotovljena.

## <a name="supported-countries-or-regions"></a>Podprte države ali regije

Trenutno podpiramo obogatitev naslovov v teh državah ali regijah: 

- Avstralija
- Kanada
- Francija
- Nemčija
- Italija
- Japonska
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
   > Navedba države/regije je obvezna tako pri naslovih z enim atributom kot tudi pri tistih z več atributi. Naslovi brez veljavnih ali podprtih vrednosti države/regije ne bodo obogateni.

1.  Preslikajte polja z naslovi iz vaše poenotene entitete stranke.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Stran za preslikavo polja z izboljšanim naslovom.":::

1. Izberite možnost **Naprej**, da dokončate preslikavo polj.

1. Navedite ime obogatitve in izhodne entitete.

1. Po pregledu svoje izbire izberite možnost **Shrani obogatitev**.

## <a name="enrichment-results"></a>Rezultati obogatitve

Če želite začeti postopek obogatitve, izberite **Zaženi** v ukazni vrstici. Sistem lahko obogatitev samodejno zažene tudi kot del [načrtovane osvežitve](system.md#schedule-tab). Čas obdelave je odvisen od velikosti podatkov o stranki.

Po končanem postopku obogatitve lahko podatke o na novo obogatenih profilih strank pregledate v možnosti **Moje obogatitve**. Poleg tega boste našli čas zadnje posodobitve in število obogatenih profilov.

Vzorec obogatenih podatkov si lahko ogledate v **Obogaten predogled strank** ploščice. Izberite **Poglej več** in izberite **Podatki** zavihek za dostop do podrobnega pogleda vsakega obogatenega profila.

### <a name="overview-card"></a>Pregledna kartica

Pregledna kartica prikazuje podrobnosti o kritju obogatitve. 

* **Naslovi obdelani in spremenjeni** : Število profilov strank z naslovi, ki so bili uspešno obogateni.

* **Naslovi so obdelani in niso spremenjeni** : število profilov strank z naslovi, ki so bili prepoznani, vendar nespremenjeni. Običajno se zgodi, ko so vhodni podatki veljavni in jih z obogatitvijo ni mogoče izboljšati.

* **Naslovi niso obdelani in nespremenjeni** : Število profilov z naslovi, ki niso bili prepoznani. Običajno za vhodne podatke, ki so neveljavni ali niso podprti z obogatitvijo.

## <a name="next-steps"></a>Naslednji koraki

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]