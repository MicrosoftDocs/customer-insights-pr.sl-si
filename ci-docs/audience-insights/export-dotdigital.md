---
title: Izvozite podatke Customer Insights v DotDigital
description: Preberite o konfiguraciji povezave s storitvijo DotDigital.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed6bd40e8575fc90258f79f60abffe54f136d274
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644468"
---
# <a name="connector-for-dotdigital-preview"></a>Povezovalnik za DotDigital (predogled)

Izvozite segmente poenotenih profilov strank v adresarje DotDigital ter jih uporabite za akcije, e-poštno trženje ter sestavljanje segmentov strank s storitvijo DotDigital. 

## <a name="prerequisites"></a>Zahteve

-   Imate [račun za DotDigital](https://dotdigital.com/) in ustrezne skrbniške poverilnice.
-   V storitvi DotDigital so na voljo obstoječi adresarji in ustrezni ID-ji. ID lahko najdete v URL-ju, ko izberete in odprete adresar. Za več informacij glejte [Adresarji DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Imate [konfigurirane segmente](segments.md) pri vpogledih v občinstvo.
-   Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.

## <a name="connect-to-dotdigital"></a>Povezovanje s storitvijo DotDigital

1. Izberite **Skrbnik** > **Cilji za izvoz**.

1. Pod razdelkom **DotDigital** izberite **Nastavi**.

1. Dajte svojemu cilju izvoza prepoznavno ime v polju **Prikazno ime**.

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Podokno konfiguracije za izvoz DotDigital.":::

1. Vnesite **uporabniško ime in geslo za DotDigital**.

1. Vpišite svoj **[ID za adresar DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.

1. Izberite **Poveži**, da inicializirate povezavo s storitvijo DotDigital.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite **Naslednji** za nastavitev izvoza.

## <a name="configure-the-connector"></a>Konfiguracija povezovalnika

1. V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje v poenotenem profilu strank, ki predstavlja e-poštni naslov stranke. Ponovite iste korake za druga neobvezna polja, kot so **Ime**, **Priimek**, **Polno ime**, **Spol** in **Poštna številka**.

1. Izberite segmente, ki jih želite izvoziti. V DotDigital lahko izvozite do 1 milijon profilov strank.

1. Izberite **Shrani**.

## <a name="export-the-data"></a>Izvoz podatkov

Lahko [izvozite podatke na zahtevo](export-destinations.md). Izvoz se bo zagnal tudi z vsakim [načrtovanim osveževanjem](system.md#schedule-tab). V storitvi DotDigital lahko zdaj najdete svoje segmente v [adresarjih DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

## <a name="known-limitations"></a>Znane omejitve

- Do 1 milijon profilov na izvoz v DotDigital.
- Izvoz v DotDigital je omejen na segmente.
- Izvoz segmentov s skupno 1 milijonom profilov lahko traja do 3 ure zaradi omejitev na strani ponudnika. 
- Število profilov, ki jih lahko izvozite v DotDigital, je odvisno in omejeno glede na vašo pogodbo s podjetjem DotDigital.

## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v DotDigital, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da DotDigital izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.
