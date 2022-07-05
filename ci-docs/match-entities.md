---
title: Pogoji ujemanja za poenotenje podatkov
description: Zagotovite ujemanje entitet za ustvarjanje poenotenih profilov strank.
recommendations: false
ms.date: 05/05/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: 770a18f3a7471714a7e044ae034da168a2601010
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082417"
---
# <a name="match-conditions-for-data-unification"></a>Pogoji ujemanja za poenotenje podatkov

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Ta korak pri poenotenju določa vrstni red ujemanja in pravila za ujemanje med entitetami. Ta korak zahteva vsaj dve entiteti.

> [!NOTE]
> Ko ustvarite pogoje ujemanja in izberete **Naslednji**, ne morete odstraniti izbrane entitete ali atributa. Po potrebi izberite **Nazaj** da pred nadaljevanjem pregledate izbrane entitete in atribute.

## <a name="include-enriched-entities-preview"></a>Vključi obogatene entitete (predogled)

Če ste obogatili entitete na ravni vir podatkov, da bi izboljšali rezultate združevanja, jih izberite. Za več informacij glejte [Obogatitev za vire podatkov](data-sources-enrichment.md). Če ste izbrali obogatene entitete na **Podvojeni zapisi** strani, vam jih ni treba znova izbrati.

1. Na **Ujemanje pogojev** stran, izberite **Uporabite obogatene entitete** na vrhu strani.

1. Iz **Uporabite obogatene entitete** izberite eno ali več obogatenih entitet.

1. Izberite **Dokončano**.

## <a name="specify-the-match-order"></a>Določanje vrstnega reda ujemanja

Vsako ujemanje združi dve ali več entitet v eno, konsolidirano entiteto. Hkrati skrbi za enolične zapise strank. Vrstni red ujemanja označuje vrstni red, v katerem sistem poskuša uskladiti zapise.

> [!IMPORTANT]
> Prva entiteta na seznamu se imenuje primarna entiteta. Primarna entiteta služi kot osnova za vaš nabor podatkov poenotenih profilov. Tej entiteti bodo dodane dodatne izbrane entitete.
>
> Pomembni premisleki:
>
> - Kot primarni subjekt izberite subjekt z najbolj popolnimi in zanesljivimi profili vaših strank.
> - Za primarno entiteto izberite entiteto, ki ima več skupnih atributov z drugimi entitetami (na primer ime, telefonska številka ali e-poštni naslov).

1. Na **Ujemanje pogojev** strani, uporabite puščice za premikanje navzgor in navzdol, da premaknete entitete v želenem vrstnem redu ali jih povlecite in spustite. Na primer, izberite **Kontakti: e-trgovina** kot primarni subjekt in **Zvestoba strank: zvestoba** kot drugi subjekt.

1. Če želite imeti vsak zapis v entiteti kot edinstveno stranko, ne glede na to, ali se najde ujemanje, izberite **Vključi vse zapise**. Vsi zapisi v tej entiteti, ki se ne ujemajo z zapisi v drugih entitetah, so vključeni v enoten profil. Zapisi, ki se ne ujemajo, se imenujejo enojni.
  
Primarni subjekt *Kontakti: e-trgovina* se ujema z naslednjo entiteto *Zvestoba strank: zvestoba*. Nabor podatkov, ki je rezultat prvega koraka ujemanja, se ujema z naslednjo entiteto, če imate več kot dve entiteti.

:::image type="content" source="media/m3_match.png" alt-text="Posnetek zaslona izbranega vrstnega reda ujemanja za entitete." lightbox="media/m3_match.png":::

## <a name="define-rules-for-match-pairs"></a>Določanje pravil za pare ujemanja

Pravila ujemanja določajo logiko, po kateri bo povezan določen par entitet. Pravilo je sestavljeno iz enega ali več pogojev.

Opozorilo poleg imena entitete pomeni, da za par ujemanja ni definirano pravilo ujemanja.

1. Izberite **Dodajte pravilo** za par subjektov za definiranje pravil ujemanja.

1. V **Dodajte pravilo** podoknu, konfigurirajte pogoje za pravilo.

   :::image type="content" source="media/m3_add_rule.png" alt-text="Posnetek zaslona podokna Dodaj pravilo.":::

   - **Izberite entiteto/polje (prva vrstica)** : Izberite povezano entiteto in atribut, da podate lastnost zapisa, ki je verjetno edinstvena za stranko. Na primer telefonska številka ali e-poštni naslov. Izogibajte se ujemanju po atributih vrste dejavnosti. Na primer ID nakupa verjetno ne bo imel ujemanja pri drugih vrstah zapisov.

   - **Izberite entiteto/polje (druga vrstica)** : Izberite atribut, ki se nanaša na atribut entitete, podane v prvi vrstici.

   - **Normaliziranje**: Izberite med naslednjimi možnostmi normalizacije za izbrane atribute.
     - **Številke** : pretvori druge številske sisteme, kot so rimske številke, v arabske številke. *VIII* postane *8*.
     - **Simboli** : Odstrani vse simbole in posebne znake. *Glava&Rama* postane *GlavaRama*.
     - **Besedilo z malimi črkami** : pretvori vse znake v male črke. *VSE Z VELIKIMI in Naslov* postane *vse z velikimi in naslov*.
     - **Vrsta (telefon, ime, naslov, organizacija)** : Standardizira imena, naslove, telefonske številke, naslove in organizacije.
     - **Unicode v ASCII** : pretvori zapis unicode v znake ASCII. */u00B2* postane *2*.
     - **Presledki** : Odstrani vse presledke. *Živjo,   svet* postane *Živjo,svet*.

   - **Natančnost**: nastavite raven natančnosti, ki se bo uporabljala za ta pogoj.
     - **Osnovni** : Izbirajte med *nizko (30 %)*, *(60 %)*, *(80 %)*, in *Točno (100%)*. Izberite **Točno** da se ujemajo samo z zapisi, ki se ujemajo 100 odstotkov.
     - **Po meri**: nastavite odstotek, ki ga morajo imeti zapisi, da se ujemajo. Sistem se bo ujemal samo z zapisi, ki presegajo ta prag.

   - **ime** : Ime za pravilo.

1. Če želite ujemati entitete samo, če atributi izpolnjujejo več pogojev, izberite **Dodaj** > **Dodajte pogoj** če želite pravilu ujemanja dodati več pogojev. Pogoji so povezani z logičnim operatorjem AND in se izvedejo le, če so izpolnjeni vsi pogoji.

1. Po želji razmislite o naprednih možnostih, kot je npr [izjeme](#add-exceptions-to-a-rule) oz [pogoje ujemanja po meri](#specify-custom-match-conditions).

1. Izberite **Končano** da dokončno uredim pravilo.

1. Po želji [dodajte več pravil](#add-rules-to-a-match-pair).

1. Kliknite **Naprej**.

> [!div class="nextstepaction"]
> [Naslednji korak: Poenotenje polj](merge-entities.md)

### <a name="add-rules-to-a-match-pair"></a>Dodajanje pravil paru ujemanja

Pravila ujemanja predstavljajo nabore pogojev. Če želite povezati entitete po pogojih na podlagi več atributov, dodajte več pravil.

1. Izberite **Dodajte pravilo** na entiteto, ki ji želite dodati pravila.

1. Sledite korakom v [Določite pravila za pare ujemanja](#define-rules-for-match-pairs).

> [!NOTE]
> Vrstni red pravil je pomemben. Algoritem ujemanja se poskuša ujemati z danim zapisom stranke na podlagi vašega prvega pravila in nadaljuje z drugim pravilom le, če s prvim pravilom ni bilo ujemanja.

## <a name="advanced-options"></a>Dodatne možnosti

### <a name="add-exceptions-to-a-rule"></a>Pravilu dodajte izjeme

V večini primerov ujemanje subjektov vodi do edinstvenih profilov strank s konsolidiranimi podatki. Za dinamično obravnavanje redkih primerov lažno pozitivnih in lažno negativnih rezultatov lahko definirate izjeme za pravilo ujemanja. Izjeme se uveljavijo po obdelavi pravil ujemanja in preprečijo ujemanje vseh zapisov, ki izpolnjujejo kriterije izjeme.

Na primer, če vaše pravilo ujemanja združuje priimek, mesto in datum rojstva, bi sistem identificiral dvojčka z istim priimek, ki živita v istem mestu kot isti profil. Določite lahko izjemo, ki se ne ujema s profili, če ime v entitetah, ki jih združite, nista enaka.

1. V **Uredi pravilo** podokno, izberite **Dodaj** > **Dodajte izjemo**.

1. Določite merila izjeme.

1. Izberite **Dokončano**, da shranite pravilo.

### <a name="specify-custom-match-conditions"></a>Določanje pogojev ujemanja po meri

Določite lahko pogoje, ki preglasijo privzeto logiko ujemanja. Na voljo so štiri možnosti:

|Možnost  |Description |Primer  |
|---------|---------|---------|
|Mora se ujemati     | Določa vrednosti, ki se vedno ujemajo.         |  Vedno se ujemajo *Mike* in *MikeR*.       |
|Nikoli se ne sme ujemati     | Opredeljuje vrednosti, ki se nikoli ne ujemajo.        | Nikoli se ne ujemajo *Janez* in *Jonathan*.        |
|Zaobitje po meri     | Definira vrednosti, ki jih mora sistem vedno prezreti v fazi ujemanja. |  Ignorirajte vrednosti *11111* in *neznano* med tekmo.        |
|Preslikava vzdevka    | Definiranje vrednosti, ki jih mora sistem obravnavati kot isto vrednost.         | Razmislite *Joe* biti enak *Jožef*.        |

1. Izberite **Po meri**.

   :::image type="content" source="media/m3_match_custom.png" alt-text="Gumb po meri":::

1. Izberite **Vrsta po meri** in izberite **Prenesite predlogo**. Za vsako možnost ujemanja potrebujete ločeno predlogo.

1. Odprite preneseno datoteko predloge in izpolnite podrobnosti. Predloga vsebuje polja, ki določajo entiteto in vrednosti primarnega ključa entitete, ki se uporabljajo v ujemanju po meri. Če želite, da se na primer primarni ključ *12345* iz entitete *Prodaja* vedno ujema s primarnim ključem *34567* iz entitete *Stik*, izpolnite predlogo:
    - Entity1: prodaja
    - Entity1Key: 12345
    - Entity2: stik
    - Entity2Key: 34567

   Ista datoteka predloge lahko določa zapise ujemanja po meri iz več entitet.

   Če želite za odpravljanje podvajanj iz entitete določiti iskanje ujemanja po meri, podajte isto entiteto kot Entity1 in Entity2 ter nastavite različne vrednosti primarnega ključa.

1. Ko dodate vse preglasitve, shranite datoteko predloge.

1. Odprite razdelek **Podatki** > **Viri podatkov** in datoteke predloge uvozite kot nove entitete.

1. Po nalaganju datotek izberite **Po meri** spet možnost. V spustnem meniju izberite zahtevane entitete in izberite **Končano**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Posnetek zaslona pogovornega okna za izbiro preglasitev za okoliščine ujemanja po meri.":::

1. Uporaba ujemanja po meri je odvisna od možnosti ujemanja, ki jo želite uporabiti.

   - Za **Vedno se ujemajo** oz **Nikoli se ne ujemajo**, nadaljujte z naslednjim korakom.
   - Za **Bypass** oz **Preslikava vzdevka**, izberite **Uredi** na obstoječe pravilo ujemanja ali ustvarite novo pravilo. V spustnem meniju Normalizacije izberite **Obvod po meri** oz **Preslikava vzdevka** možnost in izberite **Končano**.

1. Izberite **Končano** na **Po meri** podokno za uporabo konfiguracije ujemanja po meri.

> [!div class="nextstepaction"]
> [Naslednji korak: Poenotenje polj](merge-entities.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
