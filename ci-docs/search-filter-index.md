---
title: Iskanje in filtriranje profilov strank
description: Hitro poiščite informacije o poenotenih profilih strank in filtrirajte za določene atribute.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: 35bfd6530b9b80a4b0ec8ff992d9014534721907
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643561"
---
# <a name="customer-profiles-search--filter-index"></a>Profili strank: Kazalo za iskanje in filtre

Rezultat poenotenja podatkov strank je vnos profila stranke, ki zagotavlja poenoten pogled v celotno bazo strank. Za hitro [iskanje informacij o določeni stranki ali skupini strank](customer-profiles.md), lahko konfigurirate zmogljivosti **Iskanje** in **Filter** na strani **Stranke**. Berite dalje, da boste izvedeli, kako uredite atribute na strani **Kazalo za iskanje in filtre**, ki je na voljo uporabnikom za iskanje in filtriranje.

   :::image type="content" source="media/search-filter.png" alt-text="Filter za iskanje":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="add-fields-and-specify-attributes"></a>Dodajanje polj in določanje atributov

Če kot skrbnik prvikrat določate atribute, po katerih je mogoče iskati, morate najprej določiti indeksirana polja. Predlagamo, da izberete vse atribute, po katerih lahko uporabniki iščejo in filtrirajo stranke na strani **Stranke**. Določite lahko samo atribute, ki obstajajo v entiteti profila stranke, ki ste jo ustvarili med postopkom poenotenja.

1. Odprite stran **Stranke** in izberite **Kazalo za iskanje in filtre**.

2. Izberite **+ Dodaj**, da določite indeksirana polja.

3. Na seznamu izberite atribute, ki jih želite dodati kot indeksirana polja. Zmeraj lahko dodate več atributov, tako da izberete **Dodaj**. Vse izbrane atribute lahko odstranite tudi tako, da izberete simbol **Odstrani**.

## <a name="explore-the-indexed-customer-fields-table"></a>Raziskovanje indeksirane tabele polj stranke

V tabeli so predstavljene naslednje informacije.

- **Ime**: predstavlja ime atributa, kot je prikazano v entiteti profila stranke.
- **Vrsta podatkov**: določa, ali je vrsta podatkov niz, številka ali datum.
- **Vključeno v iskanje**: določa, ali je ta atribut mogoče uporabiti za iskanje strank na strani **Stranke** s poljem **Iskanje**.
- **Dodaj filter**: kontrolnik za določanje, kako je mogoče ta atribut uporabljati za filtriranje na strani **Stranke**.

## <a name="editing-filtering-options-for-a-given-attribute"></a>Urejanje možnosti filtriranja za določen atribut

Meni **Filter** na strani **Stranke** lahko vključuje različno število ravni atributa (na primer različne starostne skupine, po katerih se stranke filtrirajo).

1. Izberite **Dodaj filter** za določeni atribut na strani **Kazalo za iskanje in filtre**. Določite lahko število rezultatov in vrsti red, v katerem bodo organizirani. Odvisno od vrste podatkov atributa se prikaže eno od naslednjih podoken.

- Atributi vrste niza: Določite število želenih rezultatov v podoknu **Možnosti filtra nizov** in politiko vrstnega reda, po kateri bodo organizirani.

- Atributi vrste numerično: Določite vključene intervale v podoknu **Možnosti filtra številk** in politiko vrstnega reda, po kateri bodo organizirani.

- Atributi vrste datuma: Določite vključene intervale v podoknu **Možnosti filtra datuma** in politiko vrstnega reda, po kateri bodo organizirani.

2. Če želite uporabiti spremembe, izberite **Shrani**.

3. Izberite **Zaženi**, ko ste pripravljeni na uveljavljanje nastavitev. Ko so spremembe obdelane, jih najdete v [karticah strank na strani stranke](customer-profiles.md). 

## <a name="next-steps"></a>Naslednji koraki

Preglejte [stran poenotenih profilov](customer-profiles.md), da poiščete profile, ali uporabite indeksirana polja, da si ogledate podmnožice vseh poenotenih profilov.


[!INCLUDE [footer-include](includes/footer-banner.md)]