---
title: Cilji za izvoz
description: Izvozite podatke in upravljajte cilje za izvoz.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9032d99357db86e66588eda544211a5f8eb2f23b
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643883"
---
# <a name="export-destinations-preview"></a><span data-ttu-id="c3d1d-103">Cilji za izvoz (predogled)</span><span class="sxs-lookup"><span data-stu-id="c3d1d-103">Export destinations (preview)</span></span>

<span data-ttu-id="c3d1d-104">Stran **Cilji za izvoz** prikazuje vsa mesta, ki ste jih nastavili za izvoz podatkov.</span><span class="sxs-lookup"><span data-stu-id="c3d1d-104">The **Export destinations** page shows you all locations you've set up to export data to.</span></span> <span data-ttu-id="c3d1d-105">Dodate lahko tudi nove cilje za izvoz.</span><span class="sxs-lookup"><span data-stu-id="c3d1d-105">You can also add new destinations for export.</span></span> <span data-ttu-id="c3d1d-106">Poleg tega prikazuje trenutno razpoložljive možnosti za izvoz.</span><span class="sxs-lookup"><span data-stu-id="c3d1d-106">Additionally, it shows export currently available options.</span></span> <span data-ttu-id="c3d1d-107">Pridobite hiter pregled, opis in informacije o tem, kaj lahko storite z vsako možnostjo razširljivosti.</span><span class="sxs-lookup"><span data-stu-id="c3d1d-107">Get a quick overview, description, and find out what you can do with each extensibility option.</span></span> <span data-ttu-id="c3d1d-108">Izvozite poenotene profile, mere in segmente v podprte aplikacije, relevantne za vaše poslovanje.</span><span class="sxs-lookup"><span data-stu-id="c3d1d-108">Export unified profiles, measures, and segments to supported apps relevant for your business.</span></span>

<span data-ttu-id="c3d1d-109">Odprite **Skrbnik** > **Cilji za izvoz**, da poiščete naslednje možnosti razširljivosti:</span><span class="sxs-lookup"><span data-stu-id="c3d1d-109">Go to **Admin** > **Export destinations** to find the following extensibility options:</span></span>

- [<span data-ttu-id="c3d1d-110">Dodatek za kartico stranke v Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="c3d1d-110">Dynamics 365 Customer Card Add-in</span></span>](customer-card-add-in.md)
- [<span data-ttu-id="c3d1d-111">Povezovalnik upravitelja oglasov kanala Facebook</span><span class="sxs-lookup"><span data-stu-id="c3d1d-111">Facebook Ads Manager connector</span></span>](export-facebook.md)
- [<span data-ttu-id="c3d1d-112">Povezovalnik Power Automate</span><span class="sxs-lookup"><span data-stu-id="c3d1d-112">Power Automate connector</span></span>](export-power-automate.md)
- [<span data-ttu-id="c3d1d-113">Povezovalnik Power Apps</span><span class="sxs-lookup"><span data-stu-id="c3d1d-113">Power Apps connector</span></span>](export-power-apps.md)
- [<span data-ttu-id="c3d1d-114">Povezovalnik Power BI</span><span class="sxs-lookup"><span data-stu-id="c3d1d-114">Power BI connector</span></span>](export-power-bi.md)
- [<span data-ttu-id="c3d1d-115">DotDigital</span><span class="sxs-lookup"><span data-stu-id="c3d1d-115">DotDigital</span></span>](export-dotdigital.md)
- [<span data-ttu-id="c3d1d-116">Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="c3d1d-116">Dynamics 365 Sales</span></span>](export-dynamics365-sales.md)
- [<span data-ttu-id="c3d1d-117">Dynamics 365 Marketing</span><span class="sxs-lookup"><span data-stu-id="c3d1d-117">Dynamics 365 Marketing</span></span>](export-dynamics365-marketing.md)
- [<span data-ttu-id="c3d1d-118">Shramba zbirke dvojiških podatkov Azure</span><span class="sxs-lookup"><span data-stu-id="c3d1d-118">Azure Blob Storage</span></span>](export-azure-blob-storage.md)
- [<span data-ttu-id="c3d1d-119">Povezovalnik LiveRamp &reg;</span><span class="sxs-lookup"><span data-stu-id="c3d1d-119">LiveRamp&reg; connector</span></span>](export-liveramp.md)
- [<span data-ttu-id="c3d1d-120">Bot za Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c3d1d-120">Bot for Microsoft Teams</span></span>](export-teams-bot.md)
- [<span data-ttu-id="c3d1d-121">MailChimp</span><span class="sxs-lookup"><span data-stu-id="c3d1d-121">Mailchimp</span></span>](export-mailchimp.md)
- [<span data-ttu-id="c3d1d-122">API za Customer Insights</span><span class="sxs-lookup"><span data-stu-id="c3d1d-122">Customer Insights API</span></span>](apis.md)

## <a name="add-a-new-export-destination"></a><span data-ttu-id="c3d1d-123">Dodajanje novega cilja za izvoz</span><span class="sxs-lookup"><span data-stu-id="c3d1d-123">Add a new export destination</span></span>

<span data-ttu-id="c3d1d-124">Če želite dodati cilje za izvoz, morate imeti [skrbniška dovoljenja](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="c3d1d-124">To add export destinations, you have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="c3d1d-125">Če izvažate v Microsoftove storitve, domnevamo, da so vse storitve v isti organizaciji.</span><span class="sxs-lookup"><span data-stu-id="c3d1d-125">If you export to Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="c3d1d-126">Izberite **Skrbnik** > **Cilji za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="c3d1d-126">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c3d1d-127">Preklopite na zavihek **Moji cilji za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="c3d1d-127">Switch to the **My export destinations** tab.</span></span>

1. <span data-ttu-id="c3d1d-128">Izberite **Dodaj cilj**, da ustvarite nov cilj za izvoz.</span><span class="sxs-lookup"><span data-stu-id="c3d1d-128">Select **Add destination** to create a new export destination.</span></span>

1. <span data-ttu-id="c3d1d-129">V podoknu **Dodaj cilj** v spustnem seznamu izberite možnost za **Vrsta** za cilj za izvoz.</span><span class="sxs-lookup"><span data-stu-id="c3d1d-129">In the **Add destination** pane, select the **Type** of export destination in the drop-down.</span></span>

1. <span data-ttu-id="c3d1d-130">Zagotovite zahtevane podrobnosti in izberite **Naprej**, da ustvarite cilj za izvoz.</span><span class="sxs-lookup"><span data-stu-id="c3d1d-130">Provide the required details and select **Next** to create the export destination.</span></span>

<span data-ttu-id="c3d1d-131">Izberete lahko tudi **Nastavitev** na ploščici na zavihku **Odkrivanje**.</span><span class="sxs-lookup"><span data-stu-id="c3d1d-131">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

## <a name="view-export-destinations"></a><span data-ttu-id="c3d1d-132">Pogled ciljev za izvoz</span><span class="sxs-lookup"><span data-stu-id="c3d1d-132">View Export destinations</span></span>

<span data-ttu-id="c3d1d-133">Po ustvarjanju ciljev za izvoz jih boste našli v tabeli na zavihku **Moji cilji za izvoz**. Ta tabela ima tri stolpce:</span><span class="sxs-lookup"><span data-stu-id="c3d1d-133">After creating export destinations, you'll find them in a table on the **My export destinations** tab. This table has three columns:</span></span>

- <span data-ttu-id="c3d1d-134">**Prikazno ime**: ime, ki ste ga vnesli pri ustvarjanju cilja.</span><span class="sxs-lookup"><span data-stu-id="c3d1d-134">**Display name**: The name you entered when creating the destination.</span></span>
- <span data-ttu-id="c3d1d-135">**Vrsta**: vrsta cilja za izvoz, ki ga nastavite, ko ustvarite cilj.</span><span class="sxs-lookup"><span data-stu-id="c3d1d-135">**Type**: The export destination type you set when creating the destination.</span></span>
- <span data-ttu-id="c3d1d-136">**Ustvarjeno**: datum, ko ste ustvarili cilj.</span><span class="sxs-lookup"><span data-stu-id="c3d1d-136">**Created**: The date you created the destination.</span></span>

## <a name="edit-an-export-destination"></a><span data-ttu-id="c3d1d-137">Urejanje cilja za izvoz</span><span class="sxs-lookup"><span data-stu-id="c3d1d-137">Edit an export destination</span></span>

1. <span data-ttu-id="c3d1d-138">Izberite navpične tri pike pri cilju za izvoz, ki ga želite urediti.</span><span class="sxs-lookup"><span data-stu-id="c3d1d-138">Select the vertical ellipsis for the Export destination you want to edit.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c3d1d-139">![Navpične tri pike](media/export-destinations-page-ellipsis.png "Navpične tri pike")</span><span class="sxs-lookup"><span data-stu-id="c3d1d-139">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

1. <span data-ttu-id="c3d1d-140">V spustnem meniju izberite **Uredi**.</span><span class="sxs-lookup"><span data-stu-id="c3d1d-140">Select **Edit** from the dropdown menu.</span></span>

1. <span data-ttu-id="c3d1d-141">Spremenite vrednosti, ki potrebujejo posodobitev, in izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="c3d1d-141">Change the values that require update and select **Save**.</span></span>

## <a name="export-data-on-demand"></a><span data-ttu-id="c3d1d-142">Izvoz podatkov na zahtevo</span><span class="sxs-lookup"><span data-stu-id="c3d1d-142">Export data on demand</span></span>

<span data-ttu-id="c3d1d-143">Po konfiguraciji povezovalnika za cilj za izvoz se izvozi zaženejo z vsako [načrtovano osvežitvijo](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c3d1d-143">After configuring a connector for an export destination, exports will run with every [scheduled refresh](system.md#schedule-tab).</span></span>

<span data-ttu-id="c3d1d-144">Če želite izvoziti podatke brez čakanja na načrtovano osvežitev, odprite zavihek **Moji cilji za izvoz** v možnosti **Skrbnik** > **Cilji za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="c3d1d-144">To export data without waiting for a scheduled refresh, go the **My export destinations** tab on **Admin** > **Export destinations**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c3d1d-145">![Navpične tri pike](media/export-destinations-page-ellipsis.png "Navpične tri pike")</span><span class="sxs-lookup"><span data-stu-id="c3d1d-145">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

- <span data-ttu-id="c3d1d-146">Izberite **Izvozi** nad seznamom, da zaženete izvoz v vse cilje za izvoz hkrati.</span><span class="sxs-lookup"><span data-stu-id="c3d1d-146">Select **Export** above the list to run the export to all export destinations simultaneously.</span></span>
- <span data-ttu-id="c3d1d-147">Izberite tri pike (...) za elementom na seznamu in nato izberite možnost **Izvoz**, da zaženete izvoz za en cilj za izvoz.</span><span class="sxs-lookup"><span data-stu-id="c3d1d-147">Select the ellipsis (...) after a list item and then choose the **Export** option to run the export for a single export destination.</span></span>

## <a name="remove-an-export-destination"></a><span data-ttu-id="c3d1d-148">Odstranjevanje cilja za izvoz</span><span class="sxs-lookup"><span data-stu-id="c3d1d-148">Remove an Export destination</span></span>

<span data-ttu-id="c3d1d-149">Če želite odstraniti cilj za izvoz, začnite na glavni strani **Cilji za izvoz**.</span><span class="sxs-lookup"><span data-stu-id="c3d1d-149">To remove an Export destination, start from the main **Export destinations** page.</span></span>

1. <span data-ttu-id="c3d1d-150">Izberite navpične tri pike pri cilju za izvoz, ki ga želite odstraniti.</span><span class="sxs-lookup"><span data-stu-id="c3d1d-150">Select the vertical ellipsis for the Export destination you want to remove.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c3d1d-151">![Navpične tri pike](media/export-destinations-page-ellipsis.png "Navpične tri pike")</span><span class="sxs-lookup"><span data-stu-id="c3d1d-151">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

2. <span data-ttu-id="c3d1d-152">Na spustnem seznamu izberite **Odstrani**.</span><span class="sxs-lookup"><span data-stu-id="c3d1d-152">Select **Remove** from the dropdown menu.</span></span>

3. <span data-ttu-id="c3d1d-153">Odstranjevanje potrdite tako, da na potrditvenem zaslonu izberete **Odstrani**.</span><span class="sxs-lookup"><span data-stu-id="c3d1d-153">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>
