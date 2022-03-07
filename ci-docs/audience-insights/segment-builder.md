---
title: Ustvarjanje segmentov z graditeljem segmentov
description: Ustvarite segmente strank, da jih združite na podlagi različnih atributov.
ms.date: 10/18/2021
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 6fa6f0738bf7fba94b2fb84a70ea17483aae8dac
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354575"
---
# <a name="create-segments"></a>Ustvari segmente

Določite zapletene filtre okoli poenotene entitete stranke in z njo povezanih entitet. Po obdelavi vsak segment ustvari niz zapisov strank, ki jih lahko izvozite in obdelate. Segmenti se upravljajo na strani **Segmenti**. Lahko [ustvarite nove segmente](#create-a-new-segment) z uporabo graditelja segmentov ali [ustvarite hitre segmente](#quick-segments) z drugih območij aplikacije. 

> [!TIP]
> - Hitri segmenti so podprti samo v okoljih za **posamezne stranke**.    
> - Segmenti na podlagi **posameznih strank** samodejno vključijo razpoložljive podatke za stik za člane segmenta. V okoljih za **poslovne račune** segmenti temeljijo na računih (podjetja ali podružnice). Če želite v segment vključiti podatke za stik, uporabite funkcijo **Atributi projekta** v graditelju segmentov.
>    - Prepričajte se, da so viri podatkov za stik [semantično preslikani v entiteto ContactProfile](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).

## <a name="segment-builder"></a>Graditelj segmentov

Naslednja slika prikazuje različne vidike graditelja segmentov. Prikazuje segment, katerega rezultat je skupina strank. Stranke so naročale blago v določenem časovnem okviru in zbrale nagradne točke ali porabile določeno količino denarja. 

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elementi graditelja segmentov." lightbox="media/segment-builder-overview.png":::

1. Organizirajte svoj segment s pravili in podpravili. Vsako pravilo ali podpravilo je sestavljeno iz pogojev. Združite pogoje z logičnimi operaterji

1. Izberite [pot odnosa](relationships.md) med entitetami, ki veljajo za pravilo. Pot odnosa določa, katere atribute je mogoče uporabiti v pogoju.

1. Upravljajte pravila in podpravila. Spremenite položaj pravila ali ga izbrišite.

1. Dodajte pogoje in z uporabo podpravil zgradite pravo raven gnezdenja.

1. Uporabite nastavljene operacije za povezana pravila.

1. S podoknom atributov dodajte atribute entitete, ki so na voljo, ali ustvarite pogoje na podlagi atributov. Podokno prikazuje seznam entitet in atributov, ki so na podlagi izbrane poti odnosa na voljo za izbrano pravilo.

1. Obstoječim pravilom in podpravilom dodajte pogoje, ki temeljijo na atributih, ali jih dodajte novemu pravilu.

1. Razveljavite in uveljavite spremembe med gradnjo segmenta.

Zgornji primer ponazarja zmogljivost segmentacije. Določili smo segment za stranke, ki so na spletu kupile blago v vrednosti vsaj 500 $ *in* jih zanima razvoj programske opreme.

## <a name="create-a-new-segment"></a>Ustvarjanje novega segmenta

Nov segment lahko ustvarite na več načinov. Ta razdelek opisuje, kako zgraditi svoj segment od začetka. Lahko tudi ustvarite *hitri segment* na podlagi obstoječih entitet ali uporabite modele strojnega učenja za pridobitev *predlaganih segmentov*. Za več informacij odprite [Pregled segmentov](segments.md).

Med ustvarjanjem segmenta lahko shranite osnutek. V fazi osnutka se segment shrani kot nedejavni segment. Ko končate konfiguracijo segmenta, jo zaženite, da aktivirate segment. Lahko pa tudi **Aktivirate** segment na strani **Vsi segmenti**.

1. Pojdite na stran **Segmenti**.

1. Izberite **Novo** > **Ustvarite svojo**.

1. Na strani graditelja segmentov določite ali sestavite pravila. Pravilo je sestavljeno iz enega ali več pogojev, ki določajo nabor strank.

1. V razdelku **Pravilo 1** izberite atribut entitete, po katerem želite filtrirati stranke. Obstajata dva načina za izbiro atributov: 
   - Preglejte seznam razpoložljivih entitet in atributov v podoknu **Dodaj v pravilo** in izberite ikono **+** zraven atributa, ki ga želite dodati. Izberite, ali želite atribut dodati obstoječemu pravilu ali ga uporabiti za ustvarjanje novega pravila.
   - V razdelku s pravili vnesite ime atributa, če si želite ogledati predloge za ujemanje.

1. Izberite operatorje, da podate ujemajoče se vrednosti pogoja. Atribut ima lahko eno od štirih vrst podatkov kot vrednost: številsko, niz, datum ali logično. Odvisno od vrste podatkov atributa so na voljo različni operaterji za določitev pogoja. Za segmente s poslovnimi računi sta na voljo dva posebna operatorja za vključitev možnih hierarhij med uvoženimi računi. Uporabite operatorja *podrejeno* in *nadrejeno*, da vključite povezane račune. 

1. Izberite **Dodaj pogoj**, če želite pravilu dodati več pogojev. Če želite ustvariti pravilo po trenutnem pravilu, izberite **Dodajanje podpravila**.

1. Če pravilo uporablja druge entitete kot entiteto *Stranka*, morate nastaviti pot odnosa. Pot odnosa mora obveščati sistem, preko katerega odnosi dostopajo do poenotene entitete stranke. Izberite **Nastavitev poti odnosa**, da preslikate izbrano entiteto v poenoteno entiteto stranke. Če obstaja le ena možna pot odnosa, jo bo sistem samodejno izbral. Različne poti odnosov lahko podajo različne rezultate. Vsako pravilo ima lahko svojo pot odnosa.

   :::image type="content" source="media/relationship-path.png" alt-text="Potencialna pot odnosa pri ustvarjanju pravila na podlagi entitete, preslikane v poenoteno entiteto stranke.":::

   Na primer entiteta *eCommerce_eCommercePurchases* na posnetku zaslona ima štiri možnosti preslikave entitete *Stranka*: 
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > Stranka
   - eCommerce_eCommercePurchases > Stranka
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Stranka
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Stranka Pri izbiri zadnje možnosti lahko v pogoje pravila vključimo atribute iz vseh navedenih entitet. Verjetno bomo dobili manj rezultatov, ker morajo biti ustrezni zapisi strank del vseh entitet. V tem primeru morajo kupiti izdelke prek e-trgovine (*eCommerce_eCommercePurchases*) na prodajnem mestu (*POS_posPurchases*) in sodelovati v našem programu zvestobe (*loyaltyScheme_loyCustomers*). Pri izbiri druge možnosti lahko izbiramo le atribute iz entitet *eCommerce_eCommercePurchases* in *Stranka*. To bo verjetno ustvarilo več profilov strank.

1. Če imate v pravilu več pogojev, lahko izberete, kateri logični operator naj jih poveže.  
   - Operator **IN**: Za vključitev zapisa v segment morajo biti izpolnjeni vsi pogoji. Ta možnost je najbolj uporabna, če določite pogoje v različnih entitetah.
   - Operator **ALI**: Za vključitev zapisa v segment mora biti izpolnjen kateri koli od pogojev. Ta možnost je najbolj uporabna, če določite več pogojev za isto entiteto.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Pravilo z dvema pogojema IN.":::

   Pri uporabi operatorja ALI morajo vsi pogoji temeljiti na entitetah, vključenih v pot odnosa.

   - Ustvarite lahko več pravil za ustvarjanje različnih naborov zapisov strank. Skupine lahko združite tako, da vključite stranke, potrebne za vaš poslovni primer. Če želite ustvariti novo pravilo, izberite **Dodaj pravilo**. Natančneje, če ne morete vključiti entitete v pravilo zaradi podane poti odnosa, morate ustvariti novo pravilo, da izberete atribute iz njega.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Segmentu dodajte novo pravilo in izberite nastavljeni operator.":::

   - Izberite enega od nastavljenih operatorjev: **Združitev**, **Presek** ali **Razen**.

      - **Unija** združi dve skupini.
      - **Presek** prekriva obe skupini. Samo podatki, ki *so pogosti* za obe skupini, ostanejo v poenoteni skupini.
      - **Razen** združuje obe skupini. Samo podatki v skupini A, ki *niso pogosti* za podatke v skupini B, se ohranijo.

1. Segmenti privzeto ustvarijo izhodno entiteto, ki vsebuje vse atribute profilov strank, ki se ujemajo z določenimi filtri. Če segment temelji na drugih entitetah kot na entiteti *stranke*, lahko v izhodno entiteto dodate več atributov teh entitet. Izberite **Atributi projekta**, da izberete atribute, ki bodo dodani izhodni entiteti. 

   > [!IMPORTANT]
   > Za segmente, ki temeljijo na poslovnih računih, je treba v segment vključiti podrobnosti o enem ali več stikih vsakega računa iz entitete *ContactProfile*, da se omogoči aktiviranje ali izvoz tega segmenta v cilje, ki zahtevajo podatke za stik. Za več informacij o entiteti *ContactProfile* glejte [Semantične preslikave](semantic-mappings.md).
   > Vzorčni izhod za segment, ki temelji na poslovnih računih s predvidenimi atributi stikov, bi lahko izgledal takole: 
   >
   > |ID  |Ime kupca  |Prihodki  |Ime stika  | Vloga stika|
   > |---------|---------|---------|---------|---|
   > |10021     | Contoso | 100.000 | [Abbie Moss, Ruth Soto]  | [Izvršni direktor, vodja nabave]

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Primer napovedanih atributov, izbranih v stranskem podoknu, za dodajanje izhodni entiteti.":::
  
   Na primer: Segment temelji na entiteti, ki vsebuje podatke o nakupu, kar je povezano z entiteto *Stranka*. Segment išče vse kupce iz Španije, ki so kupili blago v tem letu. Izberete lahko, da atribute, kot je cena blaga, ali datum nakupa, priložite vsem ustreznim zapisom strank v izhodni entiteti. Te informacije so lahko uporabne za analizo sezonskih korelacij s skupno porabo.

   > [!NOTE]
   > - **Atributi projekta** deluje samo za entitete, ki imajo z entiteto stranke odnos »eden proti mnogo«. Ena stranka ima na primer lahko več naročnin.
   > - Če je atribut, ki ga želite predvideti, od entitete *Stranka* oddaljen več kot en skok, kot je opredeljeno v odnosu, je treba ta atribut uporabiti pri vsakem pravilu poizvedbe segmenta, ki ga gradite. 
   > - Če je atribut, ki ga želite predvideti, od entitete *Stranka* oddaljen samo en skok, ni treba, da je atribut prisoten pri vsakem pravilu poizvedbe segmenta, ki ga gradite. 
   > - **Predvideni atributi** se upoštevajo pri uporabi operatorjev nabora.

1. Preden shranite in zaženete segment, izberite **Uredi podrobnosti** zraven imena segmenta. Vnesite ime za svoj segment in posodobite predlagano **Ime izhodne entitete** za segment. Segmentu lahko dodate tudi opis.

1. Izberite **Zagon**, če želite shraniti segment, ga aktivirajte in začnite obdelovati svoj segment na podlagi vseh pravil in pogojev. V nasprotnem primeru bo shranjen kot nedejavni segment.
   
1. Izberite **Nazaj na segmente**, da se vrnete na stran **Segmenti**.

1. Privzeto je segment ustvarjen kot dinamični segment. To pomeni, da se segment med osveževanjem sistema osveži. Za [ustavitev samodejnega osveževanja](segments.md#manage-existing-segments) izberite segment in možnost **Statično**. Statične segmente je mogoče kadar koli [osvežiti ročno](segments.md#refresh-segments).

> [!TIP]
> - Graditelj segmentov ne bo predlagal veljavnih vrednosti iz entitet pri nastavljanju operatorjev za pogoje. Odprete lahko razdelek **Podatki** > **Entitete** in prenesete podatke entitete, da vidite, katere vrednosti so na voljo.
> - Pogoji, ki temeljijo na datumih, omogočajo preklapljanje med fiksnimi datumi in plavajočim datumskim obsegom.
> - Če imate za svoj segment več pravil, ima pravilo, ki ga urejate, zraven navpično modro črto. 
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
