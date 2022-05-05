---
title: Ustvarite nove ukrepe z gradnikom meril
description: Zgradite ukrepe iz nič za analizo ključnih meritev vašega podjetja.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-builder
- customerInsights
ms.openlocfilehash: 6370df0287362a5512a837cdb588f5d20ef03d3b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643761"
---
# <a name="use-measure-builder-to-create-measures-from-scratch"></a>Uporabite graditelj meril za ustvarjanje ukrepov iz nič

Ta članek pojasnjuje, kako ustvariti novo [meriti](measures.md) iz nič. Graditelj meril vam omogoča definiranje izračunov z uporabo matematičnih operaterjev, funkcij združevanja in filtrov. Mero lahko zgradite z atributi iz entitet, ki so povezane s poenotenim *Stranka* entiteta.

Ustvarjanje ukrepov v okoljih B-to-C in B-to-B deluje na enak način. Vendar, če ste B-to-B okolje [uporablja račune s hierarhijo](relationships.md#set-up-account-hierarchies), se lahko odločite, da boste merilo združili po povezanih podračunih.

Mero lahko tudi hitro ustvarite tako, da izberete iz nabora pogosto uporabljenih in vnaprej določenih mer. Za več informacij glejte [Za izdelavo merila uporabite predlogo](measure-templates.md).

# <a name="individual-consumers-b-to-c"></a>[Posamezni potrošniki (prodaja strankam)](#tab/b2c)

Mere lahko ustvarite na ravni posamezne stranke (atribut stranke, meritev stranke) ali na ravni podjetja/organizacije (poslovni ukrep). Atribut stranke in meritev stranke sta dve vrsti, ki vam omogočata spremljanje uspešnosti na stranko. Na primer, skupna poraba vsake stranke. Poslovni ukrepi vam omogočajo spremljanje uspešnosti posameznega podjetja. Na primer skupni prihodek podjetja.

- Atribut stranke: ustvari izhod kot nov atribut, ki se shrani kot nov stolpec v sistemsko ustvarjeni entiteti z imenom *Customer_Measure*. Ko osvežite atribut stranke, vsi drugi atributi stranke v *Customer_Measure* hkrati osveži entiteto. Poleg tega so atributi stranke prikazani na kartici profila stranke. Ko je atribut stranke zagnan ali shranjen, ga ne morete spremeniti v meritev stranke.

- Merilo stranke: generira izhod kot lastno entiteto in ga ne morete spremeniti v atribut stranke, ko ga enkrat zaženete ali shranite. Meritve stranke niso prikazane na kartici profila stranke.

- Poslovni ukrep: ustvari izhod kot lastno entiteto in se prikaže na domači strani vašega okolja Customer Insights.

1. Pojdi do **Ukrepi**.

1. Izberite **Novo** in nato še **Ustvarite si svojega**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Prazen konfiguracijski zaslon za ukrep B-to-C." lightbox="media/measure-b2c.png":::

1. Če želite spremljati uspešnost na ravni podjetja, preklopite **Vrsta meritve** do **Poslovna raven**. **Raven strank** je privzeto izbran. **Raven strank** samodejno doda *Identifikacijska številka stranke* atributom Dimensions while **Poslovna raven** samodejno odstrani.

1. V konfiguracijskem območju izberite funkcijo združevanja iz možnosti **Izberite funkcijo** spustni meni. Združevalne funkcije vključujejo:
   - **Vsota**
   - **Povprečje**
   - **Število**
   - **Št. enoličnih**
   - **Maksimum**
   - **Min**
   - **Najprej**: vzame prvo vrednost podatkovnega zapisa
   - **Zadnje**: vzame zadnjo vrednost, ki je bila dodana v podatkovni zapis
   - **ArgMax** : najde podatkovni zapis, ki daje največjo vrednost ciljne funkcije
   - **ArgMin** : najde podatkovni zapis, ki daje najmanjšo vrednost iz ciljne funkcije

1. Izberite možnost **Dodaj atribut**, da izberete podatke, ki jih potrebujete za izdelavo te mere.

   1. Izberite zavihek **Atributi**.
   1. Podatkovna entiteta: izberite entiteto, ki vključuje atribut, ki ga želite izmeriti.
   1. Atribut podatkov: izberite atribut, ki ga želite uporabiti v združevalni funkciji za izračun mere. Naenkrat lahko izberete le en atribut.
   1. Atribut podatkov lahko izberete tudi iz obstoječe mere tako, da odprete zavihek **Mere** ali poiščete ime entitete ali mere.
   1. Izberite možnost **Dodaj**, da meri dodate izbrani atribut.

1. Če želite zgraditi bolj zapletene mere, lahko v funkcijo mere dodate več atributov ali uporabite matematične operatorje.

1. Če želite dodati filtre, v konfiguracijskem območju izberite možnost **Filter**. Uporaba filtrov bo za izračun mere uporabila samo zapise, ki se ujemajo s filtri.
  
   1. V razdelku **Dodaj atribut**, in sicer v podoknu **Filtri**, izberite atribut, ki ga želite uporabiti za ustvarjanje filtrov.
   1. Nastavite operatorje filtrov, da določite filter za vsak izbrani atribut.
   1. Izberite možnost **Dodaj**, da meri dodate filter.

1. Izberite **Dimenzija** da izberete več polj, ki so dodana kot stolpci izhodni entiteti merila.

   1. Izberite možnost **Uredi razsežnosti**, da dodate atribute podatkov, po katerih želite vrednosti mer razvrstiti v skupine. Na primer po mestu ali spolu.
   > [!TIP]
   > Če ste izbrali **Raven strank** kot **Vrsta meritve** the *Identifikacijska številka stranke* atribut je že dodan. Če odstranite atribut, **Vrsta meritve** preklopi na **Poslovna raven**.
   1. Izberite možnost **Končano**, da meri dodate razsežnosti.

1. Če so v vaših podatkih vrednosti, ki jih morate zamenjati s celim številom, izberite **Pravila**. Konfigurirajte pravilo in se prepričajte, da jih nadomestite le s celimi števili. Zamenjajte na primer *null* z *0*.

1. Če med podatkovno entiteto, ki ste jo preslikali, in *entiteto* stranke obstaja več poti, morate izbrati eno od prepoznanih [poti odnosov entitet](relationships.md). Rezultati mere se lahko razlikujejo glede na izbrano pot.

   1. Izberite **Pot odnosa** in nato pot entitete, ki jo je treba uporabiti za identifikacijo vaše mere. Če obstaja samo ena pot do entitete *stranke*, ta nadzor ne bo prikazan.
   1. Izberite možnost **Končano**, da uporabite izbor.

1. Če želite dodati več izračunov za mero, izberite možnost **Nov izračun**. Entitete z isto potjo lahko uporabite samo za nove izračune. Dodatni izračuni bodo prikazani kot novi stolpci v entiteti izhodnih mer.

1. V izračunu izberite tri pike **...**, da **podvojite**, **preimenujete** ali **odstranite** izračun iz mere.

1. Na območju **predogleda** boste videli podatkovno shemo entitete izhodnih mer, vključno s filtri in razsežnostmi. Predogled se dinamično odziva na spremembe v konfiguraciji.

1. Izberite **Uredite podrobnosti** poleg Neimenovane mere. Navedite ime za ukrep. Po želji dodajte [oznake](work-with-tags-columns.md#manage-tags) po meri.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Pogovorno okno Uredi podrobnosti.":::

1. Izberite možnost **Zaženi** za izračun rezultatov za konfigurirano mero. Izberite možnost **Shrani in zapri**, če želite obdržati trenutno konfiguracijo in mero zagnati pozneje.

1. Na strani **Mere** si na seznamu oglejte novo ustvarjeno mero.

# <a name="business-accounts-b-to-b"></a>[Poslovni računi (podjetja podjetjem)](#tab/b2b)

Ukrepe lahko ustvarite na ravni posameznih računov (ukrep strank) ali na ravni vseh računov (poslovni ukrep).

- Ukrep stranke: generira rezultate kot lastno entiteto. Meritve stranke niso prikazane na kartici profila stranke.

- Poslovni ukrep: ustvari izhod kot lastno entiteto in se prikaže na domači strani vašega okolja Customer Insights.

1. Pojdi do **Ukrepi**.

1. Izberite **Novo**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Prazen konfiguracijski zaslon za ukrep B-to-B.":::

1. V konfiguracijskem območju izberite funkcijo združevanja iz možnosti **Izberite funkcijo** spustni meni. Združevalne funkcije vključujejo:
   - **Vsota**
   - **Povprečje**
   - **Število**
   - **Št. enoličnih**
   - **Maksimum**
   - **Min**
   - **Najprej**: vzame prvo vrednost podatkovnega zapisa
   - **Zadnje**: vzame zadnjo vrednost, ki je bila dodana v podatkovni zapis

1. Izberite možnost **Dodaj atribut**, da izberete podatke, ki jih potrebujete za izdelavo te mere.

   1. Izberite zavihek **Atributi**.
   1. Podatkovna entiteta: izberite entiteto, ki vključuje atribut, ki ga želite izmeriti.
   1. Atribut podatkov: izberite atribut, ki ga želite uporabiti v združevalni funkciji za izračun mere. Naenkrat lahko izberete le en atribut.
   1. Atribut podatkov lahko izberete tudi iz obstoječe mere tako, da odprete zavihek **Mere** ali poiščete ime entitete ali mere.
   1. Izberite možnost **Dodaj**, da meri dodate izbrani atribut.

1. Če želite zgraditi bolj zapletene mere, lahko v funkcijo mere dodate več atributov ali uporabite matematične operatorje.

1. Če želite dodati filtre, v konfiguracijskem območju izberite možnost **Filter**. Uporaba filtrov bo za izračun mere uporabila samo zapise, ki se ujemajo s filtri.
  
   1. V razdelku **Dodaj atribut**, in sicer v podoknu **Filtri**, izberite atribut, ki ga želite uporabiti za ustvarjanje filtrov.
   1. Nastavite operatorje filtrov, da določite filter za vsak izbrani atribut.
   1. Izberite možnost **Dodaj**, da meri dodate filter.

1. Izberite **Dimenzija** da izberete več polj, ki so dodana kot stolpci izhodni entiteti merila.

   1. Izberite možnost **Uredi razsežnosti**, da dodate atribute podatkov, po katerih želite vrednosti mer razvrstiti v skupine. Na primer po mestu ali spolu.
      > [!TIP]
      > Če ste izbrali **Raven strank** kot **Vrsta meritve** the *Identifikacijska številka stranke* atribut je že dodan. Če odstranite atribut, **Vrsta meritve** preklopi na **Poslovna raven**.
   1. Izberite možnost **Končano**, da meri dodate razsežnosti.

1. Če so v vaših podatkih vrednosti, ki jih morate zamenjati s celim številom, izberite **Pravila**. Konfigurirajte pravilo in se prepričajte, da jih nadomestite le s celimi števili. Zamenjajte na primer *null* z *0*.

1. Uporabite lahko preklop **Zbiranje podračunov**, če [uporabljajte račune s hierarhijo](relationships.md#set-up-account-hierarchies).
   - Če je nastavljen na **Izklopljeno**, se mera izračuna za vsak račun. Vsak račun dobi svoj rezultat.
   - Če je nastavljen na **Vklopljeno**, izberite **Uredi** za izbiro hierarhije računa glede na uvožene hierarhije. Mera bo zagotovila le en rezultat, ker je združena s podračuni.

1. Če med podatkovno entiteto, ki ste jo preslikali, in *entiteto* stranke obstaja več poti, morate izbrati eno od prepoznanih [poti odnosov entitet](relationships.md). Rezultati mere se lahko razlikujejo glede na izbrano pot.

   1. Izberite **Pot odnosa** in nato pot entitete, ki jo je treba uporabiti za identifikacijo vaše mere. Če obstaja samo ena pot do entitete *stranke*, ta nadzor ne bo prikazan.
   1. Izberite možnost **Končano**, da uporabite izbor.

1. V izračunu izberite tri pike **...**, da **podvojite**, **preimenujete** ali **odstranite** izračun iz mere.

1. Na območju **predogleda** boste videli podatkovno shemo entitete izhodnih mer, vključno s filtri in razsežnostmi. Predogled se dinamično odziva na spremembe v konfiguraciji.

1. Izberite **Uredite podrobnosti** poleg Neimenovane mere. Navedite ime za ukrep. Po želji dodajte [oznake](work-with-tags-columns.md#manage-tags) po meri.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Pogovorno okno Uredi podrobnosti.":::

1. Izberite možnost **Zaženi** za izračun rezultatov za konfigurirano mero. Izberite možnost **Shrani in zapri**, če želite obdržati trenutno konfiguracijo in mero zagnati pozneje.

1. Na strani **Mere** si na seznamu oglejte novo ustvarjeno mero.
