---
title: Povežite se z a Power Query vir podatkov (vsebuje video)
description: Vnos podatkov prek a Power Query priključek (vsebuje video).
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 6a25e332bafab414c9def4e1e6b461139dd24ea6
ms.sourcegitcommit: dfba60e17ae6dc1e2e3830e6365e2c1f87230afd
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 09/09/2022
ms.locfileid: "9463285"
---
# <a name="connect-to-a-power-query-data-source"></a>Povežite se z a Power Query vir podatkov

Power Query ponuja širok nabor konektorjev za vnos podatkov. Dynamics 365 Customer Insights podpira večino teh povezovalnikov.

Dodajanje podatkovnih virov na podlagi Power Query priključkov na splošno sledi korakom, opisanim v tem razdelku. Vendar pa so glede na povezovalnik, ki ga uporabljate, potrebne drugačne informacije. Če želite izvedeti več, glejte dokumentacijo o posameznih konektorjih v [Power Query referenca priključka](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Ustvarjanje novega vira podatkov

1. Pojdite na **Podatki** > **Viri podatkov**.

1. Izberite **Dodaj vir podatkov**.

1. Izberite **Microsoft Power Query**.

1. Zagotovite a **Ime** in neobvezno **Opis** za vir podatkov in izberite **Naslednji**.

1. Izberite enega od [razpoložljivih povezovalnikov](#available-power-query-data-sources). V tem primeru izberemo **Besedilo/CSV** priključek.

1. Vnesite zahtevane podrobnosti v **Nastavitve povezave** za izbrani povezovalnik in izberite **Naprej**, da si ogledate predogled podatkov.

1. Izberite **Pretvori podatke**.

1. The **Power Query - Uredite poizvedbe** vam omogoča pregledovanje in izboljšanje podatkov. Entitete, ki jih sistemi, opredeljeni v izbranem viru podatkov, prikažejo v levem podoknu.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Pogovorno okno urejanja poizvedb":::

1. Podatke pa lahko tudi preoblikujete. Izberite entiteto, ki jo želite urediti ali preoblikovati. Uporabite možnosti v Power Query okno za uporabo transformacij. Vsaka transformacija je navedena pod **Uporabljeni koraki**. Power Query zagotavlja številne [vnaprej zgrajena transformacija](/power-query/power-query-what-is-power-query#transformations) opcije.

   Priporočamo, da uporabite naslednje transformacije:

   - Če vnašate podatke iz datoteke CSV, prva vrstica pogosto vsebuje glave. Pojdi do **Preobrazba** in izberite **Prvo vrstico uporabite kot glave**.
   - Prepričajte se, da je vrsta podatkov pravilno nastavljena. Na primer, za datumska polja izberite vrsto datuma.

1. Če želite dodati dodatne entitete v svoj vir podatkov v **Uredite poizvedbe** dialog, pojdi na **domov** in izberite **Pridobite podatke**. Ponavljajte korake 5–10, dokler ne dodate vseh entitet za ta vir podatkov. Če imate zbirko podatkov, ki vključuje več naborov podatkov, je vsak nabor podatkov svoja entiteta.

1. Izberite **Shrani**. The **Viri podatkov** odpre se stran, ki prikazuje novo vir podatkov v **Osvežujoče** stanje.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Nalaganje podatkov lahko traja nekaj časa. Po uspešni osvežitvi lahko vnesene podatke pregledate iz [**Entitete**](entities.md) strani.

> [!CAUTION]
>
> - Vir podatkov temelji na Power Query ustvarja a [tok podatkov v Dataverse](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Ne spreminjajte imena toka podatkov v Power Platform skrbniško središče, ki se uporablja v Customer Insights. Preimenovanje toka podatkov povzroča težave s sklici med Customer Insights vir podatkov in Dataverse pretok podatkov.
> - Sočasne ocene za Power Query viri podatkov v Customer Insights imajo enako [omejitve osveževanja, kot so tokovi podatkov v PowerBI.com](/power-query/power-query-online-limits#refresh-limits). Če osvežitev podatkov ne uspe, ker so dosegli omejitev vrednotenja, priporočamo, da prilagodite razpored osveževanja za vsak tok podatkov, da zagotovite, da se viri podatkov ne obdelujejo hkrati.

### <a name="available-power-query-data-sources"></a>Na voljo Power Query viri podatkov

Glej [Power Query referenca priključka](/power-query/connectors/) za seznam povezovalnikov, ki jih lahko uporabite za uvoz podatkov v Customer Insights.

Konektorji s kljukico v **Vpogledi strank (podatkovni tokovi)** na voljo za ustvarjanje novih podatkovnih virov na podlagi Power Query. Preglejte dokumentacijo določenega priključka, če želite izvedeti več o njegovih predpogojih, [omejitve poizvedbe](/power-query/power-query-online-limits), in druge podrobnosti.

## <a name="add-data-from-on-premises-data-sources"></a>Dodajanje podatkov iz virov podatkov na mestu uporabe

Vnos podatkov iz podatkovnih virov na mestu uporabe je podprt na podlagi Microsoft Power Platform podatkovnih tokov (PPDF). Podatkovne tokove v Customer Insights lahko omogočite tako, da [zagotavljanje Microsoft Dataverse URL okolja](create-environment.md) pri postavljanju okolja.

Viri podatkov, ki so ustvarjeni po povezovanju a Dataverse okolje z uporabo Customer Insights [Power Platform podatkovnih tokov](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) privzeto. Za podatkovne tokove je prek prehoda za podatke podprta povezljivost na mestu uporabe. Lahko odstranite in znova ustvarite vire podatkov, ki so obstajali pred a Dataverse okolje je bilo povezano [z uporabo na mestu uporabe podatkovnih prehodov](/data-integration/gateway/service-gateway-app).

Podatkovni prehodi iz obstoječega Power BI oz Power Apps okolje bodo vidni in jih lahko znova uporabite v Customer Insights, če sta podatkovni prehod in okolje Customer Insights v isti regiji Azure. Na strani z viri podatkov se nahajajo povezave do okolja Microsoft Power Platform, kjer si lahko ogledate prehode za podatke na mestu uporabe ter jih konfigurirate.

> [!IMPORTANT]
> Prepričajte se, da so vaši prehodi posodobljeni na najnovejšo različico. Namestite lahko posodobitev in znova konfigurirate prehod iz poziva, prikazanega na zaslonu prehoda, neposredno ali [prenesite najnovejšo različico](https://powerapps.microsoft.com/downloads/). Če ne uporabljate najnovejše različice prehoda, osvežitev podatkovnega toka ne uspe s sporočili o napakah, kot je **Ključna beseda ni podprta: lastnosti konfiguracije. Ime parametra: ključna beseda**.
>
> Napake s na mestu uporabe podatkovnimi prehodi v Customer Insights so pogosto posledica težav s konfiguracijo. Za več informacij o odpravljanju težav s podatkovnimi prehodi glejte [Odpravite težave s podatkovnim prehodom na mestu uporabe](/data-integration/gateway/service-gateway-tshoot).

## <a name="edit-power-query-data-sources"></a>Uredi Power Query viri podatkov

> [!NOTE]
> Morda ne bo mogoče spremeniti virov podatkov, ki se trenutno uporabljajo v enem od procesov aplikacije (na primer segmentacija ali poenotenje podatkov).
>
> V **nastavitve** strani, lahko spremljate napredek vsakega od aktivnih procesov. Ko se proces zaključi, se lahko vrnete na stran **Viri podatkov** in opravite spremembe.

1. Pojdite na **Podatki** > **Viri podatkov**.

1. Izberite poleg vir podatkov, ki ga želite posodobiti **Uredi**.

1. Uporabite svoje spremembe in transformacije v **Power Query - Uredite poizvedbe** pogovorno okno, kot je opisano v [Ustvarite nov vir podatkov](#create-a-new-data-source) razdelek.

1. Izberite **Shrani** da uveljavite svoje spremembe in se vrnete na **Viri podatkov** strani.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
