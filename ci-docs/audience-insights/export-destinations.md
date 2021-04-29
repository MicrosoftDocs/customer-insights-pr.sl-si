---
title: Izvoz podatkov iz storitve Customer Insights
description: Upravljajte izvoze za skupno rabo podatkov.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896163"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="04bcd-103">Pregled izvozov (predogledna različica)</span><span class="sxs-lookup"><span data-stu-id="04bcd-103">Exports (preview) overview</span></span>

<span data-ttu-id="04bcd-104">Na strani **Izvozi** so prikazani vsi konfigurirani izvozi.</span><span class="sxs-lookup"><span data-stu-id="04bcd-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="04bcd-105">Izvozi dajo specifične podatke v skupno rabo z različnimi aplikacijami.</span><span class="sxs-lookup"><span data-stu-id="04bcd-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="04bcd-106">Vključujejo lahko profile strank ali entitete, sheme in podrobnosti o preslikavi.</span><span class="sxs-lookup"><span data-stu-id="04bcd-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="04bcd-107">Za vsak izvoz je potrebna [povezava, ki jo nastavi skrbnik, za upravljanje preverjanja pristnosti in dostopa](connections.md).</span><span class="sxs-lookup"><span data-stu-id="04bcd-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

> [!NOTE]
> <span data-ttu-id="04bcd-108">Do marca 2021 so izvozi samodejno ustvarili povezavo s pripadajočo storitvijo.</span><span class="sxs-lookup"><span data-stu-id="04bcd-108">Until March 2021, exports created a connection to the corresponding service automatically.</span></span> <span data-ttu-id="04bcd-109">Zdaj je za izvoze potrebna [povezava, ki jo ustvari in da v skupno rabo skrbnik](connections.md), preden je možno ustvarjanje.</span><span class="sxs-lookup"><span data-stu-id="04bcd-109">Exports now require a [connection, created and shared by an administrator](connections.md) before you can create them.</span></span>

<span data-ttu-id="04bcd-110">Pojdite na **Podatki** > **Izvozi** za ogled strani z izvozi.</span><span class="sxs-lookup"><span data-stu-id="04bcd-110">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="04bcd-111">Vse uporabniške vloge imajo dostop za ogled konfiguriranih izvozov.</span><span class="sxs-lookup"><span data-stu-id="04bcd-111">All user roles have access to view configured exports.</span></span> <span data-ttu-id="04bcd-112">Uporabite polje za iskanje v ukazni vrstici, da najdete izvoze po njihovem imenu, imenu povezave in vrsti povezave.</span><span class="sxs-lookup"><span data-stu-id="04bcd-112">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="04bcd-113">Nastavitev novega izvoza</span><span class="sxs-lookup"><span data-stu-id="04bcd-113">Set up a new export</span></span>

<span data-ttu-id="04bcd-114">Če želite nastaviti ali urediti izvoz, morate imeti na voljo povezave.</span><span class="sxs-lookup"><span data-stu-id="04bcd-114">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="04bcd-115">Povezave so odvisne od vaše [uporabniške vloge](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="04bcd-115">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="04bcd-116">Skrbniki imajo dostop do vseh povezav.</span><span class="sxs-lookup"><span data-stu-id="04bcd-116">Administrators have access to all connections.</span></span> <span data-ttu-id="04bcd-117">Pri nastavitvi izvoza lahko ustvarijo tudi nove povezave.</span><span class="sxs-lookup"><span data-stu-id="04bcd-117">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="04bcd-118">Udeleženci lahko imajo dostop do določenih povezav.</span><span class="sxs-lookup"><span data-stu-id="04bcd-118">Contributors can have access to specific connections.</span></span> <span data-ttu-id="04bcd-119">Pri konfiguriranju in skupni rabi povezav so odvisni od skrbnikov.</span><span class="sxs-lookup"><span data-stu-id="04bcd-119">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="04bcd-120">Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="04bcd-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="04bcd-121">Gledalci si lahko ogledajo samo obstoječe izvoze, vendar jih ne morejo ustvariti.</span><span class="sxs-lookup"><span data-stu-id="04bcd-121">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="04bcd-122">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="04bcd-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="04bcd-123">Izberite **Dodaj izvoz** za ustvarjanje novega cilja za izvoz.</span><span class="sxs-lookup"><span data-stu-id="04bcd-123">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="04bcd-124">V podoknu **Nastavitev izvoza** izberite, katero povezavo uporabiti.</span><span class="sxs-lookup"><span data-stu-id="04bcd-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="04bcd-125">[Povezave](connections.md) upravljajo skrbniki.</span><span class="sxs-lookup"><span data-stu-id="04bcd-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="04bcd-126">Navedite zahtevane podrobnosti in izberite **Shrani**, da ustvarite izvoz.</span><span class="sxs-lookup"><span data-stu-id="04bcd-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="04bcd-127">Urejanje izvoza</span><span class="sxs-lookup"><span data-stu-id="04bcd-127">Edit an export</span></span>

1. <span data-ttu-id="04bcd-128">Izberite navpične tri pike pri cilju za izvoz, ki ga želite urediti.</span><span class="sxs-lookup"><span data-stu-id="04bcd-128">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="04bcd-129">V spustnem meniju izberite **Uredi**.</span><span class="sxs-lookup"><span data-stu-id="04bcd-129">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="04bcd-130">Spremenite vrednosti, ki jih želite posodobiti, in izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="04bcd-130">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="04bcd-131">Ogled izvozov in podrobnosti izvozov</span><span class="sxs-lookup"><span data-stu-id="04bcd-131">View Exports and export details</span></span>

<span data-ttu-id="04bcd-132">Po ustvarjanju ciljev za izvoz so ti navedeni na **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="04bcd-132">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="04bcd-133">Vsi uporabniki lahko vidijo, kateri podatki so v skupni rabi in njihovo zadnje stanje.</span><span class="sxs-lookup"><span data-stu-id="04bcd-133">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="04bcd-134">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="04bcd-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="04bcd-135">Uporabniki brez dovoljenj za urejanje izberejo **Ogled** namesto **Urejanje** za prikaz podrobnosti izvoza.</span><span class="sxs-lookup"><span data-stu-id="04bcd-135">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="04bcd-136">V tem stranskem podoknu je prikazana nastavitev tega izvoza.</span><span class="sxs-lookup"><span data-stu-id="04bcd-136">This side pane shows the set up of this export.</span></span> <span data-ttu-id="04bcd-137">Brez dovoljenj za urejanje ne morete spreminjati vrednosti.</span><span class="sxs-lookup"><span data-stu-id="04bcd-137">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="04bcd-138">Izberite **Zapri**, da se vrnete na stran z izvozi.</span><span class="sxs-lookup"><span data-stu-id="04bcd-138">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="04bcd-139">Zaženi izvoze na zahtevo</span><span class="sxs-lookup"><span data-stu-id="04bcd-139">Run exports on demand</span></span>

<span data-ttu-id="04bcd-140">Po konfiguraciji izvoza se bo ta zagnal z vsako [načrtovano osvežitvijo](system.md#schedule-tab), če le ima delujočo povezavo.</span><span class="sxs-lookup"><span data-stu-id="04bcd-140">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="04bcd-141">Za izvoz podatkov brez čakanja na načrtovano osvežitev, pojdite na **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="04bcd-141">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="04bcd-142">Na voljo imate dve možnosti:</span><span class="sxs-lookup"><span data-stu-id="04bcd-142">You have two options:</span></span>

- <span data-ttu-id="04bcd-143">Če želite zagnati vse izvoze, izberite **Zaženi vse** v ukazni vrstici.</span><span class="sxs-lookup"><span data-stu-id="04bcd-143">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="04bcd-144">Če želite zagnati en izvoz, izberite tri pike (...) na elementu seznama in nato izberite **Zagon**.</span><span class="sxs-lookup"><span data-stu-id="04bcd-144">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="04bcd-145">Odstranjevanje izvoza</span><span class="sxs-lookup"><span data-stu-id="04bcd-145">Remove an Export</span></span>

1. <span data-ttu-id="04bcd-146">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="04bcd-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="04bcd-147">Izberite navpične tri pike pri izvozu, ki ga želite odstraniti.</span><span class="sxs-lookup"><span data-stu-id="04bcd-147">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="04bcd-148">Na spustnem seznamu izberite **Odstrani**.</span><span class="sxs-lookup"><span data-stu-id="04bcd-148">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="04bcd-149">Odstranjevanje potrdite tako, da na potrditvenem zaslonu izberete **Odstrani**.</span><span class="sxs-lookup"><span data-stu-id="04bcd-149">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
