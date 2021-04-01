---
title: Preslikava entitet za poenotenje podatkov
description: Preslikajte podatke za ustvarjanje poenotenih profilov strank.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 36b7f7b2fac9497245cf6759506c53753972f173
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596013"
---
# <a name="map-entities-and-attributes"></a>Entitete in atributi zemljevida

**Preslikava** je prva stopnja v postopku poenotenja podatkov pri vpogledih v občinstvo. Preslikava je sestavljena iz treh faz:

- *Izbira entitete*: določite združljive entitete, ki vodijo do nabora podatkov s popolnejšimi informacijami o vaših strankah.
- *Izbira atributa:* za vsako entiteto določite stolpce, ki jih želite združiti in uskladiti v fazah *ujemanja* in *spajanja*. Ti stolpci se imenujejo *Atributi*.
- *Izbira primarnega ključa in vrste semantike*: za vsako entiteto določite atribut, ki ga želite definirati kot primarni ključ za to entiteto, za vsak atribut pa vrsto semantike, ki najbolje opisuje ta atribut.

Če želite več informacij o splošnem poteku poenotenja podatkov, glejte [Poenotenje](data-unification.md).

## <a name="select-the-first-entities"></a>Izbira prvih entitet

1. Pri vpogledih v občinstvo izberite **Podatki** > **Poenoti** > **Preslikaj**.

2. Fazo preslikave nastavite tako, da izberete **Izberi entitete**.

3. Izberite entitete in atribute, ki jih želite uporabiti v fazah *ujemanja* in *spajanja*. Obvezne atribute lahko iz entitete izberete posamezno ali pa iz nje vključite vse atribute in sicer tako, da izberete potrditveno polje na ravni entitete **Vključi vsa polja**. Priporočamo, da izberete vsaj dve entiteti, da boste lahko izkoristili postopek poenotenja podatkov.

   > [!div class="mx-imgBorder"]
   > ![Primer dodajanja entitet](media/data-manager-configure-map-add-entities-example.png "Primer dodajanja entitet")

   V tem primeru dodajamo entiteti **eCommerceContacts** in **loyCustomers**. Če izberete te dve entiteti lahko pridobite vpogled v to, kateri od spletnih poslovnih strank so člani programa zvestobe.
   
   Po ključnih besedah lahko iščete po vseh atributih in entitetah, da izberete zahtevane atribute, ki jih želite preslikati.
   
     > [!div class="mx-imgBorder"]
   > ![Primer polj za iskanje](media/data-manager-configure-map-search-fields-example.png "Primer polj za iskanje")

4. Izberite **Uporabi** za potrditev izbire.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Izbira primarnega ključa in vrste semantike za atribute

Ko izberete entitete, stran **Preslikava** navede izbrane entitete vam v pregled. Določite primarni ključ za entiteto in določite vrsto semantike za atribut v entiteti.

- **Primarni ključ**: izberite en atribut kot primarni ključ za vsako od entitet. Atribut je veljaven primarni ključ samo v primeru, če ne vsebuje podvojenih vrednosti, manjkajočih vrednosti ali ničelnih vrednosti. Atributi podatkovnih tipov niz, celo število in GUID so podprti kot primarni ključi in bodo prikazani v polju, iz katerega lahko izbirate.

- **Vrsta semantike atributa**: kategorije atributov, na primer e-poštni naslov ali ime. Če želite uporabiti modele umetne inteligence za pametno predvidevanje semantike, prihranite čas in izboljšajte natančnost, možnost **Pametna preslikava** nastavite na **VKLOPLJENO**. Pametna preslikava označi priporočila semantike na podlagi umetne inteligence v polju **Vrsta**. Če jo nastavite na **IZKLOPLJENO**, boste videli naša običajna priporočila za preslikavo. Na razpoložljivem seznamu možnosti lahko izberete katero koli semantično vrsto in preglasite predlagani izbor.

> [!div class="mx-imgBorder"]
> ![Vrsta atributa in predvidevanje semantike](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Vrsta atributa in predvidevanje semantike")

Možno je tudi dodajanje vrste semantike po meri. Izberite polje vrste za atribut in vnesite ime za vrsto semantike po meri. Tako lahko spremenite tudi vrste atributov, ki jih je sistem prepoznal.

Vsi atributi, za katere je vrsta semantike samodejno določena, so združeni v razdelku **Pregled preslikanih polj**. Preglejte te atribute in njihove vrste semantike, ker bodo uporabljeni za združevanje vaših entitet v koraku spajanja, kjer se poenotijo podatki.

Atributi, ki niso samodejno preslikani v vrsto semantike, so združeni v razdelku **Določanje podatkov v nepreslikanih poljih**. Izberite polje vrste semantike za nepreslikane atribute ali vnesite ime vrste atributa po meri.

> [!div class="mx-imgBorder"]
> ![Primarni ključ in vrsta atributa](media/data-manager-configure-map-add-attributes.png "Primarni ključ in vrsta atributa")

> [!NOTE]
> Eno polje se mora preslikati v vrsto semantike »Person.FullName«, da ime stranke vnese v kartico stranke. Sicer bodo kartice strank prikazane brez imen. 

## <a name="add-and-remove-attributes-and-entities"></a>Dodajanje in odstranjevanje atributov in entitet

1. V razdelku **Poenotenje** > **Preslikava** izberite **Uredi polja**.

2. V podoknu **Uredi polja** dodajte ali odstranite atribute in entitete. Z iskanjem ali drsanjem navzdol in navzgor poiščite atribute in entitete, ki vas zanimajo, in jih izberite. Atributa ali entitete ne morete odstraniti, če se že ujema.

   > [!div class="mx-imgBorder"]
   > ![Dodajanje ali odstranjevanje atributov](media/configure-data-map-edit.png "Dodajanje ali odstranjevanje atributov")

3. Izberite **Uporabi**.

## <a name="add-images-to-profiles"></a>Dodajanje slik v profile

Če entiteta vsebuje URL-je za javno dostopne slike profilov ali logotipe, jih lahko dodate v poenoten profil stranke.

Izberite entiteto in poiščite polje, ki vsebuje URL slike profila. V vnosno polje **Vrsta** ročno vnesite naslednjo vrednost: 
- Za osebo: Person.ProfileImage
- Za organizacijo: Organization.LogoImage

Nadaljujte s koraki za poenotenje in poskrbite, da je atribut, ki vsebuje URL slike, dodan tudi v korak [Spajanje](merge-entities.md).

## <a name="set-attributes-for-organizations"></a>Nastavitev atributov za organizacije

Za organizacije (predogledna različica) mora biti vrsta atributa preslikana v »Organization.Name«
> [!div class="mx-imgBorder"]
> ![Primarni ključ in vrsta atributa pri prodaji podjetjem](media/configure-data-map-edit-b2b.png "Primarni ključ in vrsta atributa pri prodaji podjetjem")

## <a name="next-step"></a>Naslednji korak

Kot del postopka poenotenja podatkov pojdite na stran **Ujemanje**. Obiščite stran [**Ujemanje**](match-entities.md), kjer najdete več informacij o tej fazi.

> [!TIP]
> Oglejte si ta videoposnetek: [Uvod: Ustvarjanje poenotenega profila stranke](https://youtu.be/oBfGEhucAxs).


[!INCLUDE[footer-include](../includes/footer-banner.md)]