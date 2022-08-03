---
title: Pregled segmentov
description: Pregled segmentov ter napotki, kako jih ustvariti in upravljati.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-customers-page
- ci-enrichment-details
- ci-segments
- ci-segment-details
- customerInsights
ms.openlocfilehash: 4bcfbb50b893ca7e6ec4607d3c156a3c6979f775
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170701"
---
# <a name="segments-overview"></a>Pregled segmentov

Segmenti vam omogočajo, da svoje stranke razvrstite na podlagi demografskih, transakcijskih ali vedenjskih atributov. Segmente lahko uporabite za ciljanje promocijskih akcij, prodajnih dejavnosti in ukrepov za podporo strankam, da dosežete svoje poslovne cilje.

Profili strank, ki se ujemajo s filtri definicije segmenta, se imenujejo *člani* segmenta. Veljajo nekatere [omejitve storitev](/dynamics365/customer-insights/service-limits).

## <a name="create-a-segment"></a>Ustvarjanje segmenta

Izberite, kako ustvariti segment na podlagi cilja občinstvo.

# <a name="individual-consumers-b-to-c"></a>[Posamezni potrošniki (prodaja strankam)](#tab/b2c)

- Kompleksni segmenti z graditeljem segmentov: [Zgradite svojega](segment-builder.md)
- Preprosti segmenti z enim operatorjem: [Hitri segment](segment-quick.md)
- Način iskanja podobnih strank, ki ga poganja AI: [Podobne stranke](find-similar-customer-segments.md)
- Predlogi, ki jih poganja AI na podlagi mer ali atributov: [Predlagani segmenti na podlagi mer](suggested-segments.md)
- Predlogi na podlagi dejavnosti: [Predlagani segmenti na podlagi dejavnosti strank](suggested-segments-activity.md)

# <a name="business-accounts-b-to-b"></a>[Poslovni računi (podjetja podjetjem)](#tab/b2b)

- Preprosti ali zapleteni segmenti z graditeljem segmentov: [Zgradite svojega](segment-builder.md)

---

## <a name="manage-existing-segments"></a>Upravljanje obstoječih segmentov

Pojdi na **Segmenti** strani za ogled segmentov, ki ste jih ustvarili, njihov status in stanje, število članov in čas zadnje osvežitve podatkov. Seznam segmentov lahko razvrstite po katerem koli stolpcu ali uporabite iskalno polje, da poiščete segment, ki ga želite upravljati.

Izberite segment za ogled razpoložljivih dejanj.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Izbrani segment s spustnim seznamom možnosti in razpoložljivimi možnostmi." lightbox="media/segments-selected-segment.png":::

- [**Pogled**](#view-segment-details) podrobnosti segmenta, vključno s trendom števila članov in predogledom članov segmenta.
- Na voljo je možnost **Prenesi** za prenos seznama članov kot datoteke .CSV.
- Za spreminjanje lastnosti segmenta lahko uporabite možnost **Uredi**.
- **Ustvarjanje dvojnika** segmenta. Lahko se odločite za takojšnje urejanje njegovih lastnosti ali shranjevanje dvojnika.
- [**Osveži**](#refresh-segments) segment za vključitev najnovejših podatkov.
- Segment lahko aktivirate ali deaktivirate prek možnosti **Aktiviraj** ali **Deaktiviraj**. Neaktivni segmenti se ne bodo osvežili med a [načrtovano osveževanje](system.md#schedule-tab) in imeti **Stanje** naveden kot **Preskočeno**, kar pomeni, da osvežitev sploh ni bila izvedena. Aktivni segmenti se osvežujejo glede na njihovo vrsto: statični ali dinamični.
- **Naredi statično** oz **Naredite dinamično** vrsto segmenta. Statične segmente je treba osvežiti ročno. Dinamični segmenti se med osveževanjem sistema samodejno osvežujejo.
- [**Poiščite podobne stranke**](find-similar-customer-segments.md) iz segmenta.
- Prek možnosti **Preimenuj** lahko segment preimenujete.
- **Oznaka** do [upravljanje oznak](work-with-tags-columns.md#manage-tags) za segment.
- [**Upravljajte izvoze**](#export-segments) da vidite segmente, povezane z izvozom, in jih upravljate. [Preberite več o izvozih.](export-destinations.md)
- Za brisanje je na voljo možnost **Izbriši**.
- **Stolpci** do [prilagodite stolpce](work-with-tags-columns.md#customize-columns) ta zaslon.
- **Filter** do [filter po oznakah](work-with-tags-columns.md#filter-on-tags).
- **Ime iskanja** za iskanje po imenu segmenta.

## <a name="view-segment-details"></a>Oglejte si podrobnosti segmenta

Na **Segmenti** izberite segment za ogled zgodovine obdelave in članov segmenta.

Zgornji del strani vključuje grafikon trenda, ki prikazuje spremembe v številu članov. S kazalcem miške pokažite na podatkovne točke, da si ogledate število članov na določen datum. Spremenite časovni okvir vizualizacije.

:::image type="content" source="media/segment-time-range.png" alt-text="Časovni obseg segmenta.":::

Spodnji del vsebuje seznam članov segmenta.

> [!NOTE]
> Polja, ki se prikažejo na tem seznamu, temeljijo na atributih entitet vašega segmenta.
>
>Seznam je predogled ujemajočih se članov segmenta in prikazuje prvih 100 zapisov vašega segmenta, tako da ga lahko po potrebi hitro ocenite in pregledate njegove definicije. Če želite videti vse ujemajoče se zapise, [izvozite segment](export-destinations.md).

## <a name="refresh-segments"></a>Osveževanje segmentov

Segmente je mogoče osveževati po samodejnem urniku ali ročno na zahtevo. Če želite ročno osvežiti enega ali več segmentov, jih izberite in izberite **Osveži**.

Za [načrtujte samodejno osveževanje](system.md#schedule-tab), Pojdi do **skrbnik** > **Sistem** > **Urnik**. Veljajo naslednja pravila:

- Vsi segmenti z vrsto **Dinamično** oz **Razširitev** bo samodejno osveženo pri nastavljeni kadenci. Ko je osvežitev končana, se **Stanje** označuje, ali je prišlo do težav pri osveževanju segmenta. The **Nazadnje osveženo** prikazuje časovni žig zadnje uspešne osvežitve. Če pride do napake, izberite napako, da si ogledate podrobnosti o tem, kaj se je zgodilo.
- Segmenti z vrsto **Statično** *ne bo* se samodejno osveži. The **Nazadnje osveženo** prikazuje časovni žig zadnjega ročnega zagona ali osveževanja statični segment.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Izvoz segmentov

Izvozite segmente v druge aplikacije za nadaljnjo uporabo podatkov. Izvozite segment s strani segmentov ali [izvozna stran](export-destinations.md).

1. Pojdi na **Segmenti** in izberite segment, ki ga želite izvoziti.

1. Izberite **Upravljajte izvoze**. Odpre se stran **Izvozi (predogledna različica) za segment**. Oglejte si vse konfigurirane izvoze, razvrščene glede na to, ali vsebujejo trenutni segment ali ne.

   1. Če želite izbranemu segmentu dodati izvoz, izberite **Uredi** za ta izvoz, da izberete ustrezen segment, nato pa ga shranite. V okoljih za posamezne stranke na seznamu izberite izvoz in izberite **Dodaj segment** da bi dosegli enak rezultat.

   1. Če želite ustvariti nov izvoz z izbranim segmentom, izberite **Dodaj izvoz**. Za več informacij o ustvarjanju izvozov glejte [Nastavitev novega izvoza](export-destinations.md#set-up-a-new-export).

1. Izberite **Nazaj** za vrnitev na glavno stran za segmente.

## <a name="track-usage-of-a-segment"></a>Sledite uporabi segmenta

Če uporabljate segmente v aplikacijah, ki temeljijo na istem Microsoft Dataverse organizacije, ki je povezana s Customer Insights, lahko sledite uporabi segmenta. Za [Segmenti Customer Insights, ki se uporabljajo na poti strank Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile), vas sistem obvesti o uporabi tega segmenta.

Pri urejanju segmenta, ki se uporablja v okolju Customer Insights ali v dejavnosti strank v Marketingu, se pasica v [graditelj segmentov](segment-builder.md) vas obvešča o odvisnostih. Preglejte podrobnosti odvisnosti neposredno iz pasice ali z izbiro **Uporaba** v graditelju segmentov.

The **Uporaba segmenta** podokno prikazuje podrobnosti o uporabi tega segmenta v Dataverse aplikacije na osnovi. Za segmente, ki se uporabljajo na poti strank, boste našli povezavo za pregled poti v Marketingu, kjer se ta segment uporablja. Če imate dovoljenja za dostop do aplikacije Marketing, si tam oglejte več podrobnosti.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Stransko podokno s podrobnostmi o uporabi segmenta v graditelju segmentov.":::

Sistem vas obvesti o uporabi sledenega segmenta, ko ga poskušate izbrisati. Če je segment, ki ga nameravate izbrisati, uporabljen v dejavnosti strank v Marketingu, se bo to potovanje ustavilo za vse uporabnike v segmentu. Če je potovanje del marketinške kampanje, bo izbris vplival na samo kampanjo. Vendar lahko segment kljub opozorilom še vedno izbrišete.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Pogovorno okno za potrditev izbrisa segmenta, ko je segment uporabljen v a Dataverse aplikacija.":::

### <a name="supported-apps"></a>Podprte aplikacije

Uporaba se trenutno spremlja v naslednjem Dataverse aplikacije, ki temeljijo na:

- [Potovanja strank v Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile)

[!INCLUDE [footer-include](includes/footer-banner.md)]
