---
title: Izvozite podatke Customer Insights v Mailchimp
description: Naučite se, kako konfigurirati povezavo in izvažati v Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a6bdf43bb40345b868bf2e7d2c91de169c8ba841ba77f732f455f4c4d496a7f5
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033559"
---
# <a name="export-segments-to-mailchimp-preview"></a>Izvoz segmentov v Mailchimp (predogledna različica)

Izvozite segmente poenotenih profilov strank v Mailchimp, da ustvarite glasila in e-poštne akcije.

## <a name="prerequisites-for-connection"></a>Predpogoji za povezavo

-   Imate [račun za Mailchimp](https://mailchimp.com/) in ustrezne skrbniške poverilnice.
-   V storitvi Mailchimp so na voljo obstoječa občinstva in ustrezni ID-ji. Če želite več informacij, glejte razdelek [Občinstva Mailchimp](https://mailchimp.com/help/create-audience/).
-   Imate [konfigurirane segmente](segments.md)
-   Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.

## <a name="known-limitations"></a>Znane omejitve

- Do 1 milijon profilov na izvoz v Mailchimp.
- Izvoz v Mailchimp je omejen na segmente.
- Izvoz segmentov z 1 milijonom profilov lahko traja do tri ure. 
- Število profilov, ki jih lahko izvozite v Mailchimp, je odvisno in omejeno glede na vašo pogodbo s podjetjem Mailchimp.

## <a name="set-up-connection-to-mailchimp"></a>Nastavitev povezave s storitvijo Mailchimp

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Za konfiguriranje povezave izberite možnost **Dodaj povezavo**, nato pa **Mailchimp**.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.

1. Izberite **Poveži** za inicializiranje povezave z Mailchimp.

1. Izberite **Preverjanje pristnosti s storitvijo Mailchimp** in vnesite svoje poverilnice za Mailchimp.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite možnost **Shrani**, da dokončate povezavo. 

## <a name="configure-the-connector"></a>Konfiguracija povezovalnika

Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave. Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Pomaknite se na možnost **Podatki** > **Izvozi**.

1. Za ustvarjanje novega izvoza izberite **Dodaj cilj**.

1. V polju **Povezava za izvoz** izberite povezavo v razdelku Mailchimp. Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.

1. Vnesite svoj **[ID občinstva storitve Mailchimp](https://mailchimp.com/help/find-audience-id/)**

3. V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje v poenotenem profilu strank, ki predstavlja e-poštni naslov stranke. 

1. Izbirno lahko izvozite **Ime** in **Priimek**, da ustvarite bolj prilagojena e-poštna sporočila. Izberite **Dodaj atribut** za preslikavo teh polj.

1. Izberite segmente, ki jih želite izvoziti. V Mailchimp lahko izvozite do 1 milijon profilov strank.

1. Izberite **Shrani**.

S shranjevanjem izvoza se ta ne zažene takoj.

Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab). Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v Mailchimp, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Mailchimp izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
