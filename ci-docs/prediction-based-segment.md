---
title: Ustvarite segment na podlagi modela predvidevanje
description: Ustvarite segmente na podlagi izhodne entitete modela predvidevanja.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: ed9c6247a1f9148628dc9b5217484e98a576224e
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610440"
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

1. Izberite model, ki ga želite pregledati, in izberite **Pogled**.

1. Na strani z rezultati izberite **Ustvari segment**. Za več informacij o strani z rezultati si oglejte članek o modelu.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Posnetek zaslona strani z rezultati predvidevanja s poudarjenim dejanjem »Ustvari segment«.":::

1. Ustvarite nov segment z uporabo atributov iz izhodne entitete izbranega modela. Za več informacij glejte [Ustvarjanje in upravljanje segmentov](segments.md).

> [!TIP]
> Ustvarite lahko tudi segment za model predvidevanje iz **Segmenti** stran z izbiro **Novo** in izbiranje **Ustvari iz** > **Inteligenca**. Za več informacij glejte [Ustvarite nov segment s hitrimi segmenti](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
