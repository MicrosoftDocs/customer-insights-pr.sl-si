---
title: Izvozite podatke Customer Insights v Dynamics 365 Marketing
description: Naučite se konfigurirati povezavo s storitvijo Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a06920b8ff25d7102ccd14ae68cf42fe91fa1ee6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269074"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Povezovalnik za Dynamics 365 Marketing (predogled)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

S [segmenti](segments.md) ustvarite akcije in stopite v stik z določenimi skupinami strank s storitvijo Dynamics 365 Marketing. Za več informacij glejte razdelek [Uporaba segmentov iz storitve Dynamics 365 Customer Insights s storitvijo Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>Predpogoj

- Zapisi o stikih morajo biti prisotni v storitvi Dynamics 365 Marketing, preden lahko izvozite segment iz rešitve Customer Insights v Marketing. Preberite več o vključevanju stikov v storitvi [Dynamics 365 Marketing z uporabo rešitve Common Data Services](connect-power-query.md).

  > [!NOTE]
  > Z izvozom segmentov iz vpogledov v občinstvo v rešitev Marketing ne bodo ustvarjeni novi zapisi stikov v primerkih aplikacije Marketing. Zapise o stikih iz rešitve Marketing je treba vključiti v vpoglede v občinstvo in jih uporabiti kot vir podatkov. Prav tako jih je treba vključiti v enotno entiteto stranke, da se ID-ji strank preslikajo v ID-je stikov, preden je segmente mogoče izvoziti.

## <a name="configure-the-connector-for-marketing"></a>Konfiguracija povezovalnika za Marketing

1. Pri vpogledih v občinstvo izberite **Skrbnik** > **Cilji izvoza**.

1. Pod možnostjo **Dynamics 365 Marketing** izberite **Nastavitev**.

1. Dajte svojemu cilju izvoza prepoznavno ime v polju **Prikazno ime**.

1. Vnesite URL za Marketing vaše organizacije v polje **Naslov strežnika**.

1. V razdelku **Skrbniški račun strežnika** izberite **Vpis** in izberite račun Dynamics 365 Marketing.

1. Polje za ID stranke preslikajte v ID stika za Dynamics 365.

1. Izberite **Naprej**.

1. Izberite enega ali več segmentov.

1. Izberite **Shrani**.

## <a name="export-the-data"></a>Izvoz podatkov

Lahko [izvozite podatke na zahtevo](export-destinations.md). Izvoz se bo zagnal tudi z vsakim [načrtovanim osveževanjem](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]