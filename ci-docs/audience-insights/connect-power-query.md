---
title: Zaužijte podatke prek a Power Query konektor (vsebuje video)
description: Konektorji za podatkovne vire, ki temeljijo na Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 4c12933a0684094702843be309525dd6d5d9b6f4
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355541"
---
# <a name="connect-to-a-power-query-data-source"></a>Povežite se z a Power Query vir podatkov

Power Query ponuja širok nabor priključkov za vnos podatkov. Dynamics 365 Customer Insights podpira večino teh povezovalnikov. 

Dodajanje podatkovnih virov na podlagi Power Query konektorji na splošno sledi korakom, opisanim v tem razdelku. Vendar pa so glede na povezovalnik, ki ga uporabljate, potrebne drugačne informacije. Če želite izvedeti več, si oglejte dokumentacijo o posameznih konektorjih v [Power Query referenca konektorja](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Ustvarjanje novega vira podatkov

1. Pri vpogledih v občinstvo izberite **Podatki** > **Viri podatkov**.

1. Izberite **Dodaj vir podatkov**.

1. Izberite **Microsoft Power Query**.

1. Vnesite **Ime** za vir podatkov in izberite **Naprej**, da ustvarite vir podatkov.

1. Izberite enega od [razpoložljivih povezovalnikov](#available-power-query-data-sources). V tem primeru izberemo **Besedilo/CSV** konektor.

1. Vnesite zahtevane podrobnosti v **Nastavitve povezave** za izbrani povezovalnik in izberite **Naprej**, da si ogledate predogled podatkov.

1. Izberite **Pretvori podatke**. V tem koraku boste dodali entitete v vir podatkov. Entitete so nabori podatkov. Če imate zbirko podatkov, ki vključuje več naborov podatkov, je vsak nabor podatkov svoja entiteta.

1. The **Power Query - Uredite poizvedbe** pogovorno okno vam omogoča pregled in izboljšanje podatkov. Entitete, ki jih sistemi, opredeljeni v izbranem viru podatkov, prikažejo v levem podoknu.

   > [!div class="mx-imgBorder"]
   > ![Pogovorno okno za urejanje poizvedb.](media/data-manager-configure-edit-queries.png "Pogovorno okno urejanja poizvedb")

1. Podatke pa lahko tudi preoblikujete. Izberite entiteto, ki jo želite urediti ali preoblikovati. Uporabite možnosti v Power Query okno za uporabo transformacij. Vsaka pretvorba je navedena pod **Uporabljeni koraki**. Power Query ponuja številne vnaprej izdelane možnosti preoblikovanja. Za več informacij glejte [Power Query Transformacije](/power-query/power-query-what-is-power-query#transformations).

   Priporočamo, da uporabite naslednje transformacije:

   - Če vnašate podatke iz datoteke CSV, prva vrstica pogosto vsebuje glave. Pojdi do **Preoblikovanje** in izberite **Uporabite prvo vrstico kot glave**.
   - Prepričajte se, da je vrsta podatkov pravilno nastavljena. Na primer, za datumska polja izberite vrsto datuma.

1. Če želite dodati dodatne entitete v svoj vir podatkov v **Uredite poizvedbe** pogovorno okno, pojdite na **Domov** in izberite **Pridobite podatke**.

1. Izberite **Shrani** na dnu Power Query okno za shranjevanje transformacij. Po shranjevanju boste našli svoj vir podatkov pod **Podatki** > **Viri podatkov**.

1. Na strani **Viri podatkov** boste opazili, da ima nov vir podatkov stanje **Osveževanje**.

## <a name="available-power-query-data-sources"></a>Na voljo Power Query viri podatkov

Glej [Power Query referenca konektorja](/power-query/connectors/) za seznam povezovalnikov, ki jih lahko uporabite za uvoz podatkov v Customer Insights. 

Konektorji s kljukico v **Vpogledi strank (tokovi podatkov)** so na voljo za ustvarjanje novih podatkovnih virov na podlagi Power Query. Preglejte dokumentacijo določenega povezovalnika, če želite izvedeti več o njegovih predpogojih, omejitvah in drugih podrobnostih.

## <a name="edit-power-query-data-sources"></a>Uredi Power Query viri podatkov

> [!NOTE]
> Morda ne bo mogoče spreminjati virov podatkov, ki se trenutno uporabljajo v enem od procesov aplikacije (na primer *segmentacija*, *ujemanje* ali *spajanje*). 
>
> V **Nastavitve** strani, lahko spremljate napredek vsakega od aktivnih procesov. Ko se proces zaključi, se lahko vrnete na stran **Viri podatkov** in opravite spremembe.

1. Pri vpogledih v občinstvo izberite **Podatki** > **Viri podatkov**.

2. Izberite navpične tri pike poleg tistega vira podatkov, ki ga želite spremeniti, nato pa v spustnem meniju izberite **Uredi**.

   > [!div class="mx-imgBorder"]
   > ![Možnost urejanja.](media/edit-option-data-sources.png "Možnost urejanja")

   [!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]
   
3. Uporabite svoje spremembe in transformacije v **Power Query - Uredite poizvedbe** pogovorno okno, kot je opisano v [Ustvarite nov vir podatkov](#create-a-new-data-source) oddelek.

4. Izberite **Shrani** v Power Query po končanem urejanju, da shranite spremembe.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
