---
title: Ujemanje entitet za poenotenje podatkov
description: Zagotovite ujemanje entitet za ustvarjanje poenotenih profilov strank.
ms.date: 02/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7ad08b8b782654939c6bfc2ca330a3d31e71054a2f2c97a921971d1056b7cd38
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033697"
---
# <a name="match-entities"></a>Ujemanje entitet

Faza ujemanja določa, kako združite nabore podatkov v nabor podatkov poenotenega profila stranke. Ko zaključite [korak preslikavanja](map-entities.md) v postopku poenotenja podatkov, ste pripravljeni na ujemanje entitet. Za fazo ujemanja potrebujete najmanj dve preslikani entiteti.

Stran za ujemanje ima tri razdelke: 
- Ključne meritve, ki povzemajo število ujemajočih se zapisov
- Vrstni red ujemanja in pravila za ujemanje med entitetami
- Pravila za odstranjevanje podvajanj pri ujemanju entitet

## <a name="specify-the-match-order"></a>Določanje vrstnega reda ujemanja

Odprite razdelek **Podatki** > **Poenoti** > **Ujemanje** in za začetek faze ujemanja izberite možnost **Nastavi vrstni red** .

Vsako ujemanje združi dve ali več entitet v eno, konsolidirano entiteto. Hkrati skrbi za enolične zapise strank. Izbrali smo na primer dve entiteti: **eCommerce:eCommerceContacts** kot primarno entiteto in **LoyaltyScheme:loyCustomers** kot drugo entiteto. Vrstni red entitet določa, v katerem vrstnem redu bo sistem poskušal ujemati zapise.

:::image type="content" source="media/match-page.png" alt-text="Posnetek zaslona strani ujemanja v območju Unify pri postopku poenotenja podatkov.":::
  
Primarna entiteta *eCommerce:eCommerceContacts* se ujema z naslednjo entiteto *LoyaltyScheme:loyCustomers*. Nabor podatkov, ki je rezultat prvega koraka ujemanja, se ujema z naslednjo entiteto, če imate več kot dve entiteti.

> [!IMPORTANT]
> Entiteta, ki jo izberete kot svojo primarno entiteto, služi kot osnova za vaš nabor podatkov o poenotenih profilih. Tej entiteti so dodane dodatne entitete, ki so izbrane med fazo ujemanja. To ne pomeni, da bo poenotena entiteta vključevala *vse* podatke, vključene v to entiteto.
>
> Ko izbirate hierarhijo svojih entitet, razmislite o dveh stvareh:
>
> - Kot primarno entiteto izberite entiteto z najbolj popolnimi in zanesljivimi podatki o profilu vaših strank.
> - Kot primarno entiteto izberite entiteto, ki ima več skupnih atributov z drugimi entitetami (na primer ime, telefonska številka ali e-poštni naslov).

Ko določite vrstni reda ujemanja, boste videli določene pare ujemanj v razdelku **Podrobnosti o ujemajočih se zapisih** pod **Podatki** > **Poenotenje** > **Ujemanje**. Ključne meritve bodo prazne, dokler se postopek ujemanja ne zaključi.

## <a name="define-rules-for-match-pairs"></a>Določanje pravil za pare ujemanja

Pravila ujemanja določajo logiko, po kateri bo povezan določen par entitet.

Opozorilo **Potrebuje pravila** poleg imena entitete kaže, da za par ujemanja ni določeno pravilo ujemanja. 

:::image type="content" source="media/match-rule-add.png" alt-text="Posnetek zaslona razdelka «Podrobnosti o ujemajočem se zapisu» s kontrolnikom za dodajanje označenih pravil.":::

1. Izberite **Dodajanje pravil** pod entiteto v razdelku **Podrobnosti o ujemajočih se zapisih** za določitev pravil ujemanja.

1. V podoknu **Ustvarjanje pravila**, konfigurirajte pogoje za pravilo.

   :::image type="content" source="media/match-rule-conditions.png" alt-text="Posnetek zaslona odprtega pravila ujemanja z dodanimi pogoji.":::

   - **Entiteta/polje (prva vrstica)**: Izberite povezano entiteto in atribut, da določite lastnost zapisa, ki je verjetno edinstvena stranki. Na primer telefonska številka ali e-poštni naslov. Izogibajte se ujemanju po atributih vrste dejavnosti. Na primer ID nakupa verjetno ne bo imel ujemanja pri drugih vrstah zapisov.

   - **Entiteta/polje (druga vrstica)**: Izberite atribut, ki se nanaša na atribut entitete, določene v prvi vrstici.

   - **Normaliziranje**: Izberite med naslednjimi možnostmi normalizacije za izbrane atribute. 
     - Presledek: odstrani vse presledke. *Živjo,   svet* postane *Živjo,svet*.
     - Simboli: odstrani vse simbole in posebne znake. *Glava&Rama* postane *GlavaRama*.
     - Besedilo z malimi črkami: pretvori vse znake v male črke. *VSE Z VELIKIMI in Naslov* postane *vse z velikimi in naslov*.
     - Unicode v ASCII: pretvori zapis unicode v znake ASCII. */u00B2* postane *2*.
     - Številke: pretvori druge številske sisteme, na primer rimske številke, v arabske številke. *VIII* postane *8*.
     - Semantične vrste: standardizira imena, nazive, telefonske številke, naslove itd. 

   - **Natančnost**: nastavite raven natančnosti, ki se bo uporabljala za ta pogoj. 
     - **Osnovno**: izberite med *nizko*, *srednje*, *visoko* in *popolno*. Izberite **Natančno**, da povežete samo zapise, ki se ujemajo stoodstotno. Izberite eno od drugih ravni, da povežete zapise, ki niso stoodstotno enaki.
     - **Po meri**: nastavite odstotek, ki ga morajo imeti zapisi, da se ujemajo. Sistem se bo ujemal samo z zapisi, ki presegajo ta prag.

1. Navedite **Ime** za pravilo.

1. [Dodajte več pogojev](#add-conditions-to-a-rule) ali izberite **Končano** za dokončanje pravila.

1. Po želji [dodajte več pravil](#add-rules-to-a-match-pair).

1. Če želite uporabiti spremembe, izberite **Shrani**.

### <a name="add-conditions-to-a-rule"></a>Dodajanje pogojev pravilu

Če želite ujemati entitete le, če atributi izpolnjujejo več pogojev, pravilu ujemanja dodajte več pogojev. Pogoji so povezani z logičnim operatorjem AND in se izvedejo le, če so izpolnjeni vsi pogoji.

1. Pojdite v **Podatki** > **Poenotenje** > **Ujemanje** in izberite **Uredi** za pravilo, ki mu želite dodati pogoje.

1. V podoknu **Uredi pravilo** izberite **Dodaj pogoj**.

1. Izberite **Dokončano**, da shranite pravilo.

### <a name="add-rules-to-a-match-pair"></a>Dodajanje pravil paru ujemanja

Pravila ujemanja predstavljajo nabore pogojev. Za ujemanje entitet pod pogoji na osnovi več atributov dodajte več pravil.

1.  Pojdite v **Podatki** > **Poenotenje** > **Ujemanje** in izberite **Dodaj pravilo** za entiteto, ki ji želite dodati pravila.

2. Sledite korakom v [Določite pravila za pare ujemanja](#define-rules-for-match-pairs).

> [!NOTE]
> Vrstni red pravil je pomemben. Algoritem ujemanja poskuša ujemati na podlagi vašega prvega pravila in nadaljuje z drugim pravilom le, če s prvim pravilom ni bilo identificiranih nobenih zadetkov.

### <a name="change-the-entity-order-in-match-rules"></a>Spreminjanje vrstnega reda entitete v pravilih ujemanja

Entitete za pravila ujemanja lahko preuredite, če želite spremeniti vrstni red njihove obdelave. Pravila, ki so v sporu zaradi spremenjenega vrstnega reda, bodo odstranjena. Odstranjena pravila morate znova ustvariti s posodobljeno konfiguracijo.

1. Odprite zavihek **Podatki** > **Poenotenje** > **Ujemanje** in izberite možnost **Uredi**.

1. V podoknu **Urejanje pravila** izberite kontrolnik za **premik gor/dol** ali povlecite in spustite entitete, če želite spremeniti vrstni red.

   :::image type="content" source="media/reorder-match-rules.png" alt-text="Možnosti za spreminjanje vrstnega reda obdelave entitet v fazi ujemanja.":::

1. Izberite **Dokončano**, da shranite pravilo.

## <a name="define-deduplication-on-a-match-entity"></a>Opredelitev odstranjevanja podvajanj za entiteto ujemanja

Poleg [pravil ujemanja med entitetami](#define-rules-for-match-pairs) lahko določite tudi pravila za odstranjevanje podvajanja. *Odstranjevanje podvajanja* je še en postopek pri ujemanju zapisov. Identificira podvojene zapise in jih združi v en zapis. Izvorni zapisi se na združeni zapis povežejo z nadomestnimi ID-ji.

Zapisi, pri katerih je bilo odstranjeno podvajanje, bodo uporabljeni v postopku ujemanja med entitetami. Odstranjevanje podvajanja se zgodi na posameznih entitetah in ga je mogoče konfigurirati za vsako entiteto, uporabljeno v parih ujemanja.

Določanje pravil za odstranjevanje podvajanja ni obvezno. Če taka pravila niso konfigurirana, se uporabijo sistemsko določena pravila. Vse zapise združijo v en zapis, preden podatke entitete posredujejo ujemanju med entitetami za večjo zmogljivost.

### <a name="add-deduplication-rules"></a>Dodajanje pravila za odstranjevanje podvajanja

1. Izberite **Podatki** > **Poenotenje** > **Ujemanje**.

1. V razdelku **Spojeni dvojniki** izberite **Nastavitev entitet**. Če so pravila za odstranjevanje ponavljanja že ustvarjena, izberite **Uredi**.

1. V podoknu **Spoji nastavitve** izberite entitete, na katerih želite zagnati odstranjevanje podvajanja.

1. Določite, kako združiti podvojene zapise, in izberite eno od treh možnosti:
   - **Najpogostejše**: opredeli zapis atributa z najbolj izpolnjenimi polji kot zapis zmagovalca. To je privzeta možnost spajanja.
   - **Najnovejše**: določi rekord zmagovalca glede na najnovejše rezultate. Zahteva datum ali številsko polje za določitev najnovejše izkušnje.
   - **Najstarejše**: določi rekord zmagovalca glede na najstarejše rezultate. Zahteva datum ali številsko polje za določitev najnovejše izkušnje.
 
   > [!div class="mx-imgBorder"]
   > ![1. korak pravil za odstranjevanje podvajanja.](media/match-selfconflation.png "1. korak pravil za odstranjevanje podvajanja")
 
1. Ko so entitete izbrane in so nastavljene nastavitve spajanja, izberite **Dodaj pravilo** za določitev pravil o odstranjevanju podvajanja na ravni entitete.
   - **Izberite polje** navede vsa razpoložljiva polja te entitete. Izberite polje, v katerem želite preveriti dvojnike. Izberite polja, ki so verjetno edinstvena vsaki stranki. Na primer e-poštni naslov ali kombinacija imena, mesta in telefonske številke.
   - Določite nastavitve normalizacije in natančnosti.
   - Določite več pogojev tako, da izberete **Dodaj pogoj**.
 
   > [!div class="mx-imgBorder"]
   > ![2. korak pravil za odstranjevanje podvajanja.](media/match-selfconflation-rules.png "2. korak pravil za odstranjevanje podvajanja")

  Za entiteto lahko ustvarite več pravil za odstranjevanje podvajanja. 

1. Zagon postopka ujemanja zdaj združuje zapise na podlagi pogojev, določenih v pravilih za odstranjevanje podvajanja. Po združevanju zapisov se za določitev zapisa zmagovalca uporabi pravilnik spajanja.

1. Ta zapis zmagovalca se nato obdela v postopku preverjanja ujemanja med entitetami, skupaj z zapisi ne-zmagovalcev (na primer nadomestni ID-ji), da se izboljša kakovost ujemanja.

1. Vsa določena pravila ujemanja po meri prepišejo pravila za odstranjevanje podvajanja. Če pravilo odstranjevanja podvajanja prepozna ujemajoče se zapise in je pravilo ujemanja po meri nastavljeno tako, da se nikoli ne ujema s temi zapisi, potem se ta dva zapisa ne bosta ujemala.

1. Po [zagonu postopka ujemanja](#run-the-match-process) bo prikazana statistika odstranjevanja podvajanja v ploščicah ključnih meritev.

### <a name="deduplication-output-as-an-entity"></a>Izhodni podatki brez podvajanj kot entiteta

Postopek odstranjevanja podvajanja ustvari novo entiteto za vsako entiteto iz parov ujemanja, da identificira zapise, pri katerih je bilo odstranjeno podvajanje. Te entitete in entiteto **ConflationMatchPairs: CustomerInsights** je mogoče najti z imenom **Deduplication_Datasource_Entity** v razdelku **Sistem** na strani **Entitete**.

Izhodna entiteta brez podvajanj vsebuje naslednje informacije:
- ID-je/ključe
  - Polje primarnega ključa in pripadajoče polje nadomestnih ID-jev Polje nadomestnih ID-jev je sestavljeno iz vseh nadomestnih ID-jev, določenih za zapis.
  - Polje Deduplication_GroupId prikazuje skupino ali gručo, identificirano znotraj entitete, ki združuje vse podobne zapise na podlagi določenih polj za odstranjevanje podvajanj. To se uporablja za namene sistemske obdelave. Če niso podana nobena pravila za ročno odstranjevanje podvajanj in veljajo sistemsko določena pravila za odstranjevanje podvajanj, tega polja v izhodni entiteti brez podvajanj morda ne boste našli.
  - Deduplication_WinnerId: to polje vsebuje ID zmagovalnega zapisa iz identificiranih skupin ali gruč. Če je vrednost Deduplication_WinnerId enaka vrednosti primarnega ključa za zapis, to pomeni, da gre za zmagovalni zapis.
- Polja, ki se uporabljajo za določanje pravil za odstranjevanje podvajanj.
- Polji Pravilo in Ocena označujeta, katera od pravil za odpravljanje podvajanj so bila uporabljena, ter rezultat, ki ga vrne algoritem za iskanje ujemanj.
   
## <a name="run-the-match-process"></a>Zagon postopka ujemanja

Ko so pravila ujemanja konfigurirana, vključno s pravili ujemanja med entitetami in odstranjevanja podvajanja, lahko zaženete postopek ujemanja. 

Pojdite v **Podatki** > **Poenotenje** > **Ujemanje** in izberite **Zaženi** za začetek postopka. Algoritem za ujemanje porabi nekaj časa za dokončanje, konfiguracije pa ne morete spremeniti, dokler postopek ni dokončan. Za spreminjanje lahko prekličete postopek. Izberite stanje posla in izberite **Prekliči posel** v podoknu **Podrobnosti o napredku**.

Rezultat uspešnega izvajanja, poenoteno entiteto profila stranke, boste našli na strani **Entitete**. Poenotena entiteta stranke se imenuje **Stranke** v razdelku **Profili**. Prvo uspešno izvajanje ujemanja ustvari poenoteno entiteto *stranke*. Vsa naslednja izvajanja ujemanja to entiteto razširijo.

> [!TIP]
> Ko zaženete postopek ujemanja, izberite stanje procesa, da odprete podokno **Podrobnosti opravila**. Ponuja pregled časa obdelave, zadnjega datuma obdelave ter vseh napak in opozoril, povezanih z opravilom. Izberite **Glej podrobnosti**, da vidite, katere entitete so sodelovale v postopku ujemanja, katera pravila so zanje veljala in ali so bile posodobitve uspešno objavljene.  
> Na voljo je [šest vrst stanja](system.md#status-types) za opravila/postopke. Poleg tega je večina postopkov [odvisna od drugih nadaljnjih postopkov](system.md#refresh-policies).  
> :::image type="content" source="media/process-detail-path.png" alt-text="Pot do več podrobnosti o obdelavi s povezave do stanja opravila.":::

## <a name="review-and-validate-your-matches"></a>Pregled in preverjanje ujemanj

Pojdite v **Podatki** > **Poenotenje** > **Ujemanje**, da ocenite kakovost svojih parov ujemanja in jih po potrebi izboljšate.

Ploščice na vrhu strani prikazujejo ključne meritve, ki seštejejo število ujemajočih se zapisov in dvojnikov.

:::image type="content" source="media/match-KPIs.png" alt-text="Obrezan posnetek zaslona ključnih meritev na strani «Ujemanje» s številkami in podrobnostmi.":::

- **Enolični izvorni zapisi** prikazuje število posameznih izvornih zapisov, ki so bili obdelani v zadnjem izvajanju ujemanja.
- **Ujemajoči se in neujemajoči se zapisi** označujejo, koliko enoličnih zapisov ostane po obdelavi pravil ujemanja.
- **Samo ujemajoči se zapisi** prikazuje število ujemanj v vseh vaših parih ujemanja.

Rezultate vsakega para ujemanja in njegova pravila lahko ocenite v tabeli **Podrobnosti o ujemajočih se zapisih**. Primerjajte število zapisov iz parov ujemanja z odstotkom uspešno ujemajočih se zapisov.

Preglejte pravila para ujemanja, da boste videli odstotek uspešno ujemajočih se zapisov na ravni pravil. Izberite tri pike (...) in nato izberite **Predogled ujemanja** za ogled vseh teh zapisov na ravni pravil. Priporočamo, da si ogledate nekaj zapisov in preverite, ali so se pravilno ujemali.

Preskusite različne pragove natančnosti v pogojih, da poiščete optimalno vrednost.

  1. Izberite tri pike (...) za pravilo, s katerim želite eksperimentirati, in izberite **Uredi**.

  2. Vrednosti natančnosti spremenite v pogojih, ki jih želite popraviti.

  3. Izberite **Predogled**, da boste videli število ujemajočih se in neujemajočih se zapisov za izbrani pogoj.

## <a name="manage-match-rules"></a>Upravljanje pravil ujemanja

Večino parametrov ujemanja lahko znova konfigurirate in prilagodite.

:::image type="content" source="media/match-rules-management.png" alt-text="Posnetek zaslona spustnega menija z možnostmi pravil ujemanja.":::

- Če ste določili več pravil, **spremenite vrstni red pravil**. Pravila ujemanja lahko preuredite tako, da izberete možnosti **Premakni navzgor** in **Premakni navzdol** ali da povlečete in spustite.

- **Spremenite pogoje pravila** tako, da izberete **Uredi** in izberete različna polja.

- **Deaktivirajte pravilo**, da se pravilo ujemanja obdrži in je hkrati izključeno iz postopka ujemanja.

- **Podvojite pravila**, če ste definirali pravilo ujemanja in bi radi ustvarili podobno pravilo s spremembami in izberite **Dvojnik**.

- **Izbrišite pravilo** tako, da izberete simbol **Izbriši**.

## <a name="specify-custom-match-conditions"></a>Določanje pogojev ujemanja po meri

Določite lahko pogoj, da se morajo določeni zapisi vedno ujemati oziroma se ne smejo nikoli ujemati. Ta pravila lahko naložite, da preglasite standardni postopek ujemanja. Če sta na primer John Doe I in John Doe II v naših evidencah, se lahko sistem z njima ujema kot z eno osebo. Pravila ujemanja po meri vam omogočajo, da določite, naj se njihovi profili nanašajo na različne ljudi. 

1. Pojdite v **Podatki** > **Poenotenje** > **Ujemanje** in izberite **Ujemanje po meri** v razdelku **Podrobnosti o ujemajočih se zapisih**.

  :::image type="content" source="media/custom-match-create.png" alt-text="Posnetek zaslona razdelka pravil ujemanja z označenim kontrolnikom za dodajanje pravil.":::

1. Če niste nastavili pravil za ujemanje po meri, boste videli novo podokno **Ujemanje po meri** z več podrobnostmi.

1. Izberite **Izpolnite predlogo**, da dobite datoteko predloge, ki določa, kateri zapisi iz katerih entitet se morajo vedno ujemati ali se ne smejo nikoli ujemati. Zapise »vedno se ujema« in zapise »nikoli se ne ujema« morate izpolniti ločeno v dveh različnih datotekah.

1. Predloga vsebuje polja, ki določajo entiteto in vrednosti primarnega ključa entitete, ki se uporabljajo v ujemanju po meri. Če želite, da se na primer primarni ključ *12345* iz entitete *Prodaja* vedno ujema s primarnim ključem *34567* iz entitete *Stik*, izpolnite predlogo:
    - Entity1: prodaja
    - Entity1Key: 12345
    - Entity2: stik
    - Entity2Key: 34567

   Ista datoteka predloge lahko določa zapise ujemanja po meri iz več entitet.
   
   Če želite za odpravljanje podvajanj iz entitete določiti iskanje ujemanja po meri, podajte isto entiteto kot Entity1 in Entity2 ter nastavite različne vrednosti primarnega ključa.

1. Ko dodate vse preglasitve, ki jih želite uporabiti, shranite datoteko predloge.

1. Odprite razdelek **Podatki** > **Viri podatkov** in datoteke predloge uvozite kot nove entitete. Po uvozu jih lahko uporabite za določanje konfiguracije ujemanja.

1. Ko so datoteke naložene in entitete na voljo, znova izberite možnost **Ujemanje po meri**. Videli boste možnosti za določanje entitet, ki jih želite vključiti. V spustnem meniju izberite zahtevane entitete.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Posnetek zaslona pogovornega okna za izbiro preglasitev za okoliščine ujemanja po meri.":::

1. Izberite entitete, ki jih želite uporabiti za možnosti **Vedno se ujema** in **Nikoli se ne ujema**, ter nato še **Dokončano**.

1. Izberite **Shrani** na strani **Ujemanje**, da uporabite konfiguracijo ujemanja po meri.

1. Izberite **Zaženi** na strani **Ujemanje**, da začnete postopek iskanja ujemanj. Konfiguracija ujemanja po meri preglasi druga določena pravila ujemanja.

> [!TIP]
> Pojdite v **Podatki** > **Entitete** in preglejte entiteto **ConflationMatchPair**, da potrdite uporabo preglasitev.

## <a name="next-step"></a>Naslednji korak

Ko dokončate postopek ujemanja za vsaj en par ujemanja, lahko morebitne spore v podatkih razrešite po navodilih v temi [**Spajanje**](merge-entities.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
