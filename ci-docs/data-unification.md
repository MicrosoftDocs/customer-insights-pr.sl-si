---
title: Pregled poenotenja podatkov
description: Pojdite skozi postopek poenotenja podatkov s svojimi podatki, da ustvarite en nabor podatkov poenotenih profilov strank.
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
ms.openlocfilehash: 766e688cb80c50a0d620943f87b76eb84a2fb89a
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139538"
---
# <a name="data-unification-overview"></a>Pregled poenotenja podatkov

Po [nastavitvi virov podatkov](data-sources.md) lahko podatke poenotite. Poenotenje podatkov vam omogoča poenotenje nekdaj različnih podatkovnih virov v en sam glavni nabor podatkov, ki zagotavlja enoten pogled na te podatke. Za posamezne potrošnike (B-to-C), kjer so podatki osredotočeni na posameznike, poenotenje zagotavlja enoten pogled na vaše stranke. Za poslovne račune (B-to-B), kjer so podatki osredotočeni na račune, poenotenje zagotavlja enoten pogled na vaše račune.

Podatki so lahko poenoteni na eni ali več entitetah. Poenotenje se izvede v naslednjem vrstnem redu:

1. [Izvorna polja](map-entities.md) (prej imenovan Zemljevid): V koraku izvornih polj izberite entitete in polja, ki jih želite vključiti v postopek poenotenja. Preslikava polj v skupni semantični tip, ki opisuje namen polja.

1. [Podvojeni zapisi](remove-duplicates.md) (prej del ujemanja): V koraku podvojenih zapisov po želji definirajte pravila za odstranjevanje podvojenih zapisov strank iz vsake entitete.

1. [Ujemanje pogojev](match-entities.md) (prej imenovano Ujemanje): V koraku pogojev ujemanja definirajte pravila, ki se ujemajo z zapisi strank med entitetami. Ko je stranka najdena v dveh ali več entitetah, se ustvari en konsolidiran zapis z vsemi stolpci in podatki iz vsake entitete.

1. [Poenotena polja za stranke](merge-entities.md) (prej imenovano Združi): V koraku poenotenih polj strank določite, katera izvorna polja je treba vključiti, izključiti ali združiti v poenoten profil stranke.  

1. [Pregled](review-unification.md) in ustvarite enoten profil.

Po končanem poenotenju podatkov lahko po želji:

- [Nastavite Odnosi med subjekti](relationships.md) za ustvarjanje prefinjenih segmentov.
- [Obogatite svoje podatke](enrichment-hub.md) da pridobite širši nabor vpogledov o svojih strankah.
- [Določite dejavnosti](activities.md) iz nekaterih zaužitih atributov.
- [Zgradite ukrepe](measures.md) za boljše razumevanje vedenja strank in poslovne uspešnosti.

[!INCLUDE [footer-include](includes/footer-banner.md)]
