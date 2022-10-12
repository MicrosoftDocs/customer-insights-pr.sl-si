---
title: Povežite se z a Power Query vir podatkov (vsebuje video)
description: Vnos podatkov prek a Power Query priključek (vsebuje video).
ms.date: 09/29/2022
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
ms.openlocfilehash: 4cc7e57dfb0f8d050e91adc441c24e849882f5d8
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609916"
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

1. Preglejte in izboljšajte svoje podatke v **Power Query - Uredite poizvedbe** strani. Entitete, ki jih sistemi, opredeljeni v izbranem viru podatkov, prikažejo v levem podoknu.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Pogovorno okno urejanja poizvedb":::

1. Preoblikujte svoje podatke. Izberite entiteto, ki jo želite urediti ali preoblikovati. Uporabite možnosti v Power Query okno za uporabo transformacij. Vsaka transformacija je navedena pod **Uporabljeni koraki**. Power Query zagotavlja številne [vnaprej zgrajena transformacija](/power-query/power-query-what-is-power-query#transformations) opcije.

   > [!IMPORTANT]
   > Priporočamo, da uporabite naslednje transformacije:
   >
   > - Če vnašate podatke iz datoteke CSV, prva vrstica pogosto vsebuje glave. Pojdi do **Preobrazba** in izberite **Prvo vrstico uporabite kot glave**.
   > - Prepričajte se, da je tip podatkov pravilno nastavljen in se ujema s podatki. Na primer, za datumska polja izberite vrsto datuma.

1. Če želite dodati dodatne entitete v svoj vir podatkov v **Uredite poizvedbe** dialog, pojdi na **domov** in izberite **Pridobite podatke**. Ponavljajte korake 5–10, dokler ne dodate vseh entitet za ta vir podatkov. Če imate zbirko podatkov, ki vključuje več naborov podatkov, je vsak nabor podatkov svoja entiteta.

1. Izberite **Shrani**. The **Viri podatkov** odpre se stran, ki prikazuje novo vir podatkov v **Osvežujoče** stanje.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Nalaganje podatkov lahko traja nekaj časa. Po uspešni osvežitvi lahko vnesene podatke pregledate iz [**Entitete**](entities.md) strani.

> [!CAUTION]
>
> - Vir podatkov temelji na Power Query ustvarja a [tok podatkov v Dataverse](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Ne spreminjajte imena toka podatkov v Power Platform skrbniško središče, ki se uporablja v Customer Insights. Preimenovanje toka podatkov povzroča težave s sklici med Customer Insights vir podatkov in Dataverse pretok podatkov.
> - Sočasne ocene za Power Query viri podatkov v Customer Insights imajo enako [omejitve osveževanja, kot so tokovi podatkov v PowerBI.com](/power-query/power-query-online-limits#refresh-limits). Če osvežitev podatkov ne uspe, ker so dosegli omejitev vrednotenja, priporočamo, da prilagodite razpored osveževanja za vsak podatkovni tok, da zagotovite, da se viri podatkov ne obdelujejo istočasno.

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

## <a name="common-reasons-for-ingestion-errors-or-corrupt-data"></a>Pogosti razlogi za napake pri vnosu ali poškodovane podatke

### <a name="data-type-does-not-match-data"></a>Vrsta podatkov se ne ujema s podatki

Najpogostejše neujemanje vrste podatkov se pojavi, ko datumsko polje ni nastavljeno na pravilno obliko datuma.

Podatke je mogoče popraviti pri viru in jih ponovno zaužiti. Ali pa popravite transformacijo znotraj Customer Insights. Če želite popraviti transformacijo:

1. Pojdite na **Podatki** > **Viri podatkov**.

1. Poleg vir podatkov s poškodovanimi podatki izberite **Uredi**.

1. Izberite **Naprej**.

1. Izberite vsako od poizvedb in poiščite transformacije, uporabljene znotraj »Uporabljenih korakov«, ki so nepravilne, ali datumske stolpce, ki niso bili preoblikovani z obliko datuma.

   :::image type="content" source="media/PQ_corruped_date.png" alt-text="Power Query- Uredi, ki prikazuje napačno obliko datuma":::

1. Spremenite vrsto podatkov, da se bodo pravilno ujemali s podatki.

1. Izberite **Shrani**. Ta vir podatkov je osvežen.

## <a name="troubleshoot-ppdf-power-query-based-data-source-refresh-issues"></a>Odpravite težave s PPDF Power Query na osnovi vir podatkov težave z osveževanjem

Če so podatki zastareli ali prejmete napake po vir podatkov osvežitvi, izvedite naslednje korake:

1. Obiščite spletno mesto [Power Platform](https://make.powerapps.com).

1. Izberite **okolje** za vaš primerek Customer Insights.

1. Pojdite na **Podatkovni tokovi**.

1. Za tok podatkov, ki ustreza vir podatkov v Customer Insights, izberite navpično elipso (&vellip;) in nato izberite **Prikaži zgodovino osveževanja**.

1. Če je **Stanje** podatkovnega toka je **Uspeh**, lastništvo nad Power Query na osnovi vir podatkov se je morda spremenilo:

   1. Preglejte urnik osveževanja iz zgodovine osveževanja.
   1. Nastavite urnik novega lastnika in shranite nastavitve.

1. Če je **Stanje** podatkovnega toka je **Ni uspelo**:

   1. Prenesite datoteko z zgodovino osveževanja.
   1. Preglejte preneseno datoteko in poiščite razlog za napako.
   1. Če napake ni mogoče odpraviti, izberite **?** Da odprete vstopnico za podporo. Vključite preneseno datoteko zgodovine osveževanja.


[!INCLUDE [footer-include](includes/footer-banner.md)]
