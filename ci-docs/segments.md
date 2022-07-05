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
ms.openlocfilehash: 8b2c2f9b84bf8b7f37d1468b871946ecb3e6aa98
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9050967"
---
# <a name="segments-overview"></a>Pregled segmentov

Segmenti vam omogočajo, da svoje stranke razvrstite na podlagi demografskih, transakcijskih ali vedenjskih atributov. Segmente lahko uporabite za ciljanje promocijskih akcij, prodajnih dejavnosti in ukrepov za podporo strankam, da dosežete svoje poslovne cilje.

Profili strank, ki se ujemajo s filtri definicije segmenta, se imenujejo *člani* segmenta. Veljajo nekatere [omejitve storitev](/dynamics365/customer-insights/service-limits).

## <a name="create-a-new-segment"></a>Ustvarjanje novega segmenta

Nov segment lahko ustvarite na več načinov: 

# <a name="individual-consumers-b-to-c"></a>[Posamezni potrošniki (prodaja strankam)](#tab/b2c)

- Zapleteni segment z graditeljem segmentov: [Zgradimo svojega](segment-builder.md#create-a-new-segment) 
- Preprosti segmenti z enim operatorjem: [Hitri segment](segment-builder.md#quick-segments) 
- Možnost na podlagi umetne inteligence za iskanje podobnih strank: [Podobne stranke](find-similar-customer-segments.md) 
- Predlogi z umetno inteligenco, ki temeljijo na merah ali atributih: [Predlagani segmenti za izboljšanje mer](suggested-segments.md) 
- Predlogi na podlagi dejavnosti: [Predlagani segmenti na podlagi dejavnosti strank](suggested-segments-activity.md) 

# <a name="business-accounts-b-to-b"></a>[Poslovni računi (podjetja podjetjem)](#tab/b2b)

- Zapleteni segment z graditeljem segmentov: [Zgradimo svojega](segment-builder.md#create-a-new-segment)

---

## <a name="manage-existing-segments"></a>Upravljanje obstoječih segmentov

Pojdite na **segmenti** stran za ogled vseh shranjenih segmentov in njihovo upravljanje.

Vsak segment predstavlja vrstica, ki vključuje dodatne informacije o segmentu.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Izbrani segment s spustnim seznamom možnosti in razpoložljivimi možnostmi." lightbox="media/segments-selected-segment.png":::

Ko izberete segment, so na voljo naslednja dejanja:

- Na voljo je **Prikaz** podrobnosti o odsekih, vključno s trendom števila članov in predogledom članov segmenta.
- Na voljo je možnost **Prenesi** za prenos seznama članov kot datoteke .CSV.
- Za spreminjanje lastnosti segmenta lahko uporabite možnost **Uredi**.
- **Ustvarjanje dvojnika** segmenta. Izberete lahko, da takoj uredite njegove lastnosti ali shranite dvojnik.
- Za vključitev najnovejših podatkov lahko izberete **Osveži**.
- Segment lahko aktivirate ali deaktivirate prek možnosti **Aktiviraj** ali **Deaktiviraj**. Za neaktivne segmente definicija segmenta obstaja, vendar še ne vsebuje nobene stranke. Aktivni segment išče stranke, ki ustrezajo definiciji segmenta. Če je konfigurirana [načrtovana osvežitev](system.md#schedule-tab), je **Stanje** neaktivnih segmentov navedeno kot **Preskočeno**, kar pomeni, da poskusa osveževanja sploh ni bilo. Ko se aktivira neaktivni segment, se bo osvežil in bo vključen v načrtovane osvežitve.
  Lahko pa uporabite funkcijo **Razporedi pozneje** v spustnem meniju **Aktiviraj/Deaktivira**, da določite datum in čas v prihodnosti za aktiviranje in deaktiviranje določenega segmenta.
- **[Poiščite podobne stranke](find-similar-customer-segments.md)** iz segmenta.
- Prek možnosti **Preimenuj** lahko segment preimenujete.
- **Oznaka** do [upravljati oznake](work-with-tags-columns.md#manage-tags) za segment.
- Na voljo je možnost **Prenesi** za prenos seznama članov kot datoteke .CSV.
- Izberite **Upravljanje izvozov**, da se vam prikaže segment, povezan z izvozi, ki jih lahko upravljate. [Preberite več o izvozih.](export-destinations.md)
- Za brisanje je na voljo možnost **Izbriši**.
- **Stolpci** do [prilagodite stolpce](work-with-tags-columns.md#customize-columns) tisti zaslon.
- **Filter** do [filter na oznakah](work-with-tags-columns.md#filter-on-tags).
- **Išči ime** za iskanje po imenu segmenta.

## <a name="refresh-segments"></a>Osveževanje segmentov

Vse segmente lahko osvežite naenkrat tako, da izberete **Osveži vse** na strani **Segmenti**, ali pa lahko osvežite enega ali več segmentov, ko jih izberete in nato izberete **Osveži** v možnostih. Lahko pa konfigurirate ponavljajoče se osveževanje prek možnosti **Skrbnik** > **Sistem** > **Načrtovanje**. Ko je konfigurirana ponavljajoča se osvežitev, veljajo naslednja pravila:

- Vsi segmenti z vrsto **Dinamično** oz **Razširitev** se samodejno osveži ob nastavljeni kadenci. Ko je osvežitev končana, **Stanje** označuje, ali je prišlo do težav pri osveževanju segmenta. The **Nazadnje osveženo** prikazuje časovni žig zadnje uspešne osvežitve. Če pride do napake, izberite napako, da si ogledate podrobnosti o tem, kaj se je zgodilo.
- Segmenti z vrsto **Statično** *ne bo* se samodejno osveži. The **Nazadnje osveženo** prikazuje časovni žig zadnjega ročnega zagona ali osveževanja statičnih segmentov.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Izvoz segmentov

Segment lahko izvozite s strani s segmenti ali s [strani z izvozi](export-destinations.md). 

1. Pojdite na stran **Segmenti**.

1. Izberite navpično elipso (&vellip;) za segment, ki ga želite izvoziti.

1. Na spustnem seznamu izberite možnost **Upravljanje izvozov**.

1. Odpre se stran **Izvozi (predogledna različica) za segment**. Ogledate si lahko vse konfigurirane izvoze, razvrščene glede na to, ali vsebujejo trenutni segment ali ne.

   1. Če želite izbranemu segmentu dodati izvoz, izberite **Uredi** za ta izvoz, da izberete ustrezen segment, nato pa ga shranite. V okoljih za posamezne stranke lahko namesto tega izberete izvoz na seznamu in izberete **Dodaj segment** da bi dosegli enak rezultat.

   1. Če želite ustvariti nov izvoz z izbranim segmentom, izberite **Dodaj izvoz**. Za več informacij o ustvarjanju izvozov glejte [Nastavitev novega izvoza](export-destinations.md#set-up-a-new-export).

1. Izberite **Nazaj** za vrnitev na glavno stran za segmente.

## <a name="track-usage-of-a-segment"></a>Sledite uporabi segmenta

Če uporabljate segmente v aplikacijah, ki temeljijo na istem Microsoft Dataverse organizaciji, ki je povezana s Customer Insights, lahko spremljate uporabo segmenta. Za [Segmenti Customer Insights, ki se uporabljajo na poteh strank v Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile), vas sistem obvesti o uporabi tega segmenta.

Ko urejate segment, ki se uporablja v okolju Customer Insights ali v dejavnosti strank v marketingu, se pasica v [graditelj segmentov](segment-builder.md) vas obvešča o odvisnostih. Podrobnosti odvisnosti si lahko ogledate neposredno iz pasice ali z izbiro **Uporaba** v graditelju segmentov.

The **Uporaba segmenta** podokno prikazuje podrobnosti o uporabi tega segmenta v Dataverse -osnovane aplikacije. Za segmente, ki se uporabljajo pri poteh strank, boste našli povezavo za pregled poti v Marketingu, kjer se ta segment uporablja. Če imate dovoljenja za dostop do aplikacije Marketing, lahko tam dostopate do več podrobnosti.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Stransko podokno s podrobnostmi o uporabi segmenta v ustvarjalniku segmentov.":::

Sistem vas obvesti o uporabi sledinega segmenta, ko ga poskušate izbrisati. Če je segment, ki ga nameravate izbrisati, uporabljen v dejavnosti strank v trženju, se bo to pot ustavilo za vse uporabnike v segmentu. Če je potovanje del marketinške kampanje, bo izbris vplival na to samo kampanjo. Kljub opozorilom pa lahko segment še vedno izbrišete.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Pogovorno okno za potrditev izbrisa segmenta, ko je segment uporabljen v a Dataverse aplikacijo.":::

### <a name="supported-apps"></a>Podprte aplikacije

Poraba se trenutno spremlja v naslednjem Dataverse -osnovane aplikacije:

- [Potovanja strank v Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="view-processing-history-and-segment-members"></a>Prikaz zgodovine obdelave in članov segmenta

Usklajene podatke o segmentu si lahko ogledate tako, da pregledate njegove podrobnosti.

Na strani **Segmenti** izberite segment, ki ga želite pregledati.

Zgornji del strani vključuje grafikon trenda, ki prikazuje spremembe v številu članov. S kazalcem miške pokažite na podatkovne točke, da si ogledate število članov na določen datum.

Časovni okvir vizualizacije lahko posodobite.

> [!div class="mx-imgBorder"]
> ![Časovni obseg segmenta.](media/segment-time-range.png "Časovni obseg segmenta")

Spodnji del vsebuje seznam članov segmenta.

> [!NOTE]
> Polja, ki se prikažejo na tem seznamu, temeljijo na atributih entitet vašega segmenta.
>
>Seznam je predogled ujemajočih se članov segmenta in prikazuje prvih 100 zapisov vašega segmenta, tako da ga lahko po potrebi hitro ocenite in pregledate njegove definicije. Če si želite ogledati vse ujemajoče se zapise, morate [izvoziti segment](export-destinations.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
