---
title: Ustvarjanje in upravljanje segmentov
description: Ustvarite segmente strank, da jih združite na podlagi različnih atributov.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064957"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="16b89-103">Ustvarjanje in upravljanje segmentov</span><span class="sxs-lookup"><span data-stu-id="16b89-103">Create and manage segments</span></span>

<span data-ttu-id="16b89-104">Določite zapletene filtre okoli poenotene entitete stranke in z njo povezanih entitet.</span><span class="sxs-lookup"><span data-stu-id="16b89-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="16b89-105">Po obdelavi vsak segment ustvari niz zapisov strank, ki jih lahko izvozite in obdelate.</span><span class="sxs-lookup"><span data-stu-id="16b89-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="16b89-106">Segmenti se upravljajo na strani **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="16b89-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="16b89-107">Naslednji primer prikazuje zmogljivost segmentacije.</span><span class="sxs-lookup"><span data-stu-id="16b89-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="16b89-108">Določili smo segment za stranke, ki so v zadnjih 90 dneh naročile blaga v vrednosti vsaj 500 USD *in* ki so bile vključene v klic storitev za stranke, ki je bil posredovan na višjo raven.</span><span class="sxs-lookup"><span data-stu-id="16b89-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Posnetek zaslona uporabniškega vmesnika za graditelja segmentov z dvema skupinama, ki določita segment stranke.":::

## <a name="create-a-new-segment"></a><span data-ttu-id="16b89-110">Ustvarjanje novega segmenta</span><span class="sxs-lookup"><span data-stu-id="16b89-110">Create a new segment</span></span>

<span data-ttu-id="16b89-111">Nov segment lahko ustvarite na več načinov.</span><span class="sxs-lookup"><span data-stu-id="16b89-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="16b89-112">Ta razdelek opisuje, kako ustvariti *prazen segment* od začetka.</span><span class="sxs-lookup"><span data-stu-id="16b89-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="16b89-113">Lahko tudi ustvarite *hitri segment* na podlagi obstoječih entitet ali uporabite modele strojnega učenja za pridobitev *predlaganih segmentov*.</span><span class="sxs-lookup"><span data-stu-id="16b89-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="16b89-114">Več informacij: [Pregled segmentov](segments.md).</span><span class="sxs-lookup"><span data-stu-id="16b89-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="16b89-115">Med ustvarjanjem segmenta lahko shranite osnutek.</span><span class="sxs-lookup"><span data-stu-id="16b89-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="16b89-116">Shranjen bo kot neaktiven segment in ga ni mogoče aktivirati, ko je končan z veljavno konfiguracijo.</span><span class="sxs-lookup"><span data-stu-id="16b89-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="16b89-117">Pojdite na stran **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="16b89-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="16b89-118">Izberite **Novo** > **Prazen segment**.</span><span class="sxs-lookup"><span data-stu-id="16b89-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="16b89-119">V podoknu **Nov segment** izberite vrsto segmenta:</span><span class="sxs-lookup"><span data-stu-id="16b89-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="16b89-120">**Dinamični segmenti** se [osvežijo](segments.md#refresh-segments) po ponavljajočem se načrtovanju.</span><span class="sxs-lookup"><span data-stu-id="16b89-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="16b89-121">**Statični segmenti** se zaženejo enkrat, ko jih ustvarite.</span><span class="sxs-lookup"><span data-stu-id="16b89-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="16b89-122">Navedite **ime izhodne entitete** za segment.</span><span class="sxs-lookup"><span data-stu-id="16b89-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="16b89-123">Po želji vnesite prikazno ime in opis, s katerim boste lažje prepoznali segment.</span><span class="sxs-lookup"><span data-stu-id="16b89-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="16b89-124">Izberite **Naprej**, da se pomaknete na stran **Graditelj segmentov**, kjer določite skupino.</span><span class="sxs-lookup"><span data-stu-id="16b89-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="16b89-125">Skupina je nabor strank.</span><span class="sxs-lookup"><span data-stu-id="16b89-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="16b89-126">Izberite entiteto, ki vključuje atribut, po katerem želite segmentirati.</span><span class="sxs-lookup"><span data-stu-id="16b89-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="16b89-127">Izberite atribut, po katerem želite segmentirati.</span><span class="sxs-lookup"><span data-stu-id="16b89-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="16b89-128">Ta atribut ima lahko eno od štirih vrst vrednosti: numerično, niz, datum ali logična vrednost.</span><span class="sxs-lookup"><span data-stu-id="16b89-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="16b89-129">Izberite operator in vrednost za izbrani atribut.</span><span class="sxs-lookup"><span data-stu-id="16b89-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="16b89-130">![Filter skupine po meri](media/customer-group-numbers.png "Filter skupine strank")</span><span class="sxs-lookup"><span data-stu-id="16b89-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="16b89-131">Številka</span><span class="sxs-lookup"><span data-stu-id="16b89-131">Number</span></span> |<span data-ttu-id="16b89-132">Definicija</span><span class="sxs-lookup"><span data-stu-id="16b89-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="16b89-133">1</span><span class="sxs-lookup"><span data-stu-id="16b89-133">1</span></span>     |<span data-ttu-id="16b89-134">Entity</span><span class="sxs-lookup"><span data-stu-id="16b89-134">Entity</span></span>          |
   |<span data-ttu-id="16b89-135">2</span><span class="sxs-lookup"><span data-stu-id="16b89-135">2</span></span>     |<span data-ttu-id="16b89-136">Atribut</span><span class="sxs-lookup"><span data-stu-id="16b89-136">Attribute</span></span>          |
   |<span data-ttu-id="16b89-137">3</span><span class="sxs-lookup"><span data-stu-id="16b89-137">3</span></span>    |<span data-ttu-id="16b89-138">Operator</span><span class="sxs-lookup"><span data-stu-id="16b89-138">Operator</span></span>         |
   |<span data-ttu-id="16b89-139">4</span><span class="sxs-lookup"><span data-stu-id="16b89-139">4</span></span>    |<span data-ttu-id="16b89-140">Vrednost</span><span class="sxs-lookup"><span data-stu-id="16b89-140">Value</span></span>         |

   1. <span data-ttu-id="16b89-141">Če želite v skupino dodati več pogojev, lahko uporabite dva logična operaterja:</span><span class="sxs-lookup"><span data-stu-id="16b89-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="16b89-142">Operator **IN**: oba pogoja morata biti izpolnjena kot del postopka segmentacije.</span><span class="sxs-lookup"><span data-stu-id="16b89-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="16b89-143">Ta možnost je najbolj uporabna, če določite pogoje v različnih entitetah.</span><span class="sxs-lookup"><span data-stu-id="16b89-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="16b89-144">Operator **ALI**: izpolnjen mora biti kateri koli od pogojev kot del postopka segmentacije.</span><span class="sxs-lookup"><span data-stu-id="16b89-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="16b89-145">Ta možnost je najbolj uporabna, če določite več pogojev za isto entiteto.</span><span class="sxs-lookup"><span data-stu-id="16b89-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="16b89-146">![Operator ALI, pri katerem mora biti izpolnjen kateri koli pogoj](media/segmentation-either-condition.png "Operator ALI, pri katerem mora biti izpolnjen kateri koli pogoj")</span><span class="sxs-lookup"><span data-stu-id="16b89-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="16b89-147">Trenutno je mogoče ugnezditi operator **ALI** pod operator **IN**, ne pa obratno.</span><span class="sxs-lookup"><span data-stu-id="16b89-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="16b89-148">Vsaka skupina se ujema z naborom strank.</span><span class="sxs-lookup"><span data-stu-id="16b89-148">Each group matches set of customers.</span></span> <span data-ttu-id="16b89-149">Skupine lahko združite tako, da vključite stranke, potrebne za vaš poslovni primer.</span><span class="sxs-lookup"><span data-stu-id="16b89-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="16b89-150">Izberite **Dodaj skupino**.</span><span class="sxs-lookup"><span data-stu-id="16b89-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="16b89-151">![Dodajanje skupine za skupino strank](media/customer-group-add-group.png "Dodajanje skupine za skupino strank")</span><span class="sxs-lookup"><span data-stu-id="16b89-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="16b89-152">Izberite enega od nastavljenih operatorjev: **Združitev**, **Presek** ali **Razen**.</span><span class="sxs-lookup"><span data-stu-id="16b89-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="16b89-153">![Dodajanje unije za skupino strank](media/customer-group-union.png "Dodajanje unije za skupino strank")</span><span class="sxs-lookup"><span data-stu-id="16b89-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="16b89-154">**Unija** združi dve skupini.</span><span class="sxs-lookup"><span data-stu-id="16b89-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="16b89-155">**Presek** prekriva obe skupini.</span><span class="sxs-lookup"><span data-stu-id="16b89-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="16b89-156">Samo podatki, ki *so skupni* obema skupinama, se ohranijo v poenoteni skupini.</span><span class="sxs-lookup"><span data-stu-id="16b89-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="16b89-157">**Razen** združuje obe skupini.</span><span class="sxs-lookup"><span data-stu-id="16b89-157">**Except** combines the two groups.</span></span> <span data-ttu-id="16b89-158">Samo podatki v skupini A, ki *niso enaki* kot podatki v skupini B, se ohranijo.</span><span class="sxs-lookup"><span data-stu-id="16b89-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="16b89-159">Če je entiteta povezana s poenoteno entiteto stranke prek [odnosov](relationships.md), morate določiti pot odnosa, da ustvarite veljaven segment.</span><span class="sxs-lookup"><span data-stu-id="16b89-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="16b89-160">Dodajte entitete s poti odnosa, dokler se na spustnem meniju ne pojavi možnost za izbiro entitete **Stranka: CustomerInsights**.</span><span class="sxs-lookup"><span data-stu-id="16b89-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="16b89-161">Nato za vsak korak izberite možnost **Vsi zapisi**.</span><span class="sxs-lookup"><span data-stu-id="16b89-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="16b89-162">![Pot odnosa med ustvarjanjem segmenta](media/segments-multiple-relationships.png "Pot odnosa med ustvarjanjem segmenta")</span><span class="sxs-lookup"><span data-stu-id="16b89-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="16b89-163">Segmenti privzeto generirajo izhodno entiteto, ki vsebuje vse atribute profilov strank, ki se ujemajo z določenimi filtri.</span><span class="sxs-lookup"><span data-stu-id="16b89-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="16b89-164">Če segment temelji na drugih entitetah kot na entiteti *stranke*, lahko v izhodno entiteto dodate več atributov teh entitet.</span><span class="sxs-lookup"><span data-stu-id="16b89-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="16b89-165">Izberite **Atributi projekta**, da izberete atribute, ki bodo dodani izhodni entiteti.</span><span class="sxs-lookup"><span data-stu-id="16b89-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="16b89-166">Primer: Segment temelji na entiteti, ki vsebuje podatke o dejavnostih strank, povezane z entiteto *stranke*.</span><span class="sxs-lookup"><span data-stu-id="16b89-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="16b89-167">Segment išče vse stranke, ki so v zadnjih 60 dneh poklicale službo za pomoč uporabnikom.</span><span class="sxs-lookup"><span data-stu-id="16b89-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="16b89-168">Trajanje in število klicev lahko v izhodni entiteti priložite v vse ustrezne zapise strank, ki se ujemajo.</span><span class="sxs-lookup"><span data-stu-id="16b89-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="16b89-169">Te informacije so lahko koristne za pošiljanje e-pošte strankam, ki so pogosto klicale, s koristnimi povezavami do spletnih člankov za pomoč in pogostih vprašanj.</span><span class="sxs-lookup"><span data-stu-id="16b89-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="16b89-170">Predvideni atributi delujejo samo za entitete, ki imajo z entiteto stranke odnos »eden proti mnogo«.</span><span class="sxs-lookup"><span data-stu-id="16b89-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="16b89-171">Ena stranka ima na primer lahko več naročnin.</span><span class="sxs-lookup"><span data-stu-id="16b89-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="16b89-172">Atribute lahko projicirate samo iz entitete, ki se uporablja v vsaki skupini poizvedb segmenta, ki jo gradite.</span><span class="sxs-lookup"><span data-stu-id="16b89-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="16b89-173">Predvideni atributi se upoštevajo pri uporabi operatorjev nabora.</span><span class="sxs-lookup"><span data-stu-id="16b89-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="16b89-174">Izberite **Shrani**, da shranite segment.</span><span class="sxs-lookup"><span data-stu-id="16b89-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="16b89-175">Če so vse zahteve potrjene, bo vaš segment shranjen in obdelan.</span><span class="sxs-lookup"><span data-stu-id="16b89-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="16b89-176">V nasprotnem primeru bo shranjen kot osnutek.</span><span class="sxs-lookup"><span data-stu-id="16b89-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="16b89-177">Izberite **Nazaj na segmente**, da se vrnete na stran **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="16b89-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="16b89-178">Hitri segmenti</span><span class="sxs-lookup"><span data-stu-id="16b89-178">Quick segments</span></span>

<span data-ttu-id="16b89-179">Hitri segmenti vam omogočajo hitro izdelavo preprostih segmentov z enim samim operatorjem za hitrejši vpogled.</span><span class="sxs-lookup"><span data-stu-id="16b89-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="16b89-180">Na strani **Segmenti** izberite možnost **Nov** > **Ustvari iz**.</span><span class="sxs-lookup"><span data-stu-id="16b89-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="16b89-181">Izberite možnost **Profili**, da ustvarite segment, ki temelji na *poenoteni entiteti stranke*.</span><span class="sxs-lookup"><span data-stu-id="16b89-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="16b89-182">Izberite možnost **Mere** za gradnjo segmenta okoli mer, ki ste jih že ustvarili.</span><span class="sxs-lookup"><span data-stu-id="16b89-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="16b89-183">Izberite možnost **Obveščanje**, da sestavite segment okoli ene od izhodnih entitet, ki ste jih ustvarili z zmogljivostmi **Predvidevanja** ali **Modeli po meri**.</span><span class="sxs-lookup"><span data-stu-id="16b89-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="16b89-184">V pogovornem oknu **Nov hitri segment** izberite atribut s spustnega seznama **Polje**.</span><span class="sxs-lookup"><span data-stu-id="16b89-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="16b89-185">Sistem bo zagotovil nekaj dodatnih vpogledov, ki vam bodo pomagali ustvariti boljše segmente strank.</span><span class="sxs-lookup"><span data-stu-id="16b89-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="16b89-186">Za kategorična polja bomo prikazali 10 največjih strank.</span><span class="sxs-lookup"><span data-stu-id="16b89-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="16b89-187">Izberite **Vrednost** in **Pregled**.</span><span class="sxs-lookup"><span data-stu-id="16b89-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="16b89-188">Pri številskem atributu sistem prikaže, katera vrednost atributa spada pod posamezni percentil stranke.</span><span class="sxs-lookup"><span data-stu-id="16b89-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="16b89-189">Izberite **Operator** in **Vrednost** ter nato **Pregled**.</span><span class="sxs-lookup"><span data-stu-id="16b89-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="16b89-190">Sistem prikaže **ocenjeno velikost segmenta**.</span><span class="sxs-lookup"><span data-stu-id="16b89-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="16b89-191">Izberete lahko, ali želite ustvariti segment, ki ste ga določili, ali se želite najprej znova vrniti nanj, da dobite drugačno velikost segmenta.</span><span class="sxs-lookup"><span data-stu-id="16b89-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="16b89-192">![Ime in ocena za hitri segment](media/quick-segment-name.png "Ime in ocena za hitri segment")</span><span class="sxs-lookup"><span data-stu-id="16b89-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="16b89-193">Vnesite **ime** za segment.</span><span class="sxs-lookup"><span data-stu-id="16b89-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="16b89-194">Po želji vnesite **prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="16b89-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="16b89-195">Izberite **Shrani**, da ustvarite segment.</span><span class="sxs-lookup"><span data-stu-id="16b89-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="16b89-196">Ko je obdelava segmenta končana, si ga lahko ogledate kot katerikoli drug segment, ki ste ga ustvarili.</span><span class="sxs-lookup"><span data-stu-id="16b89-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="16b89-197">Naslednji koraki</span><span class="sxs-lookup"><span data-stu-id="16b89-197">Next steps</span></span>

<span data-ttu-id="16b89-198">[Izvozite segment](export-destinations.md) in raziščite [kartico stranke](customer-card-add-in.md) in [povezovalnike](export-power-bi.md), da pridobite vpoglede na ravni stranke.</span><span class="sxs-lookup"><span data-stu-id="16b89-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
