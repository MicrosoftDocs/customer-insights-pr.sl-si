---
title: Izvozite podatke Customer Insights v Dynamics 365 Sales
description: Naučite se konfigurirati povezavo s storitvijo Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643838"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Povezovalnik za Dynamics 365 Sales (predogled)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Na podlagi podatkov o strankah z aplikacijo Dynamics 365 Sales ustvarjajte sezname za trženje in postopke za nadaljnje delo ter pošiljajte promocijske vsebine.

## <a name="prerequisite"></a>Predpogoj

Zapisi stikov [iz storitve Dynamics 365 Sales, uvožene prek storitve Common Data Service](connect-power-query.md).

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
