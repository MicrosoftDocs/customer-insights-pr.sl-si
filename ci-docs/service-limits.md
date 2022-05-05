---
title: Omejitve storitve v Dynamics 365 Customer Insights
description: Razumevanje omejitev.
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e2e7fc3033c25646693831d4c4c800d84ae6d6da
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8641782"
---
# <a name="service-limits-in-customer-insights"></a>Omejitve storitev v Customer Insights

V tem članku so opisane vgrajene omejitve storitve Customer Insights, ki so zasnovane, da zagotavljajo zanesljivost in stabilnost storitve. Vse zahteve za spremembe pošljite v naš [forum za zamisli](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="customer-insights"></a>Customer Insights

| Površina  | Omejitve  | Beležke |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenti, meritve in napovedi | 300  | Skupno število [segmentih](segments.md),[ukrepe](measures.md), in [napovedi](predictions.md) skupaj ne sme presegati 300.  |
| Relacije | 20 stopenj globine v odnosih poti entitete. | Pri ustvarjanju [segmentov](segments.md) ali [ukrepov](measures.md) z uporabo vmesnika za gradnjo imajo lahko poti entitet do 20 povezav med začetno in ciljno entiteto.  |


[!INCLUDE [footer-include](includes/footer-banner.md)]
