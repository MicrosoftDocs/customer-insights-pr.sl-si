---
title: Pred poenotenjem podatkov odstranite dvojnike
description: Drugi korak v procesu poenotenja je izbira, kateri zapis obdržati, ko so najdeni dvojniki.
recommendations: false
ms.date: 08/01/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: sstabbert
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: 3f84c1c149f0befcbe489ccdd8a666ce6d5d798a
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304493"
---
# <a name="remove-duplicates-before-unifying-data"></a>Pred poenotenjem podatkov odstranite dvojnike

Ta izbirni korak pri poenotenju vam omogoča nastavitev pravil za odpravo podvojenih zapisov **znotraj** subjekt. Deduplikacija prepozna več zapisov za stranko in izbere najboljši zapis za vodenje (na podlagi osnovnih nastavitev združevanja) ali združi zapise v enega (na podlagi naprednih nastavitev združevanja). Izvorni zapisi se na združeni zapis povežejo z nadomestnimi ID-ji. Če pravila niso konfigurirana, se uporabijo sistemsko definirana pravila.

## <a name="default-deduplication"></a>Privzeta deduplikacija

Sistemsko določena pravila veljajo, če niso dodana pravila za odstranjevanje dvojnikov.

- Primarni ključ je dedupliciran.
  Za vse zapise z istim primarnim ključem je **Najbolj napolnjena** zapis (tisti z najmanj ničelnimi vrednostmi) je zmagovalec.
- Vsa pravila ujemanja med entitetami se uporabijo za entiteto.
  Na primer: v koraku ujemanja, če se entiteta A ujema z entiteto B na *Polno ime* in *Datum rojstva*, potem je tudi entiteta A deduplicirana s strani *Polno ime* in *Datum rojstva*. Ker *Polno ime* in *Datum rojstva* so veljavni ključi za identifikacijo stranke v entiteti A, so ti ključi veljavni tudi za identifikacijo podvojenih strank v entiteti A.

## <a name="include-enriched-entities-preview"></a>Vključi obogatene entitete (predogled)

Če ste obogatili entitete na ravni vir podatkov, da bi izboljšali rezultate združevanja, jih izberite. Za več informacij glejte [Obogatitev podatkovnih virov](data-sources-enrichment.md).

1. Na **Podvojeni zapisi** stran, izberite **Uporabite obogatene entitete** na vrhu strani.

1. Iz **Uporabite obogatene entitete** podoknu izberite eno ali več obogatenih entitet.

1. Izberite **Dokončano**.

## <a name="define-deduplication-rules"></a>Določite pravila deduplikacije

1. Na **Podvojeni zapisi** strani, izberite entiteto in izberite **Dodaj pravilo** za določitev pravil deduplikacije.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="Posnetek zaslona strani s podvojenimi zapisi z označeno entiteto in prikazanim pravilom za dodajanje"  lightbox="media/m3_duplicates_showmore.png":::

   1. V **Dodaj pravilo** podoknu vnesite naslednje podatke:
      - **Izberite polje** : Izberite s seznama razpoložljivih polj iz entitete, za katero želite preveriti dvojnike. Izberite polja, ki so verjetno edinstvena vsaki stranki. Na primer e-poštni naslov ali kombinacija imena, mesta in telefonske številke.
      - **Normaliziranje**: Izberite med naslednjimi možnostmi normalizacije za izbrane atribute.
        - **Številke** : Pretvori druge številske sisteme, kot so rimske številke, v arabske številke. *VIII* postane *8*.
        - **Simboli** : Odstrani vse simbole in posebne znake. *Glava&Rama* postane *GlavaRama*.
        - **Besedilo v male črke: vse znake pretvori v male črke**. *VSE Z VELIKIMI in Naslov* postane *vse z velikimi in naslov*.
        - **Vrsta (telefon, ime, naslov, organizacija)** : standardizira imena, naslove, telefonske številke, naslove itd.
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

[!INCLUDE[footer-include](includes/footer-banner.md)]
