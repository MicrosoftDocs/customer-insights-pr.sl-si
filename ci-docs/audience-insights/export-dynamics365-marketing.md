---
title: Izvozite podatke Customer Insights v Dynamics 365 Marketing
description: Naučite se, kako konfigurirati povezavo in izvažati v Dynamics 365 Marketing.
ms.date: 08/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 2c673c432f308efa289625a159de608d07f8d2b3
ms.sourcegitcommit: f988114ac7a288ccadf2db35b02dbef5cacea4d9
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 01/14/2022
ms.locfileid: "7975144"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a>Uporaba segmentov v storitvi Dynamics 365 Marketing (predogledna različica)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

S [segmenti](segments.md) ustvarite akcije in stopite v stik z določenimi skupinami strank s storitvijo Dynamics 365 Marketing. Za več informacij glejte razdelek [Uporaba segmentov iz storitve Dynamics 365 Customer Insights s storitvijo Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Če uporabljate nove zmogljivosti storitve Dynamics 365 Marketing za sprotno organiziranje dejavnosti strank v organizaciji storitve Dataverse, vam ni treba ustvariti standardnega izvoza za storitev Dynamics 365 Marketing. Stiki in segmenti iz vpogledov občinstva so na voljo neposredno v storitvi Dynamics 365 Marketing, potem ko povežete storitvi Marketing in Customer Insights. Preden izbrišete obstoječi izvoz, preglejte dokumentacijo o tem, [kako povezati vpoglede občinstva in sprotno organiziranje dejavnosti strank storitve Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite-for-a-connection"></a>Predpogoj za povezavo

- Zapisi o stikih morajo biti prisotni v storitvi Dynamics 365 Marketing, preden lahko izvozite segment iz rešitve Customer Insights v Marketing. Preberite več o vključevanju stikov v storitvi [Dynamics 365 Marketing z uporabo rešitve Microsoft Dataverse](connect-power-query.md).

  > [!NOTE]
  > Z izvozom segmentov iz vpogledov v občinstvo v rešitev Marketing ne bodo ustvarjeni novi zapisi stikov v primerkih aplikacije Marketing. Zapise o stikih iz rešitve Marketing je treba vključiti v vpoglede v občinstvo in jih uporabiti kot vir podatkov. Prav tako jih je treba vključiti v enotno entiteto stranke, da se ID-ji strank preslikajo v ID-je stikov, preden je segmente mogoče izvoziti.

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

[!INCLUDE[footer-include](../includes/footer-banner.md)]
