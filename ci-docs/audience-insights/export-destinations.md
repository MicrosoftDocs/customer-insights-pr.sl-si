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
ms.openlocfilehash: 28563e3a76535cb0c92bfcda4ef5037430d00cfa
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305498"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="6a089-103">Pregled izvozov (predogledna različica)</span><span class="sxs-lookup"><span data-stu-id="6a089-103">Exports (preview) overview</span></span>

<span data-ttu-id="6a089-104">Na strani **Izvozi** so prikazani vsi konfigurirani izvozi.</span><span class="sxs-lookup"><span data-stu-id="6a089-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="6a089-105">Izvozi dajo specifične podatke v skupno rabo z različnimi aplikacijami.</span><span class="sxs-lookup"><span data-stu-id="6a089-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="6a089-106">Vključujejo lahko profile strank ali entitete, sheme in podrobnosti o preslikavi.</span><span class="sxs-lookup"><span data-stu-id="6a089-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="6a089-107">Za vsak izvoz je potrebna [povezava, ki jo nastavi skrbnik, za upravljanje preverjanja pristnosti in dostopa](connections.md).</span><span class="sxs-lookup"><span data-stu-id="6a089-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="6a089-108">Pojdite na **Podatki** > **Izvozi** za ogled strani z izvozi.</span><span class="sxs-lookup"><span data-stu-id="6a089-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="6a089-109">Konfigurirani izvozi so za ogled na voljo vsem uporabniškim vlogam.</span><span class="sxs-lookup"><span data-stu-id="6a089-109">All user roles can view configured exports.</span></span> <span data-ttu-id="6a089-110">S pomočjo iskalnega polja v ukazni vrstici poiščite izvoze glede na njihovo poimenovanje, ime povezave ali vrsto povezave.</span><span class="sxs-lookup"><span data-stu-id="6a089-110">Use the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="6a089-111">Nastavitev novega izvoza</span><span class="sxs-lookup"><span data-stu-id="6a089-111">Set up a new export</span></span>

<span data-ttu-id="6a089-112">Če želite nastaviti ali urediti izvoz, morate imeti na voljo povezave.</span><span class="sxs-lookup"><span data-stu-id="6a089-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="6a089-113">Povezave so odvisne od vaše [uporabniške vloge](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="6a089-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="6a089-114">Skrbniki imajo dostop do vseh povezav.</span><span class="sxs-lookup"><span data-stu-id="6a089-114">Administrators have access to all connections.</span></span> <span data-ttu-id="6a089-115">Pri nastavitvi izvoza lahko ustvarijo tudi nove povezave.</span><span class="sxs-lookup"><span data-stu-id="6a089-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="6a089-116">Udeleženci lahko imajo dostop do določenih povezav.</span><span class="sxs-lookup"><span data-stu-id="6a089-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="6a089-117">Pri konfiguriranju in skupni rabi povezav so odvisni od skrbnikov.</span><span class="sxs-lookup"><span data-stu-id="6a089-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="6a089-118">Seznam izvozov sodelavcem prikazuje, ali lahko urejajo ali samo ogledujejo izvoz v stolpcu **Vaša dovoljenja**.</span><span class="sxs-lookup"><span data-stu-id="6a089-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="6a089-119">Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="6a089-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="6a089-120">Gledalci si lahko ogledajo samo obstoječe izvoze, vendar jih ne morejo ustvariti.</span><span class="sxs-lookup"><span data-stu-id="6a089-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="6a089-121">Določitev novega izvoza</span><span class="sxs-lookup"><span data-stu-id="6a089-121">Define a new export</span></span>

1. <span data-ttu-id="6a089-122">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="6a089-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6a089-123">Izberite možnost **Dodaj izvoz**, da ustvarite nov izvoz.</span><span class="sxs-lookup"><span data-stu-id="6a089-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="6a089-124">V podoknu **Nastavitev izvoza** izberite, katero povezavo uporabiti.</span><span class="sxs-lookup"><span data-stu-id="6a089-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="6a089-125">[Povezave](connections.md) upravljajo skrbniki.</span><span class="sxs-lookup"><span data-stu-id="6a089-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="6a089-126">Navedite zahtevane podrobnosti in izberite **Shrani**, da ustvarite izvoz.</span><span class="sxs-lookup"><span data-stu-id="6a089-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="6a089-127">Določitev novega izvoza na podlagi obstoječega izvoza</span><span class="sxs-lookup"><span data-stu-id="6a089-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="6a089-128">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="6a089-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6a089-129">Na seznamu izvozov izberite izvoz, ki ga želite podvojiti.</span><span class="sxs-lookup"><span data-stu-id="6a089-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="6a089-130">Izberite **Ustvari dvojnik** v ukazni vrstici, da odprete podokno **Nastavi izvoz** s podrobnostmi izbranega izvoza.</span><span class="sxs-lookup"><span data-stu-id="6a089-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="6a089-131">Preglejte in prilagodite izvoz ter izberite **Shrani**, da ustvarite nov izvoz.</span><span class="sxs-lookup"><span data-stu-id="6a089-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="6a089-132">Urejanje izvoza</span><span class="sxs-lookup"><span data-stu-id="6a089-132">Edit an export</span></span>

1. <span data-ttu-id="6a089-133">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="6a089-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6a089-134">Na seznamu izvozov izberite izvoz, ki ga želite urediti.</span><span class="sxs-lookup"><span data-stu-id="6a089-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="6a089-135">V ukazni vrstici izberite **Uredi**.</span><span class="sxs-lookup"><span data-stu-id="6a089-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="6a089-136">Spremenite vrednosti, ki jih želite posodobiti, in izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="6a089-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="6a089-137">Ogled izvozov in podrobnosti izvozov</span><span class="sxs-lookup"><span data-stu-id="6a089-137">View exports and export details</span></span>

<span data-ttu-id="6a089-138">Po ustvarjanju ciljev za izvoz so ti navedeni na **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="6a089-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="6a089-139">Vsi uporabniki lahko vidijo, kateri podatki so v skupni rabi in njihovo zadnje stanje.</span><span class="sxs-lookup"><span data-stu-id="6a089-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="6a089-140">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="6a089-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6a089-141">Uporabniki brez dovoljenja za urejanje naj za ogled podrobnosti o izvozu izberejo možnost **Pogled**, ne pa možnosti **Uredi**.</span><span class="sxs-lookup"><span data-stu-id="6a089-141">Users without edit permissions select **View** instead of **Edit** to see the export details.</span></span>

1. <span data-ttu-id="6a089-142">V stranskem podoknu je prikazana konfiguracija izvoza.</span><span class="sxs-lookup"><span data-stu-id="6a089-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="6a089-143">Brez dovoljenj za urejanje ne morete spreminjati vrednosti.</span><span class="sxs-lookup"><span data-stu-id="6a089-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="6a089-144">Izberite **Zapri**, da se vrnete na stran z izvozi.</span><span class="sxs-lookup"><span data-stu-id="6a089-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="6a089-145">Načrtovanje in zagon izvozov</span><span class="sxs-lookup"><span data-stu-id="6a089-145">Schedule and run exports</span></span>

<span data-ttu-id="6a089-146">Vsak izvoz, ki ga konfigurirate, ima urnik osveževanja.</span><span class="sxs-lookup"><span data-stu-id="6a089-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="6a089-147">Med osveževanjem sistem išče nove ali posodobljene podatke, ki jih bo vključil v izvoz.</span><span class="sxs-lookup"><span data-stu-id="6a089-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="6a089-148">Izvozi se privzeto izvajajo kot del vsakega [načrtovanega osveževanja sistema](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6a089-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="6a089-149">Za ročni zagon izvozov lahko prilagodite urnik osveževanja ali ga izklopite.</span><span class="sxs-lookup"><span data-stu-id="6a089-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="6a089-150">Urniki izvoza so odvisni od stanja vašega okolja.</span><span class="sxs-lookup"><span data-stu-id="6a089-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="6a089-151">Če so posodobitve v teku v [odvisnostih](system.md#refresh-policies), ko bi se moral načrtovani izvoz začeti, bo sistem najprej dokončal posodobitve, šele nato pa začel z izvozom.</span><span class="sxs-lookup"><span data-stu-id="6a089-151">If there are updates in progress on [dependencies](system.md#refresh-policies) when a scheduled export should start, the system will first complete the updates and then run the export.</span></span> <span data-ttu-id="6a089-152">V stolpcu **Osveženo** lahko vidite, kdaj je bil izvoz nazadnje osvežen.</span><span class="sxs-lookup"><span data-stu-id="6a089-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="6a089-153">Načrtovanje izvozov</span><span class="sxs-lookup"><span data-stu-id="6a089-153">Schedule exports</span></span>

<span data-ttu-id="6a089-154">Določite lahko urnike osveževanja po meri za posamezen izvoz ali več izvozov hkrati.</span><span class="sxs-lookup"><span data-stu-id="6a089-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="6a089-155">Trenutno določen urnik je naveden v stolpcu **Načrtovanje** na seznamu izvoza.</span><span class="sxs-lookup"><span data-stu-id="6a089-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="6a089-156">Dovoljenje za spremembo urnika je enako kot za [urejanje in določanje izvozov](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="6a089-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="6a089-157">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="6a089-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6a089-158">Izberite izvoz, ki ga želite načrtovati.</span><span class="sxs-lookup"><span data-stu-id="6a089-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="6a089-159">V ukazni vrstici izberite **Načrtovanje**.</span><span class="sxs-lookup"><span data-stu-id="6a089-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="6a089-160">V podoknu **Načrtovanje izvoza** nastavite **Zagon načrtovanja** na **Vklopljeno**, da samodejno zaženete izvoz.</span><span class="sxs-lookup"><span data-stu-id="6a089-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="6a089-161">Nastavite ga na **Izklopljeno**, da ga ročno osvežite.</span><span class="sxs-lookup"><span data-stu-id="6a089-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="6a089-162">Za samodejno osvežene izvoze izberite vrednost **Ponovitev** in določite podrobnosti zanjo.</span><span class="sxs-lookup"><span data-stu-id="6a089-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="6a089-163">Opredeljeni čas velja za vse primerke ponovitev.</span><span class="sxs-lookup"><span data-stu-id="6a089-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="6a089-164">To je čas, ko bi se izvoz moral začeti osveževati.</span><span class="sxs-lookup"><span data-stu-id="6a089-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="6a089-165">Svoje spremembe uveljavite in aktivirajte tako, da izberete **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="6a089-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="6a089-166">Pri urejanju urnika za več izvozov morate izbrati eno od možnosti v razdelku **Obdržite ali preglasite razporede**:</span><span class="sxs-lookup"><span data-stu-id="6a089-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="6a089-167">**Obdržite posamezne razporede**: obdržite predhodno določeni urnik za izbrane izvoze in jih le onemogočite ali omogočite.</span><span class="sxs-lookup"><span data-stu-id="6a089-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="6a089-168">**Določite nov urnik za vse izbrane izvoze**: preglasite obstoječe urnike izbranih izvozov.</span><span class="sxs-lookup"><span data-stu-id="6a089-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="6a089-169">Zaženi izvoze na zahtevo</span><span class="sxs-lookup"><span data-stu-id="6a089-169">Run exports on demand</span></span>

<span data-ttu-id="6a089-170">Za izvoz podatkov brez čakanja na načrtovano osvežitev, pojdite na **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="6a089-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="6a089-171">Če želite zagnati vse izvoze, izberite **Zaženi vse** v ukazni vrstici.</span><span class="sxs-lookup"><span data-stu-id="6a089-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="6a089-172">S tem dejanjem se bodo zagnali samo izvozi z aktivnim urnikom.</span><span class="sxs-lookup"><span data-stu-id="6a089-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="6a089-173">Če želite zagnati en izvoz, ga izberite na seznamu in kliknite **Zaženi** v ukazni vrstici.</span><span class="sxs-lookup"><span data-stu-id="6a089-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="6a089-174">Tako boste zagnali izvoze brez aktivnega urnika.</span><span class="sxs-lookup"><span data-stu-id="6a089-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="6a089-175">Odstranjevanje izvoza</span><span class="sxs-lookup"><span data-stu-id="6a089-175">Remove an Export</span></span>

1. <span data-ttu-id="6a089-176">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="6a089-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6a089-177">Izberite izvoz, ki ga želite odstraniti.</span><span class="sxs-lookup"><span data-stu-id="6a089-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="6a089-178">V ukazni vrstici izberite **Odstrani**.</span><span class="sxs-lookup"><span data-stu-id="6a089-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="6a089-179">Odstranjevanje potrdite tako, da na potrditvenem zaslonu izberete **Odstrani**.</span><span class="sxs-lookup"><span data-stu-id="6a089-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
