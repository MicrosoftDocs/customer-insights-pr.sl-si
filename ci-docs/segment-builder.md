---
title: Ustvarite zapletene segmente z graditeljem segmentov
description: Uporabite graditelj segmentov, da ustvarite zapletene segmente strank tako, da jih razvrstite v skupine na podlagi različnih atributov.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: cde373cd65e296675e1b3c92f3024e1093853842
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170655"
---
# <a name="create-complex-segments-with-segment-builder"></a>Ustvarite zapletene segmente z graditeljem segmentov

Določite zapletene filtre okoli poenotene entitete stranke in z njo povezanih entitet. Po obdelavi vsak segment ustvari niz zapisov strank, ki jih lahko izvozite in obdelate.

> [!TIP]
> Segmenti na podlagi **posameznih strank** samodejno vključijo razpoložljive podatke za stik za člane segmenta. V okoljih za **poslovne račune** segmenti temeljijo na računih (podjetja ali podružnice). Če želite v segment vključiti podatke za stik, uporabite funkcijo **Atributi projekta** v graditelju segmentov. Prepričajte se, da so viri podatkov za stik [semantično preslikani v entiteto ContactProfile](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).

## <a name="segment-builder"></a>Graditelj segmentov

Naslednja slika prikazuje različne vidike graditelja segmentov. Prikazuje segment, katerega rezultat je skupina strank. Stranke so naročale blago v določenem časovnem okviru in zbrale nagradne točke ali porabile določeno količino denarja.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elementi graditelja segmentov." lightbox="media/segment-builder-overview.png":::

1. Organizirajte svoj segment s pravili in podpravili. Vsako pravilo ali podpravilo je sestavljeno iz pogojev. Kombinirajte pogoje z logičnimi operatorji.

1. Izberite [pot odnosa](relationships.md) med entitetami, ki veljajo za pravilo. Pot odnosa določa, katere atribute je mogoče uporabiti v pogoju.

1. Upravljajte pravila in podpravila. Spremenite položaj pravila ali ga izbrišite.

1. Dodajte pogoje in z uporabo podpravil zgradite pravo raven gnezdenja.

1. Uporabite nastavljene operacije za povezana pravila.

1. S podoknom atributov dodajte atribute entitete, ki so na voljo, ali ustvarite pogoje na podlagi atributov. Podokno prikazuje seznam entitet in atributov, ki so na podlagi izbrane poti odnosa na voljo za izbrano pravilo.

1. Obstoječim pravilom in podpravilom dodajte pogoje, ki temeljijo na atributih, ali jih dodajte novemu pravilu.

1. Razveljavite in uveljavite spremembe med gradnjo segmenta.

Zgornji primer ponazarja zmogljivost segmentacije. Določili smo segment za stranke, ki so na spletu kupile blago v vrednosti vsaj 500 $ *in* jih zanima razvoj programske opreme.

## <a name="create-a-new-segment-with-segment-builder"></a>Ustvarite nov segment z graditeljem segmentov

1. Izberite **Segmenti**.

1. Izberite **Novo** > **Ustvarite svojo**. Na strani graditelja segmentov določite ali sestavite pravila. Pravilo je sestavljeno iz enega ali več pogojev, ki določajo nabor strank.

1. Izberite **Uredi podrobnosti** poleg segmenta brez naslova. Vnesite ime za svoj segment in posodobite predlagano **Ime izhodne entitete** za segment. Po želji dodajte opis in [oznake](work-with-tags-columns.md#manage-tags) na segment.

   :::image type="content" source="media/segments_edit_details.png" alt-text="Pogovorno okno za urejanje podrobnosti.":::

1. V **Pravilo 1** izberite atribut subjekta, po katerem želite filtrirati stranke. Obstajata dva načina za izbiro atributov:
   - Preglejte seznam razpoložljivih entitet in atributov v podoknu **Dodaj v pravilo** in izberite ikono **+** zraven atributa, ki ga želite dodati. Izberite, ali želite atribut dodati obstoječemu pravilu ali ga uporabiti za ustvarjanje novega pravila.
   - V razdelku s pravili vnesite ime atributa, če si želite ogledati predloge za ujemanje.

1. Izberite operatorje, da podate ujemajoče se vrednosti pogoja. Atribut ima lahko eno od štirih vrst podatkov kot vrednost: številsko, niz, datum ali logično. Odvisno od vrste podatkov atributa so na voljo različni operaterji za določitev pogoja. Za segmente s poslovnimi računi sta na voljo dva posebna operatorja za vključitev možnih hierarhij med uvoženimi računi. Uporabite operatorja *podrejeno* in *nadrejeno*, da vključite povezane račune.

1. Izberite **Dodaj pogoj**, če želite pravilu dodati več pogojev. Če želite ustvariti pravilo po trenutnem pravilu, izberite **Dodajanje podpravila**.

1. Če pravilo uporablja druge entitete kot *Stranka* subjekt, izberite **Nastavite pot odnosa** za preslikavo izbrane entitete v enotno strankino entiteto. Če obstaja le ena možna pot razmerja, jo sistem samodejno izbere. Drugačen [poti odnosov](relationships.md#relationship-paths) lahko prinese različne rezultate. Vsako pravilo ima lahko svojo pot odnosa.

   :::image type="content" source="media/relationship-path.png" alt-text="Potencialna pot odnosa pri ustvarjanju pravila na podlagi entitete, preslikane v poenoteno entiteto stranke.":::

1. Če imate v pravilu več pogojev, izberite, kateri logični operator jih povezuje.  
   - Operator **IN**: Za vključitev zapisa v segment morajo biti izpolnjeni vsi pogoji. To možnost uporabite, ko definirate pogoje v različnih entitetah.
   - Operator **ALI**: Za vključitev zapisa v segment mora biti izpolnjen kateri koli od pogojev. To možnost uporabite, ko definirate več pogojev za isto entiteto.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Pravilo z dvema pogojema IN.":::

   Pri uporabi operatorja ALI morajo vsi pogoji temeljiti na entitetah, vključenih v pot odnosa.

1. Če želite ustvariti različne nize zapisov strank, ustvarite več pravil. Če želite vključiti stranke, potrebne za vaš poslovni primer, združite skupine. Natančneje, če entitete ne morete vključiti v pravilo zaradi podane poti razmerja, ustvarite novo pravilo, da iz njega izberete atribute.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Segmentu dodajte novo pravilo in izberite nastavljeni operator.":::

   1. Izberite **Dodaj pravilo**.
   1. Izberite enega od nastavljenih operatorjev: **Združitev**, **Presek** ali **Razen**.

      - **Unija** združi dve skupini.
      - **Presek** prekriva obe skupini. Samo podatki, ki *so pogosti* za obe skupini, ostanejo v poenoteni skupini.
      - **Razen** združuje obe skupini. Samo podatki v skupini A, ki *niso pogosti* za podatke v skupini B, se ohranijo.

1. Privzeto bo izhodna entiteta samodejno vsebovala vse atribute profilov strank, ki ustrezajo definiranim filtrom. Če segment temelji na drugih subjektih kot na *Stranka* subjekt, izberite **Atributi projekta** da dodate več atributov iz teh entitet v izhodno entiteto.

   > [!IMPORTANT]
   > Za segmente, ki temeljijo na poslovnih računih, podrobnosti o enem ali več stikih vsakega računa iz *ContactProfile* entiteta mora biti vključena v segment, da se ta segment lahko aktivira ali izvozi na cilje, ki zahtevajo kontaktne podatke. Za več informacij o entiteti *ContactProfile* glejte [Semantične preslikave](semantic-mappings.md).
   > Vzorčni izhod za segment, ki temelji na poslovnih računih s predvidenimi atributi stikov, bi lahko izgledal takole:
   >
   > |ID  |Ime kupca  |Prihodki  |Ime stika  | Vloga stika|
   > |---------|---------|---------|---------|---|
   > |10021     | Contoso | 100.000 | [Abbie Moss, Ruth Soto]  | [Izvršni direktor, vodja nabave]

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Primer napovedanih atributov, izbranih v stranskem podoknu, za dodajanje izhodni entiteti.":::
  
   Na primer: Segment temelji na entiteti, ki vsebuje podatke o nakupu, kar je povezano z entiteto *Stranka*. Segment išče vse kupce iz Španije, ki so kupili blago v tem letu. Izberete lahko, da dodate atribute, kot je cena blaga ali datum nakupa, vsem ujemajočim se zapisom strank v izhodni entiteti. Te informacije so lahko uporabne za analizo sezonskih korelacij s skupno porabo.

   > [!NOTE]
   > - **Atributi projekta** deluje samo za entitete, ki imajo z entiteto stranke odnos »eden proti mnogo«. Ena stranka ima na primer lahko več naročnin.
   > - Če je atribut, ki ga želite predvideti, od entitete *Stranka* oddaljen več kot en skok, kot je opredeljeno v odnosu, je treba ta atribut uporabiti pri vsakem pravilu poizvedbe segmenta, ki ga gradite.
   > - Če je atribut, ki ga želite predvideti, od entitete *Stranka* oddaljen samo en skok, ni treba, da je atribut prisoten pri vsakem pravilu poizvedbe segmenta, ki ga gradite.
   > - **Predvideni atributi** se upoštevajo pri uporabi operatorjev nabora.

1. Izberite **Teči** ustvariti segment. Izberite **Shrani** če želite obdržati trenutno konfiguracijo in zagnati segment pozneje. The **Segmenti** prikazi strani.

### <a name="segment-builder-tips"></a>Nasveti za ustvarjanje segmentov

Ko ustvarjate segment z graditeljem segmentov, upoštevajte naslednje nasvete:

- Graditelj segmentov ne bo predlagal veljavnih vrednosti iz entitet pri nastavljanju operatorjev za pogoje. Odprete lahko razdelek **Podatki** > **Entitete** in prenesete podatke entitete, da vidite, katere vrednosti so na voljo.
- Pogoji, ki temeljijo na datumih, vam omogočajo preklapljanje med fiksnimi datumi in plavajočim časovnim obdobjem.
- Če imate za svoj segment več pravil, ima pravilo, ki ga urejate, zraven navpično modro črto.
- Pravila in pogoje lahko premaknete na druga mesta v definiciji segmenta. Izberite navpično elipso (&vellip;) poleg pravila ali pogoja in izberite, kako in kam ga želite premakniti.
- Kontrolnika **Razveljavi** in **Uveljavi** v ukazni vrstici omogočata razveljavitev sprememb.
- Ko ustvarite segment, vam nekateri segmenti omogočajo [sledite uporabi segmenta](segments.md#track-usage-of-a-segment).

## <a name="next-steps"></a>Naslednji koraki

[Izvozite segment](export-destinations.md) in raziščite [Integracija kartice stranke](customer-card-add-in.md) za uporabo segmentov v drugih aplikacijah.

[!INCLUDE [footer-include](includes/footer-banner.md)]
