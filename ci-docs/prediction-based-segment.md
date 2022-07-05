---
title: Ustvarite segment na podlagi modela predvidevanje
description: Ustvarite segmente na podlagi izhodne entitete modela predvidevanja.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: d67594f2467c1a0fde84b1ba0bd1afa4025e7b71
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082438"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a>Ustvarjanje segmenta na podlagi modela predvidevanja (predogledna različica)

Rezultati predvidevanja se včasih nanašajo samo na podmnožico vaših strank. V večji meri prilagodite priporočila z ustvarjanjem segmentov iz rezultatov modelov predvidevanja. Morda boste na primer želeli dati posebna priporočila strankam, ki imajo raje določeno vrsto storitve. 

## <a name="prerequisites"></a>Zahteve

- Vsaj [dovoljenja sodelavcev](permissions.md) v storitvi Customer Insights.

- Model za priporočanje izdelkov, izgubo transakcij, izgubo naročnin ali življenjsko vrednost stranke, konfiguriran v storitvi Customer Insights. Preglejte zahteve za nastavitev različnih modelov:

  - [Model priporočila izdelka](predict-product-recommendation.md)
  - [Model izgube naročnine](predict-subscription-churn.md)
  - [Model izgube transakcij](predict-transactional-churn.md)
  - [Model življenjske vrednosti stranke](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a>Ustvarjanje segmenta stranke na podlagi predvidevanj

1. Izberite **Obveščanje** > **Predvidevanja** in izberite zavihek **Moja predvidevanja**.

1. Izberite navpične tri pike poleg modela, ki ga želite pregledati, in izberite **Ogled**.

1. Na strani z rezultati izberite **Ustvari segment**. Za več informacij o strani z rezultati si oglejte članek o modelu.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Posnetek zaslona strani z rezultati predvidevanja s poudarjenim dejanjem »Ustvari segment«.":::

1. Ustvarite nov segment na podlagi izhodne entitete izbranega modela. Za več informacij glejte [Ustvarjanje in upravljanje segmentov](segments.md).