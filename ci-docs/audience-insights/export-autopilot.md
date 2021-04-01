---
title: Izvoz podatkov iz Customer Insights v storitev Autopilot
description: Preberite o konfiguraciji povezave s storitvijo Autopilot.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d039c4afd84eaad942d214d4e6fb8ef7b1ec72a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596151"
---
# <a name="connector-for-autopilot-preview"></a>Povezovalnik za Autopilot (predogled)

Izvozite segmente poenotenih profilov strank v storitev Autopilot in jih uporabite za e-poštno trženje v storitvi Autopilot. 

## <a name="prerequisites"></a>Zahteve

-   Imate [račun za storitev Autopilot](https://www.autopilothq.com/) in ustrezne skrbniške poverilnice.
-   Imate [konfigurirane segmente](segments.md) pri vpogledih v občinstvo.
-   Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.

## <a name="connect-to-autopilot"></a>Vzpostavljanje povezave s storitvijo Autopilot

1. Izberite **Skrbnik** > **Cilji za izvoz**.

1. Pod razdelkom **Autopilot** izberite možnost **Nastavi**.

1. Dajte svojemu cilju izvoza prepoznavno ime v polju **Prikazno ime**.

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Konfiguracijsko podokno za povezavo s storitvijo Autopilot.":::

1. Vnesite **ključ za API storitve Autopilot** [Ključ za API storitve Autopilot](https://autopilot.docs.apiary.io/#).

1. Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.

1. Izberite možnost **Poveži**, da inicializirate povezavo s storitvijo Autopilot.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite **Naslednji** za nastavitev izvoza.

## <a name="configure-the-connector"></a>Konfiguracija povezovalnika

1. V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje v poenotenem profilu strank, ki predstavlja e-poštni naslov stranke. Ponovite iste korake za druga neobvezna polja, kot so **ime**, **priimek**.

1. Izberite segmente, ki jih želite izvoziti. Močno **priporočamo, da v storitev Autopilot skupno ne izvozite več kot sto tisoč profilov strank**. 

1. Izberite **Shrani**.

## <a name="export-the-data"></a>Izvoz podatkov

Lahko [izvozite podatke na zahtevo](export-destinations.md). Izvoz se bo zagnal tudi z vsakim [načrtovanim osveževanjem](system.md#schedule-tab).

## <a name="known-limitations"></a>Znane omejitve

- V storitev Autopilot lahko izvozite do sto tisoč profilov.
- Izvoz v storitev Autopilot je omejen na segmente.
- Izvoz do sto tisoč profilov v storitev Autopilot lahko traja do nekaj ur. 
- Število profilov, ki jih lahko izvozite v storitev Autopilot, je odvisno in omejeno glede na vašo pogodbo za Autopilot.

## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v storitev Autopilot, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Autopilot izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.


[!INCLUDE[footer-include](../includes/footer-banner.md)]