---
title: Izvozite podatke Customer Insights v Marketo
description: Preberite o konfiguraciji povezave s storitvijo Marketo.
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 74d19a0448123904210c26f7b8760d00296c9cfd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597991"
---
# <a name="connector-for-marketo-preview"></a>Povezovalnik za Marketo (predogled)

Izvozite segmente poenotenih profilov strank, da akcije, zagotovite e-poštno trženje in uporabite določene skupine strank s storitvijo Marketo.

## <a name="prerequisites"></a>Zahteve

-   Imate [račun za Marketo](https://login.marketo.com/) in ustrezne skrbniške poverilnice.
-   V storitvi Marketo so na voljo obstoječi seznami in ustrezni ID-ji. Več informacij je na voljo na [seznamih Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Imate [konfigurirane segmente](segments.md).
-   Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.

## <a name="connect-to-marketo"></a>Povezava s storitvijo Marketo

1. Izberite **Skrbnik** > **Cilji za izvoz**.

1. Pod razdelkom **Marketo** izberite **Nastavi**.

1. Dajte svojemu cilju izvoza prepoznavno ime v polju **Prikazno ime**.

1. Vnesite svoj **[ID odjemalca Marketo, skrivnost odjemalca in ime gostitelja končne točke REST](https://developers.marketo.com/rest-api/authentication/)**.

1. Vnesite svoj **[ID seznama Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** 

1. Izberite **Strinjam se** za potrditev možnosti **Zasebnost podatkov in skladnost** in izberite možnost **Poveži**, da inicializirate povezavo s storitvijo Marketo.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Posnetek zaslona izvoza za povezavo Marketo":::

1. Izberite **Naslednji** za nastavitev izvoza.

## <a name="configure-the-connector"></a>Konfiguracija povezovalnika

1. V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje v poenotenem profilu strank, ki predstavlja e-poštni naslov stranke. 

1. Po želji lahko izvozite **ime**, **priimek**, **mesto**, **zvezna država** in **država/regija** kot dodatna polja za ustvarjanje bolj prilagojenih e-poštnih sporočil. Izberite **Dodaj atribut** za preslikavo teh polj.

1. Izberite segmente, ki jih želite izvoziti. V Marketo lahko izvozite do 1 milijon profilov strank.

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Izberite polja in segmente, ki jih želite izvoziti v Marketo":::

1. Izberite **Shrani**.

## <a name="export-the-data"></a>Izvoz podatkov

Lahko [izvozite podatke na zahtevo](export-destinations.md). Izvoz se bo zagnal tudi z vsakim [načrtovanim osveževanjem](system.md#schedule-tab). V storitvi Marketo lahko zdaj najdete svoje segmente pod možnostjo [Občinstva Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

## <a name="known-limitations"></a>Znane omejitve

- Do 1 milijon profilov na izvoz v Marketo.
- Izvoz v Marketo je omejen na segmente.
- Izvoz segmentov s skupno 1 milijonom profilov lahko traja do 3 ure. 
- Število profilov, ki jih lahko izvozite v Marketo, je odvisno in omejeno glede na vašo pogodbo s podjetjem Marketo.

## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v Marketo, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Marketo izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.


[!INCLUDE[footer-include](../includes/footer-banner.md)]