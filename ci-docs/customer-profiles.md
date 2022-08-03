---
title: Ogled profilov strank
description: Oglejte si poenotene podatke o strankah, vključno z uporabo iskanja in filtra
ms.date: 06/08/2022
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
ms.openlocfilehash: 6cdf47e6997f230811dcb0f2cf5542f3a6db2367
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188113"
---
# <a name="view-customer-profiles"></a>Ogled profilov strank

Profili strank so na voljo, ko ste [ustvarite enotno *Stranka* entiteta](data-unification.md). Kombinirani pogled vaših poenotenih profilov strank se prikaže na **Stranke** strani. Stranke so lahko posamezniki ali organizacije.

Pojdi na **Stranke** stran za ogled vaših strank in njihovih profilov. Vsak profil stranke je predstavljen s ploščico. Če želite dobiti več zapisov, uporabite kontrolnike za oštevilčevanje strani. Kartica prikazuje polja iz entitete *Stranka*, kot je opredeljeno v **indeksu iskanja in filtriranja**. Vrstni red polj znotraj vsake kartice izbere sistem.

> [!NOTE]
> Če ne vidite ploščic, ko izberete **Stranke**, mora skrbnik [definirajte vsaj en atribut, ki ga je mogoče iskati](search-filter-index.md) v **Išči in filtriraj indeks**.

:::image type="content" source="media/customers-page-result-tiles-B2C.png" alt-text="Stran strank, ki prikazuje ploščice z rezultati.":::

Izberite katero koli od naslednjih dejanj:
- [Oglejte si podrobnosti o stranki](#view-customer-details)
- [Upravljanje indeksa iskanja in filtriranja](search-filter-index.md) (samo skrbniki)
- [Filtriranje strank](#filter-customers)
- **Razširite kartice** oz **Strni kartice** za razširitev ali strnitev informacij, prikazanih na ploščici stranke
- **Razvrsti po** določen atribut
- [Iskanje strank](#search-for-customers)

  > [!NOTE]
  > Za uporabo iskanja in filtra mora skrbnik konfigurirati atribute, ki jih je mogoče iskati, in definirati polja, ki jih je mogoče filtrirati, z uporabo indeksa za iskanje in filtriranje.

## <a name="search-for-customers"></a>Iskanje strank

Poiščite stranke tako, da vnesete ime ali drug atribut **Iskanje strank**. Atribute, po katerih je mogoče iskati, določi skrbnik in prihajajo iz poenotenega *Stranka* entiteta.

> [!NOTE]
> **Vrvica** je edina vrsta podatkov, ki je vključena v iskanje. Uporabite ga v **Iskanje strank** na strani Stranke za iskanje strank.

## <a name="filter-customers"></a>Filtriranje strank

Filtrirajte stranke po *Stranka* polja entitet. Polja, ki jih je mogoče filtrirati, določi skrbnik.

1. Na **Stranke** stran, izberite **Prikaži filtre**. Prikaže se podokno Filter.

1. Potrdite polja poleg atributov, po katerih želite filtrirati stranke.

1. Z izbiro odstranite vse filtre **Počisti filtre** ali počistite potrditveno polje poleg izbranega atributa.

1. Izberite **Skrij filtre** da zaprete podokno filtra.

1. Če želite rezultate filtra shraniti kot a [segment](segments.md), izberite **Shrani filtre kot segment**.
   1. Vnesite ime segmenta.
   1. Izberite **Shrani** da shranite segment.
   1. Izberite, ali želite zdaj zagnati segment, tako da izberete **Aktiviraj** ali zaženite **Kasneje**.

## <a name="view-customer-details"></a>Oglejte si podrobnosti o stranki

Na **Stranke** izberite ploščico stranke, da si ogledate podrobnosti za izbrano stranko.

:::image type="content" source="media/customers-details-B2C.png" alt-text="Stran s podrobnostmi o stranki.":::

Podrobnosti o stranki vključujejo:

**Ploščica profila stranke** prikazuje različne vrednosti od poenotenih *Stranka* entiteta. Če polje nima vrednosti za izbrani profil stranke, se ne bo prikazalo, razen polja naslova. Ploščica je razdeljena v razdelke:

- Prvi razdelek prikazuje vnaprej določen niz polj, ki mu sledijo vsa polja, ki so del indeksa iskanja in filtriranja. Vsa polja, povezana z naslovom, so združena v eno vrstico, ki je prikazana, tudi če profil ne vsebuje podatkov o naslovu.
- **Kontakti za to stranko** prikaz v okoljih za poslovne račune. Vsak stik je prikazan s svojimi polji. Prazna polja so skrita.
- **Dodatna polja** prikazuje preostala polja izbrane stranke, razen ID-jev.
- **osebne izkaznice** navede vse ID-je pod njihovim ustreznim imenom subjekta. Polja so identificirana kot ID-ji po svoji semantiki.

**Časovnica dejavnosti** prikazuje podatke, če ste konfigurirali [aktivnosti](activities.md). Pogled časovnice vsebuje kronološko razvrščene dejavnosti izbrane stranke, z najnovejšo dejavnostjo na začetku.

**Vpogledi**:

- **Ukrepi** pokaži, če si konfiguriral [meritve lastnosti strank](measures.md). Vključujejo izračunane KPI-je v zvezi z vašimi strankami na ravni posamezne stranke.

- **Potencialni interesi, potencialne blagovne znamke** pokaži, če si konfiguriral a [obogatitev blagovne znamke ali interesne afinitete](enrichment-microsoft.md). Predstavlja možna zanimanja in afinitete za blagovne znamke na podlagi drugih strank, katerih profil je podoben profilu izbranega kupca.

Da se vrnem k **Stranke** stran, izberite **Nazaj k strankam**.

## <a name="next-steps"></a>Naslednji koraki

[Dodajte več virov podatkov](data-sources.md), [obogatite poenotene profile](enrichment-hub.md) ali [ustvarite segmente](segments.md) za delo s poenotenimi profili strank v drugih aplikacijah.

[!INCLUDE [footer-include](includes/footer-banner.md)]
