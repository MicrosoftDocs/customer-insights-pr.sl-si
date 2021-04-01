---
title: Povezovalnik Power Automate | Microsoftovo gradivo
description: Ustvarjajte tokove v storitvi Microsoft Power Automate iz storitve Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e973bb11b31c9e70b695ebec8aa2700fdaa5e44f
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597945"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="a7c84-103">Povezovalnik za Power Automate (predogled)</span><span class="sxs-lookup"><span data-stu-id="a7c84-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="a7c84-104">Nastavite sprožilnike za samodejno izvajanje določenih dogodkov, ko se podatki spremenijo, in upravljajte zahtevnejše poteke v storitvi [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="a7c84-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="a7c84-105">Sprožilci za Power Automate</span><span class="sxs-lookup"><span data-stu-id="a7c84-105">Power Automate triggers</span></span>

<span data-ttu-id="a7c84-106">Uporabite sprožilce za ustvarjanje tokov za oblake in avtomatizacijo ponavljajočih se opravil, kot so obvestila ali naprednejša dejanja.</span><span class="sxs-lookup"><span data-stu-id="a7c84-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="a7c84-107">Sproži, ko osvežitev vira podatkov ne uspe.</span><span class="sxs-lookup"><span data-stu-id="a7c84-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="a7c84-108">Sproži, ko osvežitev vira podatkov uspe.</span><span class="sxs-lookup"><span data-stu-id="a7c84-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="a7c84-109">Sproži, ko je prag segmenta presežen.</span><span class="sxs-lookup"><span data-stu-id="a7c84-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="a7c84-110">Sprožilec je omejen na preseganje praga.</span><span class="sxs-lookup"><span data-stu-id="a7c84-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="a7c84-111">Sproži, ko je prag presežen v poslovni meri.</span><span class="sxs-lookup"><span data-stu-id="a7c84-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="a7c84-112">Sprožilec je omejen s preseganjem praga.</span><span class="sxs-lookup"><span data-stu-id="a7c84-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="a7c84-113">Sprožilec, ko je opravljeno polno osveževanje (viri podatkov, segmenti, mere, ...).</span><span class="sxs-lookup"><span data-stu-id="a7c84-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="a7c84-114">Sproži, ko je dokončana osvežitev postopka poenotenja (preslikava, ujemanje, spajanje).</span><span class="sxs-lookup"><span data-stu-id="a7c84-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="a7c84-115">[Konfigurirajte sprožilce v storitvi Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="a7c84-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="a7c84-116">Dejanja Power Automate</span><span class="sxs-lookup"><span data-stu-id="a7c84-116">Power Automate actions</span></span>
<span data-ttu-id="a7c84-117">Povezovalnik za Power Automate poleg razpoložljivih sprožilcev zagotavlja še druga dejanja.</span><span class="sxs-lookup"><span data-stu-id="a7c84-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="a7c84-118">Če želite več informacij, glejte [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="a7c84-118">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="a7c84-119">Ustvarjanje toka storitve Power Automate</span><span class="sxs-lookup"><span data-stu-id="a7c84-119">Create a Power Automate flow</span></span>

1. <span data-ttu-id="a7c84-120">Pri vpogledih v občinstvo izberite **Skrbnik** > **Cilji izvoza**.</span><span class="sxs-lookup"><span data-stu-id="a7c84-120">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="a7c84-121">Na ploščici **Power Automate** izberite možnost **Nastavitev**.</span><span class="sxs-lookup"><span data-stu-id="a7c84-121">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="a7c84-122">V storitvi Power Automate se odpre Customer Insights Connector (predogled).</span><span class="sxs-lookup"><span data-stu-id="a7c84-122">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="a7c84-123">**Vpišite se** v storitev Power Automate.</span><span class="sxs-lookup"><span data-stu-id="a7c84-123">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="a7c84-124">Izberite enega od razpoložljivih sprožilcev in dodajte več korakov v novi tok.</span><span class="sxs-lookup"><span data-stu-id="a7c84-124">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="a7c84-125">Za več informacij glejte razdelek [Ustvarjanje toka za oblak v storitvi Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="a7c84-125">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="a7c84-126">Primeri uporabe tokov:</span><span class="sxs-lookup"><span data-stu-id="a7c84-126">Examples how to use flows:</span></span> 
- <span data-ttu-id="a7c84-127">Pošljite sporočilo v kanal storitve Microsoft Teams, če osvežitev vira podatkov ne uspe.</span><span class="sxs-lookup"><span data-stu-id="a7c84-127">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="a7c84-128">Ko je prag na segmentu presežen, pošljite e-pošto lastnikom podatkov.</span><span class="sxs-lookup"><span data-stu-id="a7c84-128">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]