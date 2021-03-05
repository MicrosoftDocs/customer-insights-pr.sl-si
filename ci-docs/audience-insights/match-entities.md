---
title: Ujemanje entitet za poenotenje podatkov
description: Zagotovite ujemanje entitet za ustvarjanje poenotenih profilov strank.
ms.date: 10/14/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 05afd17b7f1b34f7f24a8fa8cb2dc32c1649d40f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267498"
---
# <a name="match-entities"></a>Ujemanje entitet

Po zaključku faze preslikave ste pripravljeni na ujemanje entitet. Faza ujemanja določa, kako združite nabore podatkov v nabor podatkov poenotenega profila stranke. Za fazo ujemanja potrebujete najmanj [dve preslikani entiteti](map-entities.md).

## <a name="specify-the-match-order"></a>Določanje vrstnega reda ujemanja

Odprite razdelek **Podatki** > **Poenoti** > **Ujemanje** in za začetek faze ujemanja izberite možnost **Nastavi vrstni red** .

Vsako ujemanje poenoti najmanj dve entiteti v eno entiteto, hkrati pa ohrani vse enolične zapise strank. V spodnjem primeru smo izbrali tri entitete: **ContactCSV: TestData** kot **primarno** entiteto, **WebAccountCSV: TestData** kot **entiteto 2** in **CallRecordSmall: TestData** kot **entiteto 3**. Diagram nad izbirami ponazarja, kako se bo izvedel vrstni red ujemanja.

> [!div class="mx-imgBorder"]
> ![Urejanje vrstnega reda ujemanja podatkov](media/configure-data-match-order-edit-page.png "Urejanje vrstnega reda ujemanja podatkov")
  
**Primarna** entiteta se ujema z **entiteto 2**. Nabor podatkov, ki je rezultat prvega ujemanja, se ujema z **entiteto 3**.
V tem primeru smo izbrali samo dve ujemanji, vendar jih sistem lahko podpira več.

> [!IMPORTANT]
> Entiteta, ki jo izberete kot svojo **primarno** entiteto, služi kot osnova za vaš poenoteni glavni nabor podatkov. Tej entiteti so dodane dodatne entitete, ki so izbrane med fazo ujemanja. Toda to ne pomeni, da bo poenotena entiteta vključevala *vse* podatke, vključene v to entiteto.
>
> Ko izbirate hierarhijo svojih entitet, razmislite o dveh stvareh:
>
> - Katera entiteta ima po vašem mnenju najbolj popolne in zanesljive podatke o svojih strankah?
> - Ali ima entiteta, ki ste jo pravkar identificirali, atribute, ki si jih delijo tudi druge entitete (na primer ime, telefonsko številko ali e-poštni naslov)? Če jih nima, izberite drugo najbolj zanesljivo entiteto.

Izberite **Dokončano**, da shranite vrstni red ujemanja.

## <a name="define-rules-for-your-first-match-pair"></a>Določanje pravil za prvi par ujemanja

Ko določite vrstni red ujemanja, na strani **Ujemanje** vidite določena ujemanja. Ploščice na vrhu zaslona bodo prazne, dokler ne zaženete vrstnega reda ujemanja.

> [!div class="mx-imgBorder"]
> ![Določanje pravil](media/configure-data-match-need-rules.png "Določanje pravil")

Opozorilo **Potrebna so pravila** sporoča, da ni določeno nobeno pravilo za par ujemanja. Pravila ujemanja določajo logiko, po kateri bo povezan določen par entitet.

1. Če želite določiti svoje prvo pravilo, odprite podokno **Definicija pravila** tako, da izberete ustrezno vrstico ujemanja v tabeli ujemanj (1) in nato še **Ustvari novo pravilo** (2).

   > [!div class="mx-imgBorder"]
   > ![Ustvarjanje novega pravila](media/configure-data-match-new-rule2.png "Ustvari novo pravilo")

2. V podoknu **Uredi pravilo** konfigurirajte pogoje za to pravilo. Posamezni pogoj predstavljata dve vrstici, ki vključujeta obvezne izbire.

   > [!div class="mx-imgBorder"]
   > ![Podokno za novo pravilo](media/configure-data-match-new-rule-condition.png "Podokno za novo pravilo")

   Entiteta/polje (prvi) – atribut, ki bo uporabljen za ujemanje iz entitete prvega para ujemanja. Primer je telefonska številka ali e-poštni naslov. Izberite atribut, ki je verjetno enoličen za stranko.

   > [!TIP]
   > Izogibajte se ujemanju na podlagi atributov vrste dejavnosti. Z drugimi besedami, če je videti, da je atribut dejavnost, potem je to morda slabo merilo za ujemanje.  

   Entiteta/polje (drugi) – atribut, ki bo uporabljen za ujemanje iz entitete drugega para ujemanja.

   Normalizacija – **način normalizacije**: za izbrane atribute so na voljo različne možnosti normalizacije. Na primer odstranjevanje ločil ali presledkov.

   Za normalizacijo imena organizacije (predogled) lahko izberete tudi **Vrsta (telefon, ime, organizacija)**.

   > [!div class="mx-imgBorder"]
   > ![Normalizacija – prodaja podjetjem](media/match-normalization-b2b.png "Normalizacija – prodaja podjetjem")

   Raven natančnosti – raven natančnosti, ki se bo uporabila za ta pogoj. Nastavitev ravni natančnosti za pogoj ujemanja je lahko dveh vrst: **Osnovno** in **Po meri**.  
   - Osnovno: izbirate lahko med štirimi možnostmi: »Nizko«, »Srednje«, »Visoko« in »Natančno«. Izberite **Natančno**, da povežete samo zapise, ki se ujemajo stoodstotno. Izberite eno od drugih ravni, da povežete zapise, ki niso stoodstotno enaki.
   - Po meri: z drsnikom določite odstotek po meri, ki je potreben za ujemanje zapisov, oziroma vnesite vrednost v polje **Po meri**. Sistem bo kot pare ujemanja povezal samo zapise, ki presežejo ta prag. Vrednosti na drsniku so med 0 in 1. 0,64 torej predstavlja 64 odstotkov.

3. Izberite **Dokončano**, da shranite pravilo.

### <a name="add-multiple-conditions"></a>Dodajanje več pogojev

Če želite, da se entitete ujemajo le, če je izpolnjenih več pogojev, dodajte več pogojev, ki so povezani prek operatorja IN.

1. V podoknu **Uredi pravilo** izberite **Dodaj pogoj**. Pogoje lahko tudi izbrišete, in sicer tako, da izberete gumb za odstranitev poleg obstoječega stanja.

2. Izberite **Dokončano**, da shranite pravilo.

## <a name="add-multiple-rules"></a>Dodajanje več pravil

Vsak pogoj velja za en par atributov, pravila pa predstavljajo niz pogojev. Če želite, da se vaše entitete ujemajo po različnih nizih atributov, lahko dodate več pravil.

1. Pri vpogledih v občinstvo izberite **Podatki** > **Poenoti** > **Ujemanje**.

2. Izberite entiteto, ki jo želite posodobiti, in nato **Dodaj pravila**.

3. Sledite postopku, kot je opisano v razdelku [Določanje pravil za prvi par ujemanja](#define-rules-for-your-first-match-pair).

> [!NOTE]
> Vrstni red pravil je pomemben. Algoritem ujemanja poskusi ujemanje na podlagi vašega prvega pravila in nadaljuje z drugim pravilom le, če pri prvem pravilu ni bilo ujemanj.

## <a name="define-deduplication-on-a-match-entity"></a>Opredelitev odstranjevanja podvajanj za entiteto ujemanja

Skupaj z določitvijo pravil za ujemanje med entitetami, kot je opisano v zgornjih razdelkih, lahko določite tudi pravila za odstranjevanje podvajanja. *Odstranjevanje podvajanja* je postopek. Prepozna podvojene zapise, jih združi v en zapis in poveže vse izvorne zapise s tem združenim zapisom z nadomestnimi ID-ji na združeni zapis.

Po prepoznavanju zapisa, pri katerem je bilo odstranjeno podvajanje, bo ta zapis uporabljen v postopku ujemanja med entitetami. Odstranjevanje podvajanja se izvaja na ravni entitete in ga je mogoče uporabiti za vsako entiteto, uporabljeno v postopku ujemanja.

### <a name="add-deduplication-rules"></a>Dodajanje pravila za odstranjevanje podvajanja

1. Pri vpogledih v občinstvo izberite **Podatki** > **Poenoti** > **Ujemanje**.

1. V razdelku **Spojeni dvojniki** izberite **Nastavitev entitet**.

1. V razdelku **Spoji nastavitve** izberite entitete, za katere želite uporabiti odstranjevanje podvajanja.

1. Določite, kako združiti podvojene zapise in izberite eno od treh možnosti spajanja:
   - *Najpogostejše*: opredeli zapis z najpogostejšimi atributi kot zapis zmagovalca. To je privzeta možnost spajanja.
   - *Najnovejše*: določi rekord zmagovalca glede na najnovejše rezultate. Zahteva datum ali številsko polje za določitev najnovejše izkušnje.
   - *Najstarejše*: določi rekord zmagovalca glede na najstarejše rezultate. Zahteva datum ali številsko polje za določitev najnovejše izkušnje.
 
   > [!div class="mx-imgBorder"]
   > ![1. korak pravil za odstranjevanje podvajanja](media/match-selfconflation.png "1. korak pravil za odstranjevanje podvajanja")
 
1. Ko so entitete izbrane in so nastavljene nastavitve spajanja, izberite **Ustvari novo pravilo** za določitev pravil o odstranjevanju podvajanja na ravni entitete.
   - Možnost **Izberite polje** navaja vsa razpoložljiva polja iz entitete, pri kateri želite odstraniti podvajanje izvornih podatkov.
   - Določite nastavitve normalizacije in natančnosti na podoben način, kot je določeno pri ujemanju med entitetami.
   - Določite lahko dodatne pogoje tako, da izberete **Dodaj pogoj**.
 
   > [!div class="mx-imgBorder"]
   > ![2. korak pravil za odstranjevanje podvajanja](media/match-selfconflation-rules.png "2. korak pravil za odstranjevanje podvajanja")

  Za entiteto lahko ustvarite več pravil za odstranjevanje podvajanja. 

1. Zagon postopka ujemanja zdaj združuje zapise na podlagi pogojev, določenih v pravilih za odstranjevanje podvajanja. Po združevanju zapisov se za določitev zapisa zmagovalca uporabi pravilnik spajanja.

1. Ta zapis zmagovalca se nato obdela v postopku preverjanja ujemanja med entitetami, skupaj z zapisi ne-zmagovalcev (na primer nadomestni ID-ji), da se izboljša kakovost ujemanja.

1. Vsa pravila po meri za ujemanje, določena za ujemanje v vseh primerih ali ujemanje v nobenem primeru, preglasijo pravila za odstranjevanje podvajanja. Če pravilo odstranjevanja podvajanja prepozna ujemajoče se zapise in je pravilo ujemanja po meri nastavljeno tako, da se nikoli ne ujema s temi zapisi, potem se ta dva zapisa ne bosta ujemala.

1. Po zagonu postopka ujemanja bo prikazana statistika odstranjevanja podvajanja.
   
> [!NOTE]
> Določanje pravil za odstranjevanje podvajanja ni obvezno. Če taka pravila niso konfigurirana, se uporabijo sistemsko določena pravila. Strnejo vse zapise, ki imajo enako kombinacijo vrednosti (natančno ujemanje), iz primarnega ključa in polj v pravilih ujemanja v en zapis, preden podatke entitet posredujejo ujemanju med entitetami za večjo zmogljivost in boljše delovanje sistema.

## <a name="run-your-match-order"></a>Zagon vrstnega reda ujemanja

Po določitvi pravil ujemanja, vključno s pravili ujemanja med entitetami in odstranjevanja podvajanja, lahko zaženete vrstni red ujemanja. Za začetek postopka izberite **Zaženi** na strani **Ujemanje**. Ustvarjanje algoritma ujemanja lahko traja nekaj časa. Lastnosti na strani **Ujemanje** ne morete spremeniti, dokler se postopek ujemanje ne zaključi. Ustvarjeno entiteto poenotenega profila stranke najdete na strani **Entitete**. Entiteta poenotene stranke se imenuje **ConflationMatchPairs : CustomerInsights**.

Če želite vnesti dodatne spremembe in ponovno zagnati korak, lahko prekličete ujemanje v teku. Izberite napis **Osveževanje ...**, nato pa **Prekliči posel** na dnu stranskega podokna, ki se prikaže.

Ko se postopek ujemanja dokonča, se napis **Osveževanje ...** spremeni v **Uspešno** in znova lahko uporabite vse funkcije strani.

Po prvem ujemanju se ustvari poenotena glavna enota. Po vseh naslednjih ujemanjih se ta entiteta razširi.

> [!TIP]
> Na voljo je [šest vrst stanja](system.md#status-types) za opravila/postopke. Poleg tega je večina postopkov [odvisna od drugih nadaljnjih postopkov](system.md#refresh-policies). Izberete lahko stanje postopka in si ogledate podrobnosti o poteku celotnega posla. Ko za enega izmed poslov izberete **Prikaži podrobnosti**, se prikažejo dodatne informacije: čas obdelave, zadnji datum obdelave ter vse napake in opozorila, povezana z opravilom.

## <a name="deduplication-output-as-an-entity"></a>Izhodni podatki brez podvajanj kot entiteta
Poleg enotne glavne entitete, ustvarjene kot del preverjanja medsebojnega ujemanja entitet, se za vsako entiteto iz vrstnega reda ujemanja s postopkom odstranjevanja podvajanj generira tudi nova entiteta, da so prepoznani zapisi brez podvajanj. Te entitete in entiteto **ConflationMatchPairs: CustomerInsights** je mogoče najti z imenom **Deduplication_Datasource_Entity** v razdelku **Sistem** na strani **Entitete**.

Izhodna entiteta brez podvajanj vsebuje naslednje informacije:
- ID-je/ključe
  - Polje primarnega ključa in pripadajoče polje nadomestnih ID-jev Polje nadomestnih ID-jev je sestavljeno iz vseh nadomestnih ID-jev, določenih za zapis.
  - Polje Deduplication_GroupId prikazuje skupino ali gručo, identificirano znotraj entitete, ki združuje vse podobne zapise na podlagi določenih polj za odstranjevanje podvajanj. To se uporablja za namene sistemske obdelave. Če niso podana nobena pravila za ročno odstranjevanje podvajanj in veljajo sistemsko določena pravila za odstranjevanje podvajanj, tega polja v izhodni entiteti brez podvajanj morda ne boste našli.
  - Deduplication_WinnerId: to polje vsebuje ID zmagovalnega zapisa iz identificiranih skupin ali gruč. Če je vrednost Deduplication_WinnerId enaka vrednosti primarnega ključa za zapis, to pomeni, da gre za zmagovalni zapis.
- Polja, ki se uporabljajo za določanje pravil za odstranjevanje podvajanj.
- Polji Pravilo in Ocena označujeta, katera od pravil za odpravljanje podvajanj so bila uporabljena, ter rezultat, ki ga vrne algoritem za iskanje ujemanj.

## <a name="review-and-validate-your-matches"></a>Pregled in preverjanje ujemanj

Ocenite kakovost parov ujemanja in jo natančneje določite:

- Na strani **Ujemanje** sta dve ploščici, ki prikazujeta začetne vpoglede v vaše podatke.

  - **Enolične stranke**: prikazuje število enoličnih profilov, ki jih je prepoznal sistem.
  - **Povezani zapisi**: prikazuje število ujemanj v vseh parih ujemanj.

- V tabeli **Vrstni red ujemanja** lahko ocenite rezultate posameznega para ujemanja tako, da primerjate število zapisov iz te entitete parov ujemanja z odstotkom uspešno povezanih zapisov.

- V razdelku **Pravila** entitete v tabeli **Vrstni red ujemanja** boste našli odstotek uspešno povezanih zapisov na ravni pravil. Če izberete simbol tabele poleg pravila, si lahko ogledate vse te zapise na ravni pravil. Priporočamo, da pregledate podmnožico zapisov in preverite, ali so bili pravilno povezani.

- Preskušajte različne prage natančnosti za pogoje, da določite optimalno vrednost.

  1. Izberite tri pike (...) za pravilo parov ujemanja, ki ga želite preskusiti, in nato **Uredi**.

  2. Izberite pogoj, ki ga želite preskusiti. Posamezni pogoj predstavlja ena vrstica v podoknu **Pravilo ujemanja**.

  3. Prikaz na strani **Predogled pogojev** je odvisen od stopnje natančnosti, ki ste jo izbrali za pogoj. Poiščite število povezanih in nepovezanih zapisov za izbrani pogoj.

     Bolje spoznajte učinke različnih mejnih ravni. Primerjate lahko, koliko zapisov se bo ujemalo na vsaki od mejnih ravni, in si ogledate zapise pod posamezno možnostjo. Izberite posamezno ploščico in preglejte podatke v razdelku tabele.

## <a name="optimize-your-matches"></a>Optimizacija ujemanj

Povečajte kakovost s ponovnim konfiguriranjem nekaterih parametrov ujemanja:

- **Spremenite vrstni red ujemanja** tako, da izberete **Uredi** in spremenite polja za vrstni red ujemanja.

  > [!div class="mx-imgBorder"]
  > ![Urejanje vrstnega reda ujemanja podatkov](media/configure-data-match-order-edit.png "Urejanje vrstnega reda ujemanja podatkov")

- Če ste določili več pravil, **spremenite vrstni red pravil**. Pravila ujemanja lahko prerazporedite tako, da v mreži pravil ujemanja izberete možnosti **Premakni navzgor** in **Premakni navzdol**.

  > [!div class="mx-imgBorder"]
  > ![Spreminjanje vrstnega reda pravil](media/configure-data-change-rule-order.png "Spreminjanje vrstnega reda pravil")

- Če ste določili pravilo ujemanja in želite ustvariti podobno pravilo s spremembami, **podvojite pravila**. To storite tako, da izberete **Podvoji**.

  > [!div class="mx-imgBorder"]
  > ![Podvajanje pravila](media/configure-data-duplicate-rule.png "Podvajanje pravila")

- **Deaktivirajte pravilo**, da se pravilo ujemanja obdrži in je hkrati izključeno iz postopka ujemanja.

  > [!div class="mx-imgBorder"]
  > ![Deaktiviranje pravila](media/configure-data-deactivate-rule.png "Deaktiviranje pravila")

- Izberite simbol **Uredi** in **uredite pravila**. Naredite lahko te spremembe:

  - Spremenite atribute za pogoj: v vrstici določenega pogoja izberite nove atribute.
  - Spremenite prag za pogoj: nastavite drsnik za natančnost.
  - Spremenite način normalizacije za pogoj: posodobite način normalizacije.

## <a name="specify-your-custom-match-records"></a>Določanje zapisov ujemanja po meri

Določite lahko pogoj, da se morajo določeni zapisi vedno ujemati oziroma se ne smejo nikoli ujemati. Ta pravila lahko množično naložite v postopek ujemanja.

1. Izberite možnost **Ujemanje po meri** na zaslonu **Vrstni red ujemanja**.

   > [!div class="mx-imgBorder"]
   > ![Ustvarjanje ujemanja po meri](media/custom-match-create.png "Ustvarjanje ujemanja po meri")

2. Če nimate naloženih entitet, se prikaže novo pogovorno okno **Ujemanje po meri**, v katerem morate vnesti nekaj podatkov. Če ste te podatke že navedli, preskočite na korak 8.

   > [!div class="mx-imgBorder"]
   > ![Novo pogovorno okno za ujemanje po meri](media/custom-match-new-dialog-box.png "Novo pogovorno okno za ujemanje po meri")

3. Izberite **Izpolnite predlogo**, da dobite datoteko predloge, ki določa, kateri zapisi iz katerih entitet se morajo vedno ujemati ali se ne smejo nikoli ujemati. Zapise »vedno se ujema« in zapise »nikoli se ne ujema« morate izpolniti ločeno v dveh različnih datotekah.

4. Predloga vsebuje polja, ki določajo entiteto in vrednosti primarnega ključa entitete, ki se uporabljajo v ujemanju po meri. Če na primer želite, da se primarni ključ 12345 iz entitete prodaje vedno ujema s primarnim ključem 34567 iz entitete stika, morate določiti naslednje:
    - Entity1: prodaja
    - Entity1Key: 12345
    - Entity2: stik
    - Entity2Key: 34567

   Ista datoteka predloge lahko določa zapise ujemanja po meri iz več entitet.
   
   Če želite za odpravljanje podvajanj iz entitete določiti iskanje ujemanja po meri, podajte isto entiteto kot Entity1 in Entity2 ter nastavite različne vrednosti primarnega ključa.

5. Ko dodate vse preglasitve, ki jih želite uporabiti, shranite datoteko predloge.

6. Odprite razdelek **Podatki** > **Viri podatkov** in datoteke predloge uvozite kot nove entitete. Po uvozu jih lahko uporabite za določanje konfiguracije ujemanja.

7. Ko so datoteke naložene in entitete na voljo, znova izberite možnost **Ujemanje po meri**. Videli boste možnosti za določanje entitet, ki jih želite vključiti. V spustnem meniju izberite potrebne entitete.

   > [!div class="mx-imgBorder"]
   > ![Preglasitve ujemanja po meri](media/custom-match-overrides.png "Preglasitve ujemanja po meri")

8. Izberite entitete, ki jih želite uporabiti za možnosti **Vedno se ujema** in **Nikoli se ne ujema**, ter nato še **Dokončano**.

9. Na strani **Ujemanje** izberite **Shrani** za konfiguracijo ujemanja po meri, ki ste jo pravkar nastavili.

10. Na strani **Ujemanje** izberite **Zaženi**, da začnete postopka ujemanja, in konfiguracija ujemanja po meri bo začela veljati. Nabor konfiguracij preglasi vsa pravila, nastavljena v sistemu.

11. Ko je ujemanje končano, lahko preverite entiteto **ConflationMatchPair**, da potrdite, da so preglasitve uporabljene v ujemanjih.

## <a name="next-step"></a>Naslednji korak

Ko dokončate postopek ujemanja za vsaj en par ujemanja, lahko morebitne spore v podatkih razrešite po navodilih v temi [**Spajanje**](merge-entities.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]