---
title: Razumeti in upravljati ukrepe
description: Naučite se, kako ukrepi pomagajo analizirati in odražati uspešnost vašega podjetja.
ms.date: 03/24/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: 84a3a10a2517258c1f895800882b9c67391ec3de
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643303"
---
# <a name="measures-overview"></a>Pregled ukrepov

Ukrepi vam pomagajo bolje razumeti vedenje strank in poslovno uspešnost. Upoštevajo relevantne vrednosti iz [poenotenih profilov](data-unification.md). Da bi podjetje razumelo zgodovino nakupov posamezne stranke, ga zanima, *koliko je določena stranka porabila*, za lažje razumevanje svojih svojega skupnega dohodka pa lahko izmeri *celotni obseg svoje prodaje*.  

Ukrepi so ustvarjeni [z uporabo graditelja meril](measure-builder.md), platforma za poizvedbe podatkov z različnimi operaterji in preprostimi možnostmi preslikave. Omogoča filtriranje podatkov, združevanje rezultatov v skupine, zaznavanje [poti odnosov entitet](relationships.md) in predogled rezultatov. Ti lahko [uporabite vnaprej določene predloge](measure-templates.md) za učinkovito konfiguracijo pogosto uporabljenih ukrepov.

Uporabite graditelja mer za načrtovanje poslovnih dejavnosti s poizvedbami po podatkih o strankah in pridobivanjem vpogledov. Ustvarjanje na primer mer za *skupno porabo na stranko* in *skupni donos na stranko* pomaga prepoznati skupino strank z visoko porabo, ki pa so hkrati zelo donosne. Ti lahko [ustvariti segment](segments.md) na podlagi teh ukrepov za spodbujanje naslednjih najboljših ukrepov.

## <a name="manage-your-measures"></a>Upravljajte svoje mere

Seznam ukrepov najdete na strani **Ukrepi**.

Našli boste podatke o vrsti mere, ustvarjalcu, datumu ustvarjanja, statusu in stanju. Ko na seznamu izberete mero, si lahko vnaprej ogledate izhod in prenesete datoteko CSV.

:::image type="content" source="media/measures-actions.png" alt-text="Dejanja za upravljanje posameznih mer."lightbox="media/measures-actions.png":::

Ko izberete ukrep, so na voljo naslednja dejanja:

- Izberete lahko možnost **Uredi** in uredite konfiguracijo mere.
- **Podvojeno** ukrep. Takoj lahko uredite njegove lastnosti ali preprosto shranite dvojnik.
- **Osveži** mero na podlagi najnovejših podatkov. Če želite hkrati osvežiti vse svoje ukrepe, izberite vse mere in nato **Osveži**.
- Mero lahko preimenujete prek možnosti **Preimenuj**.
- **Aktiviraj** ali **deaktiviraj**. Nedejavne mere se med [načrtovano osvežitvijo](system.md#schedule-tab) ne bodo osvežile.
- **Oznaka** do [upravljati oznake](work-with-tags-columns.md#manage-tags) za segment.
- Za brisanje mere je na voljo **Izbriši**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-step"></a>Naslednji korak

Za ustvarjanje [segmenta stranke](segments.md) lahko uporabite obstoječe mere.

[!INCLUDE [footer-include](includes/footer-banner.md)]
