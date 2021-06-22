---
title: Izvoz podatkov iz storitve Customer Insights
description: Upravljajte izvoze za skupno rabo podatkov.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6e7793fa99f8431d9d420529b39e0b5b5dbf6748
ms.sourcegitcommit: 0689e7ed4265855d1f76745d68af390f8f4af8a0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/14/2021
ms.locfileid: "6253060"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="e7637-103">Pregled izvozov (predogledna različica)</span><span class="sxs-lookup"><span data-stu-id="e7637-103">Exports (preview) overview</span></span>

<span data-ttu-id="e7637-104">Na strani **Izvozi** so prikazani vsi konfigurirani izvozi.</span><span class="sxs-lookup"><span data-stu-id="e7637-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="e7637-105">Izvozi dajo specifične podatke v skupno rabo z različnimi aplikacijami.</span><span class="sxs-lookup"><span data-stu-id="e7637-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="e7637-106">Vključujejo lahko profile strank ali entitete, sheme in podrobnosti o preslikavi.</span><span class="sxs-lookup"><span data-stu-id="e7637-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="e7637-107">Za vsak izvoz je potrebna [povezava, ki jo nastavi skrbnik, za upravljanje preverjanja pristnosti in dostopa](connections.md).</span><span class="sxs-lookup"><span data-stu-id="e7637-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="e7637-108">Pojdite na **Podatki** > **Izvozi** za ogled strani z izvozi.</span><span class="sxs-lookup"><span data-stu-id="e7637-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="e7637-109">Vse uporabniške vloge imajo dostop za ogled konfiguriranih izvozov.</span><span class="sxs-lookup"><span data-stu-id="e7637-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="e7637-110">Uporabite polje za iskanje v ukazni vrstici, da najdete izvoze po njihovem imenu, imenu povezave in vrsti povezave.</span><span class="sxs-lookup"><span data-stu-id="e7637-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="e7637-111">Nastavitev novega izvoza</span><span class="sxs-lookup"><span data-stu-id="e7637-111">Set up a new export</span></span>

<span data-ttu-id="e7637-112">Če želite nastaviti ali urediti izvoz, morate imeti na voljo povezave.</span><span class="sxs-lookup"><span data-stu-id="e7637-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="e7637-113">Povezave so odvisne od vaše [uporabniške vloge](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="e7637-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="e7637-114">Skrbniki imajo dostop do vseh povezav.</span><span class="sxs-lookup"><span data-stu-id="e7637-114">Administrators have access to all connections.</span></span> <span data-ttu-id="e7637-115">Pri nastavitvi izvoza lahko ustvarijo tudi nove povezave.</span><span class="sxs-lookup"><span data-stu-id="e7637-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="e7637-116">Udeleženci lahko imajo dostop do določenih povezav.</span><span class="sxs-lookup"><span data-stu-id="e7637-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="e7637-117">Pri konfiguriranju in skupni rabi povezav so odvisni od skrbnikov.</span><span class="sxs-lookup"><span data-stu-id="e7637-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="e7637-118">Seznam izvozov sodelavcem prikazuje, ali lahko urejajo ali samo ogledujejo izvoz v stolpcu **Vaša dovoljenja**.</span><span class="sxs-lookup"><span data-stu-id="e7637-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="e7637-119">Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e7637-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="e7637-120">Gledalci si lahko ogledajo samo obstoječe izvoze, vendar jih ne morejo ustvariti.</span><span class="sxs-lookup"><span data-stu-id="e7637-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="e7637-121">Določitev novega izvoza</span><span class="sxs-lookup"><span data-stu-id="e7637-121">Define a new export</span></span>

1. <span data-ttu-id="e7637-122">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="e7637-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e7637-123">Izberite možnost **Dodaj izvoz**, da ustvarite nov izvoz.</span><span class="sxs-lookup"><span data-stu-id="e7637-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="e7637-124">V podoknu **Nastavitev izvoza** izberite, katero povezavo uporabiti.</span><span class="sxs-lookup"><span data-stu-id="e7637-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="e7637-125">[Povezave](connections.md) upravljajo skrbniki.</span><span class="sxs-lookup"><span data-stu-id="e7637-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="e7637-126">Navedite zahtevane podrobnosti in izberite **Shrani**, da ustvarite izvoz.</span><span class="sxs-lookup"><span data-stu-id="e7637-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="e7637-127">Določitev novega izvoza na podlagi obstoječega izvoza</span><span class="sxs-lookup"><span data-stu-id="e7637-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="e7637-128">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="e7637-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e7637-129">Na seznamu izvozov izberite izvoz, ki ga želite podvojiti.</span><span class="sxs-lookup"><span data-stu-id="e7637-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="e7637-130">Izberite **Ustvari dvojnik** v ukazni vrstici, da odprete podokno **Nastavi izvoz** s podrobnostmi izbranega izvoza.</span><span class="sxs-lookup"><span data-stu-id="e7637-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="e7637-131">Preglejte in prilagodite izvoz ter izberite **Shrani**, da ustvarite nov izvoz.</span><span class="sxs-lookup"><span data-stu-id="e7637-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="e7637-132">Urejanje izvoza</span><span class="sxs-lookup"><span data-stu-id="e7637-132">Edit an export</span></span>

1. <span data-ttu-id="e7637-133">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="e7637-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e7637-134">Na seznamu izvozov izberite izvoz, ki ga želite urediti.</span><span class="sxs-lookup"><span data-stu-id="e7637-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="e7637-135">V ukazni vrstici izberite **Uredi**.</span><span class="sxs-lookup"><span data-stu-id="e7637-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="e7637-136">Spremenite vrednosti, ki jih želite posodobiti, in izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="e7637-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="e7637-137">Ogled izvozov in podrobnosti izvozov</span><span class="sxs-lookup"><span data-stu-id="e7637-137">View exports and export details</span></span>

<span data-ttu-id="e7637-138">Po ustvarjanju ciljev za izvoz so ti navedeni na **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="e7637-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="e7637-139">Vsi uporabniki lahko vidijo, kateri podatki so v skupni rabi in njihovo zadnje stanje.</span><span class="sxs-lookup"><span data-stu-id="e7637-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="e7637-140">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="e7637-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e7637-141">Uporabniki brez dovoljenj za urejanje izberejo **Ogled** namesto **Urejanje** za prikaz podrobnosti izvoza.</span><span class="sxs-lookup"><span data-stu-id="e7637-141">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="e7637-142">V stranskem podoknu je prikazana konfiguracija izvoza.</span><span class="sxs-lookup"><span data-stu-id="e7637-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="e7637-143">Brez dovoljenj za urejanje ne morete spreminjati vrednosti.</span><span class="sxs-lookup"><span data-stu-id="e7637-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="e7637-144">Izberite **Zapri**, da se vrnete na stran z izvozi.</span><span class="sxs-lookup"><span data-stu-id="e7637-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="e7637-145">Načrtovanje in zagon izvozov</span><span class="sxs-lookup"><span data-stu-id="e7637-145">Schedule and run exports</span></span>

<span data-ttu-id="e7637-146">Vsak izvoz, ki ga konfigurirate, ima urnik osveževanja.</span><span class="sxs-lookup"><span data-stu-id="e7637-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="e7637-147">Med osveževanjem sistem išče nove ali posodobljene podatke, ki jih bo vključil v izvoz.</span><span class="sxs-lookup"><span data-stu-id="e7637-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="e7637-148">Izvozi se privzeto izvajajo kot del vsakega [načrtovanega osveževanja sistema](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e7637-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e7637-149">Za ročni zagon izvozov lahko prilagodite urnik osveževanja ali ga izklopite.</span><span class="sxs-lookup"><span data-stu-id="e7637-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="e7637-150">Urniki izvoza so odvisni od stanja vašega okolja.</span><span class="sxs-lookup"><span data-stu-id="e7637-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="e7637-151">Če potekajo posodobitve [odvisnosti](system.md#refresh-policies), ko naj bi se začel načrtovani izvoz, bo sistem najprej dokončal odvisnosti in nato zagnal izvoz.</span><span class="sxs-lookup"><span data-stu-id="e7637-151">If there are updates on [dependencies](system.md#refresh-policies) in progress when a scheduled export should start, the system will first complete the dependencies and then run the export.</span></span> <span data-ttu-id="e7637-152">V stolpcu **Osveženo** lahko vidite, kdaj je bil izvoz nazadnje osvežen.</span><span class="sxs-lookup"><span data-stu-id="e7637-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="e7637-153">Načrtovanje izvozov</span><span class="sxs-lookup"><span data-stu-id="e7637-153">Schedule exports</span></span>

<span data-ttu-id="e7637-154">Določite lahko urnike osveževanja po meri za posamezen izvoz ali več izvozov hkrati.</span><span class="sxs-lookup"><span data-stu-id="e7637-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="e7637-155">Trenutno določen urnik je naveden v stolpcu **Načrtovanje** na seznamu izvoza.</span><span class="sxs-lookup"><span data-stu-id="e7637-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="e7637-156">Dovoljenje za spremembo urnika je enako kot za [urejanje in določanje izvozov](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e7637-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="e7637-157">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="e7637-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e7637-158">Izberite izvoz, ki ga želite načrtovati.</span><span class="sxs-lookup"><span data-stu-id="e7637-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="e7637-159">V ukazni vrstici izberite **Načrtovanje**.</span><span class="sxs-lookup"><span data-stu-id="e7637-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="e7637-160">V podoknu **Načrtovanje izvoza** nastavite **Zagon načrtovanja** na **Vklopljeno**, da samodejno zaženete izvoz.</span><span class="sxs-lookup"><span data-stu-id="e7637-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="e7637-161">Nastavite ga na **Izklopljeno**, da ga ročno osvežite.</span><span class="sxs-lookup"><span data-stu-id="e7637-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="e7637-162">Za samodejno osvežene izvoze izberite vrednost **Ponovitev** in določite podrobnosti zanjo.</span><span class="sxs-lookup"><span data-stu-id="e7637-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="e7637-163">Opredeljeni čas velja za vse primerke ponovitev.</span><span class="sxs-lookup"><span data-stu-id="e7637-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="e7637-164">To je čas, ko bi se izvoz moral začeti osveževati.</span><span class="sxs-lookup"><span data-stu-id="e7637-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="e7637-165">Svoje spremembe uveljavite in aktivirajte tako, da izberete **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="e7637-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="e7637-166">Pri urejanju urnika za več izvozov morate izbrati eno od možnosti v razdelku **Obdržite ali preglasite razporede**:</span><span class="sxs-lookup"><span data-stu-id="e7637-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="e7637-167">**Obdržite posamezne razporede**: obdržite predhodno določeni urnik za izbrane izvoze in jih le onemogočite ali omogočite.</span><span class="sxs-lookup"><span data-stu-id="e7637-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="e7637-168">**Določite nov urnik za vse izbrane izvoze**: preglasite obstoječe urnike izbranih izvozov.</span><span class="sxs-lookup"><span data-stu-id="e7637-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="e7637-169">Zaženi izvoze na zahtevo</span><span class="sxs-lookup"><span data-stu-id="e7637-169">Run exports on demand</span></span>

<span data-ttu-id="e7637-170">Za izvoz podatkov brez čakanja na načrtovano osvežitev, pojdite na **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="e7637-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="e7637-171">Če želite zagnati vse izvoze, izberite **Zaženi vse** v ukazni vrstici.</span><span class="sxs-lookup"><span data-stu-id="e7637-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="e7637-172">S tem dejanjem se bodo zagnali samo izvozi z aktivnim urnikom.</span><span class="sxs-lookup"><span data-stu-id="e7637-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="e7637-173">Če želite zagnati en izvoz, ga izberite na seznamu in kliknite **Zaženi** v ukazni vrstici.</span><span class="sxs-lookup"><span data-stu-id="e7637-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="e7637-174">Tako boste zagnali izvoze brez aktivnega urnika.</span><span class="sxs-lookup"><span data-stu-id="e7637-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="e7637-175">Odstranjevanje izvoza</span><span class="sxs-lookup"><span data-stu-id="e7637-175">Remove an Export</span></span>

1. <span data-ttu-id="e7637-176">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="e7637-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e7637-177">Izberite izvoz, ki ga želite odstraniti.</span><span class="sxs-lookup"><span data-stu-id="e7637-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="e7637-178">V ukazni vrstici izberite **Odstrani**.</span><span class="sxs-lookup"><span data-stu-id="e7637-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="e7637-179">Odstranjevanje potrdite tako, da na potrditvenem zaslonu izberete **Odstrani**.</span><span class="sxs-lookup"><span data-stu-id="e7637-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
