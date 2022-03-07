---
title: Izvoz podatkov iz storitve Customer Insights v storitev Klaviyo
description: Preberite, kako konfigurirate povezavo in podatke izvozite v storitev Klaviyo.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 027aee70d9fdab0a92d7fd99209a6ac2ca3cc361
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225488"
---
# <a name="export-segment-lists-to-klaviyo-preview"></a>Izvoz seznamov segmentov v storitev Klaviyo (predogledna različica)

Segmente poenotenih profilov strank izvozite v storitev Klaviyo in jih uporabite za trženjske dejavnosti.

## <a name="prerequisites"></a>Zahteve

-   Imate [račun Klaviyo](https://www.klaviyo.com/) in ustrezne poverilnice skrbnika.
-   Imate [konfigurirane segmente](segments.md) pri vpogledih v občinstvo.
-   Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.

## <a name="known-limitations"></a>Znane omejitve

- V storitev Klaviyo lahko izvozite do 100.000 profilov strank na izvoz.
- Pri izvažanju v storitev Klaviyo ste omejeni na segmente.
- Izvoz do 1 milijon profilov strank v storitev Klaviyo lahko traja do 20 minut. 
- Število profilov strank, ki jih lahko izvozite v storitev Klaviyo, je odvisno in omejeno glede na vašo pogodbo s storitvijo Klaviyo.

## <a name="set-up-connection-to-klaviyo"></a>Vzpostavitev povezave s storitvijo Klaviyo

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Za konfiguriranje povezave izberite **Dodaj povezavo**, nato pa **Klaviyo**.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Podajte svoj [ključ za API Klaviyo](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys) za nadaljevanje prijave. 

1. Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.

1. Za inicializiranje povezave s storitvijo Klaviyo izberite možnost **Poveži**.

1. Izberite **Preverjanje pristnosti s storitvijo Klaviyo** in skrbniku zagotovite poverilnice za storitev Klaviyo.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave. Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Za ustvarjanje novega izvoza izberite **Dodaj cilj**.

1. V polju **Povezava za izvoz**, in sicer v razdelku Klaviyo, izberite povezavo. Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.

1. Vnesite svoj [**ID seznama za storitev Klaviyo**](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID).     

3. V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje, ki predstavlja e-poštni naslov stranke. Segmente morate izvoziti v storitev Klaviyo.

1. Izberite **Shrani**.

S shranjevanjem izvoza se ta ne zažene takoj.

Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab). Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

S tem ko dovolite, da storitev Dynamics 365 Customer Insights podatke prenese storitvi Klaviyo, omogočite prenos podatkov zunaj omejitve skladnosti za storitev Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo tovrstne podatke prenesel skladno z vašimi navodili, vendar ste vi odgovorni za to, da storitev Klaviyo izpolni morebitne obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).

Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.
