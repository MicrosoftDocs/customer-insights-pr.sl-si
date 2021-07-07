---
title: Ogled profilov strank
description: Pridobite kombiniran pogled vaših poenotenih podatkov o strankah.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: c9adb4d7db74573d0512ae7a68a0e7ab51c994a0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304624"
---
# <a name="customer-profiles"></a>Profili strank

Stran **Stranke** prikazuje kombiniran pogled vaših strank na podlagi podatkov o profilu, zbranih iz [vseh virov podatkov](data-sources.md). Profili strank so na voljo, ko [ustvarite poenoteno entiteto stranke](data-unification.md). Za podrobnejše prikaze strank dokončajte postopek poenotenja podatkov. Stran omogoča tudi iskanje strank.

Stranke so lahko posamezniki ali organizacije (predogled). Ploščica predstavlja vsak posamezni profil stranke ali organizacije. Izberite ploščico in si oglejte dodatne informacije o določeni stranki ali organizaciji. Za prikaz dodatnih zapisov uporabite kontrolnik za oštevilčevanje strani na dnu strani.

> [!div class="mx-imgBorder"] 
> ![Profili strank pri prodaji strankam](media/profiles-customers.png "Profili strank pri prodaji strankam")

Organizacije (predogled)
> [!div class="mx-imgBorder"] 
> ![Profili strank pri prodaji podjetjem](media/profile-customers-b2b.png "Profili strank pri prodaji podjetjem")

> [!NOTE]
> Če pri krmarjenju po izbiri možnosti **Stranke** ne vidite ploščic, mora vaš skrbnik [določiti vsaj en atribut, ki je omogočen za iskanje](search-filter-index.md), v možnosti **Kazalo za iskanje in filtre**.

## <a name="search-for-customers"></a>Iskanje strank

Stranke poiščete tako, da v polje za iskanje vnesete ime ali kakšen drug atribut. Iskanje deluje samo v entiteti »Profil stranke«, ki je bila ustvarjena med postopkom poenotenja podatkov.

Kot skrbnik lahko konfigurirate atribute, omogočene za iskanje, na strani **Kazalo za iskanje in filtriranje**. Za več informacij glejte [Upravljanje kazala za iskanje in filtriranje](search-filter-index.md).

## <a name="filter-customers"></a>Filtriranje strank

Stranke lahko filtrirate po poljih entitete »Profil stranke«. Podobno kot pri iskanju mora vaš skrbnik na strani **Kazalo za iskanje in filtriranje** najprej omogočiti filtriranje za polja.

1. Izberite **Filter** na strani **Stranke**.

2. Potrdite polja poleg atributov, po katerih želite filtrirati stranke.

   > [!div class="mx-imgBorder"] 
   > ![Profili strank](media/profiles-customers3.png "Profili strank")

3. Odstranite filtre tako, da izberete **Počisti filtre** na strani **Stranke**.

##  <a name="customer-details-page"></a>Stran s podrobnostmi o stranki

Izberite katero koli ploščico stranke, da odprete **stran s podrobnostmi o stranki**. Ta pogled vsebuje poenotene podatke za izbrano stranko.

Podrobnosti o stranki vključujejo:

-   **Ploščica profila stranke:** ploščica prikazuje različne vrednosti iz poenotene entitete profila stranke. Te podrobnosti lahko vključujejo e-poštni naslov, ime, mesto itd. 

-   **Potencialna zanimanja, potencialne blagovne znamke**: pokaže vam, ali ste konfigurirali obogatitev proizvajalca. Predstavlja potencialne interese in priljubljene blagovne znamke za stranke s podobnim profilom kot ta stranka. Za več informacij glejte [Obogatitev profilov strank s priljubljenimi blagovnimi znamkami in zanimanji](enrichment-microsoft.md).

-   **Mere:** pokažejo vam, ali ste konfigurirali eno mero ali več mer določene vrste: mere atributov stranke. Vključujejo izračunane KPI-je v zvezi z vašimi strankami na ravni posamezne stranke. Za več informacij glejte [Določanje in upravljanje mer](measures.md).

-   **Časovnica dejavnosti:** pokaže, ali ste konfigurirali dejavnosti. Pogled časovnice vsebuje kronološko razvrščene dejavnosti te stranke, pri čemer se začne z najnovejšo dejavnostjo. Za več informacij glejte [Dejavnosti stranke](activities.md).

Izberite **Nazaj k strankam** za vrnitev na stran za iskanje strank.

## <a name="next-steps"></a>Naslednji koraki

[Dodajte več virov podatkov](data-sources.md) ali [ustvarite segmente strank](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
