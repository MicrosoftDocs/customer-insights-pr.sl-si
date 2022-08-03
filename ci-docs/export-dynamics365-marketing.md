---
title: Izvozi segmente v Dynamics 365 Marketing (predogled)
description: Naučite se, kako konfigurirati povezavo in izvažati v Dynamics 365 Marketing.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 123b565421a7d096e7341a8f600f91e59aefe8d0
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196644"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>Izvozi segmente v Dynamics 365 Marketing (predogled)

Uporaba [segmenti](segments.md) za ustvarjanje kampanj in stik s posebnimi skupinami strank [Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Če uporabljate nove zmogljivosti storitve Dynamics 365 Marketing za sprotno organiziranje dejavnosti strank v organizaciji storitve Dataverse, vam ni treba ustvariti standardnega izvoza za storitev Dynamics 365 Marketing. Stiki in segmenti iz Customer Insights so na voljo neposredno v Dynamics 365 Marketing po povezavi Marketing in Customer Insights. Preden izbrišete obstoječe izvoze, preglejte dokumentacijo o [kako povezati Customer Insights in Dynamics 365 Marketing dejavnosti strank orkestracijo](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite"></a>Predpogoj

Zapisi o stikih morajo biti prisotni v storitvi Dynamics 365 Marketing, preden lahko izvozite segment iz rešitve Customer Insights v Marketing. Preberite več o vključevanju stikov v storitvi [Dynamics 365 Marketing z uporabo rešitve Microsoft Dataverse](connect-dataverse-managed-lake.md).

> [!NOTE]
> Z izvozom segmentov iz storitve Customer Insights v Marketing ne boste ustvarili novih zapisov stikov v instancah Marketing. Zapise stikov iz Marketinga je treba vnesti v Customer Insights in uporabiti kot vir podatkov. Prav tako jih je treba vključiti v enotno entiteto stranke, da se ID-ji strank preslikajo v ID-je stikov, preden je segmente mogoče izvoziti.

## <a name="set-up-connection-to-marketing"></a>Nastavitev povezave s storitvijo Marketing

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajte povezavo** in izberite **Dynamics 365 Marketing**.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Privzeto jo lahko uporabljajo samo skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vnesite URL za Marketing vaše organizacije v polje **Naslov strežnika**.

1. V razdelku **Skrbniški račun strežnika** izberite **Vpis** in izberite račun Dynamics 365 Marketing.

1. Preslikajte polje ID stika v entiteti Stranka v ID stika Dynamics 365.

1. Preglejte [zasebnost podatkov in skladnost](connections.md#data-privacy-and-compliance) in izberite **strinjam se**.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite **Dodaj izvoz**.

1. V polju **Povezava za izvoz** izberite povezavo v razdelku Dynamics 365 Marketing. Če ni na voljo nobena povezava, se obrnite na skrbnika.

1. Vnesite ime za izvoz.

1. Izberite polje ID stika v entiteti stranke, ki se ujema z ID-jem stika Dynamics 365.

1. Izberite segmente, ki jih želite izvoziti.

1. Izberite **Shrani**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
