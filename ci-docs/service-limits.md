---
title: Omejitve storitev v Customer Insights
description: Razumevanje omejitev in omejitev v storitvi Customer Insights SaaS.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 421e1aa41a54a4b8c34ac27fc7c02e510d2bb588
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387176"
---
# <a name="service-limits-in-customer-insights"></a>Omejitve storitev v Customer Insights

 Customer Insights ima vgrajene omejitve, ki zagotavljajo zanesljivost in stabilnost storitve. Vse zahteve za spremembe pošljite v naš [forum za zamisli](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| Površina  | Omejitve  | Beležke |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenti, mere in napovedi | 300  | Skupno število [segmente](segments.md) ,[ukrepe](measures.md) , in [napovedi](predictions.md) skupaj ne sme preseči 300.  |
| Relacije | 20 stopenj globine v odnosih poti entitete. | Pri ustvarjanju [segmentov](segments.md) ali [ukrepov](measures.md) z uporabo vmesnika za gradnjo imajo lahko poti entitet do 20 povezav med začetno in ciljno entiteto.  |

## <a name="fair-scheduling-of-jobs"></a>Pravično razporejanje delovnih mest

Customer Insights je storitev SaaS, ki uporablja skupne vire Azure. Stranke imajo običajno delovne obremenitve spremenljive intenzivnosti in po različnih urnikih. Da bi zagotovili pošten dostop do osnovnih virov, poskrbimo, da se sistemski procesi izvajajo v poštenem vrstnem redu. Primeri sistemskih procesov so opravila, povezana s poenotenjem podatkov, posodobitvami segmentov ali izračunom mer. Pošteno razporejanje vas ščiti pred čakanjem v čakalni vrsti za vire, če pride do skokovitega števila zahtevanih opravil. Hkrati Customer Insights ne zagotavlja, da bodo vsa opravila, ki jih postavite v čakalno vrsto, obdelana vzporedno.

[!INCLUDE [footer-include](includes/footer-banner.md)]
