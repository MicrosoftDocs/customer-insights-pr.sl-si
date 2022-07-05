---
title: Izvoz segmentov v SendGrid (predogledna različica)
description: Naučite se, kako konfigurirati povezavo in izvažati v SendGrid.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 669f0fb48b095f6a9faeebf257ee9df3d1c580c7
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9083047"
---
# <a name="export-segments-to-sendgrid-preview"></a>Izvoz segmentov v SendGrid (predogledna različica)

Izvozite segmente poenotenih profilov strank v seznam strank storitve SendGrid in jih uporabite za akcije ter e-poštno trženje v storitvi SendGrid. 

## <a name="prerequisites-for-a-connection"></a>Predpogoji za povezavo

-   Imate [račun za SendGrid](https://sendgrid.com/) in ustrezne skrbniške poverilnice.
-   V storitvi SendGrid so na voljo obstoječi seznami stikov in ustrezni ID-ji. Za več informacij glejte razdelek [SendGrid - upravljanje stikov](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Imaš [konfigurirani segmenti](segments.md) v Customer Insights.
-   Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.

## <a name="known-limitations"></a>Znane omejitve

- Skupno do 100.000 profilov strank v storitev SendGrid.
- Izvoz v storitev SendGrid je omejen na segmente.
- Izvoz do 100.000 profilov strank v storitev SendGrid lahko traja do nekaj ur. 
- Število profilov strank, ki jih lahko izvozite v storitev SendGrid, je odvisno in omejeno glede na vašo pogodbo s storitvijo SendGrid.

## <a name="set-up-connection-to-sendgrid"></a>Nastavitev povezave s storitvijo SendGrid

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajanje povezave** in izberite **SendGrid** za konfiguracijo povezave.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vpiši **ključ za API storitve SendGrid** [Ključ za API storitve SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Izberite potrditveno polje **Strinjam se**, da potrdite **Zasebnost in skladnost podatkov**.

1. Izberite možnost **Poveži**, da inicializirate povezavo s storitvijo SendGrid.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave. Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Za ustvarjanje novega izvoza izberite **Dodaj cilj**.

1. V polju **Povezava za izvoz** izberite povezavo v razdelku SendGrid. Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.

1. Vnesite **[ID seznama SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje, ki predstavlja e-poštni naslov stranke. Ponovite te korake še za druga neobvezna polja, kot so **ime**, **priimek**, **država/regija**, **zvezna država**, **mesto** in **poštna številka**.

1. Izberite segmente, ki jih želite izvoziti. Močno **priporočamo, da v storitev SendGrid skupno ne izvozite več kot sto tisoč profilov strank**. 

1. Izberite **Shrani**.

S shranjevanjem izvoza se ta ne zažene takoj.

Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab). Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko storitvi Dynamics 365 Customer Insights omogočite prenos podatkov v storitev SendGrid, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da SendGrid izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš skrbnik za Dynamics 365 Customer Insights lahko kadar koli odstrani ta cilj izvoza in s tem prekine uporabljati to funkcijo.


[!INCLUDE [footer-include](includes/footer-banner.md)]
