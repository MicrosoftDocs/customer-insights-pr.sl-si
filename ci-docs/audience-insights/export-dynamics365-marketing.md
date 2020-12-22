---
title: Izvozite podatke Customer Insights v Dynamics 365 Marketing
description: Naučite se konfigurirati povezavo s storitvijo Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643793"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Povezovalnik za Dynamics 365 Marketing (predogled)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

S [segmenti](segments.md) ustvarite akcije in stopite v stik z določenimi skupinami strank s storitvijo Dynamics 365 Marketing. Za več informacij glejte razdelek [Uporaba segmentov iz storitve Dynamics 365 Customer Insights s storitvijo Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>Predpogoj

Zapisi stikov [iz storitve Dynamics 365 Marketing, uvoženi prek storitve Common Data Service](connect-power-query.md).

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
