---
title: Ustvarite enoten kontaktni profil (predogled)
description: Pojdite skozi postopek poenotenja podatkov, da ustvarite en sam glavni nabor podatkov o stikih.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- ci-match
- ci-merge
- customerInsights
ms.openlocfilehash: 721f47563582a94b5b8244ca5d5d7d1350695512
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/16/2022
ms.locfileid: "9305091"
---
# <a name="create-a-unified-contact-profile-preview"></a>Ustvarite enoten kontaktni profil (predogled)

Po [poenotenje poslovnih računov](map-entities.md), lahko po želji poenotite stike za te račune in povežete poenotene stike z poenotenimi računi. Postopek poenotenja stikov preslika podatke o stikih iz več virov podatkov, odstrani dvojnike, poveže podatke med entitetami, nastavi semantično preslikavo, ustvari Odnosi med stiki in računi ter nato ustvari poenoten profil stika.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

Prvih nekaj korakov je enakih korakom za poenotenje računov.

## <a name="prerequisites"></a>Zahteve

Zapisi računa in stikov morajo imeti edinstven ključ (imenovan tuji ključ), ki ju povezuje. Na primer ID računa, ki obstaja v zapisu računa in zapisu stika, ki povezujeta račun in stik.

## <a name="preview-limitations"></a>Omejitve predogleda

- Stiki brez povezave z računom so izbrisani.
- Če je račun dedupliciran, se zmagovalni zapis določi na podlagi nastavitev združevanja. Zapisi poražencev niso izbrani in se zato izločijo. Stiki, povezani z izgubljenimi zapisi, so izbrisani.
- Račun ima lahko več stikov, vendar je stik povezan z enim samim računom.
- Atributi stika, preslikani v koraku semantične preslikave, so edini atributi, ki se lahko prikažejo na kartici stranke. Vendar pa je na voljo 17 atributov.

## <a name="select-source-fields"></a>Izberite izvorna polja

1. Spodaj **Poenotite stike (predogled)**, izberite **Začeti**.

1. [Izberite entitete in polja](map-entities.md) za vaše kontaktne vire podatkov, vključno s primarnimi ključi in vrstami atributov.

1. Izberite **Naprej**.

## <a name="remove-duplicate-records"></a>Odstranite podvojene zapise

1. Po želji, [določite pravila deduplikacije](remove-duplicates.md) za vaše izbrane entitete.

1. Izberite **Naprej**.

## <a name="match-conditions"></a>Pogoji tekme

1. [Določite vrstni red ujemanja in pravila](match-entities.md) za ujemanje med entitetami.

1. Izberite **Naprej**.

## <a name="unify-contact-fields"></a>Poenotite kontaktna polja

1. [Združite in izključite kontaktna polja](merge-entities.md).

1. Izberite **Naprej**.

## <a name="define-the-semantic-fields-for-unified-contacts"></a>Določanje semantičnih polj za poenotene stike

Ta korak v procesu poenotenja preslika vaša poenotena kontaktna polja v semantične vrste. V B-to-B kartice strank prikazujejo račune. Ko je kartica izbrana, se prikažejo vsi stiki, povezani z računom. Polja, ki jih preslikate v tem koraku, so polja, ki bodo prikazana na karticah.

1. Izberite semantično vrsto, ki se preslika v vsako poenoteno polje. Izberite **Noben** če semantični tip ni na voljo.

   :::image type="content" source="media/semantic_mapping.png" alt-text="Posnetek zaslona strani Semantična polja za definiranje pomenskih vrst." lightbox="media/semantic_mapping.png":::

1. Po preslikavi vseh enotnih polj izberite **Naslednji**.

## <a name="set-the-relationship-between-contacts-and-accounts"></a>Nastavite razmerje med stiki in računi

Ta korak v procesu poenotenja poveže vaše kontaktne podatke z ustreznimi podatki računa.

1. Za vsako entiteto vnesite naslednje podatke:

   - **Tuji ključ iz kontaktne entitete** : izberite atribut, ki povezuje vašo kontaktno entiteto z računom.
   - **Računskemu subjektu** : izberite entiteto računa, povezano s kontaktom.

   :::image type="content" source="media/contact_relationship.png" alt-text="Posnetek zaslona strani Relationship za povezovanje subjektov stika in računa.":::

1. Izberite **Naprej**.

## <a name="review-contact-unification"></a>Preglejte združevanje stikov

Preglejte povzetek sprememb, ustvarite poenoten profil in preglejte rezultate.

### <a name="review-and-create-contact-profiles"></a>Pregledovanje in ustvarjanje profilov stikov

Ta zadnji korak v procesu združevanja prikazuje povzetek korakov v postopku in ponuja možnost, da naredite spremembe, preden ustvarite poenoten profil stika.

:::image type="content" source="media/b2b_review_contacts.png" alt-text="Posnetek zaslona Pregled in ustvarjanje profilov stikov.":::

1. Izberite **Uredi** na katerem koli koraku združevanja stikov, da pregledate in izvedete morebitne spremembe.

1. Če ste zadovoljni s svojo izbiro, izberite **Ustvarite kontaktne profile**. The **Poenotiti** med ustvarjanjem poenotenega kontaktnega profila se prikaže stran.
  
   :::image type="content" source="media/b2b_unify_refreshing.png" alt-text="Posnetek zaslona strani Unify Contacts s ploščicami, ki prikazujejo Čakalno vrsto ali Osveževanje.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Algoritem poenotenja traja nekaj časa, da se dokonča in ne morete spremeniti konfiguracije, dokler ni dokončan.

### <a name="view-the-results-of-contact-unification"></a>Oglejte si rezultate združevanja stikov

Po končanem združevanju se **podatki** > **Poenotiti** stran prikazuje število poenotenih kontaktnih profilov. Rezultati vsakega koraka v procesu združevanja so prikazani na vsaki ploščici. Na primer **Izvorna polja** prikazuje število preslikanih atributov (polj) in **Podvojeni zapisi** prikazuje število najdenih podvojenih zapisov.

:::image type="content" source="media/unified_contacts.png" alt-text="Posnetek zaslona strani Data Unify po poenotenju stikov.":::

> [!TIP]
> The **Ujemanje pogojev** ploščica se prikaže le, če je izbranih več entitet.

Priporočamo, da pregledate rezultate, zlasti kakovost vašega [pravila tekme](data-unification-update.md#manage-match-rules) in jih po potrebi izboljšati.

Ko je potrebno, [spremenite nastavitve združevanja stikov](data-unification-update.md) in znova zaženite poenoten profil.

### <a name="verify-output-entities-from-data-unification"></a>Preverite izhodne entitete iz poenotenja podatkov

Pojdi do **podatki** > **Entitete** za preverjanje izhodnih entitet.

Enotna entiteta kontaktnega profila, imenovana *ContactProfile*, se prikaže v **Pomenske entitete** razdelek. Prvi uspešen zagon poenotenja ustvari poenoteno *ContactProfile* entiteta. Vsi naslednji zagoni razširijo to entiteto.

The *Kontakti Stranka* entiteta (predogled) je ustvarjena in prikazana v **Profili** razdelek. Ta entiteta vsebuje kontaktne podatke brez povezav do računov. Ta entiteta se uporablja kot vhod v korake semantičnega preslikave in odnosa pri poenotenju stikov.

Entitete deduplikacije in konflacije so ustvarjene in prikazane v **Sistem** razdelek. Z imenom se ustvari deduplicirana entiteta za vsako od izvornih entitet **Deduplication_DataSource_Entity**. The **ContactsConflationMatchPairs** entiteta vsebuje informacije o ujemanju med entitetami.

Izhodna entiteta brez podvajanj vsebuje naslednje informacije:
- ID-je/ključe
  - Polji za primarni ključ in nadomestni ID. Polje z nadomestnim ID-jem je sestavljeno iz vseh nadomestnih ID-jev, identificiranih za zapis.
  - Polje Deduplication_GroupId prikazuje skupino ali gručo, identificirano znotraj entitete, ki združuje vse podobne zapise na podlagi določenih polj za odstranjevanje podvajanj. To se uporablja za namene sistemske obdelave. Če niso podana nobena pravila za ročno odstranjevanje podvajanj in veljajo sistemsko določena pravila za odstranjevanje podvajanj, tega polja v izhodni entiteti brez podvajanj morda ne boste našli.
  - Deduplication_WinnerId: to polje vsebuje ID zmagovalnega zapisa iz identificiranih skupin ali gruč. Če je vrednost Deduplication_WinnerId enaka vrednosti primarnega ključa za zapis, to pomeni, da gre za zmagovalni zapis.
- Polja, ki se uporabljajo za določanje pravil za odstranjevanje podvajanj.
- Polji Pravilo in Ocena označujeta, katera od pravil za odpravljanje podvajanj so bila uporabljena, ter rezultat, ki ga vrne algoritem za iskanje ujemanj.

## <a name="next-step"></a>Naslednji korak

Konfiguriraj [aktivnosti](activities.md),[obogatitev](enrichment-hub.md), oz [Odnosi](relationships.md) da pridobite več vpogledov v svoje stike.
