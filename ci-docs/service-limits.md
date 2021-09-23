---
title: Omejitve storitve v Dynamics 365 Customer Insights
description: Razumevanje omejitev.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eba7871faf304d5945191b5b9bc215243b4f8a05
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483709"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Omejitve storitve v zmogljivostih storitve Customer Insights

V tem članku so opisane vgrajene omejitve storitve Customer Insights, ki so zasnovane, da zagotavljajo zanesljivost in stabilnost storitve. Vse zahteve za spremembe pošljite v naš [forum za zamisli](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Vpogledi v občinstvo

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Omejitve storitev pri zmogljivosti vpogledov v občinstvo Dynamics 365 Customer Insights

| Površina  | Omejitve  | Beležke |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenti in mere | 100 segmentov ali mer. | Skupno število aktivnih [segmentov](audience-insights/segments.md) in [mer](audience-insights/measures.md) ne sme presegati 100.  |
| Odnosi | 20 stopenj globine v odnosih poti entitete. | Pri ustvarjanju [segmentov](audience-insights/segments.md) ali [ukrepov](audience-insights/measures.md) z uporabo vmesnika za gradnjo imajo lahko poti entitet do 20 povezav med začetno in ciljno entiteto.  |


## <a name="engagement-insights"></a>Vpogledi v interakcije

### <a name="workspace-and-event-quotas"></a>Kvote za delovni prostor in dogodke

Vpogledi v interakcije so zelo prilagodljiva aplikacija, ki lahko podpira milijone dogodkov na sekundo. Med predogledno različico za javnost imajo dogodki prag glede obsega. Obstaja tudi omejitev števila delovnih prostorov v organizaciji.

### <a name="engagement-insights-limits"></a>Omejitve vpogledov v interakcije

- Največji obseg dogodkov na delovni prostor = 100 dogodkov na sekundo

- Največje dovoljeno število delovnih prostorov na organizacijo = 100

Ko dogodki presežejo prag, lahko to privede do izgube podatkov v poročilih, ki temeljijo na teh dogodkih. Stopite lahko v [stik s podporo](https://go.microsoft.com/fwlink/?linkid=2145734), da zahtevate povečanje obsega, preden presežete omejitve. V sodelovanju z vami bomo ugotovili, ali potrebujete povečanje obsega, in podprli vašo zahtevo.


[!INCLUDE[footer-include](includes/footer-banner.md)]