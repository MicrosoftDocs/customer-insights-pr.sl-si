---
title: Poenotite polja strank za poenotenje podatkov
description: Združite entitete za ustvarjanje poenotenih profilov strank.
recommendations: false
ms.date: 05/04/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-merge
- ci-match
- ci-relationships
- customerInsights
ms.openlocfilehash: 4a19b753e7a5979fe72d7e96bc4452d7795c2d48
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139677"
---
# <a name="unify-customer-fields-for-data-unification"></a>Poenotite polja strank za poenotenje podatkov

V tem koraku postopka poenotenja izberite in izključite atribute, ki jih želite združiti znotraj entitete poenotenega profila. Če so na primer tri entitete imele e-poštne podatke, boste morda želeli obdržati vsa tri ločena e-poštna polja ali jih združiti v eno e-poštno polje za poenoten profil. Nekatere atribute sistem samodejno združi. Ustvarite lahko stabilne in edinstvene ID-je strank ter združite povezane profile v gručo.

:::image type="content" source="media/m3_unify.png" alt-text="Stran za spajanje v postopku poenotenja podatkov, ki prikazuje tabelo s spojenimi polji, ki določajo poenoten profil kupca.":::

## <a name="review-and-update-the-customer-fields"></a>Preglejte in posodobite polja strank

1. Preglejte seznam polj, ki bodo poenotena pod **Polja strank** zavihek tabele. Naredite morebitne spremembe, če je primerno.

   1. Za katera koli kombinirana polja lahko:
      - [Urejanje](#edit-a-merged-field)
      - [Preimenuj](#rename-fields)
      - [Loči](#separate-merged-fields)
      - [Izključi](#exclude-fields)
      - [Premaknite se gor ali dol](#change-the-order-of-fields)

   1. Za katera koli posamezna polja lahko:
      - [Združitev polj](#combine-fields-manually)
      - [Združite skupino polj](#combine-a-group-of-fields)
      - [Preimenuj](#rename-fields)
      - [Izključi](#exclude-fields)
      - [Premaknite se gor ali dol](#change-the-order-of-fields)

1. Po želji, [ustvarite konfiguracijo ID-ja stranke](#configure-customer-id-generation).

1. Po želji, [skupine profilov v gospodinjstva ali grozde](#group-profiles-into-households-or-clusters).

> [!div class="nextstepaction"]
> [Naslednji korak: Pregled poenotenja](review-unification.md)

### <a name="edit-a-merged-field"></a>Urejanje spojenega polja

1. Izberite združeno polje in izberite **Uredi**. Prikaže se podokno Združi polja.

1. Določite, kako združiti ali spojiti polja z eno od treh možnosti:
    - **Pomembnost**: Določi zmagovalno vrednost na podlagi uvrstitve pomembnosti, določene za vključena polja. To je privzeta možnost spajanja. Izberite **Premakni gor/dol**, da določite razvrstitev pomembnosti.

      :::image type="content" source="media/importance-merge-option.png" alt-text="Možnost pomembnosti v dialogu za spajanje polj.":::

    - **Najnovejše**: Določi zmagovalno vrednost na podlagi najnovejših. Zahteva datum ali številsko polje za vsako vključeno entiteto v obsegu spajanja polj za določitev nedavnosti.

      :::image type="content" source="media/recency-merge-option.png" alt-text="Možnost nedavnosti v dialogu za spajanje polj.":::

    - **Najstarejše**: Določi zmagovalno vrednost na podlagi najstarejših. Zahteva datum ali številsko polje za vsako vključeno entiteto v obsegu spajanja polj za določitev nedavnosti.

1. Če želite sodelovati v postopku spajanja, lahko dodate več polj.

1. Spojeno polje lahko preimenujete.

1. Če želite uporabiti spremembe, izberite **Dokončaj**.

### <a name="rename-fields"></a>Preimenuj polja

Spremenite prikazno ime združenih ali ločenih polj. Imen izhodne entitete ni mogoče spremeniti.

1. Izberite polje in izberite **Preimenuj**.

1. Vnesite novo prikazno ime.

1. Izberite **Dokončano**.

### <a name="separate-merged-fields"></a>Ločevanje spojenih polj

Če želite ločiti spojena polja, v tabeli poiščite atribut. Ločena polja so prikazana kot posamezne podatkovne točke na poenotenem profilu stranke.

1. Izberite združeno polje in izberite **Ločena polja**.

1. Potrdite ločevanje.

### <a name="exclude-fields"></a>Izključi polja

Iz poenotenega profila stranke izključite združeno ali ločeno polje. Če se polje uporablja v drugih procesih, na primer v segmentu, ga odstranite iz teh procesov, preden ga izključite iz profila stranke.

1. Izberite polje in izberite **Izključi**.

1. Potrdite izključitev.

Če si želite ogledati seznam vseh izključenih polj, izberite **Izključena polja**. Po potrebi lahko preberete izključeno polje.

### <a name="change-the-order-of-fields"></a>Spreminjanje vrstnega reda polj

Nekatere entitete vsebujejo več podrobnosti kot druge. Če entiteta vključuje najnovejše podatke o polju, jo lahko pri spajanju vrednosti prednostno obravnavate pred drugimi entitetami.

1. Izberite polje.
  
1. Izberite **Premakni se gor/dol** da nastavite vrstni red ali jih povlecite in spustite na želeno mesto.

### <a name="combine-fields-manually"></a>Ročno združite polja

Združite ločena polja, da ustvarite združeni atribut.

1. Izberite **Združite** > **Polja**. Prikaže se podokno Združi polja.

1. Pravilnik zmagovalnega spajanja določite v spustnem meniju **Združi polja glede na**.

1. Izberite **Dodaj polje** združiti več polj.

1. Navedite **Ime** in **Ime izhodnega polja**.

1. Če želite uporabiti spremembe, izberite **Dokončaj**.

### <a name="combine-a-group-of-fields"></a>Združite skupino polj

Obravnavajte skupino polj kot eno samo enoto. Na primer, če naši zapisi vsebujejo polja Naslov1, Naslov2, Mesto, Država in Poštna številka, ne želimo združiti naslova2 drugega zapisa, saj menimo, da bodo naši podatki popolnejši.

1. Izberite **Združite** > **Skupina polj**.

1. Določite pravilnik zmagovalca spajanja v **Razvrsti skupine po** spustni meni.

1. Izberite **Dodaj** in izberite, ali želite poljem dodati več polj ali skupin.

1. Zagotovite a **Ime** in an **Izhodno ime** za vsako kombinirano polje.

1. Zagotovite a **Ime** za skupino polj.

1. Če želite uporabiti spremembe, izberite **Dokončaj**.

## <a name="configure-customer-id-generation"></a>Konfigurirajte ustvarjanje ID-ja stranke

Določite, kako ustvariti vrednosti ID-ja stranke, edinstvene identifikatorje profila stranke. Korak poenotenja polj v procesu poenotenja podatkov ustvari edinstven identifikator profila stranke. Identifikator je *Identifikacijska številka stranke* v *Stranka* entiteta, ki izhaja iz procesa poenotenja podatkov.

The *Identifikacijska številka stranke*  temelji na zgoščeni vrednosti prve vrednosti zmagovalnih primarnih ključev, ki niso ničelni. Ti ključi izvirajo iz entitet, uporabljenih pri poenotenju podatkov, nanje pa vpliva vrstni red ujemanja.Tako se lahko ustvarjeni ID stranke spremeni, ko se spremeni vrednost primarnega ključa v primarni entiteti vrstnega reda ujemanja. Vrednost primarnega ključa morda ne predstavlja vedno iste stranke.

Če konfigurirate stabilen ID stranke, se lahko temu izognete.

1. Izberite zavihek **Ključi**.

1. Lebdite na **Identifikacijska številka stranke** vrstico in izberite **Konfiguriraj**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Kontrolnik za prilagoditev ID-ja generacije.":::

1. Izberite do pet polj, ki bodo vsebovala edinstven ID stranke in so bolj stabilna. Zapisi, ki se ne ujemajo z vašo konfiguracijo, namesto tega uporabljajo sistemsko konfiguriran ID.  

1. Izberite **Dokončano**.

## <a name="group-profiles-into-households-or-clusters"></a>Združevanje profilov v gospodinjstva ali gruče

Določite lahko pravila za združevanje povezanih profilov v gručo. Trenutno sta na voljo dve vrsti gruč – gospodinjska in po meri. Sistem samodejno izbere gospodinjstvo z vnaprej določenimi pravili, če entiteta *Stranka* vsebuje semantični polji *Person.LastName* in *Location.Address*. Ustvarite lahko tudi gručo z lastnimi pravili in pogoji, ki so podobni [pravilom za ujemanje](match-entities.md#define-rules-for-match-pairs).

1. Izberite **Napredno** > **Ustvarite gručo**.

   :::image type="content" source="media/create-cluster.png" alt-text="Nadzor za ustvarjanje nove gruče.":::

1. Izberite med gručama **Gospodinjstvo** ali **Po meri**. Če semantični polji *Person.LastName* in *Location.Address* obstajata v entiteti *Stranka*, bo samodejno izbrano gospodinjstvo.

1. Vnesite ime za gručo in izberite **Končano**.

1. Izberite zavihek **Gruče**, da poiščete gručo, ki ste jo ustvarili.

1. Določite pravila in pogoje za opredelitev gruče.

1. Izberite **Dokončano**. Grozd je ustvarjen, ko je postopek združevanja končan. Identifikatorji gruče so dodani kot nova polja v *Stranka* entiteta.

> [!div class="nextstepaction"]
> [Naslednji korak: Pregled poenotenja](review-unification.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
