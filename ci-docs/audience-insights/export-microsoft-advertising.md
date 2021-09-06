---
title: Izvoz podatkov Customer Insights v Microsoft Advertising
description: Naučite se, kako konfigurirati povezavo in izvažati v storitev Microsoft Advertising.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8f8a4cbb9590f9c5311789154319283530e0a10343cccbe9c7aec99765b4fbf2
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031492"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Izvoz segmentov v Microsoft Advertising (predogledna različica)

Izvozite segmente Customer Insights v Microsoft Advertising, da ustvarite ciljne skupine za storitev Customer Match. Uporabite te ciljne skupine za svoje oglaševalske akcije.

## <a name="prerequisites"></a>Zahteve

-   Imate [račun za Microsoft Advertising](https://ads.microsoft.com/) in pripadajoče skrbniške poverilnice.
-   Sprejeli ste pogoje uporabe storitve Customer Match. 
-   [Konfigurirani segmenti](segments.md) v vpogledih za občinstvo.
-   Poenoteni profili strank v izvoženih segmentih vsebujejo polje z e-poštnim naslovom.

## <a name="known-limitations"></a>Znane omejitve

- V Microsoft Advertising lahko izvozite do 500.000 profilov na izvoz.
- Izvoz v Microsoft Advertising je omejen na segmente.
- Izvoz do 500.000 profilov v Microsoft Advertising lahko traja do 10 minut. 


## <a name="set-up-the-connection-to-microsoft-advertising"></a>Nastavitev povezave s storitvijo Microsoft Advertising

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajanje povezave** in izberite **Microsoft Advertising** za konfiguracijo povezave.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Privzeto so nastavljeni skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.

1. Izberite **Poveži** za inicializiranje povezave s storitvijo Microsoft Advertising.

1. Izberite **Preverjanje pristnosti s storitvijo Microsoft Advertising** in vnesite skrbniške poverilnice za Microsoft Advertising.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave. Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Za ustvarjanje novega izvoza izberite **Dodaj cilj**.

1. V polju **Povezava za izvoz** izberite povezavo v razdelku Microsoft Advertising. Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.

1. Izberite segmente, ki jih želite izvoziti. Ciljne skupine storitve Customer Match v programu Microsoft Advertising se samodejno ustvarijo z imeni segmentov, ki so izbrani za izvoz. Vsak segment bo prikazal ločeno ciljno skupino za storitev Customer Match. 

1. Vpišite **ID stranke Microsoft Advertising in ID računa**. ID stranke (`cid`) in ID računa (`aid`) lahko najdete v parametrih URL-ja, ko ste prijavljeni v Microsoft Advertising.

1. V razdelku **Ujemanje podatkov** v polju **E-pošta** izberite polje v svojem poenotenem profilu stranke, ki ima e-poštni naslov stranke. To je obvezno za izvoz segmentov Microsoft Advertising.

1. Izberite **Shrani**.

S shranjevanjem izvoza se ta ne zažene takoj.

Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab). Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite, da Dynamics 365 Customer Insights prenese podatke v Microsoft Advertising, dovolite prenos podatkov zunaj meja zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno potencialno občutljivih podatkov, kot so osebni podatki. Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Microsoft Advertising izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti, ki jih morda imate. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).

Vaš skrbnik Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza, da prenehate uporabljati to funkcijo.
