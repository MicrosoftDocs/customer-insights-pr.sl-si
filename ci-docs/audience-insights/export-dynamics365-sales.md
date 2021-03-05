---
title: Izvozite podatke Customer Insights v Dynamics 365 Sales
description: Naučite se konfigurirati povezavo s storitvijo Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0013c4e6a96401d6cdbea55ed38f85f5e10dcc56
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269028"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Povezovalnik za Dynamics 365 Sales (predogled)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Na podlagi podatkov o strankah z aplikacijo Dynamics 365 Sales ustvarjajte sezname za trženje in postopke za nadaljnje delo ter pošiljajte promocijske vsebine.

## <a name="prerequisite"></a>Predpogoj

1. Zapisi o stikih morajo biti prisotni v storitvi Dynamics 365 Sales, preden lahko izvozite segment iz rešitve Customer Insights v Sales. Preberite več o vključevanju stikov v storitvi [Dynamics 365 Sales z uporabo rešitve Common Data Services](connect-power-query.md).

   > [!NOTE]
   > Z izvozom segmentov iz vpogledov v občinstvo v rešitev Sales ne bodo ustvarjeni novi zapisi stikov v primerkih aplikacije Sales. Zapise o stikih iz rešitve Sales je treba vključiti v vpoglede v občinstvo in jih uporabiti kot vir podatkov. Prav tako jih je treba vključiti v enotno entiteto stranke, da se ID-ji strank preslikajo v ID-je stikov, preden je segmente mogoče izvoziti.

## <a name="configure-the-connector-for-sales"></a>Konfiguracija povezovalnika za Sales

1. Pri vpogledih v občinstvo izberite **Skrbnik** > **Cilji izvoza**.

1. Pod možnostjo **Dynamics 365 Sales** izberite **Nastavitev**.

1. Dajte svojemu cilju izvoza prepoznavno ime v polju **Prikazno ime**.

1. Vnesite URL za Sales vaše organizacije v polje **Naslov strežnika**.

1. V razdelku **Skrbniški račun strežnika** izberite **Vpis** in izberite račun Dynamics 365 Sales.

1. Polje za ID stranke preslikajte v ID stika za Dynamics 365.

1. Izberite **Naprej**.

1. Izberite enega ali več segmentov.

1. Izberite **Shrani**.

## <a name="export-the-data"></a>Izvoz podatkov

Lahko [izvozite podatke na zahtevo](export-destinations.md). Izvoz se bo zagnal tudi z vsakim [načrtovanim osveževanjem](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]