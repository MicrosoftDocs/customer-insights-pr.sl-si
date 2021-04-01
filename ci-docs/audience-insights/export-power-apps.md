---
title: Povezovalnik Power Apps
description: Povezava s storitvama Power Apps in Power Automate.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3fa91553fd50a22ab62b5a2b1e3f13b9483776a8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598175"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="fc557-103">Povezovalnik storitve Microsoft Power Apps (predogled)</span><span class="sxs-lookup"><span data-stu-id="fc557-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="fc557-104">Vnesite poenotene profile strank v svoje prilagojene aplikacije s storitvijo Power Apps.</span><span class="sxs-lookup"><span data-stu-id="fc557-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="fc557-105">Povezava storitev Power Apps in Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="fc557-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="fc557-106">Storitev Customer Insights je ena od mnogih [razpoložljivih virov podatkov v storitvi Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).</span><span class="sxs-lookup"><span data-stu-id="fc557-106">Customer Insights is one of the many [available sources for data in Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="fc557-107">Oglejte si dokumentacijo za Power Apps, če želite izvedeti več o [dodajanju podatkovne povezave v aplikacijo](/powerapps/maker/canvas-apps/add-data-connection).</span><span class="sxs-lookup"><span data-stu-id="fc557-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="fc557-108">Priporočamo, da pregledate tudi [kako se v storitvi Power Apps uporablja pooblastitve za obdelavo velikih množic podatkov v aplikacijah s platnom](/powerapps/maker/canvas-apps/delegation-overview).</span><span class="sxs-lookup"><span data-stu-id="fc557-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="fc557-109">Entitete, ki so na voljo</span><span class="sxs-lookup"><span data-stu-id="fc557-109">Available entities</span></span>

<span data-ttu-id="fc557-110">Ko dodate storitev Customer Insights kot podatkovno povezavo, lahko v storitvi Power Apps izberete naslednje entitete:</span><span class="sxs-lookup"><span data-stu-id="fc557-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="fc557-111">Stranka: uporaba podatkov iz [poenotenega profila stranke](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="fc557-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="fc557-112">UnifiedActivity: prikaz [časovnice dejavnosti](activities.md) v aplikaciji</span><span class="sxs-lookup"><span data-stu-id="fc557-112">UnifiedActivity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="fc557-113">Omejitve</span><span class="sxs-lookup"><span data-stu-id="fc557-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="fc557-114">Entitete, ki jih je mogoče pridobiti</span><span class="sxs-lookup"><span data-stu-id="fc557-114">Retrievable entities</span></span>

<span data-ttu-id="fc557-115">Prek povezovalnika za Power Apps lahko pridobite samo entitete **Stranka**, **UnifiedActivity** in **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="fc557-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="fc557-116">Prikazane so druge entitete, ker jih osnovni povezovalnik podpira prek sprožilcev v storitvi Power Automate.</span><span class="sxs-lookup"><span data-stu-id="fc557-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="fc557-117">Pooblastitev</span><span class="sxs-lookup"><span data-stu-id="fc557-117">Delegation</span></span>

<span data-ttu-id="fc557-118">Pooblastitev deluje za entiteto »Stranka« in entiteto »UnifiedActivity«.</span><span class="sxs-lookup"><span data-stu-id="fc557-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="fc557-119">Pooblastitev za entiteto **Stranka**: če želite uporabiti pooblastitev za to entiteto, je treba polja indeksirati pri možnosti [Kazalo za iskanje in filtre](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="fc557-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="fc557-120">Pooblastitev za entiteto **UnifiedActivity**: pooblastitev za to entiteto deluje samo za polja **ActivityId** in **CustomerId**.</span><span class="sxs-lookup"><span data-stu-id="fc557-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="fc557-121">Za več informacij o pooblastitvi glejte [Funkcije in postopki v storitvi Power Apps. ki jih je mogoče pooblastiti](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span><span class="sxs-lookup"><span data-stu-id="fc557-121">For more information about delegation, see [Power Apps delegable functions and operations](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="fc557-122">Primer kontrolnika galerije</span><span class="sxs-lookup"><span data-stu-id="fc557-122">Example gallery control</span></span>

<span data-ttu-id="fc557-123">Profile strank na primer dodate v [kontrolnik galerije](/powerapps/maker/canvas-apps/add-gallery).</span><span class="sxs-lookup"><span data-stu-id="fc557-123">For example, you add customer profiles to a [gallery control](/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="fc557-124">Aplikaciji, ki jo ustvarjate, dodajte kontrolnik **Galerija**.</span><span class="sxs-lookup"><span data-stu-id="fc557-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="fc557-125">![Dodajanje elementa galerije](media/connector-powerapps9.png "Dodajanje elementa galerije")</span><span class="sxs-lookup"><span data-stu-id="fc557-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="fc557-126">Kot vir podatkov za elemente izberite **Stranka**.</span><span class="sxs-lookup"><span data-stu-id="fc557-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="fc557-127">![Izbira vira podatkov](media/choose-datasource-powerapps.png "Izbira vira podatkov")</span><span class="sxs-lookup"><span data-stu-id="fc557-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="fc557-128">Ploščo podatkov na desni strani lahko spremenite in izberete, katero polje za entiteto stranke bo prikazano v galeriji.</span><span class="sxs-lookup"><span data-stu-id="fc557-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="fc557-129">Če želite prikazati določeno polje iz izbrane stranke v galeriji, izpolnite lastnost »Besedilo« za nalepko: **{Name_of_the_gallery}.Selected.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="fc557-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="fc557-130">Primer: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="fc557-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="fc557-131">Če želite prikazati poenoteno časovnico za stranko, dodajte element galerije in lastnost »Elementi«: **('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="fc557-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="fc557-132">Primer: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="fc557-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]