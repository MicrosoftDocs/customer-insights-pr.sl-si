---
title: Posodobite nastavitve združevanja strank, računa ali stikov
description: Posodobite podvojena pravila, pravila ujemanja ali poenotena polja v nastavitvah združevanja stranke ali računa.
ms.date: 08/26/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: Scott-Stabbert
ms.author: sstabbert
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: e893e66fd7691b9703d51ed8f87cfad63880cc3b
ms.sourcegitcommit: 560c4ee16376a9c6fdd7860988ce2d2440194fa5
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 09/01/2022
ms.locfileid: "9392491"
---
# <a name="update-unification-settings"></a>Posodobite nastavitve združevanja

Če želite pregledati ali spremeniti katere koli nastavitve poenotenja, ko je poenoten profil ustvarjen, izvedite naslednje korake.

1. Pojdi do **podatki** > **Poenotiti**.

   Za posamezne stranke (B-to-C) je **Poenotiti** stran prikazuje število poenotenih profilov strank in ploščic za vsakega od korakov poenotenja.

   :::image type="content" source="media/m3_unified.png" alt-text="Posnetek zaslona strani Data Unify po poenotenju podatkov." lightbox="media/m3_unified.png":::

   Za poslovne račune (B-to-B) je **Poenotiti** stran prikazuje število poenotenih profilov računov in ploščic za vsak korak združevanja računov. Če so bili stiki poenoteni, se prikaže število poenotenih profilov stikov in ploščic za vsak korak poenotenja stikov. Izberite ustrezno ploščico pod **Poenotite račune** oz **Poenotite stike (predogled)** odvisno od tega, kaj želite posodobiti.

   :::image type="content" source="media/b2b_unified.png" alt-text="Posnetek zaslona strani Data Unify po poenotenju podatkov o računu in stikih." lightbox="media/b2b_unified.png":::

   > [!TIP]
   > The **Ujemanje pogojev** ploščica se prikaže le, če je izbranih več entitet.

1. Izberite, kaj želite posodobiti:
   - [Izvorna polja](#edit-source-fields) za dodajanje atributov ali entitet ali spreminjanje vrst atributov. Če želite odstraniti atribut, glejte [Odstranite poenoteno polje](#remove-a-unified-field). Če želite odstraniti entiteto, glejte [Odstranite poenoteno entiteto](#remove-a-unified-entity).
   - [Podvojeni zapisi](#manage-deduplication-rules) za upravljanje pravil za odstranjevanje podvojitev ali preferenc združevanja.
   - [Ujemanje pogojev](#manage-match-rules) za posodobitev pravil ujemanja v dveh ali več entitetah.
   - [Poenotena polja za stranke](#manage-unified-fields) za združevanje ali izključitev polj. Povezane profile lahko tudi združite v gruče.
   - [Pomenska polja](#manage-semantic-fields-for-unified-contacts) za upravljanje semantičnih tipov za poenotena kontaktna polja.
   - [Odnosi](#manage-contact-and-account-relationships) za upravljanje razmerja med stikom in računom.

1. Po spremembah izberite naslednjo možnost:

   - [Izvedite pogoje ujemanja](#run-matching-conditions) za hitro oceno kakovosti vaših pogojev ujemanja (deduplikacija in pravila ujemanja) brez posodabljanja poenotenega profila. The **Zaženi samo pogoje, ki se ujemajo** možnost se ne prikaže za posamezno entiteto.
   - [Poenotite profile](#run-updates-to-the-unified-profile) za izvajanje pogojev ujemanja in posodobitev enote poenotenega profila brez vplivanja na odvisnosti (kot so obogatitve, segmenti ali mere). Odvisni procesi se ne izvajajo, ampak bodo osveženi kot [določeno v urniku osveževanja](schedule-refresh.md).
   - [Poenotite profile in odvisnosti](#run-updates-to-the-unified-profile) za izvajanje ujemajočih se pogojev posodobite enoto poenotenega profila in posodobite vse odvisnosti (kot so obogatitve, segmenti ali mere). Vsi procesi se samodejno znova izvedejo. V B-to-B se poenotenje izvaja na računih in kontaktnih entitetah, ki posodabljajo poenotene profile.

## <a name="edit-source-fields"></a>Uredi izvorna polja

1. Izberite **Uredi** na **Izvorna polja** ploščica.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Posnetek zaslona strani Source fields, ki prikazuje število primarnih ključev, preslikanih in nepreslikanih polj":::

   Prikaz števila preslikanih in nepreslikanih polj.

1. Če želite dodati druge atribute ali entitete, izberite **Izberite entitete in polja**.

1. Po želji lahko spremenite primarni ključ za entiteto, vrste atributov in preklop **Inteligentno kartiranje** vklop ali izklop. Za več informacij glejte [Izberite izvorna polja](map-entities.md).

1. Izberite **Naslednji** če želite spremeniti pravila za odstranjevanje podvojitev, ali izberite **Shrani in zapri** in se vrniti k [Posodobite nastavitve združevanja](#update-unification-settings).

### <a name="remove-a-unified-field"></a>Odstranite poenoteno polje

Če želite odstraniti polje, ki je bilo poenoteno, je treba polje odstraniti iz vseh odvisnosti, kot so segmenti, mere, obogatitve ali Odnosi.

1. Ko so vse odvisnosti za polje odstranjene, pojdite na **podatki** > **Poenotiti**.

1. Izberite **Uredi** na **Poenotena polja za stranke** ploščica.

1. Izberite vse pojavitve polja in nato izberite **Izključi**.

   :::image type="content" source="media/m3_remove_attribute1.png" alt-text="Posnetek zaslona strani poenotenih polj, ki prikazuje izbrana polja in gumb Izključi":::

1. Izberite **Končano** za potrditev in nato izberite **Shrani in zapri**.

   > [!TIP]
   > Če vidite sporočilo »Ni bilo mogoče shraniti unify. Podanega vira ni mogoče spremeniti ali izbrisati zaradi nadaljnjih odvisnosti", potem se polje še vedno uporablja v nadaljnji odvisnosti.

1. Če je polje uporabljeno v pravilu za podvojene zapise ali pogoje ujemanja, izvedite naslednje korake. V nasprotnem primeru pojdite na naslednji korak.
   1. Izberite **Uredi** na **Podvojeni zapisi** ploščica.
   1. Odstranite polje iz vseh pravil, v katerih se uporablja, če obstajajo, in nato izberite **Naslednji**.
   1. Na **Ujemanje pogojev** stran, odstranite polje iz vseh pravil, v katerih je uporabljeno, in nato izberite **Shrani in zapri**.
   1. Izberite **Poenotiti** > **Poenotite profile strank in odvisnosti**. Preden nadaljujete z naslednjim korakom, počakajte, da se poenotenje konča.

1. Izberite **Uredi** na **Izvorna polja** ploščica.

1. Izberite **Izberite entitete in polja** in počistite potrditveno polje ob vsaki pojavitvi polja.

   :::image type="content" source="media/m3_remove_attribute2.png" alt-text="Posnetek zaslona pogovornega okna Izberi entitete in polja, ki prikazuje počiščena potrditvena polja":::

1. Izberite **Uporabi**.

1. Izberite **Shrani in zapri**.

1. Izberite **Poenotiti** > **Poenotite profile strank in odvisnosti** za posodobitev enotnega profila.

### <a name="remove-a-unified-entity"></a>Odstranite poenoteno entiteto

Če želite odstraniti entiteto, ki je bila poenotena, je treba entiteto odstraniti iz vseh odvisnosti, kot so segmenti, mere, obogatitve ali Odnosi.

1. Ko so vse odvisnosti za entiteto odstranjene, pojdite na **podatki** > **Poenotiti**.

1. Izberite **Uredi** na **Poenotena polja za stranke** ploščica.

1. Izberite vsa polja za entiteto in nato izberite **Izključi**.

   :::image type="content" source="media/m3_remove_entity1.png" alt-text="Posnetek zaslona poenotenih polj z vsemi izbranimi polji za entiteto in gumbom Izključi":::

1. Izberite **Končano** za potrditev in nato izberite **Shrani in zapri**.

   > [!TIP]
   > Če vidite sporočilo »Ni bilo mogoče shraniti unify. Podanega vira ni mogoče spremeniti ali izbrisati zaradi nadaljnjih odvisnosti", potem se entiteta še vedno uporablja v nadaljnji odvisnosti.

1. Izberite **Uredi** na **Podvojeni zapisi** ploščica.

1. Odstranite vsa pravila iz entitete, če obstajajo, in nato izberite **Naslednji**.

1. Na **Ujemanje pogojev** strani, izberite entiteto in nato izberite **Izbriši**.

   :::image type="content" source="media/m3_remove_entity2.png" alt-text="Posnetek zaslona pogojev ujemanja z izbrano entiteto in gumbom Izbriši":::

1. Izberite **Shrani in zapri**.

1. Izberite **Uredi** na **Izvorna polja** ploščica.

1. Izberite **Izberite entitete in polja** in počistite potrditveno polje poleg entitete.

   :::image type="content" source="media/m3_remove_entity3.png" alt-text="Posnetek zaslona pogovornega okna Izberi entitete in polja s počiščenim potrditvenim poljem entitete":::

1. Izberite **Uporabi**.

1. Izberite **Shrani in zapri**.

1. Izberite **Poenotiti** > **Poenotite profile strank in odvisnosti** za posodobitev enotnega profila.

## <a name="manage-deduplication-rules"></a>Upravljajte pravila deduplikacije

1. Izberite **Uredi** na **Podvojeni zapisi** ploščica.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Posnetek zaslona strani s podvojenimi zapisi, ki prikazuje število podvojenih zapisov" lightbox="media/m3_duplicates_edit.png":::

   Število najdenih podvojenih zapisov je prikazano pod **Dvojniki**. The **Zapisi so deduplicirani** prikazuje, katere entitete so imele podvojene zapise in odstotek podvojenih zapisov.

1. Če želite uporabiti obogateno entiteto, izberite **Uporabite obogatene entitete**. Za več informacij glejte [Obogatitev podatkovnih virov](data-sources-enrichment.md).

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

   1. Izberite **Dokončano**.

1. Izberite **Naslednji** če želite spremeniti pogoje ujemanja, ali izberite **Shrani in zapri** in se vrniti k [Posodobite nastavitve združevanja](#update-unification-settings).

## <a name="manage-match-rules"></a>Upravljanje pravil ujemanja

Večino parametrov ujemanja lahko znova konfigurirate in prilagodite. Entitet ne morete dodajati ali brisati. Pravila ujemanja ne veljajo za posamezno entiteto.

1. Izberite **Uredi** na **Ujemanje pogojev** ploščica.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Posnetek zaslona strani s pravili in pogoji tekme s statistiko." lightbox="media/m3_match_edit.png":::

   Stran prikazuje vrstni red ujemanja in definirana pravila ter naslednjo statistiko:
   - **Edinstveni izvorni zapisi** prikaže število posameznih izvornih zapisov, ki so bili obdelani v zadnjem teku ujemanja.
   - **Ujemajoči in neujemajoči se zapisi** označite, koliko edinstvenih zapisov ostane po obdelavi pravil ujemanja.
   - **Samo ujemajoči se zapisi** prikažite število ujemanj v vseh vaših parih ujemanj.

1. Za ogled rezultatov vseh pravil in njihovih točk izberite **Oglejte si zadnjo vožnjo**. Prikaz rezultatov, vključno z nadomestnimi ID-ji stikov. Rezultate lahko prenesete.

1. Za ogled rezultatov in rezultatov določenega pravila izberite pravilo in nato **Predogled**. Prikaz rezultatov. Rezultate lahko prenesete.

1. Če si želite ogledati rezultate določenega pogoja za pravilo, izberite pravilo in nato **Uredi**. V podoknu za urejanje izberite **Predogled** pod pogojem. Rezultate lahko prenesete.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Grafična predstavitev neujemajočih se in ujemajočih se zapisov, vključno s seznamom podatkov.":::

1. Če ste dodali obogateno entiteto, izberite **Uporabite obogatene entitete**. Za več informacij glejte [Obogatitev podatkovnih virov](data-sources-enrichment.md).

1. Za upravljanje pravil izberite katero koli od naslednjih možnosti:
   - **Ustvarite novo pravilo** : Izberite **Dodaj pravilo** pod ustreznim subjektom. Za več informacij glejte [Določite pravila za ujemanje parov](match-entities.md#define-rules-for-match-pairs).
   - **Spremenite vrstni red svojih pravil** če ste določili več pravil: povlecite in spustite pravila v želenem vrstnem redu. Za več informacij glejte [Določite vrstni red ujemanja](match-entities.md#specify-the-match-order).
   - **Spremenite pogoje pravil** : Izberite pravilo in nato **Uredi**. Spremenite polja, dodajte ali odstranite pogoje ali dodajte ali odstranite izjeme.
   - **Deaktivirajte pravilo** : Izberite pravilo in nato **Deaktiviraj** da obdržite pravilo ujemanja in ga izključite iz postopka ujemanja.
   - **Podvoji pravilo** : Izberite pravilo in nato **Dvojnik** ustvariti podobno pravilo s spremembami.
   - **Izbriši pravilo** : Izberite pravilo in nato **Izbriši**.

1. Izberite **Naslednji** če želite spremeniti poenotena polja, ali izberite **Shrani in zapri** in se vrniti k [Posodobite nastavitve združevanja](#update-unification-settings).

## <a name="manage-unified-fields"></a>Upravljajte poenotena polja

1. Izberite **Uredi** na **Poenotena polja za stranke** ploščica.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Posnetek zaslona poenotenih polj strank":::

1. Preglejte združena in izključena polja ter po potrebi spremenite. Dodajte ali uredite ključ CustomerID ali profile skupin v gruče. Za več informacij glejte [Poenotite polja strank](merge-entities.md).

1. Za stranke ali račune izberite **Naslednji** pregledati in [posodobite poenoten profil in odvisnosti](#run-updates-to-the-unified-profile). Ali izberite **Shrani in zapri** in se vrniti k [Posodobite nastavitve združevanja](#update-unification-settings) narediti več sprememb.

   Za stike izberite **Naslednji** za upravljanje pomenskih polj. Ali izberite **Shrani in zapri** in se vrniti k [Posodobite nastavitve združevanja](#update-unification-settings) narediti več sprememb.

## <a name="manage-semantic-fields-for-unified-contacts"></a>Upravljajte semantična polja za poenotene stike

1. Izberite **Uredi** na **Pomenska polja** ploščica.

1. Če želite spremeniti semantično vrsto za enotno polje, izberite novo vrsto. Za več informacij glejte [Določite semantična polja za poenotene stike](data-unification-contacts.md#define-the-semantic-fields-for-unified-contacts).

1. Izberite **Naslednji** za upravljanje računa in stikov ali izberite **Shrani in zapri** in se vrniti k [Posodobite nastavitve združevanja](#update-unification-settings) narediti več sprememb.

## <a name="manage-contact-and-account-relationships"></a>Upravljanje stika in računa Odnosi

1. Izberite **Uredi** na **Odnosi** ploščica.

1. Če želite spremeniti razmerje med stikom in računom, spremenite katerega koli od naslednjih podatkov:

   - **Tuji ključ iz kontaktne entitete** : izberite atribut, ki povezuje vašo kontaktno entiteto z računom.
   - **Računskemu subjektu** : izberite entiteto računa, povezano s kontaktom.

1. Izberite **Naslednji** za pregled nastavitev združevanja in [posodobite poenoten profil in odvisnosti](#run-updates-to-the-unified-profile) ali izberite **Shrani in zapri** in se vrniti k [Posodobite nastavitve združevanja](#update-unification-settings) narediti več sprememb.

## <a name="run-matching-conditions"></a>Izvedite pogoje ujemanja

Zaženite samo odstranjevanje podvajanj za izvedbe pogojev ujemanja in pravila ujemanja ter posodobite entiteti *Deduplication_* in *ConflationMatchPair*.

1. Iz **podatki** > **Poenotiti** stran, izberite **Zaženi samo pogoje, ki se ujemajo**.

   The **Podvojeni zapisi** in **Ujemanje pogojev** ploščice kažejo **V čakalni vrsti** oz **Osvežujoče** stanje.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Ko je postopek ujemanja končan, izberite **Uredi** na **Ujemanje pogojev** ploščica.

   :::image type="content" source="media/match-KPIs.png" alt-text="Obrezan posnetek zaslona ključnih meritev na strani «Ujemanje» s številkami in podrobnostmi.":::

1. Če želite narediti spremembe, glejte [Upravljajte pravila deduplikacije](#manage-deduplication-rules) oz [Upravljajte pravila tekem](#manage-match-rules).

1. Ponovno zaženite postopek ujemanja oz [zaženite posodobitve profila](#run-updates-to-the-unified-profile).

## <a name="run-updates-to-the-unified-profile"></a>Zaženite posodobitve poenotenega profila

- Za izvajanje pogojev ujemanja in posodobitev enote poenotenega profila *brez* vpliva na odvisnosti (kot so kartice strank, obogatitve, segmenti ali mere), izberite **Poenotite profile strank**. Za račune izberite **Poenotite račune** > **Poenotite profile**. Za stike izberite **Poenotite stike (predogled)** > **Poenotite profile**. Odvisni procesi se ne izvajajo, ampak bodo osveženi kot [določeno v urniku osveževanja](schedule-refresh.md).
- Če želite zagnati pogoje ujemanja, posodobiti poenoten profil in zagnati vse odvisnosti, izberite **Poenotite profile strank in odvisnosti**. Vsi procesi se samodejno znova izvedejo. Za račune in stike izberite **Poenotite račune** > **Poenotite profile in odvisnosti**. Pogoji ujemanja se izvajajo za oba računa in stike, ki posodabljajo oba poenotena profila in izvajajo se vse druge odvisnosti.

Vse ploščice razen **Izvorna polja** pokazati **V čakalni vrsti** oz **Osvežujoče**.

[!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Rezultati uspešnega teka so prikazani na **Poenotiti** stran, ki prikazuje število poenotenih profilov.
