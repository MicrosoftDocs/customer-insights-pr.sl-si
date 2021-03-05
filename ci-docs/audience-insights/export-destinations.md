---
title: Cilji za izvoz
description: Izvozite podatke in upravljajte cilje za izvoz.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 63caa2ebdd7d637d14ac9c9cc7972095803aee2f
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477153"
---
# <a name="export-destinations-preview-overview"></a>Pregled ciljev za izvoz (predogled)

Stran **Cilji za izvoz** prikazuje vsa mesta, ki ste jih nastavili za izvoz podatkov. Dodate lahko tudi nove cilje za izvoz. Poleg tega prikazuje trenutno razpoložljive možnosti za izvoz. Pridobite hiter pregled, opis in informacije o tem, kaj lahko storite z vsako možnostjo razširljivosti. Izvozite poenotene profile, mere in segmente v podprte aplikacije, relevantne za vaše poslovanje.

Odprite **Skrbnik** > **Cilji za izvoz**, da poiščete naslednje možnosti razširljivosti:

- [Dodatek za kartico stranke v Dynamics 365 Customer Insights](customer-card-add-in.md)
- [Povezovalnik upravitelja oglasov kanala Facebook](export-facebook.md)
- [Povezovalnik Power Automate](export-power-automate.md)
- [Povezovalnik Power Apps](export-power-apps.md)
- [Povezovalnik Power BI](export-power-bi.md)
- [Autopilot](export-autopilot.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Shramba zbirke dvojiških podatkov Azure](export-azure-blob-storage.md)
- [Azure Data Lake Storage Gen2](export-azure-data-lake-storage-gen2.md)
- [SendGrid](export-sendgrid.md)
- [Povezovalnik LiveRamp &reg;](export-liveramp.md)
- [Bot za Microsoft Teams](export-teams-bot.md)
- [MailChimp](export-mailchimp.md)
- [API za Customer Insights](apis.md)

## <a name="add-a-new-export-destination"></a>Dodajanje novega cilja za izvoz

Če želite dodati cilje za izvoz, morate imeti [skrbniška dovoljenja](permissions.md). Če izvažate v Microsoftove storitve, domnevamo, da so vse storitve v isti organizaciji.

1. Izberite **Skrbnik** > **Cilji za izvoz**.

1. Preklopite na zavihek **Moji cilji za izvoz**.

1. Izberite **Dodaj cilj**, da ustvarite nov cilj za izvoz.

1. V podoknu **Dodaj cilj** v spustnem seznamu izberite možnost za **Vrsta** za cilj za izvoz.

1. Zagotovite zahtevane podrobnosti in izberite **Naprej**, da ustvarite cilj za izvoz.

Izberete lahko tudi **Nastavitev** na ploščici na zavihku **Odkrivanje**.

## <a name="view-export-destinations"></a>Pogled ciljev za izvoz

Po ustvarjanju ciljev za izvoz jih boste našli v tabeli na zavihku **Moji cilji za izvoz**. Ta tabela ima tri stolpce:

- **Prikazno ime**: ime, ki ste ga vnesli pri ustvarjanju cilja.
- **Vrsta**: vrsta cilja za izvoz, ki ga nastavite, ko ustvarite cilj.
- **Ustvarjeno**: datum, ko ste ustvarili cilj.

## <a name="edit-an-export-destination"></a>Urejanje cilja za izvoz

1. Izberite navpične tri pike pri cilju za izvoz, ki ga želite urediti.

   > [!div class="mx-imgBorder"]
   > ![Navpične tri pike](media/export-destinations-page-ellipsis.png "Navpične tri pike")

1. V spustnem meniju izberite **Uredi**.

1. Spremenite vrednosti, ki potrebujejo posodobitev, in izberite **Shrani**.

## <a name="export-data-on-demand"></a>Izvoz podatkov na zahtevo

Po konfiguraciji povezovalnika za cilj za izvoz se izvozi zaženejo z vsako [načrtovano osvežitvijo](system.md#schedule-tab).

Če želite izvoziti podatke brez čakanja na načrtovano osvežitev, odprite zavihek **Moji cilji za izvoz** v možnosti **Skrbnik** > **Cilji za izvoz**.

> [!div class="mx-imgBorder"]
> ![Navpične tri pike](media/export-destinations-page-ellipsis.png "Navpične tri pike")

- Izberite **Izvozi** nad seznamom, da zaženete izvoz v vse cilje za izvoz hkrati.
- Izberite tri pike (...) za elementom na seznamu in nato izberite možnost **Izvoz**, da zaženete izvoz za en cilj za izvoz.

## <a name="remove-an-export-destination"></a>Odstranjevanje cilja za izvoz

Če želite odstraniti cilj za izvoz, začnite na glavni strani **Cilji za izvoz**.

1. Izberite navpične tri pike pri cilju za izvoz, ki ga želite odstraniti.

   > [!div class="mx-imgBorder"]
   > ![Navpične tri pike](media/export-destinations-page-ellipsis.png "Navpične tri pike")

2. Na spustnem seznamu izberite **Odstrani**.

3. Odstranjevanje potrdite tako, da na potrditvenem zaslonu izberete **Odstrani**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]