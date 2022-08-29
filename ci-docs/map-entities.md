---
title: Izberite izvorna polja za poenotenje podatkov
description: Prvi korak v procesu poenotenja je izbira entitet, atributov, primarnih ključev in semantičnih tipov za preslikavo podatkov v poenoten profil stranke.
recommendations: false
ms.date: 08/12/2022
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
ms.openlocfilehash: bc120aa7a3713e1184ff278edf0942925faafa12
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304585"
---
# <a name="select-source-fields-for-data-unification"></a>Izberite izvorna polja za poenotenje podatkov

Prvi korak pri poenotenju je izbira entitet in polj znotraj naborov podatkov, ki jih želite poenotiti. Izberite entitete, ki vsebujejo podrobnosti, povezane s strankami, kot so ime, naslov, telefonska številka in e-pošta. Izberete lahko eno ali več entitet.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

## <a name="select-entities-and-fields"></a>Izbira entitet in polj

1. Pojdi do **podatki** > **Poenotiti**.

   Za posamezne stranke (B-to-C) je **Poenotiti** prikazov ciljne strani, ki prikazujejo **Začeti** na prvem koraku, **Izvorna polja**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Posnetek zaslona enotne ciljne strani za prvo izkušnjo za posamezne stranke.":::

   Za poslovne račune (B-to-B) je **Poenotiti** prikazov ciljne strani **Poenotite račune** prikazuje **Začeti** na prvem koraku, **Izvorna polja**. The **Poenotite stike (predogled)** koraki so neobvezni in čakajo na dokončanje združevanja računov.

   :::image type="content" source="media/b2b_unify_land.png" alt-text="Posnetek zaslona enotne ciljne strani za prvo izkušnjo za poslovne račune.":::

1. Izberite **Začetek**.

1. Na **Izvorna polja** stran, izberite **Izberite entitete in polja**. The **Izberite entitete in polja** zasloni v podoknu.

1. Izberite vsaj eno entiteto.

1. Za vsako izbrano entiteto določite polja, ki jih želite uporabiti za ujemanje zapisov strank, in polja, ki jih želite vključiti v poenoten profil. Ta polja se imenujejo *Lastnosti*. Zahtevane atribute lahko izberete posamezno iz entitete ali vključite vse atribute iz entitete tako, da izberete potrditveno polje na ravni entitete. Po ključnih besedah lahko iščete po vseh atributih in entitetah, da izberete zahtevane atribute, ki jih želite preslikati.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Posnetek zaslona izbranih entitet in atributov.":::

   V tem primeru dodajamo **eCommerceContacts** in **loyCustomer** entitete. Če izberete te dve entiteti lahko pridobite vpogled v to, kateri od spletnih poslovnih strank so člani programa zvestobe.

1. Izberite **Uporabi** za potrditev izbire. Prikažejo se izbrane entitete in atributi.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Izbira primarnega ključa in vrste semantike za atribute

   :::image type="content" source="media/m3_select_primary.png" alt-text="Posnetek zaslona izbranih entitet s primarnim ključem, ki še ni izbran." lightbox="media/m3_select_primary.png":::

Za vsako entiteto izvedite naslednje korake.

1. Izberite **Primarni ključ**. Primarni ključ je atribut, edinstven za entiteto. Atribut je veljaven primarni ključ samo v primeru, če ne vsebuje podvojenih vrednosti, manjkajočih vrednosti ali ničelnih vrednosti. Kot primarni ključi so podprti atributi podatkovnega tipa niz, celo število in GUID.

1. Če želite uporabiti modele AI za pametno predvidevanje semantiko, ki prihrani čas in izboljša natančnost, zagotovite **Inteligentno kartiranje** je vklopljen. Inteligentno preslikavo zagotavlja semantična priporočila na osnovi umetne inteligence v **Vrsta** polje.

1. Za vsak atribut izberite semantiko **Vrsta** ki najbolje opisuje ta atribut, na primer ime, mesto ali e-poštni naslov.

   > [!NOTE]
   > V B-to-C se mora eno polje preslikati v semantični tip *Oseba. Polno ime* za vnos imena stranke na kartico stranke. V B-to-B se mora ime računa preslikati v *Organization.Name*. Sicer bodo kartice strank prikazane brez imen.

   1. Če želite preglasiti vrsto atributa, ki ga prepozna sistem, izberite drugo možnost. Če vrsta ne obstaja, ustvarite semantično vrsto po meri tako, da izberete **Vrsta** polje za atribut in vnos imena semantičnega tipa po meri.

   1. Če želite javno dostopnim profilnim slikam ali logotipom dodati atribut, ki vsebuje URL, izberite entiteto in polje, ki vsebuje URL. V **Vrsta** polje vnesite naslednje:
      - Za osebo: Person.ProfileImage
      - Za organizacijo: Organization.LogoImage

1. Preglejte atribute, kjer je semantični tip samodejno identificiran. Ti atributi so navedeni pod **Preglejte preslikana polja**. Samo atribute istega tipa je mogoče kombinirati v **Poenotite polja strank** korak. Semantične vrste se uporabljajo za samodejno predlaganje vpogledov. Prepričajte se, da so tipi, ki ste jih izbrali, skladni v vseh izbranih entitetah.

1. Za atribute, ki niso samodejno preslikani v semantični tip, izberite polje semantičnega tipa, vnesite ime tipa atributa po meri ali jih pustite nepreslikanih. Ti atributi so navedeni pod **Določite podatke v nepreslikanih poljih**.

1. Ko dokončate korake za vsako entiteto, izberite **Shrani izvorna polja**.

1. Izberite **Naprej**.

> [!div class="nextstepaction"]
> [Naslednji korak: odstranite dvojnike](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
