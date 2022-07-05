---
title: Obogatite profile strank z izboljšanimi naslovi (vsebuje video)
description: Z Microsoftovimi modeli obogatite in uravnotežite podatke o naslovih za profile strank.
ms.date: 06/10/2022
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
ms.openlocfilehash: 01f1c917c75e932cc69f4c7251e57524fc859dce
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082081"
---
# <a name="enrich-customer-profiles-with-enhanced-addresses"></a>Obogatite profile strank z izboljšanimi naslovi

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

Izboljšani naslovi delujejo samo z vrednostmi, ki že obstajajo v vaših prevzetih naslovnih podatkih. Model ne izvaja naslednjega:

1. Ne preveri, ali je naslov veljaven.
2. Ne preveri, ali je katera od vrednosti, na primer poštne številke ali imena ulic, veljavna.
3. Ne spremeni vrednosti, ki jih ne prepozna.

Model za izboljšanje naslovov uporablja tehnike, ki temeljijo na strojnem učenju. Kot pri vsakem modelu, ki temelji na strojnem učenju, 100-odstotna natančnost ni zagotovljena.

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

## <a name="configure-the-enrichment"></a>Konfiguriranje obogatitve

1. Pojdite v **Podatki** > **Obogatitev** in izberite zavihek **Odkrivanje**.

1. Izberite **Obogatitev podatkov** na ploščici **Izboljšani naslovi**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Posnetek zaslona ploščice Izboljšani naslovi.":::

1. Preglejte pregled in nato izberite **Naslednji**.

1. Izberite **Stranka nabor podatkov** in izberite profil ali segment, ki ga želite obogatiti. The *Stranka* entiteta obogati vse vaše profile strank, medtem ko segment obogati le profile strank, ki jih vsebuje ta segment.

1. Izberite način oblikovanja naslovov v naboru podatkih. Izberite **Naslov z enim atributom**, če naslovi v vaših podatkih uporabljajo eno samo polje. Izberite **Naslov z več atributi**, če naslovi v vaših podatkih uporabljajo več kot eno podatkovno polje.

1. Izberite **Naslednji** in preslikajte naslovna polja iz vaše enotne stranke.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Stran za preslikavo polja z izboljšanim naslovom.":::

   > [!NOTE]
   > Navedba države/regije je obvezna tako pri naslovih z enim atributom kot tudi pri tistih z več atributi. Naslovi brez veljavnih ali podprtih vrednosti države/regije ne bodo obogateni.

1. Izberite možnost **Naprej**, da dokončate preslikavo polj.

1. Zagotovite a **ime** za obogatitev in **Izhodna entiteta**.

1. Po pregledu svoje izbire izberite možnost **Shrani obogatitev**.

## <a name="view-enrichment-results"></a>Oglejte si rezultate obogatitve

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

The **Število strank, obogatenih po področjih** zagotavlja pregled pokritosti vsakega obogatenega polja.

### <a name="overview-card"></a>Pregledna kartica

The **Pregled sprememb strank** kartica prikazuje podrobnosti o kritju obogatitve:

- **Naslovi obdelani in spremenjeni** : Število profilov strank z naslovi, ki so bili uspešno obogateni.
- **Naslovi so obdelani in niso spremenjeni** : Število profilov strank z naslovi, ki so bili prepoznani, vendar nespremenjeni. Običajno se zgodi, ko so vhodni podatki veljavni in jih z obogatitvijo ni mogoče izboljšati.
- **Naslovi niso obdelani in niso spremenjeni** : število profilov z naslovi, ki niso bili prepoznani. Običajno za vhodne podatke, ki so neveljavni ali niso podprti z obogatitvijo.

## <a name="next-steps"></a>Naslednji koraki

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
