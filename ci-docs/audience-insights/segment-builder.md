---
title: Ustvarjanje in upravljanje segmentov
description: Ustvarite segmente strank, da jih združite na podlagi različnih atributov.
ms.date: 07/18/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e759872643cc7387cf732d73c7a320ae8901e5a9
ms.sourcegitcommit: 42692a815695b9fdc93b9358eae09f2c3e97293c
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/13/2021
ms.locfileid: "7377808"
---
# <a name="create-and-manage-segments"></a>Ustvarjanje in upravljanje segmentov

> [!IMPORTANT]
> V izkušnjo ustvarjanja segmentov bo septembra 2021 uvedenih več sprememb: 
> - Graditelj segmentov bo videti nekoliko drugače, s prenovljenimi elementi in izboljšanim pretokom uporabnikov.
> - V graditelju segmentov so omogočeni novi operaterji datetime in izboljšani izbirnik datumov.
> - Lahko boste dodali ali odstranili pogoje in pravila iz segmentov. 
> - Na voljo bodo ugnezdena pravila, ki se začnejo s pogojem ALI. Na zunanjem sloju ne potrebujete več pogoja IN.
> - Stransko podokno za izbiro atributov bo nenehno na voljo.
> - Možnost izbire poti odnosa entitet.
> Če želite preizkusiti novega izdelovalca segmentov, pošljite e-poštno sporočilo z zadevo »Zahteva za omogočanje novega graditelja segmentov« na cihelp [at] microsoft.com. Dopišite ime vaše organizacije in ID vašega preizkusnega okolja.
> :::image type="content" source="media/segment-builder-overview.png" alt-text="Elementi graditelja segmentov." lightbox="media/segment-builder-overview.png":::
>
> 1 – Organizirajte svoj segment s pravili in podpravili. Vsako pravilo ali podpravilo je sestavljeno iz pogojev. Združite pogoje z logičnimi operaterji
>
> 2 – Izberite [pot odnosa](relationships.md) med entitetami, ki veljajo za pravilo. Pot odnosa določa, katere atribute je mogoče uporabiti v pogoju.
>
> 3 – Upravljajte pravila in podpravila. Spremenite položaj pravila ali ga izbrišite.
>
> 4 – Dodajte pogoje in z uporabo podpravil zgradite pravo raven gnezdenja.
>
> 5 – Uporabite nastavljene operacije za povezana pravila.
>
> 6 – S podoknom atributov dodajte atribute entitete, ki so na voljo, ali ustvarite pogoje na podlagi atributov. Podokno prikazuje seznam entitet in atributov, ki so na podlagi izbrane poti odnosa na voljo za izbrano pravilo.
>
> 7 – Obstoječim pravilom in podpravilom dodajte pogoje, ki temeljijo na atributih, ali jih dodajte novemu pravilu.
>
> 8 – Razveljavite in uveljavite spremembe med gradnjo segmenta.

Določite zapletene filtre okoli poenotene entitete stranke in z njo povezanih entitet. Po obdelavi vsak segment ustvari niz zapisov strank, ki jih lahko izvozite in obdelate. Segmenti se upravljajo na strani **Segmenti**. 

Naslednji primer prikazuje zmogljivost segmentacije. Določili smo segment za stranke, ki so v zadnjih 90 dneh naročile blaga v vrednosti vsaj 500 USD *in* ki so bile vključene v klic storitev za stranke, ki je bil posredovan na višjo raven.

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Posnetek zaslona uporabniškega vmesnika za graditelja segmentov z dvema skupinama, ki določita segment stranke.":::

## <a name="create-a-new-segment"></a>Ustvarjanje novega segmenta

Nov segment lahko ustvarite na več načinov. Ta razdelek opisuje, kako ustvariti *prazen segment* od začetka. Lahko tudi ustvarite *hitri segment* na podlagi obstoječih entitet ali uporabite modele strojnega učenja za pridobitev *predlaganih segmentov*. Več informacij: [Pregled segmentov](segments.md).

Med ustvarjanjem segmenta lahko shranite osnutek. Shranjen bo kot neaktiven segment in ga ni mogoče aktivirati, ko je končan z veljavno konfiguracijo.

1. Pojdite na stran **Segmenti**.

1. Izberite **Novo** > **Prazen segment**.

1. V podoknu **Nov segment** izberite vrsto segmenta:

   - **Dinamični segmenti** se [osvežijo](segments.md#refresh-segments) po ponavljajočem se načrtovanju.
   - **Statični segmenti** se zaženejo enkrat, ko jih ustvarite.

1. Navedite **ime izhodne entitete** za segment. Po želji vnesite prikazno ime in opis, s katerim boste lažje prepoznali segment.

1. Izberite **Naprej**, da se pomaknete na stran **Graditelj segmentov**, kjer določite skupino. Skupina je nabor strank.

1. Izberite entiteto, ki vključuje atribut, po katerem želite segmentirati.

1. Izberite atribut, po katerem želite segmentirati. Ta atribut ima lahko eno od štirih vrst vrednosti: numerično, niz, datum ali logična vrednost.

1. Izberite operator in vrednost za izbrani atribut.

   > [!div class="mx-imgBorder"]
   > ![Filter skupine po meri.](media/customer-group-numbers.png "Filter skupine strank")

   |Številka |Definicija  |
   |---------|---------|
   |1     |Entity          |
   |2     |Atribut          |
   |3    |Operator         |
   |4    |Vrednost         |

   1. Če želite v skupino dodati več pogojev, lahko uporabite dva logična operaterja:

      - Operator **IN**: oba pogoja morata biti izpolnjena kot del postopka segmentacije. Ta možnost je najbolj uporabna, če določite pogoje v različnih entitetah.

      - Operator **ALI**: izpolnjen mora biti kateri koli od pogojev kot del postopka segmentacije. Ta možnost je najbolj uporabna, če določite več pogojev za isto entiteto.

      > [!div class="mx-imgBorder"]
      > ![Operator ALI, pri katerem mora biti izpolnjen kateri koli pogoj.](media/segmentation-either-condition.png "Operator ALI, pri katerem mora biti izpolnjen kateri koli pogoj")

      Trenutno je mogoče ugnezditi operator **ALI** pod operator **IN**, ne pa obratno.

   1. Vsaka skupina se ujema z naborom strank. Skupine lahko združite tako, da vključite stranke, potrebne za vaš poslovni primer.    
   Izberite **Dodaj skupino**.

      > [!div class="mx-imgBorder"]
      > ![Dodajanje skupine za skupino strank.](media/customer-group-add-group.png "Dodajanje skupine za skupino strank")

   1. Izberite enega od nastavljenih operatorjev: **Združitev**, **Presek** ali **Razen**.

   > [!div class="mx-imgBorder"]
   > ![Dodajanje unije za skupino strank.](media/customer-group-union.png "Dodajanje unije za skupino strank")

   - **Unija** združi dve skupini.

   - **Presek** prekriva obe skupini. Samo podatki, ki *so skupni* obema skupinama, se ohranijo v poenoteni skupini.

   - **Razen** združuje obe skupini. Samo podatki v skupini A, ki *niso enaki* kot podatki v skupini B, se ohranijo.

1. Če je entiteta povezana s poenoteno entiteto stranke prek [odnosov](relationships.md), morate določiti pot odnosa, da ustvarite veljaven segment. Dodajte entitete s poti odnosa, dokler se na spustnem meniju ne pojavi možnost za izbiro entitete **Stranka: CustomerInsights**. Nato za vsak korak izberite možnost **Vsi zapisi**.

   > [!div class="mx-imgBorder"]
   > ![Pot odnosa med ustvarjanjem segmenta.](media/segments-multiple-relationships.png "Pot odnosa med ustvarjanjem segmenta")

1. Segmenti privzeto generirajo izhodno entiteto, ki vsebuje vse atribute profilov strank, ki se ujemajo z določenimi filtri. Če segment temelji na drugih entitetah kot na entiteti *stranke*, lahko v izhodno entiteto dodate več atributov teh entitet. Izberite **Atributi projekta**, da izberete atribute, ki bodo dodani izhodni entiteti.  
  
   Primer: Segment temelji na entiteti, ki vsebuje podatke o dejavnostih strank, povezane z entiteto *stranke*. Segment išče vse stranke, ki so v zadnjih 60 dneh poklicale službo za pomoč uporabnikom. Trajanje in število klicev lahko v izhodni entiteti priložite v vse ustrezne zapise strank, ki se ujemajo. Te informacije so lahko koristne za pošiljanje e-pošte strankam, ki so pogosto klicale, s koristnimi povezavami do spletnih člankov za pomoč in pogostih vprašanj.

   > [!NOTE]
   > - Predvideni atributi delujejo samo za entitete, ki imajo z entiteto stranke odnos »eden proti mnogo«. Ena stranka ima na primer lahko več naročnin.
   > - Atribute lahko projicirate samo iz entitete, ki se uporablja v vsaki skupini poizvedb segmenta, ki jo gradite.
   > - Predvideni atributi se upoštevajo pri uporabi operatorjev nabora.

1. Izberite **Shrani**, da shranite segment. Če so vse zahteve potrjene, bo vaš segment shranjen in obdelan. V nasprotnem primeru bo shranjen kot osnutek.

1. Izberite **Nazaj na segmente**, da se vrnete na stran **Segmenti**.



## <a name="quick-segments"></a>Hitri segmenti

Hitri segmenti vam omogočajo hitro izdelavo preprostih segmentov z enim samim operatorjem za hitrejši vpogled.

1. Na strani **Segmenti** izberite možnost **Nov** > **Ustvari iz**.

   - Izberite možnost **Profili**, da ustvarite segment, ki temelji na *poenoteni entiteti stranke*.
   - Izberite možnost **Mere** za gradnjo segmenta okoli mer, ki ste jih že ustvarili.
   - Izberite možnost **Obveščanje**, da sestavite segment okoli ene od izhodnih entitet, ki ste jih ustvarili z zmogljivostmi **Predvidevanja** ali **Modeli po meri**.

2. V pogovornem oknu **Nov hitri segment** izberite atribut s spustnega seznama **Polje**.

3. Sistem bo zagotovil nekaj dodatnih vpogledov, ki vam bodo pomagali ustvariti boljše segmente strank.
   - Za kategorična polja bomo prikazali 10 največjih strank. Izberite **Vrednost** in **Pregled**.

   - Pri številskem atributu sistem prikaže, katera vrednost atributa spada pod posamezni percentil stranke. Izberite **Operator** in **Vrednost** ter nato **Pregled**.

4. Sistem prikaže **ocenjeno velikost segmenta**. Izberete lahko, ali želite ustvariti segment, ki ste ga določili, ali se želite najprej znova vrniti nanj, da dobite drugačno velikost segmenta.

    > [!div class="mx-imgBorder"]
    > ![Ime in ocena za hitri segment.](media/quick-segment-name.png "Ime in ocena za hitri segment")

5. Vnesite **ime** za segment. Po želji vnesite **prikazno ime**.

6. Izberite **Shrani**, da ustvarite segment.

7. Ko je obdelava segmenta končana, si ga lahko ogledate kot katerikoli drug segment, ki ste ga ustvarili.

## <a name="next-steps"></a>Naslednji koraki

[Izvozite segment](export-destinations.md) in raziščite [Integracija kartice stranke](customer-card-add-in.md) za uporabo segmentov v drugih aplikacijah.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
