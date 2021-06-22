---
title: Segmenti v vpogledih v občinstvo
description: Pregled segmentov ter napotki, kako jih ustvariti in upravljati.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6cb7bd62bf0f61e6dc5811b20e5011e4a086c743
ms.sourcegitcommit: 84283d523a891298fca8aaf629d9f9ab2a1bc067
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 05/27/2021
ms.locfileid: "6111407"
---
# <a name="segments-overview"></a>Pregled segmentov

Segmenti vam omogočajo, da svoje stranke razvrstite na podlagi demografskih, transakcijskih ali vedenjskih atributov. Segmente lahko uporabite za ciljanje promocijskih akcij, prodajnih dejavnosti in ukrepov za podporo strankam, da dosežete svoje poslovne cilje.

Profili strank, ki se ujemajo s filtri definicije segmenta, se imenujejo *člani* segmenta. Veljajo nekatere [omejitve storitev](service-limits.md).

## <a name="create-a-new-segment"></a>Ustvarjanje novega segmenta

Nov segment lahko ustvarite na več načinov: 

- Kompleksni segment z graditeljem segmentov: [Prazen segment](segment-builder.md#create-a-new-segment)
- Preprosti segmenti z enim operatorjem: [Hitri segment](segment-builder.md#quick-segments)
- Možnost na podlagi umetne inteligence za iskanje podobnih strank: [Podobne stranke](find-similar-customer-segments.md)
- Predlogi z umetno inteligenco, ki temeljijo na merah ali atributih: [Predlagani segmenti za izboljšanje mer](suggested-segments.md)
- Predlogi na podlagi dejavnosti: [Predlagani segmenti na podlagi dejavnosti strank](suggested-segments-activity.md)

## <a name="manage-existing-segments"></a>Upravljanje obstoječih segmentov

Odprite stran **Segmenti**, da si ogledate vse shranjene segmente in jih upravljate.

Vsak segment predstavlja vrstica, ki vključuje dodatne informacije o segmentu.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Izbrani segment s spustnim seznamom možnosti in razpoložljivimi možnostmi.":::

Ko izberete segment, je na voljo naslednje dejanje:

- Na voljo je **Prikaz** podrobnosti o odsekih, vključno s trendom števila članov in predogledom članov segmenta.
- Za spreminjanje lastnosti segmenta lahko uporabite možnost **Uredi**.
- **Ustvarjanje dvojnika** segmenta. Takoj lahko uredite njegove lastnosti ali preprosto shranite dvojnik.
- Za vključitev najnovejših podatkov lahko izberete **Osveži**.
- Segment lahko aktivirate ali deaktivirate prek možnosti **Aktiviraj** ali **Deaktiviraj**. Segmenti imajo dve možni stanji - aktivno ali neaktivno. Stanji sta vam lahko v pomoč pri urejanju segmenta. Za neaktivne segmente definicija segmenta obstaja, vendar še ne vsebuje nobene stranke. Ko aktivirate segment, se njegovo stanje spremeni iz »neaktiven« v »aktiven« in začne iskati stranke, ki ustrezajo definiciji segmenta. Če je konfigurirana [načrtovana osvežitev](system.md#schedule-tab), je **Stanje** neaktivnih segmentov navedeno kot **Preskočeno**, kar pomeni, da poskusa osveževanja sploh ni bilo. Ko se aktivira neaktivni segment, se bo osvežil in bo vključen v načrtovane osvežitve.
  Lahko pa uporabite funkcijo **Razporedi pozneje** v spustnem meniju **Aktiviraj/Deaktivira**, da določite datum in čas v prihodnosti za aktiviranje in deaktiviranje določenega segmenta.
- Prek možnosti **Preimenuj** lahko segment preimenujete.
- Na voljo je možnost **Prenesi** za prenos seznama članov kot datoteke .CSV.
- Izberite **Upravljanje izvozov**, da se vam prikaže segment, povezan z izvozi, ki jih lahko upravljate. [Preberite več o izvozih.](export-destinations.md)
- Za brisanje je na voljo možnost **Izbriši**.

## <a name="refresh-segments"></a>Osveževanje segmentov

Vse segmente lahko osvežite naenkrat tako, da izberete **Osveži vse** na strani **Segmenti**, ali pa lahko osvežite enega ali več segmentov, ko jih izberete in nato izberete **Osveži** v možnostih. Lahko pa konfigurirate ponavljajoče se osveževanje prek možnosti **Skrbnik** > **Sistem** > **Načrtovanje**.

> [!TIP]
> Na voljo je [šest vrst stanja](system.md#status-types) za opravila/postopke. Poleg tega je večina postopkov [odvisna od drugih nadaljnjih postopkov](system.md#refresh-policies). Izberete lahko stanje postopka in si ogledate podrobnosti o poteku celotnega posla. Ko za enega izmed poslov izberete **Prikaži podrobnosti**, se prikažejo dodatne informacije: čas obdelave, zadnji datum obdelave ter vse napake in opozorila, povezana z opravilom.

## <a name="export-segments"></a>Izvoz segmentov

Segment lahko izvozite s strani s segmenti ali s [strani z izvozi](export-destinations.md). 

1. Pojdite na stran **Segmenti**.

1. Izberite **Pokaži več [...]** za segment, ki ga želite izvoziti.

1. Izberite **Upravljanje izvozov** na spustnem seznamu z dejanji.

1. Odpre se stran **Izvozi (predogledna različica) za segment**. Ogledate si lahko vse konfigurirane izvoze, razvrščene po izvozih, ki trenutni segment vsebujejo ali ne.

   1. Če želite izbrani segment dodati izvozu, izberite izvoz na seznamu in nato **Dodaj segment**.

   1. Če želite ustvariti nov izvoz z izbranim segmentom, izberite **Dodaj izvoz**. Za več informacij o ustvarjanju izvozov glejte [Nastavitev novega izvoza](export-destinations.md#set-up-a-new-export).

1. Izberite **Nazaj** za vrnitev na glavno stran za segmente.

## <a name="view-processing-history-and-segment-members"></a>Prikaz zgodovine obdelave in članov segmenta

Usklajene podatke o segmentu si lahko ogledate tako, da pregledate njegove podrobnosti.

Na strani **Segmenti** izberite segment, ki ga želite pregledati.

Zgornji del strani vključuje grafikon trenda, ki prikazuje spremembe v številu članov. S kazalcem miške pokažite na podatkovne točke, da si ogledate število članov na določen datum.

Časovni okvir vizualizacije lahko posodobite.

> [!div class="mx-imgBorder"]
> ![Časovni obseg segmenta](media/segment-time-range.png "Časovni obseg segmenta")

Spodnji del vsebuje seznam članov segmenta.

> [!NOTE]
> Polja, ki se prikažejo na tem seznamu, temeljijo na atributih entitet vašega segmenta.
>
>Seznam je predogled ujemajočih se članov segmenta in prikazuje prvih 100 zapisov vašega segmenta, tako da ga lahko po potrebi hitro ocenite in pregledate njegove definicije. Če si želite ogledati vse ujemajoče se zapise, morate [izvoziti segment](export-destinations.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
