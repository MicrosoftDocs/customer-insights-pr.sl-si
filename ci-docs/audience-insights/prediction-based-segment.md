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
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741449"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="69a53-103">Ustvarjanje segmenta na podlagi modela predvidevanja (predogledna različica)</span><span class="sxs-lookup"><span data-stu-id="69a53-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="69a53-104">Rezultati predvidevanja se včasih nanašajo samo na podmnožico vaših strank.</span><span class="sxs-lookup"><span data-stu-id="69a53-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="69a53-105">V večji meri prilagodite priporočila z ustvarjanjem segmentov iz rezultatov modelov predvidevanja.</span><span class="sxs-lookup"><span data-stu-id="69a53-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="69a53-106">Morda boste na primer želeli dati posebna priporočila strankam, ki imajo raje določeno vrsto storitve.</span><span class="sxs-lookup"><span data-stu-id="69a53-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="69a53-107">Zahteve</span><span class="sxs-lookup"><span data-stu-id="69a53-107">Prerequisites</span></span>

- <span data-ttu-id="69a53-108">Vsaj [dovoljenja sodelavcev](permissions.md) v storitvi Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="69a53-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="69a53-109">Model za priporočanje izdelkov, izgubo transakcij, izgubo naročnin ali življenjsko vrednost stranke, konfiguriran v storitvi Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="69a53-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="69a53-110">Preglejte zahteve za nastavitev različnih modelov:</span><span class="sxs-lookup"><span data-stu-id="69a53-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="69a53-111">Model priporočila izdelka</span><span class="sxs-lookup"><span data-stu-id="69a53-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="69a53-112">Model izgube naročnine</span><span class="sxs-lookup"><span data-stu-id="69a53-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="69a53-113">Model izgube transakcij</span><span class="sxs-lookup"><span data-stu-id="69a53-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="69a53-114">Model življenjske vrednosti stranke</span><span class="sxs-lookup"><span data-stu-id="69a53-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="69a53-115">Ustvarjanje segmenta stranke na podlagi predvidevanj</span><span class="sxs-lookup"><span data-stu-id="69a53-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="69a53-116">Izberite **Obveščanje** > **Predvidevanja** in izberite zavihek **Moja predvidevanja**.</span><span class="sxs-lookup"><span data-stu-id="69a53-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="69a53-117">Izberite navpične tri pike poleg modela, ki ga želite pregledati, in izberite **Ogled**.</span><span class="sxs-lookup"><span data-stu-id="69a53-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="69a53-118">Na strani z rezultati izberite **Ustvari segment**.</span><span class="sxs-lookup"><span data-stu-id="69a53-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="69a53-119">Za več informacij o strani z rezultati si oglejte članek o modelu.</span><span class="sxs-lookup"><span data-stu-id="69a53-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Posnetek zaslona strani z rezultati predvidevanja s poudarjenim dejanjem »Ustvari segment«.":::

1. <span data-ttu-id="69a53-121">Ustvarite nov segment na podlagi izhodne entitete izbranega modela.</span><span class="sxs-lookup"><span data-stu-id="69a53-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="69a53-122">Za več informacij glejte [Ustvarjanje in upravljanje segmentov](segments.md).</span><span class="sxs-lookup"><span data-stu-id="69a53-122">For more information, see [Create and manage segments](segments.md).</span></span>