---
title: Ustvarjanje in upravljanje segmentov
description: Ustvarite segmente strank, da jih združite na podlagi različnih atributov.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 6931110c2ae93cd2792d319aa5a34f0df3088552
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406999"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="a1ba0-103">Ustvarjanje in upravljanje segmentov</span><span class="sxs-lookup"><span data-stu-id="a1ba0-103">Create and manage segments</span></span>

<span data-ttu-id="a1ba0-104">Segmenti vam omogočajo, da svoje stranke razvrstite na podlagi demografskih, transakcijskih ali vedenjskih atributov.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="a1ba0-105">Segmente lahko uporabite za ciljanje promocijskih akcij, prodajnih dejavnosti in ukrepov za podporo strankam, da dosežete svoje poslovne cilje.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="a1ba0-106">Za entiteto profila stranke in njene povezane entitete lahko določite zapletene filtre.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="a1ba0-107">Po obdelavi vsak segment ustvari niz zapisov strank, ki jih lahko izvozite in obdelate.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="a1ba0-108">Veljajo nekatere [omejitve storitev](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="a1ba0-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="a1ba0-109">Če ni drugače določeno, so vsi segmenti **Dinamični segmenti**, ki se osvežujejo po rednem urniku.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="a1ba0-110">Naslednji primer prikazuje zmogljivost segmentacije.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="a1ba0-111">Določili smo segment za stranke, ki so v zadnjih 90 dneh naročile blaga v vrednosti vsaj 500 USD *in* ki so bile vključene v klic storitev za stranke, ki je bil posredovan na višjo raven.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a1ba0-112">![Več skupin](media/segmentation-group1-2.png "Več skupin")</span><span class="sxs-lookup"><span data-stu-id="a1ba0-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="a1ba0-113">Ustvarjanje novega segmenta</span><span class="sxs-lookup"><span data-stu-id="a1ba0-113">Create a new segment</span></span>

<span data-ttu-id="a1ba0-114">Segmenti se upravljajo na strani **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="a1ba0-115">Pri vpogledih v občinstvo odprite stran **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-115">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="a1ba0-116">Izberite **Novo** > **Prazen segment**.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-116">Select **New** > **Blank segment**.</span></span>

3. <span data-ttu-id="a1ba0-117">Na strani **Nov segment** izberite vrsto segmenta in vnesite **ime**.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="a1ba0-118">Po želji vnesite prikazno ime in opis, s katerim boste lažje prepoznali segment.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

4. <span data-ttu-id="a1ba0-119">Izberite **Naprej**, da se pomaknete na stran **Graditelj segmentov**, kjer določite skupino.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="a1ba0-120">Skupina je nabor strank.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-120">A group is a set of customers.</span></span>

5. <span data-ttu-id="a1ba0-121">Izberite entiteto, ki vključuje atribut, po katerem želite segmentirati.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-121">Choose the entity that includes the attribute you want to segment by.</span></span>

6. <span data-ttu-id="a1ba0-122">Izberite atribut, po katerem želite segmentirati.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="a1ba0-123">Ta atribut ima lahko eno od štirih vrst vrednosti: numerično, niz, datum ali logična vrednost.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

7. <span data-ttu-id="a1ba0-124">Izberite operator in vrednost za izbrani atribut.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a1ba0-125">![Filter skupine po meri](media/customer-group-numbers.png "Filter skupine strank")</span><span class="sxs-lookup"><span data-stu-id="a1ba0-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="a1ba0-126">Število</span><span class="sxs-lookup"><span data-stu-id="a1ba0-126">Number</span></span> |<span data-ttu-id="a1ba0-127">Definicija</span><span class="sxs-lookup"><span data-stu-id="a1ba0-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="a1ba0-128">1</span><span class="sxs-lookup"><span data-stu-id="a1ba0-128">1</span></span>     |<span data-ttu-id="a1ba0-129">Entity</span><span class="sxs-lookup"><span data-stu-id="a1ba0-129">Entity</span></span>          |
   |<span data-ttu-id="a1ba0-130">2</span><span class="sxs-lookup"><span data-stu-id="a1ba0-130">2</span></span>     |<span data-ttu-id="a1ba0-131">Atribut</span><span class="sxs-lookup"><span data-stu-id="a1ba0-131">Attribute</span></span>          |
   |<span data-ttu-id="a1ba0-132">3</span><span class="sxs-lookup"><span data-stu-id="a1ba0-132">3</span></span>    |<span data-ttu-id="a1ba0-133">Operator</span><span class="sxs-lookup"><span data-stu-id="a1ba0-133">Operator</span></span>         |
   |<span data-ttu-id="a1ba0-134">4</span><span class="sxs-lookup"><span data-stu-id="a1ba0-134">4</span></span>    |<span data-ttu-id="a1ba0-135">Vrednost</span><span class="sxs-lookup"><span data-stu-id="a1ba0-135">Value</span></span>         |

8. <span data-ttu-id="a1ba0-136">Če je entiteta povezana s poenoteno entiteto stranke prek [odnosov](relationships.md), morate določiti pot odnosa, da ustvarite veljaven segment.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="a1ba0-137">Dodajte entitete s poti odnosa, dokler se na spustnem meniju ne pojavi možnost za izbiro entitete **Stranka: CustomerInsights**.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="a1ba0-138">Nato za vsak pogoj izberite možnost **Vsi zapisi**.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a1ba0-139">![Pot odnosa med ustvarjanjem segmenta](media/segments-multiple-relationships.png "Pot odnosa med ustvarjanjem segmenta")</span><span class="sxs-lookup"><span data-stu-id="a1ba0-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

9. <span data-ttu-id="a1ba0-140">Izberite **Shrani**, da shranite segment.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-140">Select **Save** to save your segment.</span></span> <span data-ttu-id="a1ba0-141">Če so vse zahteve potrjene, bo vaš segment shranjen in obdelan.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-141">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="a1ba0-142">V nasprotnem primeru bo shranjen kot osnutek.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-142">Otherwise, it will be saved as a draft.</span></span>

10. <span data-ttu-id="a1ba0-143">Izberite **Nazaj na segmente**, da se vrnete na stran **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-143">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="a1ba0-144">Upravljanje obstoječih segmentov</span><span class="sxs-lookup"><span data-stu-id="a1ba0-144">Manage existing segments</span></span>

<span data-ttu-id="a1ba0-145">Na strani **Segmenti** si lahko ogledate vse shranjene segmente in jih upravljate.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-145">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="a1ba0-146">Vsak segment predstavlja vrstica, ki vključuje dodatne informacije o segmentu.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-146">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="a1ba0-147">Segmente lahko razvrstite v stolpcu tako, da izberete naslov stolpca.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-147">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="a1ba0-148">Za filtriranje segmentov uporabite polje **Iskanje** v zgornjem desnem kotu.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-148">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a1ba0-149">![Možnosti za upravljanje obstoječega segmenta](media/segments-selected-segment.png "Možnosti za upravljanje obstoječega segmenta")</span><span class="sxs-lookup"><span data-stu-id="a1ba0-149">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="a1ba0-150">Ko izberete segment, je na voljo naslednje dejanje:</span><span class="sxs-lookup"><span data-stu-id="a1ba0-150">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="a1ba0-151">Na voljo je **Prikaz** podrobnosti o odsekih, vključno s trendom števila članov in predogledom članov segmenta.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-151">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="a1ba0-152">Za spreminjanje lastnosti segmenta lahko uporabite možnost **Uredi**.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-152">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="a1ba0-153">Za vključitev najnovejših podatkov lahko izberete **Osveži**.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-153">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="a1ba0-154">Segment lahko aktivirate ali deaktivirate prek možnosti **Aktiviraj** ali **Deaktiviraj**.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-154">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="a1ba0-155">Segmenti imajo dve možni stanji - aktivno ali neaktivno.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-155">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="a1ba0-156">Stanji sta vam lahko v pomoč pri urejanju segmenta.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-156">These states come in handy when editing a segment.</span></span> <span data-ttu-id="a1ba0-157">Za neaktivne segmente definicija segmenta obstaja, vendar še ne vsebuje nobene stranke.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-157">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="a1ba0-158">Ko aktivirate segment, se njegovo stanje spremeni iz »neaktiven« v »aktiven« in začne iskati stranke, ki ustrezajo definiciji segmenta.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-158">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="a1ba0-159">Če je konfigurirana [načrtovana osvežitev](system.md#schedule-tab), je **Stanje** neaktivnih segmentov navedeno kot **Preskočeno**, kar pomeni, da poskusa osveževanja sploh ni bilo.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-159">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="a1ba0-160">Ko se aktivira neaktivni segment, se bo osvežil in bo vključen v načrtovane osvežitve.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-160">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="a1ba0-161">Lahko pa uporabite funkcijo **Razporedi pozneje** v spustnem meniju **Aktiviraj/Deaktivira**, da določite datum in čas v prihodnosti za aktiviranje in deaktiviranje določenega segmenta.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-161">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="a1ba0-162">Prek možnosti **Preimenuj** lahko segment preimenujete.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-162">**Rename** the segment.</span></span>
- <span data-ttu-id="a1ba0-163">Na voljo je možnost **Prenesi** za prenos seznama članov kot datoteke .CSV.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-163">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="a1ba0-164">Možnost **Dodaj v** pošlje seznam ID-jev strank v segment za obdelavo v drugi aplikaciji.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-164">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="a1ba0-165">Za brisanje je na voljo možnost **Izbriši**.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-165">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="a1ba0-166">Osveževanje segmentov</span><span class="sxs-lookup"><span data-stu-id="a1ba0-166">Refresh segments</span></span>

<span data-ttu-id="a1ba0-167">Vse segmente lahko osvežite naenkrat tako, da izberete **Osveži vse** na strani **Segmenti**, ali pa lahko osvežite enega ali več segmentov, ko jih izberete in nato izberete **Osveži** v možnostih.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-167">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="a1ba0-168">Lahko pa konfigurirate ponavljajoče se osveževanje prek možnosti **Skrbnik** > **Sistem** > **Načrtovanje**.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-168">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="a1ba0-169">Na voljo je [šest vrst stanja](system.md#status-types) za opravila/postopke.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-169">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="a1ba0-170">Poleg tega je večina postopkov [odvisna od drugih nadaljnjih postopkov](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="a1ba0-170">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="a1ba0-171">Izberete lahko stanje postopka in si ogledate podrobnosti o poteku celotnega posla.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-171">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="a1ba0-172">Ko za enega izmed poslov izberete **Prikaži podrobnosti**, se prikažejo dodatne informacije: čas obdelave, zadnji datum obdelave ter vse napake in opozorila, povezana z opravilom.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-172">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="a1ba0-173">Prenos in izvoz segmentov</span><span class="sxs-lookup"><span data-stu-id="a1ba0-173">Download and export segments</span></span>

<span data-ttu-id="a1ba0-174">Segmente lahko prenesete v datoteko CSV ali jih izvozite v storitev Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-174">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="a1ba0-175">Prenesite segmente v datoteko CSV</span><span class="sxs-lookup"><span data-stu-id="a1ba0-175">Download segments to a CSV file</span></span>

1. <span data-ttu-id="a1ba0-176">Pri vpogledih v občinstvo odprite stran **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-176">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="a1ba0-177">Izberite tri pike na ploščici posameznega segmenta.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-177">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="a1ba0-178">Na spustnem seznamu dejanj izberite **Prenesi kot CSV**.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-178">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="a1ba0-179">Izvoz segmentov v storitev Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="a1ba0-179">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="a1ba0-180">Pred izvozom segmentov v storitev Dynamics 365 Sales mora skrbnik [ustvariti cilj izvoza](export-destinations.md) za storitev Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-180">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="a1ba0-181">Pri vpogledih v občinstvo odprite stran **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-181">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="a1ba0-182">Izberite tri pike na ploščici posameznega segmenta.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-182">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="a1ba0-183">Na spustnem seznamu dejanj izberite možnost **Dodaj v** in nato izberite cilj izvoza, kamor želite poslati podatke.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-183">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="a1ba0-184">Način osnutka za segmente</span><span class="sxs-lookup"><span data-stu-id="a1ba0-184">Draft mode for segments</span></span>

<span data-ttu-id="a1ba0-185">Če niso izpolnjene vse zahteve za obdelavo segmenta, lahko shranite segment kot osnutek in do njega dostopate s strani **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-185">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="a1ba0-186">Shranjen bo kot neaktiven segment in ga ni mogoče aktivirati, dokler ne postane veljaven.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-186">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="a1ba0-187">Dodajanje več pogojev v skupino</span><span class="sxs-lookup"><span data-stu-id="a1ba0-187">Add more conditions to a group</span></span>

<span data-ttu-id="a1ba0-188">Če želite v skupino dodati več pogojev, lahko uporabite dva logična operaterja:</span><span class="sxs-lookup"><span data-stu-id="a1ba0-188">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="a1ba0-189">Operator **IN**: oba pogoja morata biti izpolnjena kot del postopka segmentacije.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-189">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="a1ba0-190">Ta možnost je najbolj uporabna, če določite pogoje v različnih entitetah.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-190">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="a1ba0-191">Operator **ALI**: izpolnjen mora biti kateri koli od pogojev kot del postopka segmentacije.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-191">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="a1ba0-192">Ta možnost je najbolj uporabna, če določite več pogojev za isto entiteto.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-192">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a1ba0-193">![Operator ALI, pri katerem mora biti izpolnjen kateri koli pogoj](media/segmentation-either-condition.png "Operator ALI, pri katerem mora biti izpolnjen kateri koli pogoj")</span><span class="sxs-lookup"><span data-stu-id="a1ba0-193">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="a1ba0-194">Trenutno je mogoče ugnezditi operator **ALI** pod operator **IN**, ne pa obratno.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-194">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="a1ba0-195">Združevanje več skupin</span><span class="sxs-lookup"><span data-stu-id="a1ba0-195">Combine multiple groups</span></span>

<span data-ttu-id="a1ba0-196">Vsaka skupina ustvari določen nabor strank.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-196">Each group produces a specific set of customers.</span></span> <span data-ttu-id="a1ba0-197">Te skupine lahko združite, da vključite stranke, ki so potrebne za vaš poslovni primer.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-197">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="a1ba0-198">Pri vpogledih v občinstvo odprite stran **Segmenti** in izberite segment.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-198">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="a1ba0-199">Izberite **Dodaj skupino**.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-199">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a1ba0-200">![Dodajanje skupine za skupino strank](media/customer-group-add-group.png "Dodajanje skupine za skupino strank")</span><span class="sxs-lookup"><span data-stu-id="a1ba0-200">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="a1ba0-201">Izberite enega od naslednjih nastavitvenih operaterjev: **Združevanje**, **Presek** ali **Razen**.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-201">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a1ba0-202">![Dodajanje unije za skupino strank](media/customer-group-union.png "Dodajanje unije za skupino strank")</span><span class="sxs-lookup"><span data-stu-id="a1ba0-202">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="a1ba0-203">Izberite nastavljenega operatorja, da lahko določite novo skupino.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-203">Select a set operator to define a new group.</span></span> <span data-ttu-id="a1ba0-204">Shranite različne skupine, da določite, kateri podatki se ohranijo:</span><span class="sxs-lookup"><span data-stu-id="a1ba0-204">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="a1ba0-205">**Unija** združi dve skupini.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-205">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="a1ba0-206">**Presek** prekriva obe skupini.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-206">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="a1ba0-207">Samo podatki, ki *so skupni* obema skupinama, se ohranijo v poenoteni skupini.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-207">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="a1ba0-208">**Razen** združuje obe skupini.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-208">**Except** combines the two groups.</span></span> <span data-ttu-id="a1ba0-209">Samo podatki v skupini A, ki *niso enaki* kot podatki v skupini B, se ohranijo.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-209">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="a1ba0-210">Prikaz zgodovine obdelave in članov segmenta</span><span class="sxs-lookup"><span data-stu-id="a1ba0-210">View processing history and segment members</span></span>

<span data-ttu-id="a1ba0-211">Usklajene podatke o segmentu si lahko ogledate tako, da pregledate njegove podrobnosti.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-211">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="a1ba0-212">Na strani **Segmenti** izberite segment, ki ga želite pregledati.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-212">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="a1ba0-213">Zgornji del strani vključuje grafikon trenda, ki prikazuje spremembe v številu članov.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-213">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="a1ba0-214">S kazalcem miške pokažite na podatkovne točke, da si ogledate število članov na določen datum.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-214">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="a1ba0-215">Časovni okvir vizualizacije lahko posodobite.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-215">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a1ba0-216">![Časovni obseg segmenta](media/segment-time-range.png "Časovni obseg segmenta")</span><span class="sxs-lookup"><span data-stu-id="a1ba0-216">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="a1ba0-217">Spodnji del vsebuje seznam članov segmenta.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-217">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="a1ba0-218">Polja, ki se prikažejo na tem seznamu, temeljijo na atributih entitet vašega segmenta.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-218">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="a1ba0-219">Seznam je predogled ujemajočih se članov segmenta in prikazuje prvih 100 zapisov vašega segmenta, tako da ga lahko po potrebi hitro ocenite in pregledate njegove definicije.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-219">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="a1ba0-220">Če si želite ogledati vse ujemajoče se zapise, morate [izvoziti segment](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="a1ba0-220">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="a1ba0-221">Hitri segmenti</span><span class="sxs-lookup"><span data-stu-id="a1ba0-221">Quick segments</span></span>

<span data-ttu-id="a1ba0-222">Poleg graditelja segmentov obstaja še ena pot za ustvarjanje segmentov.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-222">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="a1ba0-223">Hitri segmenti vam omogočajo hitro ustvarjanje preprostih segmentov z enim samim operaterjem in s takojšnjimi vpogledi.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-223">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="a1ba0-224">Na strani **Segmenti** izberite možnost **Novo** > **Hitro ustvarjanje iz**.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-224">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="a1ba0-225">Izberite možnost **Profili**, da ustvarite segment, ki temelji na poenoteni entiteti stranke.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-225">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="a1ba0-226">Izberite možnost **Mere**, da ustvarite segment okoli vsake vrste atributov stranke za mere, ki ste jih ustvarili na strani **Mere**.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-226">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="a1ba0-227">Izberite možnost **Obveščanje**, da sestavite segment okoli ene od izhodnih entitet, ki ste jih ustvarili z zmogljivostmi **Predvidevanja** ali **Modeli po meri**.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-227">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="a1ba0-228">V pogovornem oknu **Nov hitri segment** izberite atribut s spustnega seznama **Polje**.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-228">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="a1ba0-229">Sistem bo zagotovil nekaj dodatnih vpogledov, ki vam bodo pomagali ustvariti boljše segmente strank.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-229">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="a1ba0-230">Za kategorična polja bomo prikazali 10 največjih strank.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-230">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="a1ba0-231">Izberite **Vrednost** in **Pregled**.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-231">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="a1ba0-232">Pri številskem atributu sistem prikaže, katera vrednost atributa spada pod posamezni percentil stranke.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-232">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="a1ba0-233">Izberite **Operator** in **Vrednost** ter nato **Pregled**.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-233">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="a1ba0-234">Sistem prikaže **ocenjeno velikost segmenta**.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-234">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="a1ba0-235">Izberete lahko, ali želite ustvariti segment, ki ste ga določili, ali se želite najprej znova vrniti nanj, da dobite drugačno velikost segmenta.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-235">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a1ba0-236">![Ime in ocena za hitri segment](media/quick-segment-name.png "Ime in ocena za hitri segment")</span><span class="sxs-lookup"><span data-stu-id="a1ba0-236">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="a1ba0-237">Vnesite **ime** za segment.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-237">Provide a **Name** for your segment.</span></span> <span data-ttu-id="a1ba0-238">Po želji vnesite **prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-238">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="a1ba0-239">Izberite **Shrani**, da ustvarite segment.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-239">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="a1ba0-240">Ko je obdelava segmenta končana, si ga lahko ogledate kot katerikoli drug segment, ki ste ga ustvarili.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-240">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="a1ba0-241">Pri spodnjih scenarijih svetujemo uporabo graditelja segmentov in ne priporočene zmogljivosti segmentov:</span><span class="sxs-lookup"><span data-stu-id="a1ba0-241">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="a1ba0-242">Ustvarjanje segmentov s filtri v kategoričnih poljih, kjer je operator drugačen od operatorja **Je**</span><span class="sxs-lookup"><span data-stu-id="a1ba0-242">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="a1ba0-243">Ustvarjanje segmentov s filtri v številskih poljih, kjer je operator drugačen od operatorjev **Med**, **Več kot** in **Manj kot**</span><span class="sxs-lookup"><span data-stu-id="a1ba0-243">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="a1ba0-244">Ustvarjanje segmentov s filtri na poljih vrste datumov</span><span class="sxs-lookup"><span data-stu-id="a1ba0-244">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="a1ba0-245">Naslednji koraki</span><span class="sxs-lookup"><span data-stu-id="a1ba0-245">Next steps</span></span>

<span data-ttu-id="a1ba0-246">[Izvozite segment](export-destinations.md) in raziščite [kartico stranke](customer-card-add-in.md) in [povezovalnike](export-power-bi.md), da pridobite vpoglede na ravni stranke.</span><span class="sxs-lookup"><span data-stu-id="a1ba0-246">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>
