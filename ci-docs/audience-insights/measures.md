---
title: Ustvarjanje in upravljanje mer
description: Določite mere za analizo in odraz uspešnosti vašega podjetja.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 5bcee3b4c51880740715575b18fd7a4dbf87e6d0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269948"
---
# <a name="define-and-manage-measures"></a>Določanje in upravljanje mer

Mere vam pomagajo bolje razumeti vedenje strank in poslovno uspešnost tako, da vam prikažejo relevantne vrednosti iz [poenotenih profilov](data-unification.md). Podjetje na primer želi videti *skupno porabo na stranko* za razumevanje zgodovine nakupov posameznih strank. Ali izmeriti *celotno prodajo podjetja* za razumevanje združenega prihodka na ravni celotnega podjetja.  

Mere so ustvarjene z graditeljem mer, platformo za poizvedbe po podatkih z različnimi operatorji in enostavnimi možnostmi preslikave. Omogoča filtriranje podatkov, združevanje rezultatov v skupine, zaznavanje [poti odnosov entitet](relationships.md) in predogled rezultatov.

Uporabite graditelja mer za načrtovanje poslovnih dejavnosti s poizvedbami po podatkih o strankah in pridobivanjem vpogledov. Ustvarjanje na primer mer za *skupno porabo na stranko* in *skupni donos na stranko* pomaga prepoznati skupino strank z visoko porabo, ki pa so hkrati zelo donosne. Mogoče je [ustvariti segment](segments.md) za spodbujanje drugih priporočenih dejanj. 

## <a name="create-a-measure"></a>Ustvarjanje mere

V tem razdelku je opisano ustvarjanje novega mere od začetka. Mero lahko sestavite z atributi podatkov iz podatkovnih entitet, ki imajo nastavljen odnos za povezavo z entiteto stranke. 

1. Pri vpogledih v občinstvo izberite **Mere**.

1. Izberite **Novo**.

1. Izberite možnost **Uredi ime** in navedite **ime** za mero. 
   > [!NOTE]
   > Če ima nova konfiguracija mere samo dve polji, na primer, CustomerID in en izračun, bodo izhodni podatki dodani kot nov stolpec v sistemsko ustvarjeni entiteti z imenom Customer_Measure. Vrednost mere pa boste lahko videli v enotnem profilu stranke. Druge mere ustvarijo lastne entitete.

1. V območju za konfiguracijo izberite združevalno funkcijo s spustnega menija **Izberi funkcijo**. Združevalne funkcije vključujejo: 
   - **Vsota**
   - **Povprečje**
   - **Število**
   - **Št. enoličnih**
   - **Maksimum**
   - **Min**
   - **Najprej**: vzame prvo vrednost podatkovnega zapisa
   - **Zadnje**: vzame zadnjo vrednost, ki je bila dodana v podatkovni zapis

   :::image type="content" source="media/measure-operators.png" alt-text="Operatorji za izračun mer.":::

1. Izberite možnost **Dodaj atribut**, da izberete podatke, ki jih potrebujete za izdelavo te mere.
   
   1. Izberite zavihek **Atributi**. 
   1. Podatkovna entiteta: izberite entiteto, ki vključuje atribut, ki ga želite izmeriti. 
   1. Atribut podatkov: izberite atribut, ki ga želite uporabiti v združevalni funkciji za izračun mere. Naenkrat lahko izberete le en atribut.
   1. Atribut podatkov lahko izberete tudi iz obstoječe mere tako, da odprete zavihek **Ukrepi**. Poiščete lahko tudi ime entitete ali mere. 
   1. Izberite možnost **Dodaj**, da meri dodate izbrani atribut.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Izberite atribut, ki ga želite uporabiti pri izračunih.":::

1. Če želite zgraditi bolj zapletene mere, lahko v funkcijo mere dodate več atributov ali uporabite matematične operatorje.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Ustvarjanje zapletene mere z matematičnimi operatorji.":::

1. Če želite dodati filtre, v konfiguracijskem območju izberite možnost **Filter**. 
  
   1. V razdelku **Dodaj atribut** na podoknu **Filtri** izberite atribut, ki ga želite uporabiti za ustvarjanje filtrov.
   1. Nastavite operatorje filtrov, da določite filter za vsak izbrani atribut.
   1. Izberite možnost **Dodaj**, da meri dodate filter.

1. Če želite dodati razsežnosti, v območju za konfiguracijo izberite možnost **Razsežnosti**. Dimenzije bodo prikazane kot stolpci v entiteti izhodnih mer.
   1. Izberite možnost **Uredi razsežnosti**, da dodate atribute podatkov, po katerih želite vrednosti mer razvrstiti v skupine. Na primer po mestu ali spolu. Privzeto je razsežnost *CustomerID* izbrana za ustvarjanje *ukrepov na ravni kupca*. Če želite ustvariti *ukrepe na ravni podjetja*, lahko odstranite privzeto dimenzijo.
   1. Izberite možnost **Končano**, da meri dodate razsežnosti.

1. Če med podatkovno entiteto, ki ste jo preslikali, in entiteto stranke obstaja več poti, morate izbrati eno od prepoznanih [poti odnosov entitet](relationships.md). Rezultati mere se lahko razlikujejo glede na izbrano pot.
   1. Izberite možnost **Podatkovne nastavitve** in izberite pot entitete, ki naj bo uporabljena za prepoznavanje mere.
   1. Izberite možnost **Končano**, da uporabite izbor. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Izberite pot entitete za mero.":::

1. Če želite dodati več izračunov za mero, izberite možnost **Nov izračun**. Entitete z isto potjo lahko uporabite samo za nove izračune. Dodatni izračuni bodo prikazani kot novi stolpci v entiteti izhodnih mer.

1. V izračunu izberite tri pike **...**, da **podvojite**, **preimenujete** ali **odstranite** izračun iz mere.

1. Na območju **predogleda** boste videli podatkovno shemo entitete izhodnih mer, vključno s filtri in razsežnostmi. Predogled se dinamično odziva na spremembe v konfiguraciji.

1. Izberite možnost **Zaženi** za izračun rezultatov za konfigurirano mero. Izberite možnost **Shrani in zapri**, če želite obdržati trenutno konfiguracijo in mero zagnati pozneje.

1. Na strani **Mere** si na seznamu oglejte novo ustvarjeno mero.

## <a name="manage-your-measures"></a>Upravljajte svoje mere

Ko [ustvarite mero](#create-a-measure), boste na strani **Mere** videli seznam mer.

Našli boste podatke o vrsti mere, ustvarjalcu, datumu ustvarjanja, statusu in stanju. Ko izberete mero s seznama, si lahko ogledate izhodne podatke in jih prenesete kot datoteko .CSV.

Če želite hkrati osvežiti vse svoje mere, izberite **Osveži vse**, ne da bi izbrali posamezno mero.

> [!div class="mx-imgBorder"]
> ![Dejanja za upravljanje posameznih mer](media/measure-actions.png "Dejanja za upravljanje posameznih mer")

Na seznamu izberite mero za naslednje možnosti:

- Za prikaz podrobnosti izberite ime mere.
- Izberete lahko možnost **Uredi** in uredite konfiguracijo mere.
- **Osveži** mero na podlagi najnovejših podatkov.
- Mero lahko preimenujete prek možnosti **Preimenuj**.
- Za brisanje mere je na voljo **Izbriši**.
- **Aktiviraj** ali **deaktiviraj**. Nedejavne mere se med [načrtovano osvežitvijo](system.md#schedule-tab) ne bodo osvežile.

> [!TIP]
> Na voljo je [šest vrst stanja](system.md#status-types) za opravila/postopke. Poleg tega je večina postopkov [odvisna od drugih nadaljnjih postopkov](system.md#refresh-policies). Izberete lahko stanje postopka in si ogledate podrobnosti o poteku celotnega posla. Ko za enega izmed poslov izberete **Prikaži podrobnosti**, se prikažejo dodatne informacije: čas obdelave, zadnji datum obdelave ter vse napake in opozorila, povezana z opravilom.

## <a name="next-step"></a>Naslednji korak

Z obstoječimi merami lahko ustvarite [segment stranke](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]