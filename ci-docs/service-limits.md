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
ms.openlocfilehash: c3863b1a72fd92ddc87755699feda11371ec9214
ms.sourcegitcommit: dfba60e17ae6dc1e2e3830e6365e2c1f87230afd
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 09/09/2022
ms.locfileid: "9463239"
---
# <a name="service-limits-in-customer-insights"></a>Omejitve storitev v Customer Insights

 Customer Insights ima vgrajene omejitve, namenjene zagotavljanju zanesljivosti in stabilnosti storitve. Vse zahteve za spremembe pošljite v naš [forum za zamisli](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| Površina  | Omejitve  | Beležke |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenti, mere in napovedi | 300  | Skupno število [segmente](segments.md),[ukrepe](measures.md), in [napovedi](predictions-overview.md) skupaj ne sme preseči 300.  |
| Relacije | 20 stopenj globine v odnosih poti entitete. | Pri ustvarjanju [segmentov](segments.md) ali [ukrepov](measures.md) z uporabo vmesnika za gradnjo imajo lahko poti entitet do 20 povezav med začetno in ciljno entiteto.  |
|Uvoz podatkov| Sočasne ocene za Power Query viri podatkov so omejeni. | Customer Insights ima enako [omejitve osveževanja, kot so tokovi podatkov v PowerBI.com](/power-query/power-query-online-limits#refresh-limits). |

## <a name="fair-scheduling-of-jobs"></a>Pravično razporejanje delovnih mest

Customer Insights je storitev SaaS, ki uporablja skupne vire Azure. Stranke imajo običajno delovne obremenitve spremenljive intenzivnosti in po različnih urnikih. Za zagotovitev poštenega dostopa do osnovnih virov poskrbimo, da se sistemski procesi izvajajo v poštenem vrstnem redu. Primeri sistemskih procesov so opravila, povezana s poenotenjem podatkov, posodobitvami segmentov ali izračunom mer. Pošteno razporejanje vas ščiti pred čakanjem v čakalni vrsti za vire, če pride do skokovitega števila zahtevanih opravil. Hkrati Customer Insights ne zagotavlja, da bodo vsa opravila, ki jih postavite v čakalno vrsto, obdelana vzporedno.

[!INCLUDE [footer-include](includes/footer-banner.md)]
