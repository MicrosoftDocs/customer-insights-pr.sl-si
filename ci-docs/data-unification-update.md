---
title: Posodobite nastavitve združevanja
description: Posodobite podvojena pravila, pravila ujemanja ali poenotena polja v nastavitvah združevanja.
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
ms.openlocfilehash: 590a2996cf8b2b1c6def59b78583169ec1910b59
ms.sourcegitcommit: 760fbac397c738407c7dea59297d54cae19b6f57
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844060"
---
# <a name="update-the-unification-settings"></a>Posodobite nastavitve združevanja

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Če želite pregledati ali spremeniti morebitne nastavitve združevanja, ko je poenoten profil ustvarjen, izvedite naslednje korake.

1. Pojdi do **Podatki** > **Združite**.

   :::image type="content" source="media/m3_unified.png" alt-text="Posnetek zaslona strani Data Unify po poenotenju podatkov.":::

   > [!TIP]
   > The **Ujemanje pogojev** ploščica se prikaže samo, če je bilo izbranih več entitet.

1. Izberite, kaj želite posodobiti:
   - [Izvorna polja](#edit-source-fields) za dodajanje entitet ali atributov ali spreminjanje vrst atributov.
   - [Podvojeni zapisi](#manage-deduplication-rules) za upravljanje pravil za odpravo podvajanja ali nastavitev spajanja.
   - [Ujemanje pogojev](#manage-match-rules) za posodobitev pravil ujemanja v dveh ali več entitetah.
   - [Poenotena polja strank](#manage-unified-fields) združiti ali izključiti polja. Povezane profile lahko tudi združite v gruče.

1. Ko naredite spremembe, izberite naslednjo možnost:

   :::image type="content" source="media/m3_run_match_merge.png" alt-text="Posnetek zaslona strani Data Unify z označenimi možnostmi Unify.":::

   - [Zaženite pogoje ujemanja](#run-matching-conditions) da hitro ocenite kakovost vaših pogojev ujemanja (odstranitev podvajanja in pravila ujemanja) brez posodabljanja enotnega profila. The **Zaženite samo pogoje ujemanja** možnost se ne prikaže za posamezno entiteto.
   - [Poenoti profile strank](#run-updates-to-the-unified-customer-profile) za izvajanje pogojev ujemanja in posodobitev enotnega profila stranke brez vpliva na odvisnosti (kot so obogatitve, segmenti ali ukrepi). Odvisni procesi se ne izvajajo, ampak bodo osveženi kot [določeno v urniku osveževanja](system.md#schedule-tab).
   - [Poenoti profile strank in odvisnosti](#run-updates-to-the-unified-customer-profile) za izvajanje pogojev ujemanja in posodobitev enotnega profila stranke in vseh odvisnosti (kot so obogatitve, segmenti ali ukrepi). Vsi procesi se samodejno znova zaženejo.

## <a name="edit-source-fields"></a>Uredite izvorna polja

Atributa ali entitete ne morete odstraniti, če sta že poenotena.

1. Izberite **Uredi** na **Izvorna polja** ploščice.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Posnetek zaslona strani Izvorna polja, ki prikazuje število primarnih ključev, preslikanih in nepreslikanih polj":::

   Prikaže se število preslikanih in nepreslikanih polj.

1. Izberite **Izberite entitete in polja** za dodajanje drugih atributov ali entitet. Z iskanjem ali drsanjem navzdol in navzgor poiščite atribute in entitete, ki vas zanimajo, in jih izberite. Izberite **Uporabi**.

1. Po želji lahko spremenite primarni ključ za entiteto, vrste atributov in preklop **Inteligentno kartiranje** vklopljen ali izklopljen. Za več informacij glejte [Izberite primarni ključ in semantični tip za atribute](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Izberite **Naslednji** če želite spremeniti pravila za odpravo podvajanja, ali izberite **Shrani in zapri** in se vrnite k [Posodobite nastavitve združevanja](#update-the-unification-settings).

## <a name="manage-deduplication-rules"></a>Upravljajte pravila za odpravo podvajanja

1. Izberite **Uredi** na **Podvojeni zapisi** ploščice.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Posnetek zaslona strani Podvojeni zapisi, ki prikazuje število podvojenih zapisov" lightbox="media/m3_duplicates_edit.png":::

   Število najdenih podvojenih zapisov je prikazano pod **Dvojniki**. The **Zapisi odstranjeni** stolpec prikazuje, kateri subjekti so imeli podvojene zapise in odstotek podvojenih zapisov.

1. Če ste dodali obogateno entiteto, izberite **Uporabite obogatene entitete**. Za več informacij glejte [Obogatitev za vire podatkov](data-sources-enrichment.md).

1. Če želite upravljati pravila za odpravo podvajanja, izberite eno od naslednjih možnosti:
   - **Ustvarite novo pravilo** : Izberite **Dodajte pravilo** pod ustreznim subjektom. Za več informacij glejte [Določite pravila za odpravo podvajanja](remove-duplicates.md#define-deduplication-rules).
   - **Spremenite pogoje pravila** : Izberite pravilo in nato **Uredi**. Spremenite polja, dodajte ali odstranite pogoje ali dodajte ali odstranite izjeme.
   - **Predogled** : Izberite pravilo in nato **Predogled** za ogled rezultatov zadnjega izvajanja za to pravilo.
   - **Deaktivirajte pravilo** : Izberite pravilo in nato **Deaktiviraj** obdržati pravilo za odpravo podvajanja, hkrati pa ga izključiti iz postopka ujemanja.
   - **Podvojite pravilo** : Izberite pravilo in nato **Podvojeno** ustvariti podobno pravilo s spremembami.
   - **Izbriši pravilo** : Izberite pravilo in nato **Izbriši**.

1. Če želite spremeniti nastavitve spajanja, izberite entiteto. Nastavitve lahko spremenite samo, če je pravilo ustvarjeno.
   1. Izberite **Uredite nastavitve spajanja** in spremenite **Zapis za shranjevanje** možnost.
   1. Če želite spremeniti nastavitve spajanja za posamezne atribute entitete, izberite **Napredno** in naredite potrebne spremembe.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Posnetek zaslona naprednih nastavitev spajanja, ki prikazuje najnovejšo e-pošto in najbolj popoln naslov":::

   1. Izberite **Dokončano**.

1. Izberite **Naslednji** če želite spremeniti pogoje ujemanja, ali izberite **Shrani in zapri** in se vrnite k [Posodobite nastavitve združevanja](#update-the-unification-settings).

## <a name="manage-match-rules"></a>Upravljanje pravil ujemanja

Večino parametrov ujemanja lahko znova konfigurirate in prilagodite. Entitet ne morete dodajati ali brisati. Pravila tekme ne veljajo za en subjekt.

1. Izberite **Uredi** na **Ujemanje pogojev** ploščice.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Posnetek zaslona strani s pravili in pogoji tekme s statistiko." lightbox="media/m3_match_edit.png":::

   Stran prikazuje vrstni red tekem in definirana pravila ter naslednjo statistiko:
   - **Enolični izvorni zapisi** prikazuje število posameznih izvornih zapisov, ki so bili obdelani v zadnjem izvajanju ujemanja.
   - **Ujemajoči se in neujemajoči se zapisi** označujejo, koliko enoličnih zapisov ostane po obdelavi pravil ujemanja.
   - **Samo ujemajoči se zapisi** prikazuje število ujemanj v vseh vaših parih ujemanja.

1. Če si želite ogledati rezultate vseh pravil in njihove rezultate, izberite **Oglejte si zadnji tek**. Prikažejo se rezultati, vključno z ID-ji nadomestnih stikov. Rezultate lahko prenesete.

1. Če si želite ogledati rezultate in rezultate določenega pravila, izberite pravilo in nato **Predogled**. Rezultati se prikažejo. Rezultate lahko prenesete.

1. Če si želite ogledati rezultate določenega pogoja za pravilo, izberite pravilo in nato **Uredi**. V podoknu za urejanje izberite **Predogled** pod pogojem. Rezultate lahko prenesete.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Grafična predstavitev neusklajenih in ujemajočih se zapisov, vključno s seznamom podatkov.":::

1. Če ste dodali obogateno entiteto, izberite **Uporabite obogatene entitete**. Za več informacij glejte [Obogatitev za vire podatkov](data-sources-enrichment.md).

1. Če želite upravljati pravila, izberite eno od naslednjih možnosti:
   - **Ustvarite novo pravilo** : Izberite **Dodajte pravilo** pod ustreznim subjektom. Za več informacij glejte [Določite pravila za pare ujemanja](match-entities.md#define-rules-for-match-pairs).
   - **Spremenite vrstni red svojih pravil** če ste definirali več pravil: povlecite in spustite pravila v želeni vrstni red. Za več informacij glejte [Določite vrstni red ujemanja](match-entities.md#specify-the-match-order).
   - **Spremenite pogoje pravila** : Izberite pravilo in nato **Uredi**. Spremenite polja, dodajte ali odstranite pogoje ali dodajte ali odstranite izjeme.
   - **Deaktivirajte pravilo** : Izberite pravilo in nato **Deaktiviraj** ohraniti pravilo ujemanja, hkrati pa ga izključiti iz postopka ujemanja.
   - **Podvojite pravilo** : Izberite pravilo in nato **Podvojeno** ustvariti podobno pravilo s spremembami.
   - **Izbriši pravilo** : Izberite pravilo in nato **Izbriši**.

1. Izberite **Naslednji** če želite spremeniti enotna polja, ali izberite **Shrani in zapri** in se vrnite k [Posodobite nastavitve združevanja](#update-the-unification-settings).

## <a name="manage-unified-fields"></a>Upravljajte enotna polja

1. Izberite **Uredi** na **Poenotena polja strank** ploščice.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Posnetek zaslona enotnih polj strank":::

1. Preglejte združena in izključena polja in po potrebi naredite vse spremembe. Dodajte ali uredite ključ CustomerID ali združite profile v gruče. Za več informacij glejte [Poenoti polja strank](merge-entities.md).

1. Izberite **Naslednji** za pregled nastavitev združevanja in [posodobite enoten profil in odvisnosti](#run-updates-to-the-unified-customer-profile) ali izberite **Shrani in zapri** in se vrnite k [Posodobite nastavitve združevanja](#update-the-unification-settings) narediti več sprememb.

## <a name="run-matching-conditions"></a>Zaženite pogoje ujemanja

Zaženite samo odstranjevanje podvajanj za izvedbe pogojev ujemanja in pravila ujemanja ter posodobite entiteti *Deduplication_* in *ConflationMatchPair*.

1. Iz **Podatki** > **Poenoti** stran, izberite **Zaženite samo pogoje ujemanja**.

   The **Podvojeni zapisi** in **Ujemanje pogojev** razstava ploščic **V čakalni vrsti** oz **Osvežujoče** stanje.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Ko je postopek ujemanja končan, izberite **Uredi** na **Ujemanje pogojev** ploščice.

   :::image type="content" source="media/match-KPIs.png" alt-text="Obrezan posnetek zaslona ključnih meritev na strani «Ujemanje» s številkami in podrobnostmi.":::

1. Če želite narediti spremembe, glejte [Upravljajte pravila za odpravo podvajanja](#manage-deduplication-rules) oz [Upravljajte pravila tekme](#manage-match-rules).

1. Ponovno zaženite postopek ujemanja oz [izvajati posodobitve profila stranke](#run-updates-to-the-unified-customer-profile).

## <a name="run-updates-to-the-unified-customer-profile"></a>Zaženite posodobitve enotnega profila stranke

1. Iz **Podatki** > **Poenoti** stran, izberite:

   - **Poenoti profile strank** : Zažene ujemajoče se pogoje in posodablja enoto enotnega profila stranke brez vpliva na odvisnosti (kot so obogatitve, segmenti ali ukrepi). Odvisni procesi se ne izvajajo, ampak bodo osveženi kot [določeno v urniku osveževanja](system.md#schedule-tab).

   - **Poenoti profile strank in odvisnosti** : Zažene ujemajoče se pogoje in posodobi enoten profil in vse odvisnosti. Vsi procesi se samodejno znova zaženejo. Ko so vsi nadaljnji procesi zaključeni, profil stranke odraža posodobljene podatke.

   The **Podvojeni zapisi**, **pogojev**, in **Poenotena polja strank** razstava ploščic **V čakalni vrsti** oz **Osvežujoče** stanje.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Rezultati uspešnega teka se prikažejo na **Poenoti** stran, ki prikazuje število enotnih profilov strank.
