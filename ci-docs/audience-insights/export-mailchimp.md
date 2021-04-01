---
title: Izvozite podatke Customer Insights v Mailchimp
description: Preberite o konfiguraciji povezave s storitvijo Mailchimp.
ms.date: 10/26/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f86616731c3cc3d26370727103ea9c5d4288c8d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598221"
---
# <a name="connector-for-mailchimp-preview"></a>Povezovalnik za Mailchimp (predogled)

Izvozite segmente poenotenih profilov strank v Mailchimp, da ustvarite glasila in e-poštne akcije.

## <a name="prerequisites"></a>Zahteve

-   Imate [račun za Mailchimp](https://mailchimp.com/) in ustrezne skrbniške poverilnice.
-   V storitvi Mailchimp so na voljo obstoječa občinstva in ustrezni ID-ji. Če želite več informacij, glejte razdelek [Občinstva Mailchimp](https://mailchimp.com/help/create-audience/).
-   Imate [konfigurirane segmente](segments.md)
-   Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.

## <a name="connect-to-mailchimp"></a>Vzpostavitev povezave s storitvijo Mailchimp

1. Izberite **Skrbnik** > **Cilji za izvoz**.

1. Pod razdelkom **Mailchimp** izberite **Nastavi**.

1. Dajte svojemu cilju izvoza prepoznavno ime v polju **Prikazno ime**.

1. Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.

1. Vnesite **[ID občinstva za Mailchimp](https://mailchimp.com/help/find-audience-id/)** in izberite **Poveži**, da inicializirate povezavo s storitvijo Mailchimp.

1. Izberite **Preverjanje pristnosti s storitvijo Mailchimp** in vnesite svoje poverilnice za Mailchimp.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Posnetek zaslona izvoza za povezavo Mailchimp":::

1. Izberite **Naslednji** za nastavitev izvoza.

## <a name="configure-the-connector"></a>Konfiguracija povezovalnika

1. V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje v poenotenem profilu strank, ki predstavlja e-poštni naslov stranke. 

1. Po želji lahko izvozite **ime** in **priimek** kot dodatna polja za ustvarjanje bolj prilagojenih e-poštnih sporočil. Izberite **Dodaj atribut** za preslikavo teh polj.

1. Izberite segmente, ki jih želite izvoziti. V Mailchimp lahko izvozite do 1 milijon profilov strank.

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Izberite polja in segmente, ki jih želite izvoziti v Mailchimp":::

1. Izberite **Shrani**.

## <a name="export-the-data"></a>Izvoz podatkov

Lahko [izvozite podatke na zahtevo](export-destinations.md). Izvoz se bo zagnal tudi z vsakim [načrtovanim osveževanjem](system.md#schedule-tab). V storitvi Mailchimp lahko zdaj najdete svoje segmente pod možnostjo [Občinstva Mailchimp](https://mailchimp.com/help/create-audience/).

## <a name="known-limitations"></a>Znane omejitve

- Do 1 milijon profilov na izvoz v Mailchimp.
- Izvoz v Mailchimp je omejen na segmente.
- Izvoz segmentov s skupno 1 milijonom profilov lahko traja do tri ure zaradi omejitev na strani ponudnika. 
- Število profilov, ki jih lahko izvozite v Mailchimp, je odvisno in omejeno glede na vašo pogodbo s podjetjem Mailchimp.

## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v Mailchimp, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Mailchimp izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.


[!INCLUDE[footer-include](../includes/footer-banner.md)]