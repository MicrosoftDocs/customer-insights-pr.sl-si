---
title: Poenoti polja strank za poenotenje podatkov
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
ms.openlocfilehash: ceb2724ad490c1ba44fd9b7ff2be04721892fca4
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082963"
---
# <a name="unify-customer-fields-for-data-unification"></a>Poenoti polja strank za poenotenje podatkov

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

V tem koraku postopka združevanja izberite in izključite atribute, ki jih želite združiti v enoti enotnega profila. Na primer, če so imeli tri entitete e-poštne podatke, boste morda želeli obdržati vsa tri ločena e-poštna polja ali jih združiti v eno e-poštno polje za enoten profil. Nekatere atribute sistem samodejno kombinira. Ustvarite lahko stabilne in edinstvene ID-je strank ter združite povezane profile v gručo.

:::image type="content" source="media/m3_unify.png" alt-text="Stran za spajanje v postopku poenotenja podatkov, ki prikazuje tabelo s spojenimi polji, ki določajo poenoten profil kupca.":::

## <a name="review-and-update-the-customer-fields"></a>Preglejte in posodobite polja za stranke

1. Preglejte seznam polj, ki bodo združena pod **Polja za stranke** zavihek tabele. Po potrebi naredite kakršne koli spremembe.

   1. Za vsa kombinirana polja lahko:
      - [Urejanje](#edit-a-merged-field)
      - [Preimenuj](#rename-fields)
      - [Loči](#separate-merged-fields)
      - [Izključi](#exclude-fields)
      - [Premaknite se navzgor ali navzdol](#change-the-order-of-fields)

   1. Za posamezna polja lahko:
      - [Združitev polj](#combine-fields-manually)
      - [Združite skupino polj](#combine-a-group-of-fields)
      - [Preimenuj](#rename-fields)
      - [Izključi](#exclude-fields)
      - [Premaknite se navzgor ali navzdol](#change-the-order-of-fields)

1. Po želji, [ustvarite konfiguracijo ID-ja stranke](#configure-customer-id-generation).

1. Po želji, [združite profile v gospodinjstva ali grozde](#group-profiles-into-households-or-clusters).

> [!div class="nextstepaction"]
> [Naslednji korak: preglejte poenotenje](review-unification.md)

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

Iz enotnega profila stranke izključite združeno ali ločeno polje. Če se polje uporablja v drugih procesih, na primer v segmentu, ga odstranite iz teh procesov, preden ga izključite iz profila stranke.

1. Izberite polje in izberite **Izključi**.

1. Potrdite izključitev.

Če si želite ogledati seznam vseh izključenih polj, izberite **Izključena polja**. Po potrebi lahko preberete izključeno polje.

### <a name="change-the-order-of-fields"></a>Spreminjanje vrstnega reda polj

Nekatere entitete vsebujejo več podrobnosti kot druge. Če entiteta vključuje najnovejše podatke o polju, jo lahko pri spajanju vrednosti prednostno obravnavate pred drugimi entitetami.

1. Izberite polje.
  
1. Izberite **Pomik gor/dol** da nastavite vrstni red ali jih povlecite in spustite na želeni položaj.

### <a name="combine-fields-manually"></a>Ročno združi polja

Združite ločena polja, da ustvarite združen atribut.

1. Izberite **Združite** > **Polja**. Prikaže se podokno Združi polja.

1. Pravilnik zmagovalnega spajanja določite v spustnem meniju **Združi polja glede na**.

1. Izberite **Dodaj polje** združiti več polj.

1. Navedite **Ime** in **Ime izhodnega polja**.

1. Če želite uporabiti spremembe, izberite **Dokončaj**.

### <a name="combine-a-group-of-fields"></a>Združite skupino polj

Skupino polj obravnavajte kot eno samo enoto. Na primer, če naši zapisi vsebujejo polja Naslov1, Naslov2, Mesto, Država in Poštna številka, se ne želimo združiti z naslovom Address2 drugega zapisa, ker mislimo, da bi naši podatki postali popolnejši.

1. Izberite **Združite** > **Skupina polj**.

1. Določite politiko zmagovalca spajanja v **Razvrstite skupine po** spustni meni.

1. Izberite **Dodaj** in izberite, ali želite v polja dodati več polj ali skupin.

1. Zagotovite a **ime** in an **Ime izhoda** za vsako kombinirano polje.

1. Zagotovite a **ime** za skupino polj.

1. Če želite uporabiti spremembe, izberite **Dokončaj**.

## <a name="configure-customer-id-generation"></a>Konfigurirajte ustvarjanje ID-ja stranke

Določite, kako ustvariti vrednosti ID-ja stranke, edinstvene identifikatorje profila stranke. Korak poenotenih polj v postopku poenotenja podatkov ustvari edinstven identifikator profila stranke. Identifikator je *Identifikacijska številka stranke* v *Stranka* subjekt, ki izhaja iz postopka poenotenja podatkov.

The *Identifikacijska številka stranke*  temelji na zgoščevanju prve vrednosti primarnih ključev zmagovalca, ki ni nič. Ti ključi prihajajo iz entitet, ki se uporabljajo pri združevanju podatkov, in nanje vpliva vrstni red ujemanja.Tako se lahko ustvarjeni ID stranke spremeni, ko se spremeni vrednost primarnega ključa v primarni entiteti naročila ujemanja. Vrednost primarnega ključa morda ne predstavlja vedno iste stranke.

Če konfigurirate stabilen ID stranke, se lahko temu izognete.

1. Izberite zavihek **Ključi**.

1. Premaknite miškin kazalec na **Identifikacijska številka stranke** vrstico in izberite **Konfiguriraj**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Kontrolnik za prilagoditev ID-ja generacije.":::

1. Izberite do pet polj, ki bodo vsebovala edinstven ID stranke in so bolj stabilna. Zapisi, ki se ne ujemajo z vašo konfiguracijo, namesto tega uporabljajo sistemsko konfiguriran ID.  

1. Izberite **Dokončano**.

## <a name="group-profiles-into-households-or-clusters"></a>Združevanje profilov v gospodinjstva ali gruče

Določite lahko pravila za združevanje povezanih profilov v gručo. Trenutno sta na voljo dve vrsti gruč – gospodinjska in po meri. Sistem samodejno izbere gospodinjstvo z vnaprej določenimi pravili, če entiteta *Stranka* vsebuje semantični polji *Person.LastName* in *Location.Address*. Ustvarite lahko tudi gručo z lastnimi pravili in pogoji, ki so podobni [pravilom za ujemanje](match-entities.md#define-rules-for-match-pairs).

1. Izberite **Napredno** > **Ustvari grozd**.

   :::image type="content" source="media/create-cluster.png" alt-text="Nadzor za ustvarjanje nove gruče.":::

1. Izberite med gručama **Gospodinjstvo** ali **Po meri**. Če semantični polji *Person.LastName* in *Location.Address* obstajata v entiteti *Stranka*, bo samodejno izbrano gospodinjstvo.

1. Vnesite ime za gručo in izberite **Končano**.

1. Izberite zavihek **Gruče**, da poiščete gručo, ki ste jo ustvarili.

1. Določite pravila in pogoje za opredelitev gruče.

1. Izberite **Dokončano**. Grozd je ustvarjen, ko je postopek združevanja končan. Identifikatorji gruče so dodani kot nova polja v *Stranka* entiteta.

> [!div class="nextstepaction"]
> [Naslednji korak: preglejte poenotenje](review-unification.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
