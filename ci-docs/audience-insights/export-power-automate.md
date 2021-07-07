---
title: Povezovalnik Power Automate | Microsoftovo gradivo
description: Ustvarjajte tokove v storitvi Microsoft Power Automate iz storitve Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 57be0a204ef920b7a4bb31cf9a5b3a77f96eca0d
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305084"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="6ef8d-103">Povezovalnik za Power Automate (predogled)</span><span class="sxs-lookup"><span data-stu-id="6ef8d-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="6ef8d-104">Nastavite sprožilnike za samodejno izvajanje določenih dogodkov, ko se podatki spremenijo, in upravljajte zahtevnejše poteke v storitvi [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="6ef8d-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="6ef8d-105">Sprožilci za Power Automate</span><span class="sxs-lookup"><span data-stu-id="6ef8d-105">Power Automate triggers</span></span>

<span data-ttu-id="6ef8d-106">Uporabite sprožilce za ustvarjanje tokov za oblake in avtomatizacijo ponavljajočih se opravil, kot so obvestila ali naprednejša dejanja.</span><span class="sxs-lookup"><span data-stu-id="6ef8d-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="6ef8d-107">Sproži, ko osvežitev vira podatkov ne uspe.</span><span class="sxs-lookup"><span data-stu-id="6ef8d-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="6ef8d-108">Sproži, ko osvežitev vira podatkov uspe.</span><span class="sxs-lookup"><span data-stu-id="6ef8d-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="6ef8d-109">Sproži, ko je prag segmenta presežen.</span><span class="sxs-lookup"><span data-stu-id="6ef8d-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="6ef8d-110">Sprožilec je omejen na preseganje praga.</span><span class="sxs-lookup"><span data-stu-id="6ef8d-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="6ef8d-111">Sproži, ko je prag presežen v poslovni meri.</span><span class="sxs-lookup"><span data-stu-id="6ef8d-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="6ef8d-112">Podprte so samo poslovne mere brez razsežnosti.</span><span class="sxs-lookup"><span data-stu-id="6ef8d-112">Only business measures without a dimension are supported.</span></span> <span data-ttu-id="6ef8d-113">Sprožilec je omejen na preseganje praga.</span><span class="sxs-lookup"><span data-stu-id="6ef8d-113">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="6ef8d-114">Sproži po končanem polnem osveževanju (virov podatkov, segmentov, mer, ...).</span><span class="sxs-lookup"><span data-stu-id="6ef8d-114">Trigger when a full refresh of (data sources, segments, measures, ...) is completed.</span></span>
- <span data-ttu-id="6ef8d-115">Sproži, ko je dokončana osvežitev postopka poenotenja (preslikava, ujemanje, spajanje).</span><span class="sxs-lookup"><span data-stu-id="6ef8d-115">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

[<span data-ttu-id="6ef8d-116">Svoje sprožilce konfigurirajte v storitvi Power Automate</span><span class="sxs-lookup"><span data-stu-id="6ef8d-116">Configure your triggers in Power Automate.</span></span>](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a><span data-ttu-id="6ef8d-117">Dejanja Power Automate</span><span class="sxs-lookup"><span data-stu-id="6ef8d-117">Power Automate actions</span></span>

<span data-ttu-id="6ef8d-118">Povezovalnik za Power Automate poleg razpoložljivih sprožilcev zagotavlja še druga dejanja.</span><span class="sxs-lookup"><span data-stu-id="6ef8d-118">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="6ef8d-119">Če želite več informacij, glejte [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="6ef8d-119">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="6ef8d-120">Ustvarjanje toka storitve Power Automate</span><span class="sxs-lookup"><span data-stu-id="6ef8d-120">Create a Power Automate flow</span></span>

1. <span data-ttu-id="6ef8d-121">Pri vpogledih v občinstvo izberite **Skrbnik** > **Cilji izvoza**.</span><span class="sxs-lookup"><span data-stu-id="6ef8d-121">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="6ef8d-122">Na ploščici **Power Automate** izberite možnost **Nastavitev**.</span><span class="sxs-lookup"><span data-stu-id="6ef8d-122">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="6ef8d-123">V storitvi Power Automate se odpre Customer Insights Connector (predogled).</span><span class="sxs-lookup"><span data-stu-id="6ef8d-123">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="6ef8d-124">**Vpišite se** v storitev Power Automate.</span><span class="sxs-lookup"><span data-stu-id="6ef8d-124">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="6ef8d-125">Izberite enega od razpoložljivih sprožilcev in dodajte več korakov v novi tok.</span><span class="sxs-lookup"><span data-stu-id="6ef8d-125">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="6ef8d-126">Za več informacij glejte razdelek [Ustvarjanje toka za oblak v storitvi Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="6ef8d-126">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="6ef8d-127">Primeri uporabe tokov:</span><span class="sxs-lookup"><span data-stu-id="6ef8d-127">Examples of how to use flows:</span></span> 
- <span data-ttu-id="6ef8d-128">Pošljite sporočilo v kanal storitve Microsoft Teams, če osvežitev vira podatkov ne uspe.</span><span class="sxs-lookup"><span data-stu-id="6ef8d-128">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="6ef8d-129">Ko je prag na segmentu presežen, pošljite e-pošto lastnikom podatkov.</span><span class="sxs-lookup"><span data-stu-id="6ef8d-129">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]
