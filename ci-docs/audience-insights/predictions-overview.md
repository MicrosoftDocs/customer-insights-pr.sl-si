---
title: Pregled podprtih scenarijev predvidevanja
description: Scenariji in možnosti predvidevanja, ki jih zajema aplikacija Dynamics 365 Customer Insights.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 69ae945b22819521db217508c6fc232876346747
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095751"
---
# <a name="predictions-overview"></a><span data-ttu-id="9c943-103">Pregled predvidevanj</span><span class="sxs-lookup"><span data-stu-id="9c943-103">Predictions overview</span></span>

<span data-ttu-id="9c943-104">Dynamics 365 Customer Insights vsebuje različne možnosti, ki uporabljajo AI in strojno učenje za napovedovanje podatkov.</span><span class="sxs-lookup"><span data-stu-id="9c943-104">Dynamics 365 Customer Insights comes with a variety of options that leverage AI and machine learning to predict data.</span></span> 

## <a name="out-of-box-models"></a><span data-ttu-id="9c943-105">Vnaprej pripravljeni modeli</span><span class="sxs-lookup"><span data-stu-id="9c943-105">Out-of-box models</span></span>

<span data-ttu-id="9c943-106">Najlažji način za začetek napovedovanja podatkov predstavljajo vnaprej določeni modeli, ki jih pogosto imenujemo vnaprej pripravljeni modeli.</span><span class="sxs-lookup"><span data-stu-id="9c943-106">The easiest way to start with predicting data are predefined models, often referred to as out-of-box models.</span></span> <span data-ttu-id="9c943-107">Za hitro ustvarjanje vpogledov potrebujejo le določene podatke in strukturo.</span><span class="sxs-lookup"><span data-stu-id="9c943-107">They only require certain data and structure to generate insights quickly.</span></span> <span data-ttu-id="9c943-108">Trenutno so na voljo naslednji modeli:</span><span class="sxs-lookup"><span data-stu-id="9c943-108">Currently, the following models are available:</span></span> 
- <span data-ttu-id="9c943-109">[Vrednost življenjske dobe stranke](predict-customer-lifetime-value.md): napoveduje potencialni prihodek stranke v celotni interakciji s podjetjem.</span><span class="sxs-lookup"><span data-stu-id="9c943-109">[Customer lifetime value](predict-customer-lifetime-value.md): Predicts the potential revenue of a customer throughout the entire interaction with a business.</span></span> 
- <span data-ttu-id="9c943-110">[Priporočilo izdelka](predict-product-recommendation.md): predlaga nabore napovednih priporočil za izdelke, ki temeljijo na nakupnem vedenju in strankah s podobnimi vzorci nakupovanja.</span><span class="sxs-lookup"><span data-stu-id="9c943-110">[Product recommendation](predict-product-recommendation.md): Suggests sets of predictive product recommendations based on purchase behavior and customers with similar purchase patterns.</span></span>
- <span data-ttu-id="9c943-111">[Izguba naročnin](predict-subscription-churn.md): predvidi, ali za stranko obstaja tveganje, če ne bo več uporabljala naročniških izdelkov ali storitev vašega podjetja.</span><span class="sxs-lookup"><span data-stu-id="9c943-111">[Subscription churn](predict-subscription-churn.md): Predicts whether a customer is at risk for no longer using your company’s subscription products or services.</span></span>
- <span data-ttu-id="9c943-112">[Izguba transakcij](predict-transactional-churn.md): predvidi, ali stranka ne bo več kupovala vaših izdelkov ali storitev v določenem časovnem okviru.</span><span class="sxs-lookup"><span data-stu-id="9c943-112">[Transactional churn](predict-transactional-churn.md): Predict if a customer will no longer purchase your products or services in a certain time frame.</span></span>

## <a name="azure-machine-learning-integration"></a><span data-ttu-id="9c943-113">Integracija strojnega učenja Azure</span><span class="sxs-lookup"><span data-stu-id="9c943-113">Azure Machine Learning integration</span></span>

<span data-ttu-id="9c943-114">Če organizacija že uporablja scenarije strojnega učenja, ki temeljijo na poskusih strojnega učenja Azure, bo funkcija modelov po meri v Customer Insights pomagala povezovati pike.</span><span class="sxs-lookup"><span data-stu-id="9c943-114">If an organization already uses machine learning scenarios based on Azure Machine Learning experiments, the custom models feature in Customer Insights helps to connect the dots.</span></span> <span data-ttu-id="9c943-115">Ustvarite poteke dela, ki vam pomagajo izbrati podatke, iz katerih želite ustvariti vpogled, in rezultate preslikajte v svoje poenotene profile strank.</span><span class="sxs-lookup"><span data-stu-id="9c943-115">Create workflows that help you choose the data you want to generate insights from and map the results to your unified customer profiles.</span></span> <span data-ttu-id="9c943-116">Za več informacij glejte [Modeli strojnega učenja po meri](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="9c943-116">For more information, see [Custom machine learning models](custom-models.md).</span></span>

## <a name="ai-builder-prediction"></a><span data-ttu-id="9c943-117">Predvidevanje AI Builder</span><span class="sxs-lookup"><span data-stu-id="9c943-117">AI Builder prediction</span></span>

<span data-ttu-id="9c943-118">Včasih so nabori podatkov nepopolni in nekatere vrednosti manjkajo.</span><span class="sxs-lookup"><span data-stu-id="9c943-118">Sometimes, data sets are incomplete and some values are missing.</span></span> <span data-ttu-id="9c943-119">Customer Insights vam lahko pomaga napovedati manjkajoče vrednosti za entiteto in segmente stranke.</span><span class="sxs-lookup"><span data-stu-id="9c943-119">Customer Insights can help to predict missing values for the Customer entity and segments.</span></span> <span data-ttu-id="9c943-120">Za več informacij glejte razdelek [Dopolnjevanje delnih podatkov s predvidevanji](predictions.md).</span><span class="sxs-lookup"><span data-stu-id="9c943-120">For more information, see [Complete your partial data with predictions](predictions.md).</span></span>
