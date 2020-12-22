---
title: Povezovalnik Power Apps
description: Povezava s storitvama Power Apps in Power Automate.
ms.date: 08/21/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b6ec103e29e218b2f27bfc1193300ea793a6b30b
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406949"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="44958-103">Povezovalnik storitve Microsoft Power Apps (predogled)</span><span class="sxs-lookup"><span data-stu-id="44958-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="44958-104">Vnesite poenotene profile strank v svoje prilagojene aplikacije s storitvijo Power Apps.</span><span class="sxs-lookup"><span data-stu-id="44958-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="44958-105">Povezava storitev Power Apps in Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="44958-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="44958-106">Storitev Customer Insights je ena od mnogih [razpoložljivih virov podatkov v storitvi Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span><span class="sxs-lookup"><span data-stu-id="44958-106">Customer Insights is one of the many [available sources for data in Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="44958-107">Oglejte si dokumentacijo za Power Apps, če želite izvedeti več o [dodajanju podatkovne povezave v aplikacijo](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span><span class="sxs-lookup"><span data-stu-id="44958-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="44958-108">Priporočamo, da pregledate tudi [kako se v storitvi Power Apps uporablja pooblastitve za obdelavo velikih množic podatkov v aplikacijah s platnom](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span><span class="sxs-lookup"><span data-stu-id="44958-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="44958-109">Entitete, ki so na voljo</span><span class="sxs-lookup"><span data-stu-id="44958-109">Available entities</span></span>

<span data-ttu-id="44958-110">Ko dodate storitev Customer Insights kot podatkovno povezavo, lahko v storitvi Power Apps izberete naslednje entitete:</span><span class="sxs-lookup"><span data-stu-id="44958-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="44958-111">Stranka: uporaba podatkov iz [poenotenega profila stranke](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="44958-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="44958-112">Poenotena dejavnost stranke: prikaz [časovnice dejavnosti](activities.md) v aplikaciji.</span><span class="sxs-lookup"><span data-stu-id="44958-112">Unified Customer Activity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="44958-113">Omejitve</span><span class="sxs-lookup"><span data-stu-id="44958-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="44958-114">Entitete, ki jih je mogoče pridobiti</span><span class="sxs-lookup"><span data-stu-id="44958-114">Retrievable entities</span></span>

<span data-ttu-id="44958-115">Prek povezovalnika za Power Apps lahko pridobite samo entitete **Stranka**, **UnifiedActivity** in **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="44958-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="44958-116">Prikazane so druge entitete, ker jih osnovni povezovalnik podpira prek sprožilcev v storitvi Power Automate.</span><span class="sxs-lookup"><span data-stu-id="44958-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="44958-117">Pooblastitev</span><span class="sxs-lookup"><span data-stu-id="44958-117">Delegation</span></span>

<span data-ttu-id="44958-118">Pooblastitev deluje za entiteto »Stranka« in entiteto »UnifiedActivity«.</span><span class="sxs-lookup"><span data-stu-id="44958-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="44958-119">Pooblastitev za entiteto **Stranka**: če želite uporabiti pooblastitev za to entiteto, je treba polja indeksirati pri možnosti [Kazalo za iskanje in filtre](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="44958-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="44958-120">Pooblastitev za entiteto **UnifiedActivity**: pooblastitev za to entiteto deluje samo za polja **ActivityId** in **CustomerId**.</span><span class="sxs-lookup"><span data-stu-id="44958-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="44958-121">Za več informacij o pooblastitvi glejte [Funkcije in postopki v storitvi Power Apps. ki jih je mogoče pooblastiti](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span><span class="sxs-lookup"><span data-stu-id="44958-121">For more information about delegation, see [Power Apps delegable functions and operations](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="44958-122">Primer kontrolnika galerije</span><span class="sxs-lookup"><span data-stu-id="44958-122">Example gallery control</span></span>

<span data-ttu-id="44958-123">Profile strank na primer dodate v [kontrolnik galerije](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span><span class="sxs-lookup"><span data-stu-id="44958-123">For example, you add customer profiles to a [gallery control](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="44958-124">Aplikaciji, ki jo ustvarjate, dodajte kontrolnik **Galerija**.</span><span class="sxs-lookup"><span data-stu-id="44958-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="44958-125">![Dodajanje elementa galerije](media/connector-powerapps9.png "Dodajanje elementa galerije")</span><span class="sxs-lookup"><span data-stu-id="44958-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="44958-126">Kot vir podatkov za elemente izberite **Stranka**.</span><span class="sxs-lookup"><span data-stu-id="44958-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="44958-127">![Izbira vira podatkov](media/choose-datasource-powerapps.png "Izbira vira podatkov")</span><span class="sxs-lookup"><span data-stu-id="44958-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="44958-128">Ploščo podatkov na desni strani lahko spremenite in izberete, katero polje za entiteto stranke bo prikazano v galeriji.</span><span class="sxs-lookup"><span data-stu-id="44958-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="44958-129">Če želite prikazati določeno polje iz izbrane stranke v galeriji, izpolnite lastnost »Besedilo« za nalepko: **{Name_of_the_gallery}.Selected.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="44958-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="44958-130">Primer: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="44958-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="44958-131">Če želite prikazati poenoteno časovnico za stranko, dodajte element galerije in lastnost »Elementi«: **('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="44958-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="44958-132">Primer: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="44958-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>
