---
title: Predlagani segmenti, ki temeljijo na dejavnosti.
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
ms.openlocfilehash: 9c10a32b770ea110a1166f20f72116a3a12cb92e
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354483"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a>Predlagani segmenti, ki temeljijo na podatkih o dejavnosti (predogledna različica)

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
Če se ukvarjate z zdravstveno oskrbo in zagotavljate javno zdravstveno oskrbo ter je vaš cilj čim bolj zmanjšati stroške za posamezne bolnike. To lahko dosežete tako, da z zagotavljanjem najboljše možne oskrbe v čim manj obiskih zmanjšate število ponavljajočih se obiskov. V tem primeru je vaš cilj ohraniti nizko pogostost obiska in zmanjšati ponavljajoče se stroške za paciente. Lahko pa prepoznate segmente pacientov, ki imajo pogoste sestanke in ponavljajoče se stroške, ter analizirate te primere za izboljšanje zdravljenja posameznika. 

## <a name="required-data"></a>Zahtevani podatki

Predlogi se ustvarijo na podlagi izbranih vhodnih podatkov. 

- Profili strank: vse stranke ali člani določenega segmenta. 

- Časovno obdobje: prejšnji mesec, lansko leto ali kateri koli časovni okvir po meri.

- Vrsta dejavnosti: nakupi, maloprodajne transakcije, spletne transakcije, primeri podpore strankam, naročnine itd.  

- Entiteta v rešitvi Customer Insights, ki vsebuje podatke o dejavnosti: entiteta UnifiedActivity ali entiteta za določeno dejavnost. 

- Razsežnosti, ki jih je treba vključiti: nedavnost, pogostost ali denarna razsežnost, odvisno od vaših poslovnih potreb.

## <a name="generate-suggested-segments"></a>Ustvarjanje predlaganih segmentov

1. Izberite **Segmenti**.

1. Izberite zavihek **Predlogi (predogled)**.

1. Izberite možnost **Poiščite nove predloge** in **Oglejte si ali predvidevajte vedenje kupcev**. Za zagon vodene izkušnje izberite gumb **Začni**.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Prvi korak čarovnika za konfiguracijo za predlagani segment na podlagi dejavnosti.":::

1. Vnesite zahtevane vhodne podatke in za nadaljevanje izberite gumb **Naprej**.

   - Izberite stranke: vključite vse stranke ali določen segment.
   - Izberite dejavnost: izberite vrsto dejavnosti in entitete, ki opisujejo dejavnost.
   - Nastavitve: nastavite časovno obdobje, ki ga želite upoštevati, dejavnike za predloge in preslikajte atribute.

1. Preglejte vnos in izberite možnost **Začni** za zagon modela in ustvarjanje predlogov.

1. To lahko traja nekaj minut, odvisno od števila profilov strank in izbranih dejavnosti. 

Ko ustvarite predloge, jih lahko filtrirate po razsežnosti ali vrednosti, ki vas najbolj zanima. 

## <a name="view-details-of-a-suggested-segment"></a>Ogled podrobnosti predlaganega segmenta

Ko so predlogi ustvarjeni, jih boste našli na v zavihku **Segmenti** > **Predlogi (predogledna različica)** v zavihku **Predlogi na podlagi dejavnosti**.

:::image type="content" source="media/suggested-segments-details.png" alt-text="Razširjeno stransko podokno s podrobnimi podatki predlaganega segmenta.":::

Na predlaganem segmentu izberite možnost **Ogled predloga**, če si želite ogledati podrobnosti tega segmenta. Stransko podokno vsebuje podrobnosti, kot je obseg posamezne razsežnosti v primerjavi s ciljno skupino. Poudarja tudi število potencialnih članov v segmentu in ustrezen odstotek vseh kupcev. Če želite predlog ohraniti kot segment, izberite možnost **Ustvari segment**.    

## <a name="save-a-suggestion-as-a-segment"></a>Shranjevanje predloga kot segmenta

1. Odprite **Segmenti** > **Predlogi (predogled)**.

1. Izberite segment, ki ga želite shraniti. 

1. V stranskem podoknu izberite možnost **Ustvari segment**. 

1. Ko shranite segment, se bo prikazal na seznamu segmentov v zavihku **Vsi segmenti**. Zdaj ga lahko [osvežite ali izbrišete kot kateri koli drug segment](segments.md). Podrobnosti segmenta ne morete urejati. Lahko pa spremenite merila vnosa za predloge in ustvarite različne predloge.

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Osvežitev ali urejanje niza segmentov

1. Odprite zavihek **Segmenti** > **Predlogi (predogledna različica)** in poiščite segment v razdelku **Predlogi na podlagi dejavnosti**.

1. Izberite **Osveži predloge**, da osvežite predloge in obdržite konfigurirane atribute. Ali izberite možnost **Urejanje predlogov**, če želite spreminjati konfigurirane atribute. Sistem bo ponovil postopek, ustvaril predloge za segmente na podlagi najnovejših podatkov in nadomestil trenutne predloge.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
