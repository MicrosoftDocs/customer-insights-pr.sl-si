---
title: Ustvarjanje in upravljanje segmentov
description: Ustvarite segmente strank, da jih združite na podlagi različnih atributov.
ms.date: 03/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a6e8a3216a2c0738d60247054afa9fc18412f55
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597079"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="851bf-103">Ustvarjanje in upravljanje segmentov</span><span class="sxs-lookup"><span data-stu-id="851bf-103">Create and manage segments</span></span>

<span data-ttu-id="851bf-104">Segmenti vam omogočajo, da svoje stranke razvrstite na podlagi demografskih, transakcijskih ali vedenjskih atributov.</span><span class="sxs-lookup"><span data-stu-id="851bf-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="851bf-105">Segmente lahko uporabite za ciljanje promocijskih akcij, prodajnih dejavnosti in ukrepov za podporo strankam, da dosežete svoje poslovne cilje.</span><span class="sxs-lookup"><span data-stu-id="851bf-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="851bf-106">Za entiteto profila stranke in njene povezane entitete lahko določite zapletene filtre.</span><span class="sxs-lookup"><span data-stu-id="851bf-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="851bf-107">Po obdelavi vsak segment ustvari niz zapisov strank, ki jih lahko izvozite in obdelate.</span><span class="sxs-lookup"><span data-stu-id="851bf-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="851bf-108">Veljajo nekatere [omejitve storitev](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="851bf-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="851bf-109">Če ni drugače določeno, so vsi segmenti **Dinamični segmenti**, ki se osvežujejo po rednem urniku.</span><span class="sxs-lookup"><span data-stu-id="851bf-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="851bf-110">Naslednji primer prikazuje zmogljivost segmentacije.</span><span class="sxs-lookup"><span data-stu-id="851bf-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="851bf-111">Določili smo segment za stranke, ki so v zadnjih 90 dneh naročile blaga v vrednosti vsaj 500 USD *in* ki so bile vključene v klic storitev za stranke, ki je bil posredovan na višjo raven.</span><span class="sxs-lookup"><span data-stu-id="851bf-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="851bf-112">![Več skupin](media/segmentation-group1-2.png "Več skupin")</span><span class="sxs-lookup"><span data-stu-id="851bf-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="851bf-113">Ustvarjanje novega segmenta</span><span class="sxs-lookup"><span data-stu-id="851bf-113">Create a new segment</span></span>

<span data-ttu-id="851bf-114">Segmenti se upravljajo na strani **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="851bf-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="851bf-115">Pri vpogledih v občinstvo odprite stran **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="851bf-115">In audience insights, go to the **Segments** page.</span></span>

1. <span data-ttu-id="851bf-116">Izberite **Novo** > **Prazen segment**.</span><span class="sxs-lookup"><span data-stu-id="851bf-116">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="851bf-117">Na strani **Nov segment** izberite vrsto segmenta in vnesite **ime**.</span><span class="sxs-lookup"><span data-stu-id="851bf-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="851bf-118">Po želji vnesite prikazno ime in opis, s katerim boste lažje prepoznali segment.</span><span class="sxs-lookup"><span data-stu-id="851bf-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="851bf-119">Izberite **Naprej**, da se pomaknete na stran **Graditelj segmentov**, kjer določite skupino.</span><span class="sxs-lookup"><span data-stu-id="851bf-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="851bf-120">Skupina je nabor strank.</span><span class="sxs-lookup"><span data-stu-id="851bf-120">A group is a set of customers.</span></span>

1. <span data-ttu-id="851bf-121">Izberite entiteto, ki vključuje atribut, po katerem želite segmentirati.</span><span class="sxs-lookup"><span data-stu-id="851bf-121">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="851bf-122">Izberite atribut, po katerem želite segmentirati.</span><span class="sxs-lookup"><span data-stu-id="851bf-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="851bf-123">Ta atribut ima lahko eno od štirih vrst vrednosti: numerično, niz, datum ali logična vrednost.</span><span class="sxs-lookup"><span data-stu-id="851bf-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="851bf-124">Izberite operator in vrednost za izbrani atribut.</span><span class="sxs-lookup"><span data-stu-id="851bf-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="851bf-125">![Filter skupine po meri](media/customer-group-numbers.png "Filter skupine strank")</span><span class="sxs-lookup"><span data-stu-id="851bf-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="851bf-126">Število</span><span class="sxs-lookup"><span data-stu-id="851bf-126">Number</span></span> |<span data-ttu-id="851bf-127">Definicija</span><span class="sxs-lookup"><span data-stu-id="851bf-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="851bf-128">1</span><span class="sxs-lookup"><span data-stu-id="851bf-128">1</span></span>     |<span data-ttu-id="851bf-129">Entity</span><span class="sxs-lookup"><span data-stu-id="851bf-129">Entity</span></span>          |
   |<span data-ttu-id="851bf-130">2</span><span class="sxs-lookup"><span data-stu-id="851bf-130">2</span></span>     |<span data-ttu-id="851bf-131">Atribut</span><span class="sxs-lookup"><span data-stu-id="851bf-131">Attribute</span></span>          |
   |<span data-ttu-id="851bf-132">3</span><span class="sxs-lookup"><span data-stu-id="851bf-132">3</span></span>    |<span data-ttu-id="851bf-133">Operator</span><span class="sxs-lookup"><span data-stu-id="851bf-133">Operator</span></span>         |
   |<span data-ttu-id="851bf-134">4</span><span class="sxs-lookup"><span data-stu-id="851bf-134">4</span></span>    |<span data-ttu-id="851bf-135">Vrednost</span><span class="sxs-lookup"><span data-stu-id="851bf-135">Value</span></span>         |

8. <span data-ttu-id="851bf-136">Če je entiteta povezana s poenoteno entiteto stranke prek [odnosov](relationships.md), morate določiti pot odnosa, da ustvarite veljaven segment.</span><span class="sxs-lookup"><span data-stu-id="851bf-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="851bf-137">Dodajte entitete s poti odnosa, dokler se na spustnem meniju ne pojavi možnost za izbiro entitete **Stranka: CustomerInsights**.</span><span class="sxs-lookup"><span data-stu-id="851bf-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="851bf-138">Nato za vsak pogoj izberite možnost **Vsi zapisi**.</span><span class="sxs-lookup"><span data-stu-id="851bf-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="851bf-139">![Pot odnosa med ustvarjanjem segmenta](media/segments-multiple-relationships.png "Pot odnosa med ustvarjanjem segmenta")</span><span class="sxs-lookup"><span data-stu-id="851bf-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="851bf-140">Segmenti privzeto generirajo izhodno entiteto, ki vsebuje vse atribute profilov strank, ki se ujemajo z določenimi filtri.</span><span class="sxs-lookup"><span data-stu-id="851bf-140">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="851bf-141">Če segment temelji na drugih entitetah kot na entiteti *stranke*, lahko v izhodno entiteto dodate več atributov teh entitet.</span><span class="sxs-lookup"><span data-stu-id="851bf-141">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="851bf-142">Izberite **Atributi projekta**, da izberete atribute, ki bodo dodani izhodni entiteti.</span><span class="sxs-lookup"><span data-stu-id="851bf-142">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  

   
   <span data-ttu-id="851bf-143">Primer: Segment temelji na entiteti, ki vsebuje podatke o dejavnostih strank, povezane z entiteto *stranke*.</span><span class="sxs-lookup"><span data-stu-id="851bf-143">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="851bf-144">Segment išče vse stranke, ki so v zadnjih 60 dneh poklicale službo za pomoč uporabnikom.</span><span class="sxs-lookup"><span data-stu-id="851bf-144">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="851bf-145">Trajanje in število klicev lahko v izhodni entiteti priložite v vse ustrezne zapise strank, ki se ujemajo.</span><span class="sxs-lookup"><span data-stu-id="851bf-145">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="851bf-146">Te informacije so lahko koristne za pošiljanje e-pošte strankam, ki so pogosto klicale, s koristnimi povezavami do spletnih člankov za pomoč in pogostih vprašanj.</span><span class="sxs-lookup"><span data-stu-id="851bf-146">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

1. <span data-ttu-id="851bf-147">Izberite **Shrani**, da shranite segment.</span><span class="sxs-lookup"><span data-stu-id="851bf-147">Select **Save** to save your segment.</span></span> <span data-ttu-id="851bf-148">Če so vse zahteve potrjene, bo vaš segment shranjen in obdelan.</span><span class="sxs-lookup"><span data-stu-id="851bf-148">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="851bf-149">V nasprotnem primeru bo shranjen kot osnutek.</span><span class="sxs-lookup"><span data-stu-id="851bf-149">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="851bf-150">Izberite **Nazaj na segmente**, da se vrnete na stran **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="851bf-150">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="851bf-151">Upravljanje obstoječih segmentov</span><span class="sxs-lookup"><span data-stu-id="851bf-151">Manage existing segments</span></span>

<span data-ttu-id="851bf-152">Na strani **Segmenti** si lahko ogledate vse shranjene segmente in jih upravljate.</span><span class="sxs-lookup"><span data-stu-id="851bf-152">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="851bf-153">Vsak segment predstavlja vrstica, ki vključuje dodatne informacije o segmentu.</span><span class="sxs-lookup"><span data-stu-id="851bf-153">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="851bf-154">Segmente lahko razvrstite v stolpcu tako, da izberete naslov stolpca.</span><span class="sxs-lookup"><span data-stu-id="851bf-154">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="851bf-155">Za filtriranje segmentov uporabite polje **Iskanje** v zgornjem desnem kotu.</span><span class="sxs-lookup"><span data-stu-id="851bf-155">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="851bf-156">![Možnosti za upravljanje obstoječega segmenta](media/segments-selected-segment.png "Možnosti za upravljanje obstoječega segmenta")</span><span class="sxs-lookup"><span data-stu-id="851bf-156">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="851bf-157">Ko izberete segment, je na voljo naslednje dejanje:</span><span class="sxs-lookup"><span data-stu-id="851bf-157">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="851bf-158">Na voljo je **Prikaz** podrobnosti o odsekih, vključno s trendom števila članov in predogledom članov segmenta.</span><span class="sxs-lookup"><span data-stu-id="851bf-158">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="851bf-159">Za spreminjanje lastnosti segmenta lahko uporabite možnost **Uredi**.</span><span class="sxs-lookup"><span data-stu-id="851bf-159">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="851bf-160">**Ustvarjanje dvojnika** segmenta.</span><span class="sxs-lookup"><span data-stu-id="851bf-160">**Create duplicate** of a segment.</span></span> <span data-ttu-id="851bf-161">Takoj lahko uredite njegove lastnosti ali preprosto shranite dvojnik.</span><span class="sxs-lookup"><span data-stu-id="851bf-161">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="851bf-162">Za vključitev najnovejših podatkov lahko izberete **Osveži**.</span><span class="sxs-lookup"><span data-stu-id="851bf-162">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="851bf-163">Segment lahko aktivirate ali deaktivirate prek možnosti **Aktiviraj** ali **Deaktiviraj**.</span><span class="sxs-lookup"><span data-stu-id="851bf-163">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="851bf-164">Segmenti imajo dve možni stanji - aktivno ali neaktivno.</span><span class="sxs-lookup"><span data-stu-id="851bf-164">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="851bf-165">Stanji sta vam lahko v pomoč pri urejanju segmenta.</span><span class="sxs-lookup"><span data-stu-id="851bf-165">These states come in handy when editing a segment.</span></span> <span data-ttu-id="851bf-166">Za neaktivne segmente definicija segmenta obstaja, vendar še ne vsebuje nobene stranke.</span><span class="sxs-lookup"><span data-stu-id="851bf-166">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="851bf-167">Ko aktivirate segment, se njegovo stanje spremeni iz »neaktiven« v »aktiven« in začne iskati stranke, ki ustrezajo definiciji segmenta.</span><span class="sxs-lookup"><span data-stu-id="851bf-167">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="851bf-168">Če je konfigurirana [načrtovana osvežitev](system.md#schedule-tab), je **Stanje** neaktivnih segmentov navedeno kot **Preskočeno**, kar pomeni, da poskusa osveževanja sploh ni bilo.</span><span class="sxs-lookup"><span data-stu-id="851bf-168">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="851bf-169">Ko se aktivira neaktivni segment, se bo osvežil in bo vključen v načrtovane osvežitve.</span><span class="sxs-lookup"><span data-stu-id="851bf-169">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="851bf-170">Lahko pa uporabite funkcijo **Razporedi pozneje** v spustnem meniju **Aktiviraj/Deaktivira**, da določite datum in čas v prihodnosti za aktiviranje in deaktiviranje določenega segmenta.</span><span class="sxs-lookup"><span data-stu-id="851bf-170">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="851bf-171">Prek možnosti **Preimenuj** lahko segment preimenujete.</span><span class="sxs-lookup"><span data-stu-id="851bf-171">**Rename** the segment.</span></span>
- <span data-ttu-id="851bf-172">Na voljo je možnost **Prenesi** za prenos seznama članov kot datoteke .CSV.</span><span class="sxs-lookup"><span data-stu-id="851bf-172">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="851bf-173">Možnost **Dodaj v** pošlje seznam ID-jev strank v segment za obdelavo v drugi aplikaciji.</span><span class="sxs-lookup"><span data-stu-id="851bf-173">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="851bf-174">Za brisanje je na voljo možnost **Izbriši**.</span><span class="sxs-lookup"><span data-stu-id="851bf-174">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="851bf-175">Osveževanje segmentov</span><span class="sxs-lookup"><span data-stu-id="851bf-175">Refresh segments</span></span>

<span data-ttu-id="851bf-176">Vse segmente lahko osvežite naenkrat tako, da izberete **Osveži vse** na strani **Segmenti**, ali pa lahko osvežite enega ali več segmentov, ko jih izberete in nato izberete **Osveži** v možnostih.</span><span class="sxs-lookup"><span data-stu-id="851bf-176">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="851bf-177">Lahko pa konfigurirate ponavljajoče se osveževanje prek možnosti **Skrbnik** > **Sistem** > **Načrtovanje**.</span><span class="sxs-lookup"><span data-stu-id="851bf-177">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="851bf-178">Na voljo je [šest vrst stanja](system.md#status-types) za opravila/postopke.</span><span class="sxs-lookup"><span data-stu-id="851bf-178">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="851bf-179">Poleg tega je večina postopkov [odvisna od drugih nadaljnjih postopkov](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="851bf-179">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="851bf-180">Izberete lahko stanje postopka in si ogledate podrobnosti o poteku celotnega posla.</span><span class="sxs-lookup"><span data-stu-id="851bf-180">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="851bf-181">Ko za enega izmed poslov izberete **Prikaži podrobnosti**, se prikažejo dodatne informacije: čas obdelave, zadnji datum obdelave ter vse napake in opozorila, povezana z opravilom.</span><span class="sxs-lookup"><span data-stu-id="851bf-181">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="851bf-182">Prenos in izvoz segmentov</span><span class="sxs-lookup"><span data-stu-id="851bf-182">Download and export segments</span></span>

<span data-ttu-id="851bf-183">Segmente lahko prenesete v datoteko CSV ali jih izvozite v storitev Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="851bf-183">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="851bf-184">Prenesite segmente v datoteko CSV</span><span class="sxs-lookup"><span data-stu-id="851bf-184">Download segments to a CSV file</span></span>

1. <span data-ttu-id="851bf-185">Pri vpogledih v občinstvo odprite stran **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="851bf-185">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="851bf-186">Izberite tri pike na ploščici posameznega segmenta.</span><span class="sxs-lookup"><span data-stu-id="851bf-186">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="851bf-187">Na spustnem seznamu dejanj izberite **Prenesi kot CSV**.</span><span class="sxs-lookup"><span data-stu-id="851bf-187">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="851bf-188">Izvoz segmentov v storitev Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="851bf-188">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="851bf-189">Pred izvozom segmentov v storitev Dynamics 365 Sales mora skrbnik [ustvariti cilj izvoza](export-destinations.md) za storitev Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="851bf-189">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="851bf-190">Pri vpogledih v občinstvo odprite stran **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="851bf-190">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="851bf-191">Izberite tri pike na ploščici posameznega segmenta.</span><span class="sxs-lookup"><span data-stu-id="851bf-191">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="851bf-192">Na spustnem seznamu dejanj izberite možnost **Dodaj v** in nato izberite cilj izvoza, kamor želite poslati podatke.</span><span class="sxs-lookup"><span data-stu-id="851bf-192">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="851bf-193">Način osnutka za segmente</span><span class="sxs-lookup"><span data-stu-id="851bf-193">Draft mode for segments</span></span>

<span data-ttu-id="851bf-194">Če niso izpolnjene vse zahteve za obdelavo segmenta, lahko shranite segment kot osnutek in do njega dostopate s strani **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="851bf-194">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="851bf-195">Shranjen bo kot neaktiven segment in ga ni mogoče aktivirati, dokler ne postane veljaven.</span><span class="sxs-lookup"><span data-stu-id="851bf-195">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="851bf-196">Dodajanje več pogojev v skupino</span><span class="sxs-lookup"><span data-stu-id="851bf-196">Add more conditions to a group</span></span>

<span data-ttu-id="851bf-197">Če želite v skupino dodati več pogojev, lahko uporabite dva logična operaterja:</span><span class="sxs-lookup"><span data-stu-id="851bf-197">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="851bf-198">Operator **IN**: oba pogoja morata biti izpolnjena kot del postopka segmentacije.</span><span class="sxs-lookup"><span data-stu-id="851bf-198">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="851bf-199">Ta možnost je najbolj uporabna, če določite pogoje v različnih entitetah.</span><span class="sxs-lookup"><span data-stu-id="851bf-199">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="851bf-200">Operator **ALI**: izpolnjen mora biti kateri koli od pogojev kot del postopka segmentacije.</span><span class="sxs-lookup"><span data-stu-id="851bf-200">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="851bf-201">Ta možnost je najbolj uporabna, če določite več pogojev za isto entiteto.</span><span class="sxs-lookup"><span data-stu-id="851bf-201">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="851bf-202">![Operator ALI, pri katerem mora biti izpolnjen kateri koli pogoj](media/segmentation-either-condition.png "Operator ALI, pri katerem mora biti izpolnjen kateri koli pogoj")</span><span class="sxs-lookup"><span data-stu-id="851bf-202">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="851bf-203">Trenutno je mogoče ugnezditi operator **ALI** pod operator **IN**, ne pa obratno.</span><span class="sxs-lookup"><span data-stu-id="851bf-203">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="851bf-204">Združevanje več skupin</span><span class="sxs-lookup"><span data-stu-id="851bf-204">Combine multiple groups</span></span>

<span data-ttu-id="851bf-205">Vsaka skupina ustvari določen nabor strank.</span><span class="sxs-lookup"><span data-stu-id="851bf-205">Each group produces a specific set of customers.</span></span> <span data-ttu-id="851bf-206">Te skupine lahko združite, da vključite stranke, ki so potrebne za vaš poslovni primer.</span><span class="sxs-lookup"><span data-stu-id="851bf-206">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="851bf-207">Pri vpogledih v občinstvo odprite stran **Segmenti** in izberite segment.</span><span class="sxs-lookup"><span data-stu-id="851bf-207">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="851bf-208">Izberite **Dodaj skupino**.</span><span class="sxs-lookup"><span data-stu-id="851bf-208">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="851bf-209">![Dodajanje skupine za skupino strank](media/customer-group-add-group.png "Dodajanje skupine za skupino strank")</span><span class="sxs-lookup"><span data-stu-id="851bf-209">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="851bf-210">Izberite enega od naslednjih nastavitvenih operaterjev: **Združevanje**, **Presek** ali **Razen**.</span><span class="sxs-lookup"><span data-stu-id="851bf-210">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="851bf-211">![Dodajanje unije za skupino strank](media/customer-group-union.png "Dodajanje unije za skupino strank")</span><span class="sxs-lookup"><span data-stu-id="851bf-211">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="851bf-212">Izberite nastavljenega operatorja, da lahko določite novo skupino.</span><span class="sxs-lookup"><span data-stu-id="851bf-212">Select a set operator to define a new group.</span></span> <span data-ttu-id="851bf-213">Shranite različne skupine, da določite, kateri podatki se ohranijo:</span><span class="sxs-lookup"><span data-stu-id="851bf-213">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="851bf-214">**Unija** združi dve skupini.</span><span class="sxs-lookup"><span data-stu-id="851bf-214">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="851bf-215">**Presek** prekriva obe skupini.</span><span class="sxs-lookup"><span data-stu-id="851bf-215">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="851bf-216">Samo podatki, ki *so skupni* obema skupinama, se ohranijo v poenoteni skupini.</span><span class="sxs-lookup"><span data-stu-id="851bf-216">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="851bf-217">**Razen** združuje obe skupini.</span><span class="sxs-lookup"><span data-stu-id="851bf-217">**Except** combines the two groups.</span></span> <span data-ttu-id="851bf-218">Samo podatki v skupini A, ki *niso enaki* kot podatki v skupini B, se ohranijo.</span><span class="sxs-lookup"><span data-stu-id="851bf-218">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="851bf-219">Prikaz zgodovine obdelave in članov segmenta</span><span class="sxs-lookup"><span data-stu-id="851bf-219">View processing history and segment members</span></span>

<span data-ttu-id="851bf-220">Usklajene podatke o segmentu si lahko ogledate tako, da pregledate njegove podrobnosti.</span><span class="sxs-lookup"><span data-stu-id="851bf-220">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="851bf-221">Na strani **Segmenti** izberite segment, ki ga želite pregledati.</span><span class="sxs-lookup"><span data-stu-id="851bf-221">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="851bf-222">Zgornji del strani vključuje grafikon trenda, ki prikazuje spremembe v številu članov.</span><span class="sxs-lookup"><span data-stu-id="851bf-222">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="851bf-223">S kazalcem miške pokažite na podatkovne točke, da si ogledate število članov na določen datum.</span><span class="sxs-lookup"><span data-stu-id="851bf-223">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="851bf-224">Časovni okvir vizualizacije lahko posodobite.</span><span class="sxs-lookup"><span data-stu-id="851bf-224">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="851bf-225">![Časovni obseg segmenta](media/segment-time-range.png "Časovni obseg segmenta")</span><span class="sxs-lookup"><span data-stu-id="851bf-225">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="851bf-226">Spodnji del vsebuje seznam članov segmenta.</span><span class="sxs-lookup"><span data-stu-id="851bf-226">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="851bf-227">Polja, ki se prikažejo na tem seznamu, temeljijo na atributih entitet vašega segmenta.</span><span class="sxs-lookup"><span data-stu-id="851bf-227">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="851bf-228">Seznam je predogled ujemajočih se članov segmenta in prikazuje prvih 100 zapisov vašega segmenta, tako da ga lahko po potrebi hitro ocenite in pregledate njegove definicije.</span><span class="sxs-lookup"><span data-stu-id="851bf-228">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="851bf-229">Če si želite ogledati vse ujemajoče se zapise, morate [izvoziti segment](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="851bf-229">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="851bf-230">Hitri segmenti</span><span class="sxs-lookup"><span data-stu-id="851bf-230">Quick segments</span></span>

<span data-ttu-id="851bf-231">Poleg graditelja segmentov obstaja še ena pot za ustvarjanje segmentov.</span><span class="sxs-lookup"><span data-stu-id="851bf-231">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="851bf-232">Hitri segmenti vam omogočajo hitro ustvarjanje preprostih segmentov z enim samim operaterjem in s takojšnjimi vpogledi.</span><span class="sxs-lookup"><span data-stu-id="851bf-232">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="851bf-233">Na strani **Segmenti** izberite možnost **Novo** > **Hitro ustvarjanje iz**.</span><span class="sxs-lookup"><span data-stu-id="851bf-233">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="851bf-234">Izberite možnost **Profili**, da ustvarite segment, ki temelji na poenoteni entiteti stranke.</span><span class="sxs-lookup"><span data-stu-id="851bf-234">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="851bf-235">Izberite možnost **Mere**, da ustvarite segment okoli vsake vrste atributov stranke za mere, ki ste jih ustvarili na strani **Mere**.</span><span class="sxs-lookup"><span data-stu-id="851bf-235">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="851bf-236">Izberite možnost **Obveščanje**, da sestavite segment okoli ene od izhodnih entitet, ki ste jih ustvarili z zmogljivostmi **Predvidevanja** ali **Modeli po meri**.</span><span class="sxs-lookup"><span data-stu-id="851bf-236">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="851bf-237">V pogovornem oknu **Nov hitri segment** izberite atribut s spustnega seznama **Polje**.</span><span class="sxs-lookup"><span data-stu-id="851bf-237">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="851bf-238">Sistem bo zagotovil nekaj dodatnih vpogledov, ki vam bodo pomagali ustvariti boljše segmente strank.</span><span class="sxs-lookup"><span data-stu-id="851bf-238">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="851bf-239">Za kategorična polja bomo prikazali 10 največjih strank.</span><span class="sxs-lookup"><span data-stu-id="851bf-239">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="851bf-240">Izberite **Vrednost** in **Pregled**.</span><span class="sxs-lookup"><span data-stu-id="851bf-240">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="851bf-241">Pri številskem atributu sistem prikaže, katera vrednost atributa spada pod posamezni percentil stranke.</span><span class="sxs-lookup"><span data-stu-id="851bf-241">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="851bf-242">Izberite **Operator** in **Vrednost** ter nato **Pregled**.</span><span class="sxs-lookup"><span data-stu-id="851bf-242">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="851bf-243">Sistem prikaže **ocenjeno velikost segmenta**.</span><span class="sxs-lookup"><span data-stu-id="851bf-243">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="851bf-244">Izberete lahko, ali želite ustvariti segment, ki ste ga določili, ali se želite najprej znova vrniti nanj, da dobite drugačno velikost segmenta.</span><span class="sxs-lookup"><span data-stu-id="851bf-244">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="851bf-245">![Ime in ocena za hitri segment](media/quick-segment-name.png "Ime in ocena za hitri segment")</span><span class="sxs-lookup"><span data-stu-id="851bf-245">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="851bf-246">Vnesite **ime** za segment.</span><span class="sxs-lookup"><span data-stu-id="851bf-246">Provide a **Name** for your segment.</span></span> <span data-ttu-id="851bf-247">Po želji vnesite **prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="851bf-247">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="851bf-248">Izberite **Shrani**, da ustvarite segment.</span><span class="sxs-lookup"><span data-stu-id="851bf-248">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="851bf-249">Ko je obdelava segmenta končana, si ga lahko ogledate kot katerikoli drug segment, ki ste ga ustvarili.</span><span class="sxs-lookup"><span data-stu-id="851bf-249">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="851bf-250">Pri spodnjih scenarijih svetujemo uporabo graditelja segmentov in ne priporočene zmogljivosti segmentov:</span><span class="sxs-lookup"><span data-stu-id="851bf-250">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="851bf-251">Ustvarjanje segmentov s filtri v kategoričnih poljih, kjer je operator drugačen od operatorja **Je**</span><span class="sxs-lookup"><span data-stu-id="851bf-251">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="851bf-252">Ustvarjanje segmentov s filtri v številskih poljih, kjer je operator drugačen od operatorjev **Med**, **Več kot** in **Manj kot**</span><span class="sxs-lookup"><span data-stu-id="851bf-252">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="851bf-253">Ustvarjanje segmentov s filtri na poljih vrste datumov</span><span class="sxs-lookup"><span data-stu-id="851bf-253">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="851bf-254">Naslednji koraki</span><span class="sxs-lookup"><span data-stu-id="851bf-254">Next steps</span></span>

<span data-ttu-id="851bf-255">[Izvozite segment](export-destinations.md) in raziščite [kartico stranke](customer-card-add-in.md) in [povezovalnike](export-power-bi.md), da pridobite vpoglede na ravni stranke.</span><span class="sxs-lookup"><span data-stu-id="851bf-255">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]