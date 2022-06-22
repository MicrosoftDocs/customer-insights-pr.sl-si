---
title: Omejitve storitev v Customer Insights
description: Razumeti omejitve in omejitve v storitvi Customer Insights SaaS.
ms.date: 05/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6d1b761a5c9f67bfdc7c5b152132c618db3ea36a
ms.sourcegitcommit: 78ef22cd39a1ebd7525f96829cd79d95f34438b9
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/07/2022
ms.locfileid: "8940688"
---
# <a name="service-limits-in-customer-insights"></a>Omejitve storitev v Customer Insights

V tem članku so opisane vgrajene omejitve storitve Customer Insights, ki so zasnovane, da zagotavljajo zanesljivost in stabilnost storitve. Vse zahteve za spremembe pošljite v naš [forum za zamisli](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| Površina  | Omejitve  | Beležke |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenti, meritve in napovedi | 300  | Skupno število [segmentih](segments.md),[ukrepe](measures.md), in [napovedi](predictions.md) skupaj ne sme presegati 300.  |
| Relacije | 20 stopenj globine v odnosih poti entitete. | Pri ustvarjanju [segmentov](segments.md) ali [ukrepov](measures.md) z uporabo vmesnika za gradnjo imajo lahko poti entitet do 20 povezav med začetno in ciljno entiteto.  |

## <a name="fair-scheduling-of-jobs"></a>Pošteno razporejanje delovnih mest

Customer Insights je storitev SaaS, ki uporablja skupne vire Azure. Stranke imajo običajno delovne obremenitve spremenljive intenzivnosti in po različnih urnikih. Da zagotovimo pošten dostop do osnovnih virov, poskrbimo, da se sistemski procesi izvajajo v poštenem vrstnem redu. Primeri sistemskih procesov so opravila, povezana z združevanjem podatkov, posodobitvami segmentov ali izračunom meritev. Pošteno razporejanje vas ščiti pred čakanjem na vire, če pride do skoka zahtevanih delovnih mest. Hkrati Customer Insights ne zagotavlja, da so vsa opravila, ki ste v čakalni vrsti, obdelana vzporedno.

[!INCLUDE [footer-include](includes/footer-banner.md)]
