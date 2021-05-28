---
title: Ustvarjanje in upravljanje mer
description: Določite mere za analizo in odraz uspešnosti vašega podjetja.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 402e5ef3515bce0e6f56788781b7bd909738aaa6
ms.sourcegitcommit: b833e333745d321edeaf96d3ed14458cbce02ff1
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049270"
---
# <a name="define-and-manage-measures"></a>Določanje in upravljanje mer

Ukrepi vam pomagajo bolje razumeti vedenje strank in poslovno uspešnost. Upoštevajo relevantne vrednosti iz [poenotenih profilov](data-unification.md). Podjetje želi na primer videti *skupno porabo stranke*, da bi razumelo zgodovino nakupov stranke, ali izmeriti *skupno prodajo podjetja*, da bi razumelo skupni prihodek celotnega posla.  

Mere so ustvarjene z graditeljem mer, platformo za poizvedbe po podatkih z različnimi operatorji in enostavnimi možnostmi preslikave. Omogoča filtriranje podatkov, združevanje rezultatov v skupine, zaznavanje [poti odnosov entitet](relationships.md) in predogled rezultatov.

Uporabite graditelja mer za načrtovanje poslovnih dejavnosti s poizvedbami po podatkih o strankah in pridobivanjem vpogledov. Ustvarjanje na primer mer za *skupno porabo na stranko* in *skupni donos na stranko* pomaga prepoznati skupino strank z visoko porabo, ki pa so hkrati zelo donosne. Mogoče je [ustvariti segment](segments.md) za spodbujanje drugih priporočenih dejanj. 

## <a name="build-your-own-measure-from-scratch"></a>Ustvarjanje ukrepa od začetka

V tem razdelku je opisano ustvarjanje novega mere od začetka. Mero lahko sestavite z atributi podatkov iz podatkovnih entitet, ki imajo nastavljen odnos za povezavo z entiteto stranke. 

1. Pri vpogledih v občinstvo izberite **Mere**.

1. Izberite **Novo** in nato še **Ustvarite si svojega**.

1. Izberite možnost **Uredi ime** in navedite **ime** za mero. 
   > [!NOTE]
   > Če ima vaša nova konfiguracija mere samo dve polji, na primer CustomerID in en izračun, bo izhod dodan kot nov stolpec k sistemsko ustvarjeni entiteti, imenovani Customer_Measure. Vrednost mere pa boste lahko videli v enotnem profilu stranke. Druge mere ustvarijo lastne entitete.

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

1. Če so v vaših podatkih vrednosti, ki jih morate zamenjati s celim številom, zamenjajte *null* na primer z *0* in izberite **Pravila**. Konfigurirajte pravilo in se prepričajte, da jih nadomestite le s celimi števili.

1. Če med podatkovno entiteto, ki ste jo preslikali, in *entiteto* stranke obstaja več poti, morate izbrati eno od prepoznanih [poti odnosov entitet](relationships.md). Rezultati mere se lahko razlikujejo glede na izbrano pot. 
   1. Izberite možnost **Podatkovne nastavitve** in izberite pot entitete, ki naj bo uporabljena za prepoznavanje mere. Če obstaja samo ena pot do entitete *stranke*, ta nadzor ne bo prikazan.
   1. Izberite možnost **Končano**, da uporabite izbor. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Izberite pot entitete za mero.":::

1. Če želite dodati več izračunov za mero, izberite možnost **Nov izračun**. Entitete z isto potjo lahko uporabite samo za nove izračune. Dodatni izračuni bodo prikazani kot novi stolpci v entiteti izhodnih mer.

1. V izračunu izberite tri pike **...**, da **podvojite**, **preimenujete** ali **odstranite** izračun iz mere.

1. Na območju **predogleda** boste videli podatkovno shemo entitete izhodnih mer, vključno s filtri in razsežnostmi. Predogled se dinamično odziva na spremembe v konfiguraciji.

1. Izberite možnost **Zaženi** za izračun rezultatov za konfigurirano mero. Izberite možnost **Shrani in zapri**, če želite obdržati trenutno konfiguracijo in mero zagnati pozneje.

1. Na strani **Mere** si na seznamu oglejte novo ustvarjeno mero.

## <a name="use-a-template-to-build-a-measure"></a>Uporaba predloge za izdelavo ukrepa

Za ustvarjanje ukrepov lahko uporabite vnaprej določene predloge pogosto uporabljenih ukrepov. Podrobni opisi predlog in vodena izkušnja vam pomagajo pri učinkovitem ustvarjanju ukrepov. Predloge temeljijo na preslikanih podatkih iz entitete *Poenotena dejavnost*. Prepričajte se, da ste konfigurirali [dejavnosti strank](activities.md), preden ustvarite ukrep iz predloge.

Razpoložljive predloge ukrepov: 
- Povprečna vrednost transakcije (ATV)
- Skupna vrednost transakcije
- Povprečni dnevni prihodek
- Povprečni letni prihodek
- Število transakcij
- Prislužene točke zvestobe
- Izkoriščene točke zvestobe
- Stanje točk zvestobe
- Življenjska doba dejavne stranke
- Trajanje članstva v programu zvestobe
- Čas od zadnjega nakupa

V naslednjem postopku so opisani koraki za ustvarjanje novega ukrepa s pomočjo predloge.

1. Pri vpogledih v občinstvo izberite **Mere**.

1. Izberite **Novo** in nato **Izberi predlogo**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Posnetek zaslona spustnega menija pri ustvarjanju novega ukrepa s poudarjeno predlogo.":::

1. Poiščite predlogo, ki ustreza vašim potrebam, in izberite **Izberi predlogo**.

1. Preglejte zahtevane podatke in izberite **Začetek**, če imate na voljo vse podatke.

1. V podoknu **Uredi ime** nastavite ime za vaš ukrep in izhodno entiteto. 

1. Izberite **Dokončano**.

1. V razdelku **Nastavi časovno obdobje** določite časovni okvir podatkov, ki jih želite uporabiti. Določite, ali želite z novim ukrepom zajeti celoten nabor podatkov, tako da izberete **Ves čas**. Ali če želite, da se ukrep osredotoči na **Določeno časovno obdobje**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Posnetek zaslona, ki prikazuje razdelek časovnega obdobja pri konfiguriranju ukrepa iz predloge.":::

1. V naslednjem razdelku izberite **Dodaj podatke**, če želite izbrati dejavnosti in preslikati ustrezne podatke iz vaše entitete *Poenotena dejavnost*.

    1. Korak 1 od 2: v razdelku **Vrsta dejavnosti** izberite vrsto entitete, ki jo želite uporabiti. Za **Dejavnosti** izberite entitete, ki jih želite preslikati.
    1. Korak 2 od 2: izberite atribut v entiteti *Poenotena dejavnost* za komponento, ki jo zahteva formula. Za povprečno vrednost transakcije je to na primer atribut, ki predstavlja vrednost transakcije. Za **Časovni žig dejavnosti** izberite atribut iz entitete poenotene dejavnosti, ki predstavlja datum in čas dejavnosti.
   
1. Ko je preslikava podatkov uspešno zaključena, se prikaže stanje **Dokončano** skupaj z imenom preslikanih dejavnosti in atributov.

   :::image type="content" source="media/measure-template-configured.png" alt-text="Posnetek zaslona dokončane konfiguracije predloge ukrepa.":::

1. Zdaj lahko izberete **Zaženi**, da izračunate rezultate ukrepa. Če jih želite pozneje prilagoditi, izberite **Shrani osnutek**.

## <a name="manage-your-measures"></a>Upravljajte svoje mere

Seznam ukrepov najdete na strani **Ukrepi**.

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
