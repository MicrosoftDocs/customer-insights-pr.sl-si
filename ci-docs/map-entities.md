---
title: Izberite izvorna polja za poenotenje podatkov
description: Prvi korak v procesu poenotenja je izbira entitet, atributov, primarnih ključev in semantičnih tipov za preslikavo podatkov v enoten profil stranke.
recommendations: false
ms.date: 04/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: a962f1353b6e25b40c60b39a81ac936873f34d92
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741015"
---
# <a name="select-source-fields-for-data-unification"></a>Izberite izvorna polja za poenotenje podatkov

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Prvi korak pri poenotenju je izbira entitet in polj znotraj vaših podatkovnih nizov, ki jih želite poenotiti. Izberite subjekte, ki vsebujejo podrobnosti, povezane s strankami, kot so ime, naslov, telefonska številka in e-pošta. Izberete lahko enega ali več subjektov.

## <a name="select-entities-and-fields"></a>Izberite entitete in polja

1. Pojdi do **Podatki** > **Združite**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Posnetek zaslona ciljne strani unify za izkušnjo prvega zagona z označenim Začetek.":::

1. Izberite **Začetek**.

1. Na **Izvorna polja** stran, izberite **Izberite entitete in polja**. The **Izberite entitete in polja** podokna.

1. Izberite vsaj eno entiteto.

1. Za vsako izbrano entiteto določite polja, ki jih želite uporabiti za ujemanje z zapisi strank in polja, ki jih želite vključiti v enoten profil. Ta polja se imenujejo *Lastnosti*. Zahtevane atribute lahko izberete posamezno iz entitete ali pa vključite vse atribute iz entitete, tako da izberete potrditveno polje na ravni entitete. Po ključnih besedah lahko iščete po vseh atributih in entitetah, da izberete zahtevane atribute, ki jih želite preslikati.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Posnetek zaslona izbranih entitet in atributov.":::

   V tem primeru dodajamo **Stiki** in **Zvestoba stranke** subjekti. Če izberete te dve entiteti lahko pridobite vpogled v to, kateri od spletnih poslovnih strank so člani programa zvestobe.

1. Izberite **Uporabi** za potrditev izbire. Prikažejo se izbrane entitete in atributi.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Izbira primarnega ključa in vrste semantike za atribute

   :::image type="content" source="media/m3_select_primary.png" alt-text="Posnetek zaslona izbranih entitet s primarnim ključem ni izbran." lightbox="media/m3_select_primary.png":::

Za vsako entiteto izvedite naslednje korake.

1. Izberite **Primarni ključ**. Primarni ključ je edinstven atribut za entiteto. Atribut je veljaven primarni ključ samo v primeru, če ne vsebuje podvojenih vrednosti, manjkajočih vrednosti ali ničelnih vrednosti. Kot primarni ključi so podprti atributi vrste podatkov niz, celo število in GUID.

1. Če želite uporabiti modele AI za pametno predvidevanje semantike, prihranite čas in izboljšate natančnost, zagotovite **Inteligentno kartiranje** je vklopljen. Pametna preslikava označi priporočila semantike na podlagi umetne inteligence v polju **Vrsta**. Predlagano izbiro lahko preglasite tako, da na seznamu možnosti, ki so na voljo, izberete katero koli semantično vrsto.

1. Za vsak atribut izberite pomen **Vrsta** ki najbolje opisuje ta atribut, na primer ime, mesto ali e-poštni naslov.

   > [!NOTE]
   > Eno polje se mora preslikati v semantični tip *Oseba.Polno ime* da vnesete ime stranke v kartico stranke. Sicer bodo kartice strank prikazane brez imen.

   1. Če želite spremeniti vrsto atributa, ki ga identificira sistem, izberite drugo vrsto. Če vrsta ne obstaja, ustvarite semantični tip po meri tako, da izberete **Vrsta** polje za atribut in vnesite svoje ime semantičnega tipa po meri.

   1. Če želite javno dostopnim slikam ali logotipom profilov dodati atribut, ki vsebuje URL, izberite entiteto in polje, ki vsebuje URL. V **Vrsta** polje, vnesite naslednje:
      - Za osebo: Person.ProfileImage
      - Za organizacijo: Organization.LogoImage

   1. Za atribut imena računa vnesite "Organization.Name" v **Vrsta** polje.

1. Preglejte atribute, kjer je semantični tip samodejno identificiran. Ti atributi so navedeni pod **Preglejte preslikana polja**. V njem je mogoče kombinirati samo atribute iste vrste **Poenotena polja strank** korak. Semantične vrste se uporabljajo za samodejno predlaganje vpogledov. Zagotovite, da so vrste, ki ste jih izbrali, skladne v vseh izbranih entitetah.

1. Za atribute, ki niso samodejno preslikani v pomensko vrsto, izberite polje semantičnega tipa, vnesite ime vrste atributa po meri ali jih pustite nepreslikane. Ti atributi so navedeni pod **Določite podatke v nepreslikanih poljih**.

1. Ko dokončate korake za vsako entiteto, izberite **Shrani izvorna polja**.

1. Izberite **Naprej**.

> [!div class="nextstepaction"]
> [Naslednji korak: odstranite dvojnike](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
