---
title: Pregled poenotenja podatkov
description: Preglejte korake poenotenja podatkov, ustvarite poenotene profile strank in preglejte rezultate
ms.date: 08/12/2022
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
ms.openlocfilehash: b4d77effc347e40fecde625a1a42a24900456471
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303987"
---
# <a name="review-data-unification"></a>Pregled poenotenja podatkov

Preglejte povzetek sprememb, ustvarite poenoten profil in preglejte rezultate.

## <a name="review-and-create-customer-profiles"></a>Pregledovanje in ustvarjanje profilov strank

Ta zadnji korak v procesu poenotenja prikazuje povzetek korakov v postopku in ponuja možnost, da naredite spremembe, preden ustvarite poenoten profil.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

:::image type="content" source="media/m3_review.png" alt-text="Posnetek zaslona Pregled in ustvarjanje profilov strank.":::

1. Izberite **Uredi** na katerem koli od korakov združevanja podatkov za pregled in morebitne spremembe.

1. Če ste zadovoljni s svojo izbiro, izberite **Ustvarite profile strank** (oz **Ustvarite profile računov** za B-do-B). The **Poenotiti** stran se prikaže med ustvarjanjem poenotenega profila stranke.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Posnetek zaslona strani Unify s ploščicami, ki prikazujejo Čakalno vrsto ali Osveževanje.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Algoritem poenotenja traja nekaj časa, da se dokonča in ne morete spremeniti konfiguracije, dokler ni dokončan.

## <a name="view-the-results-of-data-unification"></a>Oglejte si rezultate poenotenja podatkov

Po združitvi je **podatki** > **Poenotiti** stran prikazuje število poenotenih profilov strank (ali profilov računov za B-to-B). Rezultati vsakega koraka v procesu združevanja so prikazani na vsaki ploščici. Na primer **Izvorna polja** prikazuje število preslikanih atributov (polj) in **Podvojeni zapisi** prikazuje število najdenih podvojenih zapisov.

:::image type="content" source="media/m3_unified.png" alt-text="Posnetek zaslona strani Data Unify po poenotenju podatkov.":::

> [!TIP]
> The **Ujemanje pogojev** ploščica se prikaže le, če je izbranih več entitet.

Priporočamo, da pregledate rezultate, zlasti kakovost vašega [pravila tekme](data-unification-update.md#manage-match-rules) in jih po potrebi izboljšati.

Ko je potrebno, [spremenite nastavitve združevanja](data-unification-update.md) in znova zaženite poenoten profil.

### <a name="verify-output-entities-from-data-unification"></a>Preverite izhodne entitete iz poenotenja podatkov

Pojdi do **podatki** > **Entitete** za preverjanje izhodnih entitet.

Enotna entiteta profila stranke, imenovana *Stranka*, se prikaže v **Profili** razdelek. Prvi uspešen zagon poenotenja ustvari poenoteno *Stranka* entiteta. Vsi naslednji zagoni razširijo to entiteto.

Entitete deduplikacije in konflacije so ustvarjene in prikazane v **Sistem** razdelek. Z imenom se ustvari deduplicirana entiteta za vsako od izvornih entitet **Deduplication_DataSource_Entity**. The **ConflationMatchPairs** entiteta vsebuje informacije o ujemanju med entitetami.

Izhodna entiteta brez podvajanj vsebuje naslednje informacije:
- ID-je/ključe
  - Polji za primarni ključ in nadomestni ID. Polje z nadomestnim ID-jem je sestavljeno iz vseh nadomestnih ID-jev, identificiranih za zapis.
  - Polje Deduplication_GroupId prikazuje skupino ali gručo, identificirano znotraj entitete, ki združuje vse podobne zapise na podlagi določenih polj za odstranjevanje podvajanj. To se uporablja za namene sistemske obdelave. Če niso podana nobena pravila za ročno odstranjevanje podvajanj in veljajo sistemsko določena pravila za odstranjevanje podvajanj, tega polja v izhodni entiteti brez podvajanj morda ne boste našli.
  - Deduplication_WinnerId: to polje vsebuje ID zmagovalnega zapisa iz identificiranih skupin ali gruč. Če je vrednost Deduplication_WinnerId enaka vrednosti primarnega ključa za zapis, to pomeni, da gre za zmagovalni zapis.
- Polja, ki se uporabljajo za določanje pravil za odstranjevanje podvajanj.
- Polji Pravilo in Ocena označujeta, katera od pravil za odpravljanje podvajanj so bila uporabljena, ter rezultat, ki ga vrne algoritem za iskanje ujemanj.

## <a name="next-step"></a>Naslednji korak

- Za B-to-B, po želji izvedite [poenotenje stikov](data-unification-contacts.md).

- Za B-to-C konfigurirajte [aktivnosti](activities.md),[obogatitve](enrichment-hub.md),[Odnosi](relationships.md), oz [ukrepe](measures.md) da pridobite več vpogledov o svojih strankah.

[!INCLUDE[footer-include](includes/footer-banner.md)]
