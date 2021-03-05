---
title: Izvoz podatkov iz Customer Insights v storitev SendGrid
description: Preberite o konfiguraciji povezave s storitvijo SendGrid.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f16d69deb2a0b48270ed04f9b72f03056f20b619
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268752"
---
# <a name="connector-for-sendgrid-preview"></a>Povezovalnik za SendGrid (predogled)

Izvozite segmente poenotenih profilov strank v seznam strank storitve SendGrid in jih uporabite za akcije ter e-poštno trženje v storitvi SendGrid. 

## <a name="prerequisites"></a>Zahteve

-   Imate [račun za SendGrid](https://sendgrid.com/) in ustrezne skrbniške poverilnice.
-   V storitvi SendGrid so na voljo obstoječi seznami stikov in ustrezni ID-ji. Za več informacij glejte razdelek [SendGrid - upravljanje stikov](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Imate [konfigurirane segmente](segments.md) pri vpogledih v občinstvo.
-   Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.

## <a name="connect-to-sendgrid"></a>Vzpostavljanje povezave s storitvijo SendGrid

1. Izberite **Skrbnik** > **Cilji za izvoz**.

1. Pod razdelkom **SendGrid** izberite možnost **Nastavi**.

1. Dajte svojemu cilju izvoza prepoznavno ime v polju **Prikazno ime**.

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Podokno za konfiguracijo izvoza v storitvi SendGrid.":::

1. Vpiši **ključ za API storitve SendGrid** [Ključ za API storitve SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Vnesite **[ID seznama SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.

1. Izberite možnost **Poveži**, da inicializirate povezavo s storitvijo SendGrid.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite **Naslednji** za nastavitev izvoza.

## <a name="configure-the-connector"></a>Konfiguracija povezovalnika

1. V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje v poenotenem profilu strank, ki predstavlja e-poštni naslov stranke. Ponovite te korake še za druga neobvezna polja, kot so **ime**, **priimek**, **država/regija**, **zvezna država**, **mesto** in **poštna številka**.

1. Izberite segmente, ki jih želite izvoziti. Močno **priporočamo, da v storitev SendGrid skupno ne izvozite več kot sto tisoč profilov strank**. 

1. Izberite **Shrani**.

## <a name="export-the-data"></a>Izvoz podatkov

Lahko [izvozite podatke na zahtevo](export-destinations.md). Izvoz se bo zagnal tudi z vsakim [načrtovanim osveževanjem](system.md#schedule-tab).

## <a name="known-limitations"></a>Znane omejitve

- Do sto tisoč profilov v storitvi SendGrid
- Izvoz v storitev SendGrid je omejen na segmente.
- Izvoz do sto tisoč profilov v storitev SendGrid lahko traja do nekaj ur. 
- Število profilov, ki jih lahko izvozite v storitev SendGrid, je odvisno in omejeno glede na vašo pogodbo s podjetjem SendGrid.

## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko storitvi Dynamics 365 Customer Insights omogočite prenos podatkov v storitev SendGrid, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da SendGrid izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.


[!INCLUDE[footer-include](../includes/footer-banner.md)]