---
title: Cilji za izvoz
description: Izvozite podatke in upravljajte cilje za izvoz.
ms.date: 07/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5557442983f8c48cd46387009e0060beb6e764bb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596106"
---
# <a name="export-destinations-preview-overview"></a>Pregled ciljev za izvoz (predogled)

Stran **Cilji za izvoz** prikazuje vsa mesta, ki ste jih nastavili za izvoz podatkov. Dodate lahko tudi nove cilje za izvoz. Poleg tega prikazuje trenutno razpoložljive možnosti za izvoz. Pridobite hiter pregled, opis in informacije o tem, kaj lahko storite z vsako možnostjo razširljivosti. Izvozite poenotene profile, mere in segmente v podprte aplikacije, relevantne za vaše poslovanje.

Odprite **Skrbnik** > **Cilji za izvoz**, da poiščete naslednje možnosti razširljivosti:

- [Adobe Campaign Standard](export-adobe-campaign-standard.md)
- [Adobe Experience Platform](export-adobe-experience-platform.md)
- [AdRoll](export-adroll.md)
- [Autopilot](export-autopilot.md)
- [Shramba zbirke dvojiških podatkov Azure](export-azure-blob-storage.md)
- [Azure Data Lake Storage Gen2](export-azure-data-lake-storage-gen2.md)
- [Bot za Microsoft Teams](export-teams-bot.md)
- [API za Customer Insights](apis.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Customer Service (dodatek za kartico stranke)](customer-card-add-in.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Središče za prodajo za Dynamics 365 (dodatek za kartico stranke)](customer-card-add-in.md)
- [Upravitelj oglasov za Facebook](export-facebook.md)
- [Google Ads](export-google-ads.md)
- [LiveRamp&reg;](export-liveramp.md)
- [MailChimp](export-mailchimp.md)
- [Marketo](export-marketo.md)
- [Power Automate](export-power-automate.md)
- [Power Apps](export-power-apps.md)
- [Power BI](export-power-bi.md)
- [SendGrid](export-sendgrid.md)
- [SFTP](export-sftp.md)

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