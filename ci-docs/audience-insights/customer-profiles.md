---
title: Ogled profilov strank
description: Pridobite kombiniran pogled vaših poenotenih podatkov o strankah.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-customer-card
- ci-activities
- ci-activities-wizard
- customerInsights
ms.openlocfilehash: 074d84eff65d52b083fff6c161282d4fafa1af85
ms.sourcegitcommit: 5bd07f3a1288f003704acd576741cf6aedc1ac33
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/31/2022
ms.locfileid: "8523757"
---
# <a name="customer-profiles"></a>Profili strank

Stran **Stranke** prikazuje kombiniran pogled na vaše enotne profile strank. Profili strank so na voljo, ko enkrat [ustvarite enotno entiteto stranke](data-unification.md). Na tej strani lahko iščete stranke in določite indeks za to iskanje.

Stranke so lahko posamezniki ali organizacije. Vsak profil stranke je predstavljen s ploščico. Če želite dobiti več zapisov, uporabite kontrolnike za oštevilčevanje strani. Kartica prikazuje polja iz entitete *Stranka*, kot je opredeljeno v **indeksu iskanja in filtriranja**. Vrstni red polj znotraj vsake kartice izbere sistem.

Izberite ploščico, če si želite ogledati podatke za izbrano stranko na posebni strani, imenovani [Stran s podrobnostmi o stranki](customer-profiles.md#customer-details-page).

> [!div class="mx-imgBorder"] 
> ![Stran strank, ki prikazuje ploščice z rezultati](media/customers-page-result-tiles-B2C.png "Stran strank, ki prikazuje ploščice z rezultati")

> [!NOTE]
> Če ne vidite ploščic, ko pri krmarjenju izberete možnost **Stranke**, mora vaš skrbnik v **indeksu iskanja in filtriranja** [določiti vsaj en atribut, ki ga je mogoče iskati](search-filter-index.md).

## <a name="search-for-customers"></a>Iskanje strank

Stranke poiščete tako, da v polje za iskanje vnesete ime ali kakšen drug atribut. Iskanje deluje samo v entiteti _Stranka_, ustvarjeni med postopkom poenotenja podatkov.

Kot skrbnik lahko konfigurirate atribute, omogočene za iskanje, na strani **Kazalo za iskanje in filtriranje**. Za več informacij odprite razdelek [Upravljanje indeksa iskanja in filtriranja](search-filter-index.md).

## <a name="filter-customers"></a>Filtriranje strank

Stranke lahko filtrirate po polju entitete _Stranka_. Podobno kot pri iskanju mora vaš skrbnik na strani **Kazalo za iskanje in filtriranje** najprej omogočiti filtriranje za polja.

1. Na strani **Stranke** izberite možnost **Pokaži filtre**.

1. Potrdite polja poleg atributov, po katerih želite filtrirati stranke.

1. Odstranite filtre tako, da izberete **Počisti filtre** na strani **Stranke**.

## <a name="customer-details-page"></a>Stran s podrobnostmi o stranki

Izberite katero koli ploščico stranke, da odprete **stran s podrobnostmi o stranki**. Ta pogled vsebuje poenotene podatke za izbrano stranko. Podatki o strankah vključujejo naslednjo vsebino:

**Ploščica profila stranke**: ta ploščica prikazuje različne vrednosti poenotene entitete _Stranka_. Če polje nima vrednosti za izbrani profil stranke, se ploščica ne prikaže. Ploščica je razdeljena v razdelke:  
  - Prvi razdelek prikazuje vnaprej določen niz polj, ki mu sledijo vsa polja, ki so del indeksa iskanja in filtriranja. Vsa polja, povezana z naslovom, so združena v eno vrstico, če profil vsebuje ta polja. 
  - **Stiki za to stranko**: v okoljih za poslovne račune bodo v drugem razdelku prikazani vsi povezani stiki za to stranko. Vsak stik je prikazan s svojimi polji. Prazna polja so skrita.
  - **Dodatna polja**: prikaže preostala polja izbrane stranke, razen ID-jev. 
  - **ID-ji**: navede vse ID-je pod ustreznim imenom entitete. Polja so po semantiki identificirana kot ID-ji, ki jih kot take razvrščajo.

**Časovnica dejavnosti**: prikaže podatke, če ste konfigurirali dejavnosti. Pogled časovnice vsebuje kronološko razvrščene dejavnosti izbrane stranke, z najnovejšo dejavnostjo na začetku. Za več informacij odprite razdelek [Dejavnosti strank](activities.md).

**Vpogledi**:  
  - **Merila**: prikaže, ali ste konfigurirali enega ali več meril za atribute strank. Vključujejo izračunane KPI-je v zvezi z vašimi strankami na ravni posamezne stranke. Za več informacij odprite razdelek [Določanje in upravljanje meril](measures.md).

  - **Možni interesi, možne blagovne znamke**: prikaže, ali ste konfigurirali obogatitev afinitete za blagovno znamko ali zanimanje. Predstavlja možna zanimanja in afinitete za blagovne znamke na podlagi drugih strank, katerih profil je podoben profilu izbranega kupca. Za več informacij odprite razdelek [Obogatitev profilov strank z afinitetami za blagovne znamke in zanimanja](enrichment-microsoft.md).

Če se želite vrniti na stran za iskanje strank, izberite možnost **Nazaj na stranke**.

## <a name="next-steps"></a>Naslednji koraki

[Dodajte več virov podatkov](data-sources.md), [obogatite poenotene profile](enrichment-hub.md) ali [ustvarite segmente](segments.md) za delo s poenotenimi profili strank v drugih aplikacijah.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
