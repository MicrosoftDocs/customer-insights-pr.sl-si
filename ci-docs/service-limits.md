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
ms.openlocfilehash: 9bf8f03b785fb3035e3fc979a3304d4e98fd8d28
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350427"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Omejitve storitve v zmogljivostih storitve Customer Insights

V tem članku so opisane vgrajene omejitve storitve Customer Insights, ki so zasnovane, da zagotavljajo zanesljivost in stabilnost storitve. Vse zahteve za spremembe pošljite v naš [forum za zamisli](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Vpogledi v občinstvo

| Površina  | Omejitve  | Beležke |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenti, meritve in napovedi | 300  | Skupno število [segmentih](audience-insights/segments.md),[ukrepe](audience-insights/measures.md), in [napovedi](audience-insights/predictions.md) skupaj ne sme presegati 300.  |
| Relacije | 20 stopenj globine v odnosih poti entitete. | Pri ustvarjanju [segmentov](audience-insights/segments.md) ali [ukrepov](audience-insights/measures.md) z uporabo vmesnika za gradnjo imajo lahko poti entitet do 20 povezav med začetno in ciljno entiteto.  |

<!--
## Engagement insights

### Workspace and event quotas

Engagement insights is a highly scalable application that can support millions of events per second. During public preview, events have a volume threshold. There's also a limit to the number of workspaces in an organization.

### Engagement insights limits

- Maximum event volume per workspace  = 100 events per second

- Maximum number of workspaces per organization = 100

When events exceed the threshold, it can lead to loss of data in reports based on those events. You can [contact support](https://go.microsoft.com/fwlink/?linkid=2145734) to request a volume increase before you exceed limits. We'll work with you to determine your need for a volume increase and support your request.
-->

[!INCLUDE[footer-include](includes/footer-banner.md)]
