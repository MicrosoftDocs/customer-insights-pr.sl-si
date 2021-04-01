---
title: Ustvarjanje in upravljanje segmentov
description: Ustvarite segmente strank, da jih združite na podlagi različnih atributov.
ms.date: 03/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a6e8a3216a2c0738d60247054afa9fc18412f55
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597079"
---
# <a name="create-and-manage-segments"></a>Ustvarjanje in upravljanje segmentov

Segmenti vam omogočajo, da svoje stranke razvrstite na podlagi demografskih, transakcijskih ali vedenjskih atributov. Segmente lahko uporabite za ciljanje promocijskih akcij, prodajnih dejavnosti in ukrepov za podporo strankam, da dosežete svoje poslovne cilje.

Za entiteto profila stranke in njene povezane entitete lahko določite zapletene filtre. Po obdelavi vsak segment ustvari niz zapisov strank, ki jih lahko izvozite in obdelate. Veljajo nekatere [omejitve storitev](service-limits.md).

Če ni drugače določeno, so vsi segmenti **Dinamični segmenti**, ki se osvežujejo po rednem urniku.

Naslednji primer prikazuje zmogljivost segmentacije. Določili smo segment za stranke, ki so v zadnjih 90 dneh naročile blaga v vrednosti vsaj 500 USD *in* ki so bile vključene v klic storitev za stranke, ki je bil posredovan na višjo raven.

> [!div class="mx-imgBorder"]
> ![Več skupin](media/segmentation-group1-2.png "Več skupin")

## <a name="create-a-new-segment"></a>Ustvarjanje novega segmenta

Segmenti se upravljajo na strani **Segmenti**.

1. Pri vpogledih v občinstvo odprite stran **Segmenti**.

1. Izberite **Novo** > **Prazen segment**.

1. Na strani **Nov segment** izberite vrsto segmenta in vnesite **ime**.

   Po želji vnesite prikazno ime in opis, s katerim boste lažje prepoznali segment.

1. Izberite **Naprej**, da se pomaknete na stran **Graditelj segmentov**, kjer določite skupino. Skupina je nabor strank.

1. Izberite entiteto, ki vključuje atribut, po katerem želite segmentirati.

1. Izberite atribut, po katerem želite segmentirati. Ta atribut ima lahko eno od štirih vrst vrednosti: numerično, niz, datum ali logična vrednost.

1. Izberite operator in vrednost za izbrani atribut.

   > [!div class="mx-imgBorder"]
   > ![Filter skupine po meri](media/customer-group-numbers.png "Filter skupine strank")

   |Število |Definicija  |
   |---------|---------|
   |1     |Entity          |
   |2     |Atribut          |
   |3    |Operator         |
   |4    |Vrednost         |

8. Če je entiteta povezana s poenoteno entiteto stranke prek [odnosov](relationships.md), morate določiti pot odnosa, da ustvarite veljaven segment. Dodajte entitete s poti odnosa, dokler se na spustnem meniju ne pojavi možnost za izbiro entitete **Stranka: CustomerInsights**. Nato za vsak pogoj izberite možnost **Vsi zapisi**.

   > [!div class="mx-imgBorder"]
   > ![Pot odnosa med ustvarjanjem segmenta](media/segments-multiple-relationships.png "Pot odnosa med ustvarjanjem segmenta")

1. Segmenti privzeto generirajo izhodno entiteto, ki vsebuje vse atribute profilov strank, ki se ujemajo z določenimi filtri. Če segment temelji na drugih entitetah kot na entiteti *stranke*, lahko v izhodno entiteto dodate več atributov teh entitet. Izberite **Atributi projekta**, da izberete atribute, ki bodo dodani izhodni entiteti.  

   
   Primer: Segment temelji na entiteti, ki vsebuje podatke o dejavnostih strank, povezane z entiteto *stranke*. Segment išče vse stranke, ki so v zadnjih 60 dneh poklicale službo za pomoč uporabnikom. Trajanje in število klicev lahko v izhodni entiteti priložite v vse ustrezne zapise strank, ki se ujemajo. Te informacije so lahko koristne za pošiljanje e-pošte strankam, ki so pogosto klicale, s koristnimi povezavami do spletnih člankov za pomoč in pogostih vprašanj.

1. Izberite **Shrani**, da shranite segment. Če so vse zahteve potrjene, bo vaš segment shranjen in obdelan. V nasprotnem primeru bo shranjen kot osnutek.

1. Izberite **Nazaj na segmente**, da se vrnete na stran **Segmenti**.

## <a name="manage-existing-segments"></a>Upravljanje obstoječih segmentov

Na strani **Segmenti** si lahko ogledate vse shranjene segmente in jih upravljate.

Vsak segment predstavlja vrstica, ki vključuje dodatne informacije o segmentu.

Segmente lahko razvrstite v stolpcu tako, da izberete naslov stolpca.

Za filtriranje segmentov uporabite polje **Iskanje** v zgornjem desnem kotu.

> [!div class="mx-imgBorder"]
> ![Možnosti za upravljanje obstoječega segmenta](media/segments-selected-segment.png "Možnosti za upravljanje obstoječega segmenta")

Ko izberete segment, je na voljo naslednje dejanje:

- Na voljo je **Prikaz** podrobnosti o odsekih, vključno s trendom števila članov in predogledom članov segmenta.
- Za spreminjanje lastnosti segmenta lahko uporabite možnost **Uredi**.
- **Ustvarjanje dvojnika** segmenta. Takoj lahko uredite njegove lastnosti ali preprosto shranite dvojnik.
- Za vključitev najnovejših podatkov lahko izberete **Osveži**.
- Segment lahko aktivirate ali deaktivirate prek možnosti **Aktiviraj** ali **Deaktiviraj**. Segmenti imajo dve možni stanji - aktivno ali neaktivno. Stanji sta vam lahko v pomoč pri urejanju segmenta. Za neaktivne segmente definicija segmenta obstaja, vendar še ne vsebuje nobene stranke. Ko aktivirate segment, se njegovo stanje spremeni iz »neaktiven« v »aktiven« in začne iskati stranke, ki ustrezajo definiciji segmenta. Če je konfigurirana [načrtovana osvežitev](system.md#schedule-tab), je **Stanje** neaktivnih segmentov navedeno kot **Preskočeno**, kar pomeni, da poskusa osveževanja sploh ni bilo. Ko se aktivira neaktivni segment, se bo osvežil in bo vključen v načrtovane osvežitve.
  Lahko pa uporabite funkcijo **Razporedi pozneje** v spustnem meniju **Aktiviraj/Deaktivira**, da določite datum in čas v prihodnosti za aktiviranje in deaktiviranje določenega segmenta.
- Prek možnosti **Preimenuj** lahko segment preimenujete.
- Na voljo je možnost **Prenesi** za prenos seznama članov kot datoteke .CSV.
- Možnost **Dodaj v** pošlje seznam ID-jev strank v segment za obdelavo v drugi aplikaciji.
- Za brisanje je na voljo možnost **Izbriši**.

## <a name="refresh-segments"></a>Osveževanje segmentov

Vse segmente lahko osvežite naenkrat tako, da izberete **Osveži vse** na strani **Segmenti**, ali pa lahko osvežite enega ali več segmentov, ko jih izberete in nato izberete **Osveži** v možnostih. Lahko pa konfigurirate ponavljajoče se osveževanje prek možnosti **Skrbnik** > **Sistem** > **Načrtovanje**.

> [!TIP]
> Na voljo je [šest vrst stanja](system.md#status-types) za opravila/postopke. Poleg tega je večina postopkov [odvisna od drugih nadaljnjih postopkov](system.md#refresh-policies). Izberete lahko stanje postopka in si ogledate podrobnosti o poteku celotnega posla. Ko za enega izmed poslov izberete **Prikaži podrobnosti**, se prikažejo dodatne informacije: čas obdelave, zadnji datum obdelave ter vse napake in opozorila, povezana z opravilom.

## <a name="download-and-export-segments"></a>Prenos in izvoz segmentov

Segmente lahko prenesete v datoteko CSV ali jih izvozite v storitev Dynamics 365 Sales.

### <a name="download-segments-to-a-csv-file"></a>Prenesite segmente v datoteko CSV

1. Pri vpogledih v občinstvo odprite stran **Segmenti**.

2. Izberite tri pike na ploščici posameznega segmenta.

3. Na spustnem seznamu dejanj izberite **Prenesi kot CSV**.

### <a name="export-segments-to-dynamics-365-sales"></a>Izvoz segmentov v storitev Dynamics 365 Sales

Pred izvozom segmentov v storitev Dynamics 365 Sales mora skrbnik [ustvariti cilj izvoza](export-destinations.md) za storitev Dynamics 365 Sales.

1. Pri vpogledih v občinstvo odprite stran **Segmenti**.

2. Izberite tri pike na ploščici posameznega segmenta.

3. Na spustnem seznamu dejanj izberite možnost **Dodaj v** in nato izberite cilj izvoza, kamor želite poslati podatke.

## <a name="draft-mode-for-segments"></a>Način osnutka za segmente

Če niso izpolnjene vse zahteve za obdelavo segmenta, lahko shranite segment kot osnutek in do njega dostopate s strani **Segmenti**.

Shranjen bo kot neaktiven segment in ga ni mogoče aktivirati, dokler ne postane veljaven.

## <a name="add-more-conditions-to-a-group"></a>Dodajanje več pogojev v skupino

Če želite v skupino dodati več pogojev, lahko uporabite dva logična operaterja:

- Operator **IN**: oba pogoja morata biti izpolnjena kot del postopka segmentacije. Ta možnost je najbolj uporabna, če določite pogoje v različnih entitetah.

- Operator **ALI**: izpolnjen mora biti kateri koli od pogojev kot del postopka segmentacije. Ta možnost je najbolj uporabna, če določite več pogojev za isto entiteto.

   > [!div class="mx-imgBorder"]
   > ![Operator ALI, pri katerem mora biti izpolnjen kateri koli pogoj](media/segmentation-either-condition.png "Operator ALI, pri katerem mora biti izpolnjen kateri koli pogoj")

Trenutno je mogoče ugnezditi operator **ALI** pod operator **IN**, ne pa obratno.

## <a name="combine-multiple-groups"></a>Združevanje več skupin

Vsaka skupina ustvari določen nabor strank. Te skupine lahko združite, da vključite stranke, ki so potrebne za vaš poslovni primer.

1. Pri vpogledih v občinstvo odprite stran **Segmenti** in izberite segment.

2. Izberite **Dodaj skupino**.

   > [!div class="mx-imgBorder"]
   > ![Dodajanje skupine za skupino strank](media/customer-group-add-group.png "Dodajanje skupine za skupino strank")

3. Izberite enega od naslednjih nastavitvenih operaterjev: **Združevanje**, **Presek** ali **Razen**.

   > [!div class="mx-imgBorder"]
   > ![Dodajanje unije za skupino strank](media/customer-group-union.png "Dodajanje unije za skupino strank")

   Izberite nastavljenega operatorja, da lahko določite novo skupino. Shranite različne skupine, da določite, kateri podatki se ohranijo:

   - **Unija** združi dve skupini.

   - **Presek** prekriva obe skupini. Samo podatki, ki *so skupni* obema skupinama, se ohranijo v poenoteni skupini.

   - **Razen** združuje obe skupini. Samo podatki v skupini A, ki *niso enaki* kot podatki v skupini B, se ohranijo.

## <a name="view-processing-history-and-segment-members"></a>Prikaz zgodovine obdelave in članov segmenta

Usklajene podatke o segmentu si lahko ogledate tako, da pregledate njegove podrobnosti.

Na strani **Segmenti** izberite segment, ki ga želite pregledati.

Zgornji del strani vključuje grafikon trenda, ki prikazuje spremembe v številu članov. S kazalcem miške pokažite na podatkovne točke, da si ogledate število članov na določen datum.

Časovni okvir vizualizacije lahko posodobite.

> [!div class="mx-imgBorder"]
> ![Časovni obseg segmenta](media/segment-time-range.png "Časovni obseg segmenta")

Spodnji del vsebuje seznam članov segmenta.

> [!NOTE]
> Polja, ki se prikažejo na tem seznamu, temeljijo na atributih entitet vašega segmenta.
>
>Seznam je predogled ujemajočih se članov segmenta in prikazuje prvih 100 zapisov vašega segmenta, tako da ga lahko po potrebi hitro ocenite in pregledate njegove definicije. Če si želite ogledati vse ujemajoče se zapise, morate [izvoziti segment](export-destinations.md).

## <a name="quick-segments"></a>Hitri segmenti

Poleg graditelja segmentov obstaja še ena pot za ustvarjanje segmentov. Hitri segmenti vam omogočajo hitro ustvarjanje preprostih segmentov z enim samim operaterjem in s takojšnjimi vpogledi.

1. Na strani **Segmenti** izberite možnost **Novo** > **Hitro ustvarjanje iz**.

   - Izberite možnost **Profili**, da ustvarite segment, ki temelji na poenoteni entiteti stranke.
   - Izberite možnost **Mere**, da ustvarite segment okoli vsake vrste atributov stranke za mere, ki ste jih ustvarili na strani **Mere**.
   - Izberite možnost **Obveščanje**, da sestavite segment okoli ene od izhodnih entitet, ki ste jih ustvarili z zmogljivostmi **Predvidevanja** ali **Modeli po meri**.

2. V pogovornem oknu **Nov hitri segment** izberite atribut s spustnega seznama **Polje**.

3. Sistem bo zagotovil nekaj dodatnih vpogledov, ki vam bodo pomagali ustvariti boljše segmente strank.
   - Za kategorična polja bomo prikazali 10 največjih strank. Izberite **Vrednost** in **Pregled**.

   - Pri številskem atributu sistem prikaže, katera vrednost atributa spada pod posamezni percentil stranke. Izberite **Operator** in **Vrednost** ter nato **Pregled**.

4. Sistem prikaže **ocenjeno velikost segmenta**. Izberete lahko, ali želite ustvariti segment, ki ste ga določili, ali se želite najprej znova vrniti nanj, da dobite drugačno velikost segmenta.

    > [!div class="mx-imgBorder"]
    > ![Ime in ocena za hitri segment](media/quick-segment-name.png "Ime in ocena za hitri segment")

5. Vnesite **ime** za segment. Po želji vnesite **prikazno ime**.

6. Izberite **Shrani**, da ustvarite segment.

7. Ko je obdelava segmenta končana, si ga lahko ogledate kot katerikoli drug segment, ki ste ga ustvarili.

Pri spodnjih scenarijih svetujemo uporabo graditelja segmentov in ne priporočene zmogljivosti segmentov:

- Ustvarjanje segmentov s filtri v kategoričnih poljih, kjer je operator drugačen od operatorja **Je**
- Ustvarjanje segmentov s filtri v številskih poljih, kjer je operator drugačen od operatorjev **Med**, **Več kot** in **Manj kot**
- Ustvarjanje segmentov s filtri na poljih vrste datumov

## <a name="next-steps"></a>Naslednji koraki

[Izvozite segment](export-destinations.md) in raziščite [kartico stranke](customer-card-add-in.md) in [povezovalnike](export-power-bi.md), da pridobite vpoglede na ravni stranke.


[!INCLUDE[footer-include](../includes/footer-banner.md)]