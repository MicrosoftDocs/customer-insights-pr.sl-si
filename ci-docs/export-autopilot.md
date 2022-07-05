---
title: Izvoz segmentov v Autopilot (predogledna različica)
description: Naučite se, kako konfigurirati povezavo in izvažati v storitev Autopilot.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e3af3d03e70c4ce9d229c84c582ec4f302be8c9f
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082543"
---
# <a name="export-segments-to-autopilot-preview"></a>Izvoz segmentov v Autopilot (predogledna različica)

Izvozite segmente poenotenih profilov strank v storitev Autopilot in jih uporabite za e-poštno trženje v storitvi Autopilot. 

## <a name="prerequisites-for-a-connection"></a>Predpogoji za povezavo

-   Imate [račun za storitev Autopilot](https://www.autopilothq.com/) in ustrezne skrbniške poverilnice.
-   Imaš [konfigurirani segmenti](segments.md) v Customer Insights.
-   Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.

## <a name="known-limitations"></a>Znane omejitve

- V storitev Autopilot lahko izvozite skupaj do 100.000 profilov strank.
- Izvoz v storitev Autopilot je omejen na segmente.
- Izvoz do 100.000 profilov strank v storitev Autopilot lahko traja do nekaj ur. 
- Število profilov strank, ki jih lahko izvozite v storitev Autopilot, je odvisno in omejeno glede na vašo pogodbo s storitvijo Autopilot.

## <a name="set-up-connection-to-autopilot"></a>Nastavitev povezave s storitvijo Autopilot

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajanje povezave** in izberite **Autopilot** za konfiguracijo povezave.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vpišite [ključ API-ja za storitev Autopilot](https://autopilot.docs.apiary.io/#).

1. Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.

1. Izberite možnost **Poveži**, da inicializirate povezavo s storitvijo Autopilot.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave. Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Za ustvarjanje novega izvoza izberite **Dodaj cilj**.

1. V polju **Povezava za izvoz** izberite povezavo v razdelku Autopilot. Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.

1. V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje, ki predstavlja e-poštni naslov stranke. Ponovite iste korake za druga neobvezna polja, kot so **ime**, **priimek**.

1. Izberite segmente, ki jih želite izvoziti. Močno **priporočamo, da v storitev Autopilot skupno ne izvozite več kot sto tisoč profilov strank**. 

1. Izberite **Shrani**.

S shranjevanjem izvoza se ta ne zažene takoj.

Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab). Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v storitev Autopilot, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Autopilot izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.


[!INCLUDE [footer-include](includes/footer-banner.md)]
