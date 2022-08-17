---
title: Posodobite nastavitve združevanja
description: Posodobite podvojena pravila, pravila ujemanja ali poenotena polja v nastavitvah poenotenja.
ms.date: 06/01/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: a7cf06c07e4b95b848a55dfe5fe0b09397fe744e
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245614"
---
# <a name="update-the-unification-settings"></a>Posodobite nastavitve združevanja

Če želite pregledati ali spremeniti katere koli nastavitve združevanja, ko je poenoten profil ustvarjen, izvedite naslednje korake.

1. Pojdi do **podatki** > **Poenotiti**.

   :::image type="content" source="media/m3_unified.png" alt-text="Posnetek zaslona strani Data Unify po poenotenju podatkov.":::

   > [!TIP]
   > The **Ujemanje pogojev** ploščica se prikaže le, če je izbranih več entitet.

1. Izberite, kaj želite posodobiti:
   - [Izvorna polja](#edit-source-fields) za dodajanje entitet ali atributov ali spreminjanje vrst atributov.
   - [Podvojeni zapisi](#manage-deduplication-rules) za upravljanje pravil za odstranjevanje podvojitev ali preferenc združevanja.
   - [Ujemanje pogojev](#manage-match-rules) za posodobitev pravil ujemanja v dveh ali več entitetah.
   - [Enotna polja za stranke](#manage-unified-fields) za združevanje ali izključitev polj. Povezane profile lahko tudi združite v gruče.

1. Po spremembah izberite naslednjo možnost:

   :::image type="content" source="media/m3_run_match_merge.png" alt-text="Posnetek zaslona strani Data Unify z označenimi možnostmi Unify.":::

   - [Izvedite pogoje ujemanja](#run-matching-conditions) za hitro oceno kakovosti vaših pogojev ujemanja (deduplikacija in pravila ujemanja) brez posodabljanja poenotenega profila. The **Zaženi samo pogoje, ki se ujemajo** možnost se ne prikaže za posamezno entiteto.
   - [Poenotite profile strank](#run-updates-to-the-unified-customer-profile) za izvajanje pogojev ujemanja in posodobitev enote poenotenega profila stranke brez vplivanja na odvisnosti (kot so obogatitve, segmenti ali mere). Odvisni procesi se ne izvajajo, ampak bodo osveženi kot [določeno v urniku osveževanja](schedule-refresh.md).
   - [Poenotite profile strank in odvisnosti](#run-updates-to-the-unified-customer-profile) za izvajanje pogojev ujemanja in posodobitev enote poenotenega profila stranke in vseh odvisnosti (kot so obogatitve, segmenti ali mere). Vsi procesi se samodejno znova izvedejo.

## <a name="edit-source-fields"></a>Uredi izvorna polja

Atributa ali entitete ne morete odstraniti, če sta že poenotena.

1. Izberite **Uredi** na **Izvorna polja** ploščica.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Posnetek zaslona strani Source fields, ki prikazuje število primarnih ključev, preslikanih in nepreslikanih polj":::

   Prikaz števila preslikanih in nepreslikanih polj.

1. Izberite **Izberite entitete in polja** za dodajanje drugih atributov ali entitet. Z iskanjem ali drsanjem navzdol in navzgor poiščite atribute in entitete, ki vas zanimajo, in jih izberite. Izberite **Uporabi**.

1. Po želji lahko spremenite primarni ključ za entiteto, vrste atributov in preklop **Inteligentno kartiranje** vklop ali izklop. Za več informacij glejte [Izberite primarni ključ in semantično vrsto za atribute](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Izberite **Naslednji** če želite spremeniti pravila za odstranjevanje podvojitev, ali izberite **Shrani in zapri** in se vrniti k [Posodobite nastavitve združevanja](#update-the-unification-settings).

## <a name="manage-deduplication-rules"></a>Upravljajte pravila deduplikacije

1. Izberite **Uredi** na **Podvojeni zapisi** ploščica.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Posnetek zaslona strani s podvojenimi zapisi, ki prikazuje število podvojenih zapisov" lightbox="media/m3_duplicates_edit.png":::

   Število najdenih podvojenih zapisov je prikazano pod **Dvojniki**. The **Zapisi so deduplicirani** prikazuje, katere entitete so imele podvojene zapise in odstotek podvojenih zapisov.

1. Če ste dodali obogateno entiteto, izberite **Uporabite obogatene entitete**. Za več informacij glejte [Obogatitev podatkovnih virov](data-sources-enrichment.md).

1. Če želite upravljati pravila za odstranjevanje dvojnikov, izberite katero koli od naslednjih možnosti:
   - **Ustvarite novo pravilo** : Izberite **Dodaj pravilo** pod ustreznim subjektom. Za več informacij glejte [Določite pravila deduplikacije](remove-duplicates.md#define-deduplication-rules).
   - **Spremenite pogoje pravil** : Izberite pravilo in nato **Uredi**. Spremenite polja, dodajte ali odstranite pogoje ali dodajte ali odstranite izjeme.
   - **Predogled** : Izberite pravilo in nato **Predogled** za ogled zadnjih rezultatov za to pravilo.
   - **Deaktivirajte pravilo** : Izberite pravilo in nato **Deaktiviraj** da obdržite pravilo deduplikacije in ga izključite iz postopka ujemanja.
   - **Podvoji pravilo** : Izberite pravilo in nato **Dvojnik** ustvariti podobno pravilo s spremembami.
   - **Izbriši pravilo** : Izberite pravilo in nato **Izbriši**.

1. Če želite spremeniti nastavitve spajanja, izberite entiteto. Nastavitve lahko spremenite le, če je ustvarjeno pravilo.
   1. Izberite **Uredite nastavitve spajanja** in spremenite **Evidenca za vodenje** možnost.
   1. Če želite spremeniti nastavitve spajanja za posamezne atribute entitete, izberite **Napredno** in naredite potrebne spremembe.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Posnetek zaslona naprednih nastavitev združevanja, ki prikazuje najnovejšo e-pošto in najbolj popoln naslov":::

   1. Izberite **Dokončano**.

1. Izberite **Naslednji** če želite spremeniti pogoje ujemanja, ali izberite **Shrani in zapri** in se vrniti k [Posodobite nastavitve združevanja](#update-the-unification-settings).

## <a name="manage-match-rules"></a>Upravljanje pravil ujemanja

Večino parametrov ujemanja lahko znova konfigurirate in prilagodite. Entitet ne morete dodajati ali brisati. Pravila ujemanja ne veljajo za posamezno entiteto.

1. Izberite **Uredi** na **Ujemanje pogojev** ploščica.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Posnetek zaslona strani s pravili in pogoji tekme s statistiko." lightbox="media/m3_match_edit.png":::

   Stran prikazuje vrstni red ujemanja in definirana pravila ter naslednjo statistiko:
   - **Enolični izvorni zapisi** prikazuje število posameznih izvornih zapisov, ki so bili obdelani v zadnjem izvajanju ujemanja.
   - **Ujemajoči se in neujemajoči se zapisi** označujejo, koliko enoličnih zapisov ostane po obdelavi pravil ujemanja.
   - **Samo ujemajoči se zapisi** prikazuje število ujemanj v vseh vaših parih ujemanja.

1. Za ogled rezultatov vseh pravil in njihovih točk izberite **Oglejte si zadnjo vožnjo**. Prikažejo se rezultati, vključno z nadomestnimi ID-ji stikov. Rezultate lahko prenesete.

1. Za ogled rezultatov in rezultatov določenega pravila izberite pravilo in nato **Predogled**. Prikažejo se rezultati. Rezultate lahko prenesete.

1. Če si želite ogledati rezultate določenega pogoja za pravilo, izberite pravilo in nato **Uredi**. V podoknu za urejanje izberite **Predogled** pod pogojem. Rezultate lahko prenesete.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Grafična predstavitev neujemajočih se in ujemajočih se zapisov, vključno s seznamom podatkov.":::

1. Če ste dodali obogateno entiteto, izberite **Uporabite obogatene entitete**. Za več informacij glejte [Obogatitev podatkovnih virov](data-sources-enrichment.md).

1. Za upravljanje pravil izberite katero koli od naslednjih možnosti:
   - **Ustvarite novo pravilo** : Izberite **Dodaj pravilo** pod ustreznim subjektom. Za več informacij glejte [Določite pravila za ujemanje parov](match-entities.md#define-rules-for-match-pairs).
   - **Spremenite vrstni red svojih pravil** če ste definirali več pravil: povlecite in spustite pravila v želenem vrstnem redu. Za več informacij glejte [Določite vrstni red ujemanja](match-entities.md#specify-the-match-order).
   - **Spremenite pogoje pravil** : Izberite pravilo in nato **Uredi**. Spremenite polja, dodajte ali odstranite pogoje ali dodajte ali odstranite izjeme.
   - **Deaktivirajte pravilo** : Izberite pravilo in nato **Deaktiviraj** da obdržite pravilo ujemanja in ga izključite iz postopka ujemanja.
   - **Podvoji pravilo** : Izberite pravilo in nato **Dvojnik** ustvariti podobno pravilo s spremembami.
   - **Izbriši pravilo** : Izberite pravilo in nato **Izbriši**.

1. Izberite **Naslednji** če želite spremeniti poenotena polja, ali izberite **Shrani in zapri** in se vrniti k [Posodobite nastavitve združevanja](#update-the-unification-settings).

## <a name="manage-unified-fields"></a>Upravljajte poenotena polja

1. Izberite **Uredi** na **Enotna polja za stranke** ploščica.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Posnetek zaslona poenotenih polj strank":::

1. Preglejte združena in izključena polja ter po potrebi spremenite. Dodajte ali uredite ključ CustomerID ali profile skupin v gruče. Za več informacij glejte [Poenotite polja strank](merge-entities.md).

1. Izberite **Naslednji** za pregled nastavitev združevanja in [posodobite poenoten profil in odvisnosti](#run-updates-to-the-unified-customer-profile) ali izberite **Shrani in zapri** in se vrniti k [Posodobite nastavitve združevanja](#update-the-unification-settings) narediti več sprememb.

## <a name="run-matching-conditions"></a>Izvedite pogoje ujemanja

Zaženite samo odstranjevanje podvajanj za izvedbe pogojev ujemanja in pravila ujemanja ter posodobite entiteti *Deduplication_* in *ConflationMatchPair*.

1. Iz **podatki** > **Poenotiti** stran, izberite **Zaženi samo pogoje, ki se ujemajo**.

   The **Podvojeni zapisi** in **Ujemanje pogojev** ploščice kažejo **V čakalni vrsti** oz **Osvežujoče** stanje.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Ko je postopek ujemanja končan, izberite **Uredi** na **Ujemanje pogojev** ploščica.

   :::image type="content" source="media/match-KPIs.png" alt-text="Obrezan posnetek zaslona ključnih meritev na strani «Ujemanje» s številkami in podrobnostmi.":::

1. Če želite narediti spremembe, glejte [Upravljajte pravila deduplikacije](#manage-deduplication-rules) oz [Upravljajte pravila tekem](#manage-match-rules).

1. Ponovno zaženite postopek ujemanja oz [izvajati posodobitve profila stranke](#run-updates-to-the-unified-customer-profile).

## <a name="run-updates-to-the-unified-customer-profile"></a>Zaženite posodobitve poenotenega profila stranke

1. Iz **podatki** > **Poenotiti** strani izberite:

   - **Poenotite profile strank** : izvaja pogoje ujemanja in posodablja entiteto poenotenega profila stranke, ne da bi vplival na odvisnosti (kot so obogatitve, segmenti ali mere). Odvisni procesi se ne izvajajo, ampak bodo osveženi kot [določeno v urniku osveževanja](schedule-refresh.md).

   - **Poenotite profile strank in odvisnosti** : Zažene ujemajoče se pogoje in posodobi poenoten profil in vse odvisnosti. Vsi procesi se samodejno znova izvedejo. Ko so zaključeni vsi nadaljnji procesi, profil stranke odraža posodobljene podatke.

   The **Podvojeni zapisi**, **pogojev**, in **Enotna polja za stranke** ploščice kažejo **V čakalni vrsti** oz **Osvežujoče** stanje.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Rezultati uspešnega teka so prikazani na **Poenotiti** stran, ki prikazuje število enotnih profilov strank.
