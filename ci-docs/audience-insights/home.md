---
title: Domača stran pri vpogledih v občinstvo
description: Začnite raziskovati aplikacijo na domači strani.
ms.date: 01/07/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: bf9080c564850bca0c239b7317eed2fc0f77d9f3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597255"
---
# <a name="create-a-new-environment"></a>Ustvarite novo okolje

## <a name="create-a-trial-environment"></a>Ustvarite preskusno okolje

Za preskusno različico se lahko prijavite na [stran za prijavo za preskusno različico](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Preskusno obdobje poteče po 30 dneh.

1. Izberite možnost **Prijava za brezplačno preskusno različico** in izberite **Prijavi se zdaj**.

1. Navedite službeni ali šolski e-poštni naslov, povejte nam več o sebi in izberite **Naprej**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Pogovorno okno za prijavo za preskusni primerek":::

1. Določite **ime** za novo okolje. 

1. Izberite vrsto preskusne različice.

1. Izberite **regijo** za svoje okolje.

1. Izbirno za skrbnike organizacije Dynamics 365: izberite **Napredne nastavitve** in navedite URL svoje organizacije za uporabo funkcij za predvidevanje, kot je izguba stranke.

1. Izberite **Ustvari**. 

Ko je okolje ustvarjeno, boste videli **predstavitveno** okolje, ki vam omogoča raziskovanje aplikacije z izmišljenimi podatki. Vzorčne podatke lahko spremenite tako, da ustrezajo vaši panogi. Izberite ikono **Nastavitve** v glavi in izberite **Nastavitve predstavitve**. Poleg tega lahko spremenite vizualno temo. 

[Preklopite na okolje](#switch-environments), ki ste ga ustvarili med postopkom prijave, in delajte z lastnimi podatki.

## <a name="create-a-new-production-or-sandbox-environment"></a>Ustvarite novo produkcijsko ali preizkusno okolje

V svojem okolju v glavi aplikacije izberite izbirnik za **Okolja** in izberite možnost **Novo**.

Sledite korakom, kot da [ustvarjate poskusno okolje](#create-a-trial-environment). Podatki so privzeto shranjeni v jezeru podatkov, ki ga upravlja aplikacija Customer Insights. Če izberete **Napredne nastavitve**, dobite dodatno možnost za shranjevanje podatkov v svoj račun Azure Data Lake. Navedite ime računa in ključ računa, da vzpostavite povezavo z vašim računom Azure Data Lake. 

> [!IMPORTANT]
> Če shranite podatke v storitev Azure Data Lake Storage, se strinjate, da bodo podatki preneseni na ustrezno geografsko lokacijo za ta račun za shrambo Azure in tam shranjeni. Ta lokacija se lahko razlikuje od lokacije, kjer so shranjeni podatki v storitvi Dynamics 365 Customer Insights. [Več o tem preberite v Microsoftovem središču zaupanja.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Raziskujte domačo stran

Do [vpogledov v občinstvo iz storitve Dynamics 365 Customer Insights lahko dostopate](https://home.ci.ai.dynamics.com/) na naslednjem URL-ju: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
Stran **Osnovno** prikazuje pregled segmentov, ukrepov in podatkov o obogatitvi (če so konfigurirani) po koncu faz [preslikave](map-entities.md), [ujemanja](match-entities.md) in [združevanja](merge-entities.md).

> [!div class="mx-imgBorder"] 
> ![Vpogledi na domači strani](media/home-page-insights.png "Vpogledi na domači strani")

V razdelku **Nedavni segmenti** vidite skupine strank na podlagi demografskih, vedenjskih ali transakcijskih atributov, ki ste jih določili. [Ustvarjanje segmentov](segments.md) vam pomaga razvrstiti bazo strank in bolje usmeriti poslovna opravila.

**Najnovejši ukrepi** prikazujejo ploščice s [ključnimi kazalniki uspešnosti (KPI-ji)](measures.md), ki ste jih določili. Na primer, povprečna verjetnost za izgubo stranki ali povprečna spletna poraba na stranko.

V razdelku **Nedavne obogatitve** so navedeni rezultati obogatitve, ki so se pred kratkim zaključili. [Obogatitve](enrichment-hub.md) dodajajo podatke o vaši bazi strank. Podatke dodajo tako, da na primer preučijo katere vsebine in blagovne znamke zanimajo stranko.

## <a name="switch-environments"></a>Zamenjava okolja

V zgornjem desnem kotu strani izberite kontrolnik **Okolje**, če želite spremeniti okolje.

> [!div class="mx-imgBorder"] 
> ![Zamenjava okolja](media/home-page-environment-switcher.png "Zamenjava okolja")

Skrbniki lahko ustvarjajo in upravljajo [več okolij](manage-environments.md). Vzdrževanje več kot enega okolja je lahko koristno, če vaša organizacija na primer deluje na mednarodni ravni in morate podatke in vpoglede ločevati na različne načine.

## <a name="next-step"></a>Naslednji korak

Če želite na začetni strani prikazati svoje vpoglede, morate najprej [dodati vire podatkov](data-sources.md) in [poenotiti](data-unification.md) podatke za oblikovanje profilov strank.


[!INCLUDE[footer-include](../includes/footer-banner.md)]