---
title: Povezovalnik Power Automate | Microsoftovo gradivo
description: Ustvarite poteke v storitvi Microsoft Power Automate iz Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406947"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="01f7d-103">Povezovalnik za Power Automate (predogled)</span><span class="sxs-lookup"><span data-stu-id="01f7d-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="01f7d-104">Nastavite sprožilnike za samodejno izvajanje določenih dogodkov, ko se podatki spremenijo, in upravljajte zahtevnejše poteke v storitvi [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="01f7d-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="01f7d-105">Sprožilci za Power Automate</span><span class="sxs-lookup"><span data-stu-id="01f7d-105">Power Automate triggers</span></span>

<span data-ttu-id="01f7d-106">Uporabite lahko različne sprožilce, ki vam omogočajo ustvarjanje potekov za avtomatizacijo ponavljajočih se opravil, kot so obvestila ali naprednejša dejanja.</span><span class="sxs-lookup"><span data-stu-id="01f7d-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="01f7d-107">Sproži, ko osvežitev vira podatkov ne uspe.</span><span class="sxs-lookup"><span data-stu-id="01f7d-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="01f7d-108">Sproži, ko osvežitev vira podatkov uspe.</span><span class="sxs-lookup"><span data-stu-id="01f7d-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="01f7d-109">Sproži, ko je prag segmenta presežen.</span><span class="sxs-lookup"><span data-stu-id="01f7d-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="01f7d-110">Sprožilec je omejen na preseganje praga.</span><span class="sxs-lookup"><span data-stu-id="01f7d-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="01f7d-111">Sproži, ko je prag presežen v poslovni meri.</span><span class="sxs-lookup"><span data-stu-id="01f7d-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="01f7d-112">Sprožilec je omejen s preseganjem praga.</span><span class="sxs-lookup"><span data-stu-id="01f7d-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="01f7d-113">Sprožilec, ko je opravljeno polno osveževanje (viri podatkov, segmenti, mere, ...).</span><span class="sxs-lookup"><span data-stu-id="01f7d-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="01f7d-114">Sproži, ko je dokončana osvežitev postopka poenotenja (preslikava, ujemanje, spajanje).</span><span class="sxs-lookup"><span data-stu-id="01f7d-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="01f7d-115">[Konfigurirajte sprožilce v storitvi Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="01f7d-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="01f7d-116">Dejanja Power Automate</span><span class="sxs-lookup"><span data-stu-id="01f7d-116">Power Automate actions</span></span>
<span data-ttu-id="01f7d-117">Povezovalnik za Power Automate poleg razpoložljivih sprožilcev zagotavlja še druga dejanja.</span><span class="sxs-lookup"><span data-stu-id="01f7d-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="01f7d-118">Če želite več informacij, glejte [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="01f7d-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="01f7d-119">Ustvarjanje poteka Power Automate pri vpogledih v občinstvo</span><span class="sxs-lookup"><span data-stu-id="01f7d-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="01f7d-120">Pri vpogledih v občinstvo izberite **Skrbnik** > **Sistem**.</span><span class="sxs-lookup"><span data-stu-id="01f7d-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="01f7d-121">Na strani **Sistem** izberite zavihek **Stanje**.</span><span class="sxs-lookup"><span data-stu-id="01f7d-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="01f7d-122">V razdelku **Viri podatkov** izberite možnost **Poteki** in **Ustvari potek** na spustnem seznamu.</span><span class="sxs-lookup"><span data-stu-id="01f7d-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="01f7d-123">![Povezovalnik Power Automate s prikazom dejanja ustvarjanja poteka](media/power-automate-connector-create-flow.png "Povezovalnik Power Automate s prikazom dejanja ustvarjanja poteka")</span><span class="sxs-lookup"><span data-stu-id="01f7d-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="01f7d-124">V povezovalniku Power Automate izberite enega od sprožilcev, ki so na voljo, da ustvarite želeni pretok.</span><span class="sxs-lookup"><span data-stu-id="01f7d-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="01f7d-125">Če ustvarjate prvi potek, morate najprej preveriti pristnost s povezovalnikom Power Automate.</span><span class="sxs-lookup"><span data-stu-id="01f7d-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>
