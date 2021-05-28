---
title: Izvozite podatke Customer Insights v Dynamics 365 Sales
description: Naučite se, kako konfigurirati povezavo in izvažati v Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 328bb2f26ebcea234fb645e5225930ab12f82a8b
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976246"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a>Uporaba segmentov v storitvi Dynamics 365 Sales (predogledna različica)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Na podlagi podatkov o strankah z aplikacijo Dynamics 365 Sales ustvarjajte sezname za trženje in postopke za nadaljnje delo ter pošiljajte promocijske vsebine.

## <a name="prerequisite-for-connection"></a>Predpogoj za povezavo

1. Zapisi o stikih morajo biti prisotni v storitvi Dynamics 365 Sales, preden lahko izvozite segment iz rešitve Customer Insights v Sales. Preberite več o vključevanju stikov v storitvi [Dynamics 365 Sales z uporabo rešitve Common Data Services](connect-power-query.md).

   > [!NOTE]
   > Z izvozom segmentov iz vpogledov v občinstvo v rešitev Sales ne bodo ustvarjeni novi zapisi stikov v primerkih aplikacije Sales. Zapise o stikih iz rešitve Sales je treba vključiti v vpoglede v občinstvo in jih uporabiti kot vir podatkov. Prav tako jih je treba vključiti v enotno entiteto stranke, da se ID-ji strank preslikajo v ID-je stikov, preden je segmente mogoče izvoziti.

## <a name="set-up-the-connection-to-sales"></a>Nastavitev povezave s storitvijo Sales

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajanje povezave** in izberite **Dynamics 365 Sales** za konfiguracijo povezave.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vnesite URL za Sales vaše organizacije v polje **Naslov strežnika**.

1. V razdelku **Skrbniški račun strežnika** izberite **Vpis** in izberite račun Dynamics 365 Sales.

1. Polje za ID stranke preslikajte v ID stika za Dynamics 365.

1. Izberite možnost **Shrani**, da dokončate povezavo. 

## <a name="configure-an-export"></a>Konfiguriranje izvoza

Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave. Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Za ustvarjanje novega izvoza izberite **Dodaj cilj**.

1. V polju **Povezava za izvoz** izberite povezavo v razdelku Dynamics 365 Sales. Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.

1. Izberite enega ali več segmentov.

1. Izberite **Shrani**

S shranjevanjem izvoza se ta ne zažene takoj.

Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab). Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand). 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
