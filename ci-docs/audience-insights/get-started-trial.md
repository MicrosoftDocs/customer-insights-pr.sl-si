---
title: Ustvarite in konfigurirajte preskus storitve Customer Insights
description: Koraki za pridobitev preskusne naročnine za storitev Dynamics 365 Customer Insights in njeno konfiguracijo.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 3a235e924395a606b9332de3d205289288a597a9
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558844"
---
# <a name="set-up-a-trial-environment"></a>Nastavitev preskusnega okolja 

Preskus storitve Dynamics 365 Customer Insights vam omogoča, da pregledate glavne zmogljivosti in izveste več o različnih funkcijah. Preskusna naročnina se po poteku izbriše. Preskusna okolja ustvarijo posamezni uporabniki, ki postanejo skrbniki svojega preskusnega okolja. Na preskus lahko povabijo več uporabnikov in konfigurirajo različne funkcije.

## <a name="create-a-trial-environment"></a>Ustvarite preskusno okolje

Za preskusno različico se lahko prijavite na [stran za prijavo za preskusno različico](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

1. Izberite možnost **Prijava za brezplačno preskusno različico** in izberite **Prijavi se zdaj**.

1. Navedite službeni ali šolski e-poštni naslov, nam povejte več o sebi in izberite **Začetek**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Pogovorno okno za prijavo za preskusni primerek":::

1. Preglejte pogoje in določila ter jih potrdite s klikom na **Nadaljuj**.

1. Določite **ime** za novo okolje. 

1. **Vrsta** okolja naj bo nastavljena na **Preskus**.

1. V polje **Izberi predstavitev panoge** lahko po želji izberete nabor podatkov, specifičnih za panogo. Lahko pa kasneje [preklopite v predstavitev panoge](#use-industry-specific-demo-data-sets-in-audience-insights) in začnete s privzetim nabor podatkov.

1. Izberite **regijo** za svoje okolje.

1. Če ste skrbnik organizacije Dynamics 365, lahko po želji izberete **Napredne nastavitve** in navedete URL svoje organizacije za uporabo funkcij predvidevanja, kot je predvidevanje izgube strank. 

1. izberite **Ustvari**. 

Za dokončanje nastavitve boste potrebovali le par minut. Po zaključku boste preusmerjeni v predstavitveno okolje ali predstavitev panoge, ki ste jih izbrali v zgornjem koraku. Zdaj lahko raziskujete aplikacijo s predstavitvenimi podatki samo za branje. Če želite v okolje dodati svoje podatke, glejte [Ustvarite predstavitvene podatke, specifične za scenarij, v svojem okolju](#create-scenario-specific-demo-data-in-your-own-environment).

:::image type="content" source="media/trial-environment.png" alt-text="Posnetek zaslona novo ustvarjenega preskusnega okolja.":::

## <a name="use-industry-specific-demo-data-sets-in-audience-insights"></a>V vpogledih občinstva uporabite nabore predstavitvenih podatkov, specifičnih za panogo

Povezovanje resničnih virov podatkov je eden od ključnih korakov pri uporabi moči storitve Customer Insights. Če želite preizkusiti funkcije, ne da bi posegali v lastne podatke, lahko po želji uporabite predstavitvene podatke za posamezno panogo. Na voljo je nekaj predstavitvenih naborov podatkov za naslednje panoge: 

-   Avtomobilska industrija
-   Bančništvo
-   Potrošno blago
-   Javna uprava
-   Zdravstvo
-   Turizem
-   Zavarovanje
-   Proizvodnja
-   Strokovne storitve
-   Maloprodaja

### <a name="see-industry-specific-demo-data-in-trials"></a>V preskusih si oglejte predstavitvene podatke za panogo

Za različico programa Customer Insights samo za branje, prilagojeno določeni panogi ali scenariju, začnite v predstavitvenem okolju. 
 
1.  V izbirniku okolja vpogledov občinstva izberite okolje **Predstavitev**.

2.  V spustnem meniju strani **Domača stran** izberite možnost »Izberi predstavitev panoge«.

:::image type="content" source="media/trial-select-industry-demo.png" alt-text="Izberite panogo za preskusno okolje.":::

### <a name="create-scenario-specific-demo-data-in-your-own-environment"></a>V svojem okolju ustvarite predstavitvene podatke, specifične za scenarij

Kot skrbnik v glavi aplikacije izberite izbirnik okolja, da ustvarite novo okolje. V novem okolju lahko konfigurirate lastne vire podatkov in nastavite aplikacijo glede na svoje zahteve. 

1.  Pri vpogledih v občinstvo izberite **Podatki** > **Viri podatkov**.

2.  Če želite uvoziti svoje vire podatkov, pojdite na [priročnik o uvozu podatkov](data-sources.md).     
   Če raje delate z vzorčnimi podatki, ki vam omogočajo preizkus uvoza podatkov, lahko v svoje okolje uvozite predstavitvene podatke panoge. Izberite možnost **Uvoz iz Datahub** in sledite spodnjim korakom.

3.  Izberite kartico panoge, ki ustreza vašemu scenariju. 

4.  Preglejte in po želji posodobite predlagano ime vira podatkov. 

5.  Izberite **Naprej** za uvoz vzorčnih podatkov. 

Zdaj lahko z uvoženimi podatki prilagodite Customer Insights za svoj scenarij. Če si želite ogledati okolje, specifično za uvožene predstavitvene podatke, v izbirniku okolja izberite možnost **<Industry> Predstavitev**.

## <a name="limitations-in-trials"></a>Omejitve preskusov

- Preskusi so privzeto aktivni 30 dni. Lahko pa jih podaljšate po 23. dnevu, ko se prijavite v preskus.
- Za shranjevanje izhodnih podatkov med preskusom ne morete uporabiti svojega lastnega računa za shrambo Azure Data Lake. Lahko pa uvozite podatke iz računa za shrambo Data Lake.
- V okolje Dataverse lahko shranite do 3 GB podatkov, ki so samodejno omogočeni, ko začnete s preskusno različico za storitev Customer Insights.

## <a name="copy-data-from-a-trial-to-a-paid-subscription"></a>Kopiranje podatkov iz preskusne različice v plačljivo naročnino

Na splošno priporočamo, da pri nadgradnji na plačljivo različico Customer Insights začnete na novo z lastnimi podatki. 

Po želji lahko svoje podatke kopirate iz preskusnega okolja, če kupite Customer Insights. Če želite preseliti nastavitve iz preskusnega v plačljivo okolje, morate biti skrbnik preskusne različice Customer Insights in globalni skrbnik najemnika Microsoft 365 ali skrbnik Dynamics 365 v svoji organizaciji. 

Ko se prvič prijavite v plačljivi primerek storitve Customer Insights, boste morali ustvariti novo okolje. V tem postopku lahko izberete kopiranje konfiguracije iz obstoječega okolja in preselite večino nastavitev. Če imate zgoraj navedena dovoljenja, bo na tem seznamu prikazano preskusno okolje. Za več informacij glejte [Kopirajte konfiguracijo okolja](manage-environments.md#copy-the-environment-configuration).

## <a name="next-steps"></a>Naslednji koraki

Oglejte si naslednje članke, ki vam bodo pomagali začeti s konfiguracijo Customer Insights. 

- [Dodajte več uporabnikov in dodelite dovoljenja](permissions.md).
- [Uvozite svoje vire podatkov](data-sources.md) in jih vodite skozi [postopek poenotenja podatkov](data-unification.md), da nastanejo [enotni profili strank](customer-profiles.md).
- [Obogatite poenotene profile strank](enrichment-hub.md) ali [zaženite modele predvidevanja](predictions-overview.md).
- S [segmenti](segments.md) lahko združujete stranke, z [ukrepi](measures.md) pa pregledate KPI-je.
- Nastavite [povezave](connections.md) in [izvoz](export-destinations.md) za obdelavo podmnožic vaših podatkov v drugih aplikacijah.
