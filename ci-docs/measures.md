---
title: Pregled ukrepov
description: Naučite se, kako meritve pomagajo analizirati in odražati uspešnost vašega podjetja.
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
ms.openlocfilehash: 99368a7ab2e8d7b3e53c04fbf25bb23bd2e550a9
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245393"
---
# <a name="measures-overview"></a>Pregled ukrepov

Ukrepi vam pomagajo bolje razumeti vedenje strank in poslovno uspešnost. Upoštevajo relevantne vrednosti iz [poenotenih profilov](data-unification.md). Da bi podjetje razumelo zgodovino nakupov posamezne stranke, ga zanima, *koliko je določena stranka porabila*, za lažje razumevanje svojih svojega skupnega dohodka pa lahko izmeri *celotni obseg svoje prodaje*.

Ustvarite ukrepe za načrtovanje poslovnih dejavnosti s poizvedovanjem po podatkih strank in pridobivanjem vpogledov. Na primer, ustvarite mero *skupna poraba na stranko* in *skupni donos na stranko* za pomoč pri prepoznavanju skupine strank z visoko porabo, a visokim donosom. Potem, [ustvarite segment](segments.md) na podlagi teh ukrepov za spodbujanje naslednjih najboljših dejanj.

## <a name="create-a-measure"></a>Ustvarjanje mere

Izberite, kako ustvarite mero na podlagi cilja občinstvo.

# <a name="individual-consumers-b-to-c"></a>[Posamezni potrošniki (prodaja strankam)](#tab/b2c)

- Od začetka z graditeljem mer: [Zgradite svojega](measure-builder.md).
- Od pogosto uporabljenih ukrepov: [Uporabite vnaprej določene predloge](measure-templates.md).

# <a name="business-accounts-b-to-b"></a>[Poslovni računi (podjetja podjetjem)](#tab/b2b)

Od začetka z graditeljem mer: [Zgradite svojega](measure-builder.md).

---

## <a name="manage-existing-measures"></a>Upravljajte obstoječe ukrepe

Pojdi na **Ukrepi** stran za ogled mer, ki ste jih ustvarili, njihov status, vrsto mere in čas zadnje osvežitve podatkov. Seznam ukrepov lahko razvrstite po katerem koli stolpcu ali uporabite iskalno polje, da poiščete ukrep, ki ga želite upravljati.

Izberite zraven mere, da si ogledate razpoložljiva dejanja. Izberite ime mere za predogled izhoda in prenos datoteke CSV.

:::image type="content" source="media/measures-actions.png" alt-text="Dejanja za upravljanje posameznih mer."lightbox="media/measures-actions.png":::

- **Uredi** ukrep za spremembo njegovih lastnosti.
- **Osveži** ukrep za vključitev najnovejših podatkov.
- Mero lahko preimenujete prek možnosti **Preimenuj**.
- **Aktiviraj** oz **Deaktiviraj** ukrep. Neaktivni ukrepi se ne bodo osvežili med a [načrtovana osvežitev](schedule-refresh.md) in imeti **Stanje** naveden kot **Preskočeno**, kar pomeni, da osvežitev sploh ni bila izvedena.
- **Oznaka** do [upravljanje oznak](work-with-tags-columns.md#manage-tags) za mero.
- Za brisanje mere je na voljo **Izbriši**.
- **Stolpci** do [prilagodite stolpce](work-with-tags-columns.md#customize-columns) ta zaslon.
- **Filter** do [filter po oznakah](work-with-tags-columns.md#filter-on-tags).
- **Ime iskanja** za iskanje po imenu mere.

## <a name="refresh-measures"></a>Osveži ukrepe

Mere je mogoče osveževati po samodejnem urniku ali ročno na zahtevo. Če želite ročno osvežiti eno ali več mer, jih izberite in izberite **Osveži**. Za [načrtujte samodejno osveževanje](schedule-refresh.md), Pojdi do **skrbnik** > **Sistem** > **Urnik**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
