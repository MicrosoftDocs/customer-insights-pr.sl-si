---
title: Pregled poenotenja podatkov
description: Preglejte korake združevanja podatkov, ustvarite enotne profile strank in preglejte rezultate
ms.date: 05/04/2022
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
ms.openlocfilehash: 4c709dfb55bf079dd2fe99e41adb4c77c2bece4b
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 05/11/2022
ms.locfileid: "8743029"
---
# <a name="review-data-unification"></a>Pregled poenotenja podatkov

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Ta zadnji korak v procesu poenotenja prikazuje povzetek korakov v procesu in ponuja možnost za spremembe, preden ustvarite enoten profil.

:::image type="content" source="media/m3_review.png" alt-text="Posnetek zaslona Pregled in ustvarjanje profilov strank.":::

## <a name="review-the-data-unification-steps"></a>Preglejte korake združevanja podatkov

1. Izberite **Uredi** na katerem koli od korakov združevanja podatkov, da pregledate in naredite kakršne koli spremembe.

1. Če ste zadovoljni z izbiro, izberite **Ustvarite profile strank**. The **Poenoti** med ustvarjanjem enotnega profila stranke se prikaže stran. Algoritem poenotenja traja nekaj časa, da se dokonča in konfiguracije ne morete spremeniti, dokler se ne zaključi.

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]

Ko se postopek združevanja zaključi, se pokliče enota enotnega profila stranke *Stranka*, je naveden na **Entitete** stran v **Profili** oddelek. Prvi uspešen združitveni zagon ustvari poenoteno *Stranka* entiteta. Vsi naslednji zagoni razširijo to entiteto.

## <a name="review-the-results-of-data-unification"></a>Preglejte rezultate poenotenja podatkov

Po združitvi, **Podatki** > **Poenoti** stran prikazuje število enotnih profilov strank. Rezultati vsakega koraka v procesu poenotenja so prikazani na vsaki ploščici. Na primer **Izvorna polja** prikazuje število preslikanih atributov (polj) in **Podvojeni zapisi** prikazuje število najdenih podvojenih zapisov.

:::image type="content" source="media/m3_unified.png" alt-text="Posnetek zaslona strani Data Unify po poenotenju podatkov.":::

> [!TIP]
> The **Ujemanje pogojev** ploščica se prikaže samo, če je bilo izbranih več entitet.

Priporočamo, da pregledate rezultate, zlasti kakovost vašega [pravila tekme](data-unification-update.md#manage-match-rules) in jih po potrebi izboljšajte.

Ko je potrebno, [spremenite nastavitve združevanja](data-unification-update.md) in znova zaženite enotni profil.

## <a name="next-step"></a>Naslednji korak

Konfiguriraj [dejavnosti](activities.md),[obogatitev](enrichment-hub.md),[Odnosi](relationships.md), oz [ukrepe](measures.md) pridobiti več vpogledov v svoje stranke.

[!INCLUDE[footer-include](includes/footer-banner.md)]
