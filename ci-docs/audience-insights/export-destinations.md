---
title: Izvoz podatkov iz storitve Customer Insights
description: Upravljajte izvoze za skupno rabo podatkov.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896163"
---
# <a name="exports-preview-overview"></a>Pregled izvozov (predogledna različica)

Na strani **Izvozi** so prikazani vsi konfigurirani izvozi. Izvozi dajo specifične podatke v skupno rabo z različnimi aplikacijami. Vključujejo lahko profile strank ali entitete, sheme in podrobnosti o preslikavi. Za vsak izvoz je potrebna [povezava, ki jo nastavi skrbnik, za upravljanje preverjanja pristnosti in dostopa](connections.md).

> [!NOTE]
> Do marca 2021 so izvozi samodejno ustvarili povezavo s pripadajočo storitvijo. Zdaj je za izvoze potrebna [povezava, ki jo ustvari in da v skupno rabo skrbnik](connections.md), preden je možno ustvarjanje.

Pojdite na **Podatki** > **Izvozi** za ogled strani z izvozi. Vse uporabniške vloge imajo dostop za ogled konfiguriranih izvozov. Uporabite polje za iskanje v ukazni vrstici, da najdete izvoze po njihovem imenu, imenu povezave in vrsti povezave.

## <a name="set-up-a-new-export"></a>Nastavitev novega izvoza

Če želite nastaviti ali urediti izvoz, morate imeti na voljo povezave. Povezave so odvisne od vaše [uporabniške vloge](permissions.md):
- Skrbniki imajo dostop do vseh povezav. Pri nastavitvi izvoza lahko ustvarijo tudi nove povezave.
- Udeleženci lahko imajo dostop do določenih povezav. Pri konfiguriranju in skupni rabi povezav so odvisni od skrbnikov. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Gledalci si lahko ogledajo samo obstoječe izvoze, vendar jih ne morejo ustvariti.

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite **Dodaj izvoz** za ustvarjanje novega cilja za izvoz.

1. V podoknu **Nastavitev izvoza** izberite, katero povezavo uporabiti. [Povezave](connections.md) upravljajo skrbniki. 

1. Navedite zahtevane podrobnosti in izberite **Shrani**, da ustvarite izvoz.

### <a name="edit-an-export"></a>Urejanje izvoza

1. Izberite navpične tri pike pri cilju za izvoz, ki ga želite urediti.

1. V spustnem meniju izberite **Uredi**.

1. Spremenite vrednosti, ki jih želite posodobiti, in izberite **Shrani**.

## <a name="view-exports-and-export-details"></a>Ogled izvozov in podrobnosti izvozov

Po ustvarjanju ciljev za izvoz so ti navedeni na **Podatki** > **Izvozi**. Vsi uporabniki lahko vidijo, kateri podatki so v skupni rabi in njihovo zadnje stanje.

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Uporabniki brez dovoljenj za urejanje izberejo **Ogled** namesto **Urejanje** za prikaz podrobnosti izvoza.

1. V tem stranskem podoknu je prikazana nastavitev tega izvoza. Brez dovoljenj za urejanje ne morete spreminjati vrednosti. Izberite **Zapri**, da se vrnete na stran z izvozi.

## <a name="run-exports-on-demand"></a>Zaženi izvoze na zahtevo

Po konfiguraciji izvoza se bo ta zagnal z vsako [načrtovano osvežitvijo](system.md#schedule-tab), če le ima delujočo povezavo.

Za izvoz podatkov brez čakanja na načrtovano osvežitev, pojdite na **Podatki** > **Izvozi**. Na voljo imate dve možnosti:

- Če želite zagnati vse izvoze, izberite **Zaženi vse** v ukazni vrstici. 
- Če želite zagnati en izvoz, izberite tri pike (...) na elementu seznama in nato izberite **Zagon**.

## <a name="remove-an-export"></a>Odstranjevanje izvoza

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite navpične tri pike pri izvozu, ki ga želite odstraniti.

1. Na spustnem seznamu izberite **Odstrani**.

1. Odstranjevanje potrdite tako, da na potrditvenem zaslonu izberete **Odstrani**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
