---
title: Ustvarite poenoten pogled za svoje stranke
description: Pojdite skozi postopek poenotenja podatkov s svojimi podatki, da ustvarite en sam glavni nabor podatkov o računih ali profilih strank.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: c2a81776eab147c4b5209a6fbf89c0f4c9853d1d
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304447"
---
# <a name="data-unification-overview"></a>Pregled poenotenja podatkov

Po [nastavitvi virov podatkov](data-sources.md) lahko podatke poenotite. Poenotenje podatkov vam omogoča poenotenje nekoč različnih podatkovnih virov v en sam glavni nabor podatkov, ki zagotavlja poenoten pogled na te podatke.

Za posamezne potrošnike (B-to-C), kjer so podatki osredotočeni na posameznike, poenotenje zagotavlja enoten pogled na vaše stranke. Za poslovne račune (B-to-B), kjer so podatki osredotočeni na račune, poenotenje zagotavlja enoten pogled na vaše račune. [Združevanje stikov (predogled)](data-unification-contacts.md) omogoča, da so stiki za te račune ločeno združeni in povezani z računi.

Podatki so lahko poenoteni na eni ali več entitetah.

# <a name="individual-consumers-b-to-c"></a>[Posamezni potrošniki (prodaja strankam)](#tab/b2c)

Postopek poenotenja preslika podatke o strankah iz vaših podatkovnih virov, odstrani dvojnike, poveže podatke med entitetami in ustvari poenoten profil. Poenotenje se izvede v naslednjem vrstnem redu:

1. [Izvorna polja](map-entities.md) (prej imenovan Zemljevid): V koraku izvornih polj izberite entitete in polja, ki jih želite vključiti v postopek poenotenja. Preslikava polj v skupni semantični tip, ki opisuje namen polja.

1. [Podvojeni zapisi](remove-duplicates.md) (prej del ujemanja): V koraku podvojenih zapisov po želji definirajte pravila za odstranjevanje podvojenih zapisov strank iz vsake entitete.

1. [Ujemanje pogojev](match-entities.md) (prej imenovano Ujemanje): V koraku pogojev ujemanja definirajte pravila, ki se ujemajo z zapisi strank med entitetami. Ko je stranka najdena v dveh ali več entitetah, se ustvari en konsolidiran zapis z vsemi stolpci in podatki iz vsake entitete.

1. [Poenotena polja za stranke](merge-entities.md) (prej imenovano Združi): V koraku poenotenih polj strank določite, katera izvorna polja je treba vključiti, izključiti ali združiti v poenoten profil stranke.  

1. [Pregled](review-unification.md) in ustvarite enoten profil.

# <a name="business-accounts-b-to-b"></a>[Poslovni računi (podjetja podjetjem)](#tab/b2b)

Postopek poenotenja preslika podatke računa iz vaših podatkovnih virov, odstrani dvojnike, poveže podatke med entitetami in ustvari poenoten profil. Poenotenje se izvede v naslednjem vrstnem redu:

1. [Izvorna polja](map-entities.md) (prej imenovan Zemljevid): V koraku izvornih polj izberite entitete in polja, ki jih želite vključiti v postopek poenotenja računa. Preslikava polj v skupni semantični tip, ki opisuje namen polja.

1. [Podvojeni zapisi](remove-duplicates.md) (prej del ujemanja): V koraku podvojenih zapisov po želji definirajte pravila za odstranjevanje podvojenih zapisov računa iz vsake entitete.

1. [Ujemanje pogojev](match-entities.md) (prej imenovano Ujemanje): V koraku pogojev ujemanja definirajte pravila, ki se ujemajo z zapisi računov med entitetami. Ko je račun najden v dveh ali več entitetah, se ustvari en konsolidiran zapis z vsemi stolpci in podatki iz vsake entitete.

1. [Poenotena polja za stranke](merge-entities.md) (prej imenovano Združi): V koraku poenotenih polj strank določite, katera izvorna polja je treba vključiti, izključiti ali združiti v poenoten profil stranke.  

1. [Pregled](review-unification.md) in ustvarite enoten profil.

Po poenotenju računov lahko izbirno [poenotenje stikov (predogled)](data-unification-contacts.md) za te račune in povežite poenotene stike z poenotenimi računi.

---

Po končanem združevanju podatkov lahko po želji:

- [Nastavite Odnosi med subjekti](relationships.md) za ustvarjanje prefinjenih segmentov.
- [Obogatite svoje podatke](enrichment-hub.md) da pridobite širši nabor vpogledov o svojih strankah.
- [Določite dejavnosti](activities.md) iz nekaterih zaužitih atributov.
- [Zgradite ukrepe](measures.md) za boljše razumevanje vedenja strank in poslovne uspešnosti.

[!INCLUDE [footer-include](includes/footer-banner.md)]
