---
title: Izvoz podatkov Customer Insights v RollWorks
description: Naučite se, kako konfigurirati povezavo in izvažati v RollWorks.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d8ce4d867835dcb7cf56c6fffff4e25d1f5c109af0e401fc0eb8b3a7427c1de4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034610"
---
# <a name="export-segments-to-rollworks-preview"></a>Izvoz segmentov v RollWorks (predogledna različica)

Izvozite segmente poenotenih profilov strank v RollWorks in jih uporabite za oglaševanje. 

## <a name="prerequisites-for-a-connection"></a>Predpogoji za povezavo

-   Imate [račun za RollWorks](https://www.rollworks.com/) in pripadajoče skrbniške poverilnice.
-   Imate [konfigurirane segmente](segments.md) pri vpogledih v občinstvo.
-   Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.

## <a name="known-limitations"></a>Znane omejitve

- V RollWorks lahko izvozite do 250.000 profilov na izvoz.
- V RollWorks ne morete izvoziti segmentov z manj kot 100 profili. 
- Izvoz v RollWorks je omejen na segmente.
- Izvoz do 250.000 profilov v RollWorks lahko traja do 10 minut. 
- Število profilov, ki jih lahko izvozite v RollWorks, je odvisno in omejeno od vaše pogodbe za RollWorks.

## <a name="set-up-connection-to-rollworks"></a>Nastavitev povezave s storitvijo RollWorks

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajanje povezave** in izberite **RollWorks** za konfiguracijo povezave.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.

1. Izberite **Poveži** za inicializiranje povezave s storitvijo RollWorks.

1. Izberite **Preverjanje pristnosti s platformo RollWorks** in vnesite skrbniške poverilnice za RollWorks.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave. Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Za ustvarjanje novega izvoza izberite **Dodaj cilj**.

1. V polju **Povezava za izvoz** izberite povezavo v razdelku RollWorks. Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.

1. Vnesite svoj **ID oglaševalca platforme RollWorks** [Oglaševanje RollWorks](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

3. V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje v poenotenem profilu strank, ki predstavlja e-poštni naslov stranke. To je obvezno za izvoz segmentov RollWorks.

1. Izberite segmente, ki jih želite izvoziti. Izberite segment z vsaj 100 člani. Manjših segmentov ni mogoče izvoziti. Poleg tega je največja velikost segmenta za izvoz 250.000 članov na izvoz. 

1. Izberite **Shrani**.

S shranjevanjem izvoza se ta ne zažene takoj.

Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab). Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite, da Dynamics 365 Customer Insights prenese podatke v RollWorks, dovolite prenos podatkov zunaj meja zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno potencialno občutljivih podatkov, kot so osebni podatki. Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da RollWorks izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti, ki jih morda imate. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).

Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.
