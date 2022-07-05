---
title: Povežite se z a Power Query vir podatkov (vsebuje video)
description: Zaužijte podatke prek a Power Query priključek (vsebuje video).
ms.date: 06/13/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: matgos
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 6736b253e3a7e652f92f61bc44bfb31ca69be31a
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082186"
---
# <a name="connect-to-a-power-query-data-source"></a>Povežite se z a Power Query vir podatkov

Power Query ponuja širok nabor priključkov za vnos podatkov. Dynamics 365 Customer Insights podpira večino teh povezovalnikov.

Dodajanje podatkovnih virov na podlagi Power Query konektorji na splošno sledi korakom, opisanim v tem razdelku. Vendar pa so glede na povezovalnik, ki ga uporabljate, potrebne drugačne informacije. Če želite izvedeti več, glejte dokumentacijo o posameznih konektorjih v [Power Query referenca konektorja](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Ustvarjanje novega vira podatkov

1. Pojdite na **Podatki** > **Viri podatkov**.

1. Izberite **Dodaj vir podatkov**.

1. Izberite **Microsoft Power Query**.

1. Zagotovite a **ime** in neobvezno **Opis** za vir podatkov in izberite **Naslednji**.

1. Izberite enega od [razpoložljivih povezovalnikov](#available-power-query-data-sources). V tem primeru izberemo **Besedilo/CSV** priključek.

1. Vnesite zahtevane podrobnosti v **Nastavitve povezave** za izbrani povezovalnik in izberite **Naprej**, da si ogledate predogled podatkov.

1. Izberite **Pretvori podatke**. V tem koraku boste dodali entitete v vir podatkov. Entitete so nabori podatkov. Če imate zbirko podatkov, ki vključuje več naborov podatkov, je vsak nabor podatkov svoja entiteta.

1. The **Power Query - Uredite poizvedbe** pogovorno okno vam omogoča pregled in izboljšanje podatkov. Entitete, ki jih sistemi, opredeljeni v izbranem viru podatkov, prikažejo v levem podoknu.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Pogovorno okno urejanja poizvedb":::

1. Podatke pa lahko tudi preoblikujete. Izberite entiteto, ki jo želite urediti ali preoblikovati. Uporabite možnosti v Power Query okno za uporabo transformacij. Vsaka transformacija je navedena pod **Uporabljeni koraki**. Power Query ponuja številne vnaprej izdelane možnosti preoblikovanja. Za več informacij glejte [Power Query Transformacije](/power-query/power-query-what-is-power-query#transformations).

   Priporočamo, da uporabite naslednje transformacije:

   - Če vnašate podatke iz datoteke CSV, prva vrstica pogosto vsebuje glave. Pojdi do **Preoblikovanje** in izberite **Uporabite prvo vrstico kot glave**.
   - Prepričajte se, da je vrsta podatkov pravilno nastavljena. Na primer, za datumska polja izberite vrsto datuma.

1. Če želite dodati dodatne entitete v svoj vir podatkov v **Uredite poizvedbe** pogovorno okno, pojdite na **Domov** in izberite **Pridobite podatke**. Ponavljajte korake 6-10, dokler ne dodate vseh entitet za to vir podatkov.

1. Izberite **Shrani**. The **Viri podatkov** odpre se stran z novim vir podatkov v **Osvežujoče** stanje.

### <a name="available-power-query-data-sources"></a>Na voljo Power Query viri podatkov

Glej [Power Query referenca konektorja](/power-query/connectors/) za seznam povezovalnikov, ki jih lahko uporabite za uvoz podatkov v Customer Insights.

Konektorji s kljukico v **Vpogledi strank (tokovi podatkov)** so na voljo za ustvarjanje novih podatkovnih virov na podlagi Power Query. Preglejte dokumentacijo določenega priključka, če želite izvedeti več o njegovih predpogojih, [omejitve poizvedbe](/power-query/power-query-online-limits), in druge podrobnosti.

## <a name="add-data-from-on-premises-data-sources"></a>Dodajanje podatkov iz virov podatkov na mestu uporabe

Vnos podatkov iz virov podatkov na mestu uporabe je podprt na podlagi Microsoft Power Platform tokovi podatkov (PPDF). Tokove podatkov v Customer Insights lahko omogočite z [zagotavljanje Microsoft Dataverse URL okolja](create-environment.md) pri postavljanju okolja.

Viri podatkov, ki so ustvarjeni po povezovanju a Dataverse okolje z uporabo Customer Insights [Power Platform tokovi podatkov](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) privzeto. Za podatkovne tokove je prek prehoda za podatke podprta povezljivost na mestu uporabe. Lahko odstranite in ponovno ustvarite vire podatkov, ki so obstajali pred a Dataverse je bilo povezano okolje [z uporabo podatkovnih prehodov na mestu uporabe](/data-integration/gateway/service-gateway-app).

Prehodi za podatke iz obstoječega okolja storitve Power BI ali Power Apps bodo vidni v storitvi Customer Insights, kjer jih lahko znova uporabite. Na strani z viri podatkov se nahajajo povezave do okolja Microsoft Power Platform, kjer si lahko ogledate prehode za podatke na mestu uporabe ter jih konfigurirate.

> [!IMPORTANT]
> Prepričajte se, da so vaši prehodi posodobljeni na najnovejšo različico. Namestite lahko posodobitev in ponovno konfigurirate prehod neposredno iz poziva, prikazanega na zaslonu prehoda ali [prenesite najnovejšo različico](https://powerapps.microsoft.com/downloads/). Če ne uporabljate najnovejše različice prehoda, osvežitev toka podatkov ne uspe s sporočili o napakah, kot je **Ključna beseda ni podprta: lastnosti konfiguracije. Ime parametra: ključna beseda**.

## <a name="edit-power-query-data-sources"></a>Uredi Power Query viri podatkov

> [!NOTE]
> Morda ne bo mogoče spreminjati virov podatkov, ki se trenutno uporabljajo v enem od procesov aplikacije (na primer *segmentacija*, *ujemanje* ali *spajanje*).
>
> V **Nastavitve** strani, lahko spremljate napredek vsakega od aktivnih procesov. Ko se proces zaključi, se lahko vrnete na stran **Viri podatkov** in opravite spremembe.

1. Pojdite na **Podatki** > **Viri podatkov**.

1. Zraven vir podatkov, ki ga želite posodobiti, izberite **Uredi**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

1. Uporabite svoje spremembe in transformacije v **Power Query - Uredite poizvedbe** pogovorno okno, kot je opisano v [Ustvarite nov vir podatkov](#create-a-new-data-source) oddelek.

1. Izberite **Shrani** v Power Query po končanem urejanju, da shranite spremembe.
