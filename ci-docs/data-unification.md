---
title: Pregled poenotenja podatkov
description: Pojdite skozi postopek poenotenja podatkov s svojimi podatki, da ustvarite en sam nabor enotnih profilov strank.
ms.date: 05/10/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: v-wendysmith
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: 0dbc3b2c75365e94758a1b6330e8cb557e6bd768
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082228"
---
# <a name="data-unification-overview"></a>Pregled poenotenja podatkov

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Po [nastavitvi virov podatkov](data-sources.md) lahko podatke poenotite. Združevanje podatkov vam omogoča poenotenje nekoč ločenih virov podatkov v en sam glavni nabor podatkov, ki zagotavlja enoten pogled na te podatke. Za posamezne potrošnike (B-to-C), kjer so podatki osredotočeni na posameznike, poenotenje zagotavlja enoten pogled na vaše stranke. Za poslovne račune (B-to-B), kjer so podatki osredotočeni na račune, poenotenje zagotavlja enoten pogled na vaše račune.

Podatke je mogoče poenotiti na eni sami ali več entitetah. Združitev se izvede v naslednjem vrstnem redu:

1. [Izvorna polja](map-entities.md) (prej imenovan Zemljevid): v koraku izvornih polj izberite entitete in polja, ki jih želite vključiti v postopek poenotenja. Preslikajte polja v običajen semantični tip, ki opisuje namen polja.

1. [Podvojeni zapisi](remove-duplicates.md) (prej del Match): v koraku podvojenih zapisov po želji določite pravila za odstranitev podvojenih zapisov strank iz vsake entitete.

1. [Ujemanje pogojev](match-entities.md) (prej imenovano Ujemanje): v koraku pogojev ujemanja definirajte pravila, ki se ujemajo z zapisi strank med entitetami. Ko stranko najdemo v dveh ali več entitetah, se ustvari en konsolidirani zapis z vsemi stolpci in podatki iz vsake entitete.

1. [Poenotena polja strank](merge-entities.md) (prej imenovano Spajanje): V koraku poenotenih polj strank določite, katera izvorna polja naj bodo vključena, izključena ali združena v enoten profil stranke.  

1. [Pregled](review-unification.md) in ustvarite enoten profil.

Po zaključku poenotenja podatkov lahko po želji:

- [Nastavite Odnosi med entitetami](relationships.md) ustvariti prefinjene segmente.
- [Obogatite svoje podatke](enrichment-hub.md) da pridobite širši nabor vpogledov o svojih strankah.
- [Določite dejavnosti](activities.md) iz nekaterih zaužitih atributov.
- [Zgradite ukrepe](measures.md) za boljše razumevanje vedenja strank in poslovne uspešnosti.

[!INCLUDE [footer-include](includes/footer-banner.md)]
