---
title: Izvoz podatkov iz storitve Customer Insights
description: Upravljajte izvoze za skupno rabo podatkov.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016656"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="2fb57-103">Pregled izvozov (predogledna različica)</span><span class="sxs-lookup"><span data-stu-id="2fb57-103">Exports (preview) overview</span></span>

<span data-ttu-id="2fb57-104">Na strani **Izvozi** so prikazani vsi konfigurirani izvozi.</span><span class="sxs-lookup"><span data-stu-id="2fb57-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="2fb57-105">Izvozi dajo specifične podatke v skupno rabo z različnimi aplikacijami.</span><span class="sxs-lookup"><span data-stu-id="2fb57-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="2fb57-106">Vključujejo lahko profile strank ali entitete, sheme in podrobnosti o preslikavi.</span><span class="sxs-lookup"><span data-stu-id="2fb57-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="2fb57-107">Za vsak izvoz je potrebna [povezava, ki jo nastavi skrbnik, za upravljanje preverjanja pristnosti in dostopa](connections.md).</span><span class="sxs-lookup"><span data-stu-id="2fb57-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="2fb57-108">Pojdite na **Podatki** > **Izvozi** za ogled strani z izvozi.</span><span class="sxs-lookup"><span data-stu-id="2fb57-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="2fb57-109">Vse uporabniške vloge imajo dostop za ogled konfiguriranih izvozov.</span><span class="sxs-lookup"><span data-stu-id="2fb57-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="2fb57-110">Uporabite polje za iskanje v ukazni vrstici, da najdete izvoze po njihovem imenu, imenu povezave in vrsti povezave.</span><span class="sxs-lookup"><span data-stu-id="2fb57-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="2fb57-111">Nastavitev novega izvoza</span><span class="sxs-lookup"><span data-stu-id="2fb57-111">Set up a new export</span></span>

<span data-ttu-id="2fb57-112">Če želite nastaviti ali urediti izvoz, morate imeti na voljo povezave.</span><span class="sxs-lookup"><span data-stu-id="2fb57-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="2fb57-113">Povezave so odvisne od vaše [uporabniške vloge](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="2fb57-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="2fb57-114">Skrbniki imajo dostop do vseh povezav.</span><span class="sxs-lookup"><span data-stu-id="2fb57-114">Administrators have access to all connections.</span></span> <span data-ttu-id="2fb57-115">Pri nastavitvi izvoza lahko ustvarijo tudi nove povezave.</span><span class="sxs-lookup"><span data-stu-id="2fb57-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="2fb57-116">Udeleženci lahko imajo dostop do določenih povezav.</span><span class="sxs-lookup"><span data-stu-id="2fb57-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="2fb57-117">Pri konfiguriranju in skupni rabi povezav so odvisni od skrbnikov.</span><span class="sxs-lookup"><span data-stu-id="2fb57-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="2fb57-118">Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="2fb57-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="2fb57-119">Gledalci si lahko ogledajo samo obstoječe izvoze, vendar jih ne morejo ustvariti.</span><span class="sxs-lookup"><span data-stu-id="2fb57-119">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="2fb57-120">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="2fb57-120">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2fb57-121">Izberite **Dodaj izvoz** za ustvarjanje novega cilja za izvoz.</span><span class="sxs-lookup"><span data-stu-id="2fb57-121">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="2fb57-122">V podoknu **Nastavitev izvoza** izberite, katero povezavo uporabiti.</span><span class="sxs-lookup"><span data-stu-id="2fb57-122">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="2fb57-123">[Povezave](connections.md) upravljajo skrbniki.</span><span class="sxs-lookup"><span data-stu-id="2fb57-123">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="2fb57-124">Navedite zahtevane podrobnosti in izberite **Shrani**, da ustvarite izvoz.</span><span class="sxs-lookup"><span data-stu-id="2fb57-124">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="2fb57-125">Urejanje izvoza</span><span class="sxs-lookup"><span data-stu-id="2fb57-125">Edit an export</span></span>

1. <span data-ttu-id="2fb57-126">Izberite navpične tri pike pri cilju za izvoz, ki ga želite urediti.</span><span class="sxs-lookup"><span data-stu-id="2fb57-126">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="2fb57-127">V spustnem meniju izberite **Uredi**.</span><span class="sxs-lookup"><span data-stu-id="2fb57-127">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="2fb57-128">Spremenite vrednosti, ki jih želite posodobiti, in izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="2fb57-128">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="2fb57-129">Ogled izvozov in podrobnosti izvozov</span><span class="sxs-lookup"><span data-stu-id="2fb57-129">View Exports and export details</span></span>

<span data-ttu-id="2fb57-130">Po ustvarjanju ciljev za izvoz so ti navedeni na **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="2fb57-130">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="2fb57-131">Vsi uporabniki lahko vidijo, kateri podatki so v skupni rabi in njihovo zadnje stanje.</span><span class="sxs-lookup"><span data-stu-id="2fb57-131">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="2fb57-132">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="2fb57-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2fb57-133">Uporabniki brez dovoljenj za urejanje izberejo **Ogled** namesto **Urejanje** za prikaz podrobnosti izvoza.</span><span class="sxs-lookup"><span data-stu-id="2fb57-133">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="2fb57-134">V tem stranskem podoknu je prikazana nastavitev tega izvoza.</span><span class="sxs-lookup"><span data-stu-id="2fb57-134">This side pane shows the set up of this export.</span></span> <span data-ttu-id="2fb57-135">Brez dovoljenj za urejanje ne morete spreminjati vrednosti.</span><span class="sxs-lookup"><span data-stu-id="2fb57-135">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="2fb57-136">Izberite **Zapri**, da se vrnete na stran z izvozi.</span><span class="sxs-lookup"><span data-stu-id="2fb57-136">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="2fb57-137">Zaženi izvoze na zahtevo</span><span class="sxs-lookup"><span data-stu-id="2fb57-137">Run exports on demand</span></span>

<span data-ttu-id="2fb57-138">Po konfiguraciji izvoza se bo ta zagnal z vsako [načrtovano osvežitvijo](system.md#schedule-tab), če le ima delujočo povezavo.</span><span class="sxs-lookup"><span data-stu-id="2fb57-138">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="2fb57-139">Za izvoz podatkov brez čakanja na načrtovano osvežitev, pojdite na **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="2fb57-139">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="2fb57-140">Na voljo imate dve možnosti:</span><span class="sxs-lookup"><span data-stu-id="2fb57-140">You have two options:</span></span>

- <span data-ttu-id="2fb57-141">Če želite zagnati vse izvoze, izberite **Zaženi vse** v ukazni vrstici.</span><span class="sxs-lookup"><span data-stu-id="2fb57-141">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="2fb57-142">Če želite zagnati en izvoz, izberite tri pike (...) na elementu seznama in nato izberite **Zagon**.</span><span class="sxs-lookup"><span data-stu-id="2fb57-142">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="2fb57-143">Odstranjevanje izvoza</span><span class="sxs-lookup"><span data-stu-id="2fb57-143">Remove an Export</span></span>

1. <span data-ttu-id="2fb57-144">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="2fb57-144">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2fb57-145">Izberite navpične tri pike pri izvozu, ki ga želite odstraniti.</span><span class="sxs-lookup"><span data-stu-id="2fb57-145">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="2fb57-146">Na spustnem seznamu izberite **Odstrani**.</span><span class="sxs-lookup"><span data-stu-id="2fb57-146">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="2fb57-147">Odstranjevanje potrdite tako, da na potrditvenem zaslonu izberete **Odstrani**.</span><span class="sxs-lookup"><span data-stu-id="2fb57-147">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
