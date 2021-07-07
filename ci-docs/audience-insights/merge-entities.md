---
title: Združevanje entitet za poenotenje podatkov
description: Združite entitete za ustvarjanje poenotenih profilov strank.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 86ab3cefa70e5fab4bdb27cde363adee26efee4c
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305674"
---
# <a name="merge-entities"></a><span data-ttu-id="09e31-103">Združevanje entitet</span><span class="sxs-lookup"><span data-stu-id="09e31-103">Merge entities</span></span>

<span data-ttu-id="09e31-104">Faza spajanja je zadnja faza v postopku poenotenja podatkov.</span><span class="sxs-lookup"><span data-stu-id="09e31-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="09e31-105">Njen namen je uskladitev podatkov v sporu.</span><span class="sxs-lookup"><span data-stu-id="09e31-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="09e31-106">Primer podatkov v sporu je na primer ime stranke, ki ga najdemo v dveh zbirkah podatkov, vendar je v vsaki prikazan nekoliko drugače (»Grant Marshall« v primerjavi z »Grant Marshal«), ali telefonska številka, ki se razlikuje v obliki zapisa (617-803-091X v primerjavi s 617803091X).</span><span class="sxs-lookup"><span data-stu-id="09e31-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="09e31-107">Spajanje teh podatkovnih točk v sporu poteka na osnovi »atribut za atributom«.</span><span class="sxs-lookup"><span data-stu-id="09e31-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="Stran za spajanje v postopku poenotenja podatkov, ki prikazuje tabelo s spojenimi polji, ki določajo poenoten profil kupca.":::

<span data-ttu-id="09e31-109">Po zaključku [faze ujemanja](match-entities.md) fazo spajanja začnete tako, da izberete ploščico **Spajanje** na strani **Poenotenje**.</span><span class="sxs-lookup"><span data-stu-id="09e31-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="09e31-110">Pregled priporočil sistema</span><span class="sxs-lookup"><span data-stu-id="09e31-110">Review system recommendations</span></span>

<span data-ttu-id="09e31-111">V zavihku **Podatki** > **Poenotenje** > **Spajanje** izberete in izključite atribute za spojitev znotraj vaše entitete poenotenega profila kupca.</span><span class="sxs-lookup"><span data-stu-id="09e31-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="09e31-112">Poenoten profil stranke je rezultat postopka poenotenja podatkov.</span><span class="sxs-lookup"><span data-stu-id="09e31-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="09e31-113">Sistem samodejno spoji nekatere atribute.</span><span class="sxs-lookup"><span data-stu-id="09e31-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="09e31-114">Če si želite ogledati atribute, ki so vključeni v enega od vaših samodejno spojenih atributov, izberite ta spojeni atribut v zavihku **Polja za stranke** v tabeli.</span><span class="sxs-lookup"><span data-stu-id="09e31-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="09e31-115">Atributi, ki sestavljajo ta spojeni atribut, bodo prikazani v dveh novih vrsticah pod spojenim atributom.</span><span class="sxs-lookup"><span data-stu-id="09e31-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="09e31-116">Ločevanje, preimenovanje, izključevanje in urejanje spojenih polj</span><span class="sxs-lookup"><span data-stu-id="09e31-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="09e31-117">Spremenite lahko, kako sistem obdeluje spojene atribute, da ustvari poenoten profil stranke.</span><span class="sxs-lookup"><span data-stu-id="09e31-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="09e31-118">Izberite možnost **Pokaži več** in izberite, kaj želite spremeniti.</span><span class="sxs-lookup"><span data-stu-id="09e31-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Možnosti v spustnem meniju Prikaži več za upravljanje spojenih atributov.":::

<span data-ttu-id="09e31-120">Če želite več informacij, glejte naslednje razdelke.</span><span class="sxs-lookup"><span data-stu-id="09e31-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="09e31-121">Ločevanje spojenih polj</span><span class="sxs-lookup"><span data-stu-id="09e31-121">Separate merged fields</span></span>

<span data-ttu-id="09e31-122">Če želite ločiti spojena polja, v tabeli poiščite atribut.</span><span class="sxs-lookup"><span data-stu-id="09e31-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="09e31-123">Ločena polja so prikazana kot posamezne podatkovne točke na poenotenem profilu stranke.</span><span class="sxs-lookup"><span data-stu-id="09e31-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="09e31-124">Izberite spojeno polje.</span><span class="sxs-lookup"><span data-stu-id="09e31-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="09e31-125">Izberite možnost **Pokaži več** in **Loči polja**.</span><span class="sxs-lookup"><span data-stu-id="09e31-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="09e31-126">Potrdite ločevanje.</span><span class="sxs-lookup"><span data-stu-id="09e31-126">Confirm the separation.</span></span>

1. <span data-ttu-id="09e31-127">Izberite možnost **Shrani** in **Zaženi** za obdelavo sprememb.</span><span class="sxs-lookup"><span data-stu-id="09e31-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="09e31-128">Preimenovanje spojenih polj</span><span class="sxs-lookup"><span data-stu-id="09e31-128">Rename merged fields</span></span>

<span data-ttu-id="09e31-129">Spremenite prikazno ime spojenih atributov.</span><span class="sxs-lookup"><span data-stu-id="09e31-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="09e31-130">Imen izhodne entitete ni mogoče spremeniti.</span><span class="sxs-lookup"><span data-stu-id="09e31-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="09e31-131">Izberite spojeno polje.</span><span class="sxs-lookup"><span data-stu-id="09e31-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="09e31-132">Izberite možnost **Pokaži več** in **Preimenuj**.</span><span class="sxs-lookup"><span data-stu-id="09e31-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="09e31-133">Potrdite spremenjeno prikazno ime.</span><span class="sxs-lookup"><span data-stu-id="09e31-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="09e31-134">Izberite možnost **Shrani** in **Zaženi** za obdelavo sprememb.</span><span class="sxs-lookup"><span data-stu-id="09e31-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="09e31-135">Izključevanje spojenih polj</span><span class="sxs-lookup"><span data-stu-id="09e31-135">Exclude merged fields</span></span>

<span data-ttu-id="09e31-136">Iz poenotenega profila stranke izključite atribut.</span><span class="sxs-lookup"><span data-stu-id="09e31-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="09e31-137">Če se polje uporablja v drugih procesih, na primer v segmentu, ga odstranite iz teh procesov, preden ga izključite iz profila stranke.</span><span class="sxs-lookup"><span data-stu-id="09e31-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="09e31-138">Izberite spojeno polje.</span><span class="sxs-lookup"><span data-stu-id="09e31-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="09e31-139">Izberite možnost **Pokaži več** in **Izključi**.</span><span class="sxs-lookup"><span data-stu-id="09e31-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="09e31-140">Potrdite izključitev.</span><span class="sxs-lookup"><span data-stu-id="09e31-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="09e31-141">Izberite možnost **Shrani** in **Zaženi** za obdelavo sprememb.</span><span class="sxs-lookup"><span data-stu-id="09e31-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="09e31-142">Na strani za **spajanje** izberite **Izključena polja** za ogled seznama vseh izključenih polj.</span><span class="sxs-lookup"><span data-stu-id="09e31-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="09e31-143">To podokno vam omogoča vnovično dodajanje izključenih polj.</span><span class="sxs-lookup"><span data-stu-id="09e31-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="09e31-144">Ročno združevanje polj</span><span class="sxs-lookup"><span data-stu-id="09e31-144">Manually combine fields</span></span>

<span data-ttu-id="09e31-145">Ročno določite spojeni atribut.</span><span class="sxs-lookup"><span data-stu-id="09e31-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="09e31-146">Na strani za **spajanje** izberite možnost **Združi polja**.</span><span class="sxs-lookup"><span data-stu-id="09e31-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="09e31-147">Navedite **Ime** in **Ime izhodnega polja**.</span><span class="sxs-lookup"><span data-stu-id="09e31-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="09e31-148">Izberite polje, ki ga želite dodati.</span><span class="sxs-lookup"><span data-stu-id="09e31-148">Choose a field to add.</span></span> <span data-ttu-id="09e31-149">Izberite možnost **Dodaj polja**, če želite združiti več polj.</span><span class="sxs-lookup"><span data-stu-id="09e31-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="09e31-150">Potrdite izključitev.</span><span class="sxs-lookup"><span data-stu-id="09e31-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="09e31-151">Izberite možnost **Shrani** in **Zaženi** za obdelavo sprememb.</span><span class="sxs-lookup"><span data-stu-id="09e31-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="09e31-152">Spreminjanje vrstnega reda polj</span><span class="sxs-lookup"><span data-stu-id="09e31-152">Change the order of fields</span></span>

<span data-ttu-id="09e31-153">Nekatere entitete vsebujejo več podrobnosti kot druge.</span><span class="sxs-lookup"><span data-stu-id="09e31-153">Some entities contain more details than others.</span></span> <span data-ttu-id="09e31-154">Če entiteta vključuje najnovejše podatke o polju, jo lahko pri spajanju vrednosti prednostno obravnavate pred drugimi entitetami.</span><span class="sxs-lookup"><span data-stu-id="09e31-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="09e31-155">Izberite spojeno polje.</span><span class="sxs-lookup"><span data-stu-id="09e31-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="09e31-156">Izberite možnost **Pokaži več** in **Uredi**.</span><span class="sxs-lookup"><span data-stu-id="09e31-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="09e31-157">V podoknu **Združevanje polj** izberite možnost **Premik gor/dol**, da nastavite vrstni red, ali pa jih povlecite in spustite na želeni položaj.</span><span class="sxs-lookup"><span data-stu-id="09e31-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="09e31-158">Potrdite spremembo.</span><span class="sxs-lookup"><span data-stu-id="09e31-158">Confirm the change.</span></span>

1. <span data-ttu-id="09e31-159">Izberite možnost **Shrani** in **Zaženi** za obdelavo sprememb.</span><span class="sxs-lookup"><span data-stu-id="09e31-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="09e31-160">Zagon spajanja</span><span class="sxs-lookup"><span data-stu-id="09e31-160">Run your merge</span></span>

<span data-ttu-id="09e31-161">Ne glede na to, ali atribute spajate ročno ali jih spoji sistem, lahko vedno zaženete spajanje.</span><span class="sxs-lookup"><span data-stu-id="09e31-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="09e31-162">Za začetek postopka izberite **Zaženi** na strani **Spajanje**.</span><span class="sxs-lookup"><span data-stu-id="09e31-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="09e31-163">![Shranjevanje in zagon spajanja podatkov](media/configure-data-merge-save-run.png "Shranjevanje in zagon spajanja podatkov")</span><span class="sxs-lookup"><span data-stu-id="09e31-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="09e31-164">Izberite možnost **Zaženi samo spajanje**, če želite, da se rezultat prikaže samo v poenoteni entiteti stranke.</span><span class="sxs-lookup"><span data-stu-id="09e31-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="09e31-165">Procesi iz strežnika bodo osveženi, kot je [opredeljeno v načrtovanju osveževanja](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="09e31-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="09e31-166">Izberite možnost **Zaženi procese spajanja in procese iz strežnika**, da osvežite sistem s svojimi spremembami.</span><span class="sxs-lookup"><span data-stu-id="09e31-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="09e31-167">Vsi procesi, vključno z obogatitvijo, segmenti in merami, se bodo samodejno ponovili.</span><span class="sxs-lookup"><span data-stu-id="09e31-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="09e31-168">Po zaključku vseh procesov iz strežnika profili strank prikažejo vse spremembe, ki ste jih naredili.</span><span class="sxs-lookup"><span data-stu-id="09e31-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="09e31-169">Če želite narediti več sprememb in ponoviti korak, lahko prekličete spajanje v teku.</span><span class="sxs-lookup"><span data-stu-id="09e31-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="09e31-170">Izberite **Osveževanje ...**, nato pa **Prekliči posel** v stranskem podoknu, ki se prikaže.</span><span class="sxs-lookup"><span data-stu-id="09e31-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="09e31-171">Na voljo je [šest vrst stanja](system.md#status-types) za opravila/postopke.</span><span class="sxs-lookup"><span data-stu-id="09e31-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="09e31-172">Poleg tega je večina postopkov [odvisna od drugih nadaljnjih postopkov](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="09e31-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="09e31-173">Izberete lahko stanje postopka in si ogledate podrobnosti o poteku celotnega posla.</span><span class="sxs-lookup"><span data-stu-id="09e31-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="09e31-174">Ko za enega izmed poslov izberete **Prikaži podrobnosti**, se prikažejo dodatne informacije: čas obdelave, zadnji datum obdelave ter vse napake in opozorila, povezana z opravilom.</span><span class="sxs-lookup"><span data-stu-id="09e31-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="09e31-175">Naslednji korak</span><span class="sxs-lookup"><span data-stu-id="09e31-175">Next Step</span></span>

<span data-ttu-id="09e31-176">Za pridobitev več vpogledov v stranke konfigurirajte možnosti [Dejavnosti](activities.md), [Obogatitev](enrichment-hub.md) ali [Odnosi](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="09e31-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="09e31-177">Če ste že konfigurirali dejavnosti, obogatitev ali segmente, bodo samodejno obdelani za uporabo najnovejših podatkov o strankah.</span><span class="sxs-lookup"><span data-stu-id="09e31-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
