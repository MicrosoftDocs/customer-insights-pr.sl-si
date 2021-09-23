---
title: Ustvarjanje segmentov z graditeljem segmentov
description: Ustvarite segmente strank, da jih združite na podlagi različnih atributov.
ms.date: 09/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7f7bd0e7e581305836287bd503ef273a2d556bff
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494522"
---
# <a name="create-segments"></a>Ustvari segmente

Določite zapletene filtre okoli poenotene entitete stranke in z njo povezanih entitet. Po obdelavi vsak segment ustvari niz zapisov strank, ki jih lahko izvozite in obdelate. Segmenti se upravljajo na strani **Segmenti**. Lahko [ustvarite nove segmente](#create-a-new-segment) z uporabo [graditelja segmentov](#segment-builder) ali [ustvarite hitre segmente](#quick-segments) z drugih območij aplikacije.

## <a name="segment-builder"></a>Graditelj segmentov

Naslednja slika prikazuje različne vidike graditelja segmentov. Prikazuje segment, katerega rezultat je skupina strank. Stranke so naročile blago v določenem časovnem okviru in zbrale številne nagradne točke ali porabile določeno količino denarja. 

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elementi graditelja segmentov." lightbox="media/segment-builder-overview.png":::

1 – Organizirajte svoj segment s pravili in podpravili. Vsako pravilo ali podpravilo je sestavljeno iz pogojev. Združite pogoje z logičnimi operaterji

2 – Izberite [pot odnosa](relationships.md) med entitetami, ki veljajo za pravilo. Pot odnosa določa, katere atribute je mogoče uporabiti v pogoju.

3 – Upravljajte pravila in podpravila. Spremenite položaj pravila ali ga izbrišite.

4 – Dodajte pogoje in z uporabo podpravil zgradite pravo raven gnezdenja.

5 – Uporabite nastavljene operacije za povezana pravila.

6 – S podoknom atributov dodajte atribute entitete, ki so na voljo, ali ustvarite pogoje na podlagi atributov. Podokno prikazuje seznam entitet in atributov, ki so na podlagi izbrane poti odnosa na voljo za izbrano pravilo.

7 – Obstoječim pravilom in podpravilom dodajte pogoje, ki temeljijo na atributih, ali jih dodajte novemu pravilu.

8 – Razveljavite in uveljavite spremembe med gradnjo segmenta.

Zgornji primer ponazarja zmogljivost segmentacije. Določili smo segment za stranke, ki so na spletu kupile blago v vrednosti vsaj 500 $ *in* jih zanima razvoj programske opreme.

## <a name="create-a-new-segment"></a>Ustvarjanje novega segmenta

Nov segment lahko ustvarite na več načinov. Ta razdelek opisuje, kako zgraditi svoj segment od začetka. Lahko tudi ustvarite *hitri segment* na podlagi obstoječih entitet ali uporabite modele strojnega učenja za pridobitev *predlaganih segmentov*. Več informacij: [Pregled segmentov](segments.md).

Med ustvarjanjem segmenta lahko shranite osnutek. Shranjen bo kot neaktiven segment in ga ni mogoče aktivirati, ko je končan z veljavno konfiguracijo.

1. Pojdite na stran **Segmenti**.

1. Izberite **Novo** > **Ustvarite svojo**.

1. Na strani graditelja segmentov določite prvo pravilo. Pravilo je sestavljeno iz enega ali več pogojev in opredeljuje nabor strank.

1. V razdelku **Pravilo 1** izberite atribut entitete, po katerem želite filtrirati stranke. Obstajata dva načina za izbiro atributov: 
   - Preglejte seznam razpoložljivih entitet in atributov v podoknu **Dodaj v pravilo** in izberite ikono **+** zraven atributa, ki ga želite dodati. Izberite, ali želite atribut dodati obstoječemu pravilu ali ga uporabiti za ustvarjanje novega pravila.
   - V razdelku s pravili vnesite ime atributa, če si želite ogledati predloge za ujemanje.

1. Izberite operatorje, da podate ujemajoče se vrednosti pogoja. Atribut ima lahko eno od štirih vrst podatkov kot vrednost: številsko, niz, datum ali logično. Odvisno od vrste podatkov atributa so na voljo različni operaterji za določitev pogoja. 

1. Izberite **Dodaj pogoj**, če želite pravilu dodati več pogojev. Če želite ustvariti pravilo po trenutnem pravilu, izberite **Dodajanje podpravila**.

1. Če pravilo uporablja druge entitete kot entiteto *Stranka*, morate nastaviti pot odnosa. Pot odnosa mora obveščati sistem, preko katerega odnosi dostopajo do poenotene entitete stranke. Izberite **Nastavitev poti odnosa**, da preslikate izbrano entiteto v poenoteno entiteto stranke. Če obstaja le ena možna pot odnosa, jo bo sistem samodejno izbral. Različne poti odnosov lahko podajo različne rezultate. Vsako pravilo ima lahko svojo pot odnosa.

   :::image type="content" source="media/relationship-path.png" alt-text="Potencialna pot odnosa pri ustvarjanju pravila na podlagi entitete, preslikane v poenoteno entiteto stranke.":::

   Na primer entiteta *eCommerce_eCommercePurchases* na posnetku zaslona ima štiri možnosti preslikave entitete *Stranka*: 
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > Stranka
   - eCommerce_eCommercePurchases > Stranka
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Stranka
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Stranka Pri izbiri zadnje možnosti lahko v pogoje pravila vključimo atribute iz vseh navedenih entitet. Verjetno bomo dobili manj rezultatov, ker morajo biti ustrezni zapisi strank del vseh entitet. V tem primeru morajo kupiti izdelke prek e-trgovine (*eCommerce_eCommercePurchases*), na prodajnem mestu (*POS_posPurchases*) in sodelovati v našem programu zvestobe (*loyaltyScheme_loyCustomers*). Pri izbiri druge možnosti lahko izbiramo le atribute iz entitet *eCommerce_eCommercePurchases* in *Stranka*. To bo verjetno ustvarilo več profilov strank.

1. Če imate v pravilu več pogojev, lahko izberete, kateri logični operator naj jih poveže.

   - Operator **IN**: Za vključitev zapisa v segment morajo biti izpolnjeni vsi pogoji. Ta možnost je najbolj uporabna, če določite pogoje v različnih entitetah.

   - Operator **ALI**: Za vključitev zapisa v segment mora biti izpolnjen kateri koli od pogojev. Ta možnost je najbolj uporabna, če določite več pogojev za isto entiteto.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Pravilo z dvema pogojema IN.":::

   Pri uporabi operatorja ALI morajo vsi pogoji temeljiti na entitetah, vključenih v pot odnosa.

   1. Ustvarite lahko več pravil za ustvarjanje različnih naborov zapisov strank. Skupine lahko združite tako, da vključite stranke, potrebne za vaš poslovni primer. Če želite ustvariti novo pravilo, izberite **Dodaj pravilo**. Natančneje, če entitete ne morete vključiti v pravilo zaradi določene poti odnosa, morate ustvariti novo pravilo, iz katerega izberete atribute.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Segmentu dodajte novo pravilo in izberite nastavljeni operator.":::

   1. Izberite enega od nastavljenih operatorjev: **Združitev**, **Presek** ali **Razen**.

   - **Unija** združi dve skupini.

   - **Presek** prekriva obe skupini. Samo podatki, ki *so skupni* obema skupinama, se ohranijo v poenoteni skupini.

   - **Razen** združuje obe skupini. Samo podatki v skupini A, ki *niso enaki* kot podatki v skupini B, se ohranijo.

1. Segmenti privzeto ustvarijo izhodno entiteto, ki vsebuje vse atribute profilov strank, ki se ujemajo z določenimi filtri. Če segment temelji na drugih entitetah kot na entiteti *stranke*, lahko v izhodno entiteto dodate več atributov teh entitet. Izberite **Atributi projekta**, da izberete atribute, ki bodo dodani izhodni entiteti.  

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Primer napovedanih atributov, izbranih v stranskem podoknu, za dodajanje izhodni entiteti.":::
  
   Primer: Segment temelji na entiteti, ki vsebuje podatke o nakupu, kar je povezano z entiteto *Stranka*. Segment išče vse kupce iz Španije, ki so kupili blago v tem letu. Izberete lahko, da atribute, kot je cena blaga, ali datum nakupa, priložite vsem ustreznim zapisom strank v izhodni entiteti. Te informacije so lahko uporabne za analizo sezonskih korelacij s skupno porabo.

   > [!NOTE]
   > - Predvideni atributi delujejo samo za entitete, ki imajo z entiteto stranke odnos »eden proti mnogo«. Ena stranka ima na primer lahko več naročnin.
   > - Atribute lahko napovemo samo iz entitete, ki se uporablja pri vsakem pravilu poizvedbe segmenta, ki ga gradite.
   > - Predvideni atributi se upoštevajo pri uporabi operatorjev nabora.

1. Preden shranite in zaženete segment, izberite **Uredi podrobnosti** zraven imena segmenta. Vnesite ime za svoj segment in posodobite predlagano **Ime izhodne entitete** za segment. Segmentu lahko dodate tudi opis.

1. Izberite **Zaženi**, da shranite in obdelate svoj segment, če so potrjene vse zahteve. V nasprotnem primeru bo shranjen kot nedejaven osnutek segmenta.

1. Izberite **Nazaj na segmente**, da se vrnete na stran **Segmenti**.

> [!TIP]
> - Graditelj segmentov ne bo predlagal veljavnih vrednosti iz entitet pri nastavljanju operatorjev za pogoje. Odprete lahko razdelek **Podatki** > **Entitete** in prenesete podatke entitete, da vidite, katere vrednosti so na voljo.
> - Pogoji, ki temeljijo na datumih, omogočajo preklapljanje med fiksnimi datumi in plavajočim datumskim obsegom.
> - Če imate za svoj segment več pravil, boste okoli pravila, ki ga urejate, našli modro vrstico.
> - Pravila in pogoje lahko premaknete na druga mesta v definiciji segmenta. Izberite [...] zraven pravila ali pogoja in izberite, kako in kam ga premakniti.
> - Kontrolnika **Razveljavi** in **Uveljavi** v ukazni vrstici omogočata razveljavitev sprememb.

## <a name="quick-segments"></a>Hitri segmenti

Hitri segmenti vam omogočajo hitro izdelavo preprostih segmentov z enim samim operatorjem za hitrejši vpogled.

1. Na strani **Segmenti** izberite možnost **Nov** > **Ustvari iz**.

   - Izberite možnost **Profili**, da ustvarite segment, ki temelji na *poenoteni entiteti stranke*.
   - Izberite možnost **Mere** za gradnjo segmenta okoli mer, ki ste jih že ustvarili.
   - Izberite možnost **Obveščanje**, da sestavite segment okoli ene od izhodnih entitet, ki ste jih ustvarili z zmogljivostmi **Predvidevanja** ali **Modeli po meri**.

2. V pogovornem oknu **Nov hitri segment** izberite atribut s spustnega seznama **Polje**.

3. Sistem bo zagotovil več vpogledov, ki vam bodo pomagali ustvariti boljše segmente vaših strank.
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
