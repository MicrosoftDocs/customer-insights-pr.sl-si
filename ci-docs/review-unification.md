---
title: Pregled poenotenja podatkov
description: Preglejte korake poenotenja podatkov, ustvarite poenotene profile strank in preglejte rezultate
ms.date: 06/02/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: adkuppa
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 20728ffaef9bb705410b3ac22d19868ffd5d1243
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139604"
---
# <a name="review-data-unification"></a>Pregled poenotenja podatkov

Ta zadnji korak v procesu poenotenja prikazuje povzetek korakov v postopku in ponuja možnost, da naredite spremembe, preden ustvarite poenoten profil.

:::image type="content" source="media/m3_review.png" alt-text="Posnetek zaslona pregleda in ustvarjanja profilov strank.":::

## <a name="review-the-data-unification-steps"></a>Preglejte korake združevanja podatkov

1. Izberite **Uredi** na katerem koli od korakov združevanja podatkov za pregled in morebitne spremembe.

1. Če ste zadovoljni s svojo izbiro, izberite **Ustvarite profile strank**. The **Poenotiti** stran se prikaže med ustvarjanjem poenotenega profila stranke. Vse ploščice razen **Izvorna polja** pokazati **V čakalni vrsti** oz **Osvežujoče** stanje.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Posnetek zaslona strani Unify s ploščicami, ki prikazujejo Čakalno vrsto ali Osveževanje.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Algoritem poenotenja traja nekaj časa, da se dokonča in ne morete spremeniti konfiguracije, dokler ni dokončan. Ko je postopek poenotenja končan, se pokliče poenotena entiteta profila stranke *Stranka*, je navedena na **Entitete** stran v **Profili** razdelek. Prvi uspešen zagon poenotenja ustvari poenoteno *Stranka* entiteta. Vsi naslednji zagoni razširijo to entiteto.

## <a name="review-the-results-of-data-unification"></a>Preglejte rezultate poenotenja podatkov

Po združitvi je **podatki** > **Poenotiti** stran prikazuje število enotnih profilov strank. Rezultati vsakega koraka v procesu združevanja so prikazani na vsaki ploščici. Na primer **Izvorna polja** prikazuje število preslikanih atributov (polj) in **Podvojeni zapisi** prikazuje število najdenih podvojenih zapisov.

:::image type="content" source="media/m3_unified.png" alt-text="Posnetek zaslona strani Data Unify po poenotenju podatkov.":::

> [!TIP]
> The **Ujemanje pogojev** ploščica se prikaže le, če je izbranih več entitet.

Priporočamo, da pregledate rezultate, zlasti kakovost vašega [pravila tekme](data-unification-update.md#manage-match-rules) in jih po potrebi izboljšati.

Ko je potrebno, [spremenite nastavitve združevanja](data-unification-update.md) in znova zaženite poenoten profil.

## <a name="next-step"></a>Naslednji korak

Konfiguriraj [aktivnosti](activities.md),[obogatitev](enrichment-hub.md),[Odnosi](relationships.md), oz [ukrepe](measures.md) da pridobite več vpogledov o svojih strankah.

[!INCLUDE[footer-include](includes/footer-banner.md)]
