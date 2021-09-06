---
title: Segmenti na podlagi rezultata predvidevanja
description: Ustvarite segmente na podlagi izhodne entitete modela predvidevanja.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: b89754aea2b0da33f27dea5b26d212920f0c090885f951a37cf42ff11c7b6e93
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036439"
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