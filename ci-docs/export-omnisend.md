---
title: Izvoz podatkov Customer Insights v Omnisend
description: Naučite se, kako konfigurirati povezavo in izvažati v Omnisend.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 70bd94ea5e4060094c3d215e3fc263a98df51229
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643641"
---
# <a name="export-segments-to-omnisend-preview"></a>Izvoz segmentov v Omnisend (predogledna različica)

Izvozite segmente poenotenih profilov strank v Omnisend in jih uporabite za tržne dejavnosti.

## <a name="prerequisites"></a>Zahteve

-   Imate [račun za Omnisend](https://www.omnisend.com/) in pripadajoče skrbniške poverilnice.
-   Imaš [konfigurirani segmenti](segments.md) v Customer Insights.
-   Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.

## <a name="known-limitations"></a>Znane omejitve

- Izvozite lahko do 1 milijon profilov strank na izvoz v storitev Omnisend in to lahko traja do 4 ure.
- Izvoz v Omnisend je omejen na segmente.
- Število profilov strank, ki jih lahko izvozite v storitev Omnisend, je odvisno od vaše pogodbe s storitvijo Omnisend.

## <a name="set-up-connection-to-omnisend"></a>Nastavitev povezave s storitvijo Omnisend

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite možnost **Dodajanje povezave** in izberite **Omnisend** za konfiguracijo povezave.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Privzeto je storitev namenjena samo skrbnikom. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vpišite [ključ API-ja za storitev Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key).

1. Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.

1. Izberite **Poveži** za inicializiranje povezave s storitvijo Omnisend.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave. Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Za ustvarjanje novega izvoza izberite **Dodaj cilj**.

1. V polju **Povezava za izvoz** izberite povezavo v razdelku Omnisend. Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.

1. V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje, ki predstavlja e-poštni naslov stranke. To je obvezno za izvoz segmentov Omnisend. Izbirno lahko izvozite Ime, Priimek, Naslov, Država/regija, Zvezna država, Mesto in Poštna številka, da ustvarite bolj prilagojena e-poštna sporočila. Izberite **Dodaj atribut** za preslikavo teh polj.

1. Izberite **Shrani**.

S shranjevanjem izvoza se ta ne zažene takoj.

Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab). Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite, da Dynamics 365 Customer Insights prenese podatke v Omnisend, dovolite prenos podatkov zunaj meja zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno potencialno občutljivih podatkov, kot so osebni podatki. Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Omnisend izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti, ki jih morda imate. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).

Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.
