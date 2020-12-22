---
title: Domača stran pri vpogledih v občinstvo
description: Začnite raziskovati aplikacijo na domači strani.
ms.date: 09/30/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: bd16966eabb126d9c9945ededc53273df02c3369
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406977"
---
# <a name="create-a-new-environment"></a>Ustvarite novo okolje

## <a name="create-a-trial-environment"></a>Ustvarite preskusno okolje

Za preskusno različico se lahko prijavite na [stran za prijavo za preskusno različico](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Preskusno obdobje poteče po 30 dneh.

1. Izberite možnost **Prijava za brezplačno preskusno različico** in izberite **Prijavi se zdaj**.

1. Navedite službeni ali šolski e-poštni naslov, povejte nam več o sebi in izberite **Naprej**.

1. Določite **ime** za novo okolje. 

1. Izberite vrsto preskusne različice.

1. Izberite **regijo** za svoje okolje.

1. Izbirno za skrbnike organizacije Dynamics 365: izberite **Napredne nastavitve** in navedite URL svoje organizacije za uporabo funkcij za predvidevanje, kot je izguba stranke.

1. Izberite **Ustvari**. 

Ko je okolje ustvarjeno, boste videli **predstavitveno** okolje, ki vam omogoča raziskovanje aplikacije z izmišljenimi podatki. Vzorčne podatke lahko spremenite tako, da ustrezajo vaši panogi. Izberite ikono **Nastavitve** v glavi in izberite **Nastavitve predstavitve**. Poleg tega lahko spremenite vizualno temo. 

[Preklopite na okolje](#change-between-environments), ki ste ga ustvarili med postopkom prijave, in delajte z lastnimi podatki.

## <a name="create-a-new-production-or-sandbox-environment"></a>Ustvarite novo produkcijsko ali preizkusno okolje

V svojem okolju v glavi izberite ikono **Nastavitve** in izberite **Novo okolje**.

Sledite korakom, kot da [ustvarjate poskusno okolje](#create-a-trial-environment). Če izberete **Napredne nastavitve**, dobite dodatno možnost za shranjevanje podatkov v svoj račun Azure Data Lake. Navedite ime računa in ključ računa, da vzpostavite povezavo z vašim računom Azure Data Lake. Podatki so privzeto shranjeni v jezeru podatkov, ki ga upravlja aplikacija Customer Insights.

> [!IMPORTANT]
> Če shranite podatke v storitev Azure Data Lake Storage, se strinjate, da bodo podatki preneseni na ustrezno geografsko lokacijo za ta račun za shrambo Azure in tam shranjeni. Ta lokacija se lahko razlikuje od lokacije, kjer so shranjeni podatki v storitvi Dynamics 365 Customer Insights. [Več o tem preberite v Microsoftovem središču zaupanja.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Raziskujte domačo stran

[Do okolja Customer Insights lahko dostopate](https://home.ci.ai.dynamics.com/) prek naslednjega URL-ja: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
**Domača stran** prikazuje pregled vaše baze strank in ključne meritve za sledenje zdravju vašega podjetja.

> [!div class="mx-imgBorder"] 
> ![Vpogledi na domači strani](media/home-page-insights.png "Vpogledi na domači strani")

V razdelku **Nedavni segmenti** vidite skupine strank na podlagi demografskih, vedenjskih ali transakcijskih atributov, ki ste jih določili. [Ustvarjanje segmentov](segments.md) vam pomaga bolje usmeriti svoje poslovne dejavnosti.

**Nedavne meritve** prikazujejo ploščice z [meritvami](measures.md). Ukrepi so ključni kazalnik učinkovitosti (KPI), ki ste jih določili. Na primer, povprečna verjetnost izgube strank ali povprečna spletna poraba na stranko.

V razdelku **Nedavne obogatitve** so navedeni rezultati obogatitve, ki so se pred kratkim zaključili. Izboljšave dodajajo podatke o vaši bazi strank. Podatke dodajo tako, da na primer preučijo katere vsebine in blagovne znamke zanimajo stranko. Te podatke je mogoče odkleniti s pomočjo zmogljivosti za [obogatitev](enrichment-microsoft-graph.md), ko dokončate faze [preslikave](map-entities.md), [ujemanja](match-entities.md) in [združevanja](merge-entities.md).

## <a name="change-between-environments"></a>Preklop med okolji

Ko nastavite in konfigurirate [vire podatkov](data-sources.md), boste želeli preklopiti iz predstavitvenega okolja v okolje v živo. Uporaba produkcijskega okolja vam omogoča, da delate z lastnimi podatki o strankah. V zgornjem desnem kotu strani izberite kontrolnik **Okolje**, če želite spremeniti okolje.

> [!div class="mx-imgBorder"] 
> ![Zamenjava okolja](media/home-page-environment-switcher.png "Zamenjava okolja")

Skrbniki lahko ustvarjajo in upravljajo [več okolij](manage-environments.md). Vzdrževanje več kot enega okolja je lahko koristno, če vaša organizacija na primer deluje na mednarodni ravni in morate podatke in vpoglede ločevati na različne načine.

## <a name="next-step"></a>Naslednji korak

Če želite na začetni strani prikazati svoje vpoglede, morate najprej [dodati vire podatkov](data-sources.md) in [poenotiti](data-unification.md) podatke za oblikovanje profilov strank.
