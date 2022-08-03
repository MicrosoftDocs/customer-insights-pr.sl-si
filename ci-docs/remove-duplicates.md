---
title: Pred poenotenjem podatkov odstranite dvojnike
description: Drugi korak v procesu poenotenja je izbira, kateri zapis obdržati, ko so najdeni dvojniki.
recommendations: false
ms.date: 04/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: a838fbdabdb3bfffc6d3835a3f0e97306a43964a
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139449"
---
# <a name="remove-duplicates-before-unifying-data"></a>Pred poenotenjem podatkov odstranite dvojnike

Ta korak pri poenotenju vam po želji omogoča nastavitev pravil za obravnavanje podvojenih zapisov znotraj entitete. *Deduplikacija* identificira podvojene zapise in jih združi v en zapis. Izvorni zapisi se na združeni zapis povežejo z nadomestnimi ID-ji. Če pravila niso konfigurirana, se uporabijo sistemsko definirana pravila.

## <a name="include-enriched-entities-preview"></a>Vključi obogatene entitete (predogled)

Če ste obogatili entitete na ravni vir podatkov, da bi izboljšali rezultate združevanja, jih izberite. Za več informacij glejte [Obogatitev podatkovnih virov](data-sources-enrichment.md).

1. Na **Podvojeni zapisi** stran, izberite **Uporabite obogatene entitete** na vrhu strani.

1. Iz **Uporabite obogatene entitete** podoknu izberite eno ali več obogatenih entitet.

1. Izberite **Dokončano**.

## <a name="define-deduplication-rules"></a>Določite pravila deduplikacije

1. Na **Podvojeni zapisi** strani, izberite entiteto in izberite **Dodaj pravilo** za določitev pravil deduplikacije.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="Posnetek zaslona strani s podvojenimi zapisi z označeno Pokaži več":::

   1. V **Dodaj pravilo** podoknu vnesite naslednje podatke:
      - **Izberite polje** : Izberite s seznama razpoložljivih polj iz entitete, za katero želite preveriti dvojnike. Izberite polja, ki so verjetno edinstvena vsaki stranki. Na primer e-poštni naslov ali kombinacija imena, mesta in telefonske številke.
      - **Normaliziranje**: Izberite med naslednjimi možnostmi normalizacije za izbrane atribute.
        - **Številke** : Pretvori druge številske sisteme, kot so rimske številke, v arabske številke. *VIII* postane *8*.
        - **Simboli** : Odstrani vse simbole in posebne znake. *Glava&Rama* postane *GlavaRama*.
        - **Besedilo v male črke: vse znake pretvori v male črke**. *VSE Z VELIKIMI in Naslov* postane *vse z velikimi in naslov*.
        - **Vrsta (telefon, ime, naslov, organizacija)** : standardizira imena, nazive, telefonske številke, naslove itd.
        - **Unicode v ASCII** : Pretvori zapis unicode v znake ASCII. */u00B2* postane *2*.
        - **Presledek** : Odstrani vse presledke. *Živjo,   svet* postane *Živjo,svet*.
      - **Natančnost**: nastavite raven natančnosti, ki se bo uporabljala za ta pogoj.
        - **Osnovno** : Izbirajte med *nizko (30 %)*, *(60 %)*, *(80 %)*, in *Točno (100 %)*. Izberite **Točno** za ujemanje samo zapisov, ki se 100-odstotno ujemajo.
        - **Po meri**: nastavite odstotek, ki ga morajo imeti zapisi, da se ujemajo. Sistem se bo ujemal samo z zapisi, ki presegajo ta prag.
      - **Ime** : ime za pravilo.

      :::image type="content" source="media/m3_duplicates_add.png" alt-text="Posnetek zaslona podokna za dodajanje pravil za odstranjevanje dvojnikov.":::

   1. Po želji izberite **Dodaj** > **Dodajte pogoj** če želite pravilu dodati več pogojev. Pogoji so povezani z logičnim operatorjem AND in se izvedejo le, če so izpolnjeni vsi pogoji.

   1. Po želji, **Dodaj** > **Dodaj izjemo** do [dodajte izjeme pravilu](match-entities.md#add-exceptions-to-a-rule). Izjeme se uporabljajo za obravnavanje redkih primerov lažno pozitivnih in lažno negativnih rezultatov.

   1. Izberite **Končano** ustvariti pravilo.

1. Po želji [dodajte več pravil](#define-deduplication-rules).

1. Izberite entiteto in nato **Uredite nastavitve spajanja**.

1. V **Združi nastavitve** podokno:
   1. Izberite eno od treh možnosti, da določite, kateri zapis obdržati, če je najden dvojnik:
      - **Najpogostejše**: opredeli zapis atributa z najbolj izpolnjenimi polji kot zapis zmagovalca. To je privzeta možnost spajanja.
      - **Najnovejše**: določi rekord zmagovalca glede na najnovejše rezultate. Zahteva datum ali številsko polje za določitev najnovejše izkušnje.
      - **Najstarejše**: določi rekord zmagovalca glede na najstarejše rezultate. Zahteva datum ali številsko polje za določitev najnovejše izkušnje.
      
      V primeru izenačenja je zmagovalni zapis tisti z MAX(PK) ali večjo vrednostjo primarnega ključa.
      
   1. Če želite definirati preference združevanja za posamezne atribute entitete, izberite **Napredno** na dnu podokna. Izberete lahko na primer, da obdržite najnovejšo e-pošto IN najpopolnejši naslov iz različnih zapisov. Razširite entiteto, da vidite vse njene atribute in določite, katero možnost uporabiti za posamezne atribute. Če izberete možnost, ki temelji na nedavnosti, morate določiti tudi polje za datum/čas, ki določa nedavnost.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Podokno z naprednimi nastavitvami združevanja prikazuje nedavno e-pošto in celoten naslov":::

   1. Izberite **Končano** da uporabite svoje nastavitve združevanja.

1. Ko določite pravila za odstranjevanje podvojitev in nastavitve spajanja, izberite **Naslednji**.
  
> [!div class="nextstepaction"]
> [Naslednji korak za eno entiteto: Poenotite polja](merge-entities.md)

> [!div class="nextstepaction"]
> [Naslednji korak za več entitet: Ujemanje pogojev](match-entities.md)

## <a name="deduplication-output-as-an-entity"></a>Izhodni podatki brez podvajanj kot entiteta

Postopek deduplikacije ustvari novo deduplicirano entiteto za vsako od izvornih entitet. Te entitete in entiteto **ConflationMatchPairs: CustomerInsights** je mogoče najti z imenom **Deduplication_Datasource_Entity** v razdelku **Sistem** na strani **Entitete**.

Izhodna entiteta brez podvajanj vsebuje naslednje informacije:

- ID-je/ključe
  - Polji za primarni ključ in nadomestni ID. Polje z nadomestnim ID-jem je sestavljeno iz vseh nadomestnih ID-jev, identificiranih za zapis.
  - Polje Deduplication_GroupId prikazuje skupino ali gručo, identificirano znotraj entitete, ki združuje vse podobne zapise na podlagi določenih polj za odstranjevanje podvajanj. To se uporablja za namene sistemske obdelave. Če niso podana nobena pravila za ročno odstranjevanje podvajanj in veljajo sistemsko določena pravila za odstranjevanje podvajanj, tega polja v izhodni entiteti brez podvajanj morda ne boste našli.
  - Deduplication_WinnerId: to polje vsebuje ID zmagovalnega zapisa iz identificiranih skupin ali gruč. Če je vrednost Deduplication_WinnerId enaka vrednosti primarnega ključa za zapis, to pomeni, da gre za zmagovalni zapis.
- Polja, ki se uporabljajo za določanje pravil za odstranjevanje podvajanj.
- Polji Pravilo in Ocena označujeta, katera od pravil za odpravljanje podvajanj so bila uporabljena, ter rezultat, ki ga vrne algoritem za iskanje ujemanj.

[!INCLUDE[footer-include](includes/footer-banner.md)]
