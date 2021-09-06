---
title: Izvozite podatke Customer Insights v DotDigital
description: Naučite se, kako konfigurirati povezavo in izvažati v DotDigital.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f09be0dfa599c1ef7cf0055b7ce1df8784cf447ada64b56bc7543c214f9a5b99
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034656"
---
# <a name="export-segments-to-dotdigital-preview"></a>Izvoz segmentov v DotDigital (predogledna različica)

Izvozite segmente poenotenih profilov strank v adresarje DotDigital ter jih uporabite za akcije, e-poštno trženje ter sestavljanje segmentov strank s storitvijo DotDigital. 

## <a name="prerequisites-for-a-connection"></a>Predpogoji za povezavo

-   Imate [račun za DotDigital](https://dotdigital.com/) in ustrezne skrbniške poverilnice.
-   V storitvi DotDigital so na voljo obstoječi adresarji in ustrezni ID-ji. ID lahko najdete v URL-ju, ko izberete in odprete adresar. Za več informacij glejte [Adresarji DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Imate [konfigurirane segmente](segments.md) pri vpogledih v občinstvo.
-   Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.

## <a name="known-limitations"></a>Znane omejitve

- Do 1 milijon profilov na izvoz v DotDigital.
- Izvoz v DotDigital je omejen na segmente.
- Izvoz segmentov s skupno 1 milijonom profilov lahko traja do 3 ure zaradi omejitev na strani ponudnika. 
- Število profilov, ki jih lahko izvozite v DotDigital, je odvisno in omejeno glede na vašo pogodbo s podjetjem DotDigital.

## <a name="set-up-connection-to-dotdigital"></a>Nastavitev povezave s storitvijo DotDigital

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajanje povezave** in izberite **DotDigital** za konfiguracijo povezave.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vnesite **uporabniško ime in geslo za DotDigital**.

1. Vpišite svoj **[ID za adresar DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.

1. Izberite **Poveži**, da inicializirate povezavo s storitvijo DotDigital.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite možnost **Shrani**, da dokončate povezavo. 

## <a name="configure-an-export"></a>Konfiguriranje izvoza

Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave. Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Za ustvarjanje novega izvoza izberite **Dodaj cilj**.

1. V polju **Povezava za izvoz** izberite povezavo v razdelku DotDigital. Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.


1. V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje v poenotenem profilu strank, ki predstavlja e-poštni naslov stranke. Ponovite iste korake za druga neobvezna polja, kot so **Ime**, **Priimek**, **Polno ime**, **Spol** in **Poštna številka**.

1. Izberite segmente, ki jih želite izvoziti. V DotDigital lahko izvozite do 1 milijon profilov strank.

1. Izberite **Shrani**.

S shranjevanjem izvoza se ta ne zažene takoj.

Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab). Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand). 
 
V storitvi DotDigital lahko zdaj najdete svoje segmente v [adresarjih DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).


## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v DotDigital, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da DotDigital izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
