---
title: Izvozite podatke Customer Insights v Dynamics 365 Marketing
description: Naučite se, kako konfigurirati povezavo in izvažati v Dynamics 365 Marketing.
ms.date: 08/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 7227f3f9e7699a9b5ad546789de5e568b56da579
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642965"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a>Uporaba segmentov v storitvi Dynamics 365 Marketing (predogledna različica)



S [segmenti](segments.md) ustvarite akcije in stopite v stik z določenimi skupinami strank s storitvijo Dynamics 365 Marketing. Za več informacij glejte razdelek [Uporaba segmentov iz storitve Dynamics 365 Customer Insights s storitvijo Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Če uporabljate nove zmogljivosti storitve Dynamics 365 Marketing za sprotno organiziranje dejavnosti strank v organizaciji storitve Dataverse, vam ni treba ustvariti standardnega izvoza za storitev Dynamics 365 Marketing. Stiki in segmenti iz Customer Insights so na voljo neposredno v Dynamics 365 Marketing po povezovanju Marketing in Customer Insights. Preden izbrišete obstoječe izvoze, preglejte dokumentacijo na [kako povezati Customer Insights in Dynamics 365 Marketing dejavnosti strank orkestracijo](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite-for-a-connection"></a>Predpogoj za povezavo

- Zapisi o stikih morajo biti prisotni v storitvi Dynamics 365 Marketing, preden lahko izvozite segment iz rešitve Customer Insights v Marketing. Preberite več o vključevanju stikov v storitvi [Dynamics 365 Marketing z uporabo rešitve Microsoft Dataverse](connect-dataverse-managed-lake.md).

  > [!NOTE]
  > Izvoz segmentov iz Customer Insights v Marketing ne bo ustvaril novih kontaktnih zapisov v primerih Marketing. Zapise o stikih iz Marketinga je treba prenesti v Customer Insights in jih uporabiti kot vir podatkov. Prav tako jih je treba vključiti v enotno entiteto stranke, da se ID-ji strank preslikajo v ID-je stikov, preden je segmente mogoče izvoziti.

## <a name="set-up-connection-to-marketing"></a>Nastavitev povezave s storitvijo Marketing

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajanje povezave** in izberite **Dynamics 365 Marketing** za konfiguracijo povezave.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vnesite URL za Marketing vaše organizacije v polje **Naslov strežnika**.

1. V razdelku **Skrbniški račun strežnika** izberite **Vpis** in izberite račun Dynamics 365 Marketing.

1. Preslikajte polje ID stika v entiteti Stranka v ID stika Dynamics 365.

1. Izberite možnost **Shrani**, da dokončate povezavo. 

## <a name="configure-an-export"></a>Konfiguriranje izvoza

Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave. Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Za ustvarjanje novega izvoza izberite **Dodaj cilj**.

1. V polju **Povezava za izvoz** izberite povezavo v razdelku Dynamics 365 Marketing. Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.

1. Izberite enega ali več segmentov.

1. Izberite **Shrani**.

S shranjevanjem izvoza se ta ne zažene takoj.

Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab). Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand). 

[!INCLUDE [footer-include](includes/footer-banner.md)]
