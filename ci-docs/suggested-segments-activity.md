---
title: Predlagani segmenti na podlagi dejavnosti (predogled)
description: Naj vam strojno učenje pomaga najti nove in zanimive segmente na podlagi dejavnosti strank.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: df4f5f4b5c9a3ad66d57a6b349e18a0d714aff62
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170609"
---
# <a name="suggested-segments-based-on-activity-preview"></a>Predlagani segmenti na podlagi dejavnosti (predogled)

Odkrijte zanimive segmente svojih strank na podlagi podatkov o dejavnostih strank, ki so uvoženi v Customer Insights. Primeri podatkov o dejavnosti so transakcije, trajanje klica za podporo, nakupi ali vračila. Za predlaganje segmentov se podatki o dejavnosti analizirajo glede na nedavnost, pogostost in denarno vrednost (ali trajanje). Lahko pa tudi ustvarite [predlagane segmente za izboljšanje mere ali boljše razumevanje vplivov na atribut](suggested-segments.md).

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Zavihek Predlagani segmenti, ki prikazuje predloge segmentov za segmente, ki temeljijo na dejavnosti in atributih.":::

## <a name="categorize-customers-by-activity"></a>Razvrščanje strank po dejavnosti

S [podatki o dejavnosti](activities.md), ki so na voljo v rešitvi Customer Insights, lahko ustvarimo predloge, ki predstavljajo skupine strank:

- najbolj dejavne stranke 
- stranke, ki so opravile največ nakupov 
- stranke, ki so ustvarile največ prihodka 
- stranke, ki zadnje čase niso aktivne 
- stranke, ki pogosto komunicirajo z vašim podjetjem  

Če imate trgovino na drobno, lahko izveste, katere stranke ustvarijo največ prihodka, in jih nagradite s kuponom. Lahko pa prepoznate občasne stranke in jim ponudite, da se pridružijo programu nagrad, da bodo pogosteje obiskali vaše podjetje.
Če nudite javno zdravstveno varstvo in je vaš cilj zmanjšati stroške za posamezne bolnike, lahko poskusite zmanjšati ponavljajoče se obiske tako, da zagotovite najboljšo možno oskrbo v čim manj obiskih. V tem primeru je vaš cilj ohraniti nizko pogostost obiska in zmanjšati ponavljajoče se stroške za paciente. Lahko pa prepoznate segmente pacientov, ki imajo pogoste sestanke in ponavljajoče se stroške, ter analizirate te primere za izboljšanje zdravljenja posameznika.

## <a name="required-data"></a>Zahtevani podatki

Predlogi se ustvarijo na podlagi izbranih vhodnih podatkov.

- Profili strank: vse stranke ali člani določenega segmenta.

- Časovno obdobje: prejšnji mesec, lansko leto ali kateri koli časovni okvir po meri.

- Vrsta dejavnosti: nakupi, maloprodajne transakcije, spletne transakcije, primeri podpore strankam, naročnine itd.  

- Entiteta v rešitvi Customer Insights, ki vsebuje podatke o dejavnosti: entiteta UnifiedActivity ali entiteta za določeno dejavnost.

- Razsežnosti, ki jih je treba vključiti: nedavnost, pogostost ali denarna razsežnost, odvisno od vaših poslovnih potreb.

## <a name="generate-suggested-segments"></a>Ustvarjanje predlaganih segmentov

1. Pojdi do **Segmenti** in izberite **Predlogi (predogled)** zavihek.

1. Izberite možnost **Poiščite nove predloge** in **Oglejte si ali predvidevajte vedenje kupcev**. Izberite **Začetek**.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Prvi korak čarovnika za konfiguracijo za predlagani segment na podlagi dejavnosti.":::

1. Vnesite zahtevane vhodne podatke in izberite **Naslednji**.

   - Izberite stranke: vključite vse stranke ali določen segment.
   - Izberite dejavnost: izberite vrsto dejavnosti in entitete, ki opisujejo dejavnost.
   - Nastavitve: nastavite časovno obdobje, ki ga želite upoštevati, dejavnike za predloge in preslikajte atribute.

1. Preglejte vnos in izberite možnost **Začni** za zagon modela in ustvarjanje predlogov.

To lahko traja nekaj minut, odvisno od števila profilov strank in izbranih dejavnosti.

Ko ustvarite predloge, jih lahko filtrirate po razsežnosti ali vrednosti, ki vas najbolj zanima.

## <a name="manage-suggested-segments"></a>Upravljajte predlagane segmente

Pojdi do **Segmenti** in izberite **Predlogi (predogled)** zavihek. V **Predlogi na podlagi dejavnosti** izberite predlagani segment za ogled razpoložljivih dejanj.

- **Glej predlog** za ogled podrobnosti tega segmenta, kot je obseg vsake dimenzije v primerjavi s ciljno skupino. Poudarja tudi število potencialnih članov v segmentu in ustrezen odstotek vseh kupcev.
- **Ustvari segment** da shranite predlagano kot segment. Prikaže se na **Vsi segmenti** zavihek in lahko [osveženo ali izbrisano](segments.md). Podrobnosti segmenta ne morete urejati. Lahko pa spremenite merila vnosa za predloge in ustvarite različne predloge.
- **Uredite predloge** da spremenite konfigurirane atribute, ki bodo nadomestili trenutne predloge.
- **Osveži predloge** da osvežite predloge, medtem ko ohranite konfigurirane atribute.

[!INCLUDE [footer-include](includes/footer-banner.md)]
