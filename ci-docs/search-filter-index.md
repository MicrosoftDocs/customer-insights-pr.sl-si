---
title: Upravljajte indeks iskanja in filtriranja za profile strank
description: Hitro poiščite informacije o poenotenih profilih strank in filtrirajte za določene atribute.
ms.date: 07/22/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: dfbfcbff3ffb3e4483252377e591229631d38556
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/22/2022
ms.locfileid: "9187929"
---
# <a name="manage-the-search--filter-index-for-customer-profiles"></a>Upravljajte indeks iskanja in filtriranja za profile strank

Rezultat poenotenja vaših podatkov o strankah je a *Stranka* subjekt, ki zagotavlja enoten pogled na vašo celotno bazo strank. Za uporabnike hitro [iskanje informacij o določeni stranki ali skupini strank](customer-profiles.md), mora skrbnik konfigurirati **Iskanje** in **Filter** zmogljivosti za **Stranke** strani.

   :::image type="content" source="media/search-filter.png" alt-text="Filter za iskanje":::

## <a name="define-searchable-attributes-and-indexed-fields"></a>Določite atribute, ki jih je mogoče iskati, in indeksirana polja

Če kot skrbnik prvič definirate atribute, ki jih je mogoče iskati, najprej definirajte indeksirana polja. Predlagamo, da izberete vse atribute, po katerih lahko uporabniki iščejo in filtrirajo stranke na strani **Stranke**. Samo atributi, ki obstajajo v *Stranka* entiteto, ustvarjeno med postopkom poenotenja podatkov, je mogoče določiti.

1. Pojdi do **Stranke** in izberite **Išči in filtriraj indeks**.

1. Izberite **+ Dodaj**.

1. Na seznamu izberite atribute, ki jih želite dodati kot indeksirana polja, in kliknite **Prijavite se**.

1. Če želite dodati več atributov, izberite **Dodaj**. Če želite odstraniti izbrani atribut, izberite atribut in nato **Izbriši**.

   :::image type="content" source="media/search-filter-index.png" alt-text="Iskanje in filtriranje indeksne strani.":::

1. Izberite **Teči** ko ste pripravljeni uporabiti nastavitve iskanja in filtra. Ko so spremembe obdelane, si jih oglejte v [kartice strank na strani za stranke](customer-profiles.md).

## <a name="define-filtering-options-for-a-given-attribute"></a>Določite možnosti filtriranja za dani atribut

Nastavite polja, ki se lahko uporabljajo za filtriranje strank na **Stranke** strani.

1. Pojdi do **Stranke** in izberite **Išči in filtriraj indeks**.

1. Izberite atribut in **Dodaj filter**. Določite število rezultatov in vrstni red, v katerem bodo organizirani. Odvisno od vrste podatkov atributa se prikaže eno od naslednjih podoken.

   - Atributi vrste nizov: Določite število želenih rezultatov na **Filter nizov** podokno in pravilnik o vrstnem redu, po katerem bodo organizirani.

   - Atributi številskega tipa: Določite intervale, vključene v **Filter številk** podokno in pravilnik o vrstnem redu, po katerem bodo organizirani.

   - Atributi tipa datuma: Določite intervale, vključene v **Datumski filter** podokno in pravilnik o vrstnem redu, po katerem bodo organizirani.

1. Izberite **V redu**. Ponovite za vse atribute, po katerih želite filtrirati.

1. Izberite **Teči** ko ste pripravljeni uporabiti nastavitve iskanja in filtra. Ko so spremembe obdelane, si jih oglejte v [kartice strank na strani za stranke](customer-profiles.md).

## <a name="view-indexed-customer-fields"></a>Oglejte si indeksirana polja strank

The **Išči in filtriraj indeks** stran prikaže naslednje informacije:

- **Ime** : Predstavlja ime atributa, kot je prikazano v *Stranka* entiteta.
- **Vrsta podatkov**: določa, ali je vrsta podatkov niz, številka ali datum.
- **Vključeno v iskanje**: določa, ali je ta atribut mogoče uporabiti za iskanje strank na strani **Stranke** s poljem **Iskanje**.
- **Dodaj filter**: kontrolnik za določanje, kako je mogoče ta atribut uporabljati za filtriranje na strani **Stranke**.

## <a name="next-steps"></a>Naslednji koraki

Preglejte [stran poenotenih profilov](customer-profiles.md), da poiščete profile, ali uporabite indeksirana polja, da si ogledate podmnožice vseh poenotenih profilov.

[!INCLUDE [footer-include](includes/footer-banner.md)]
