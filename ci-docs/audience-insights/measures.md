---
title: Ustvarjanje in upravljanje mer
description: Določite mere za analizo in odraz uspešnosti vašega podjetja.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 5bcee3b4c51880740715575b18fd7a4dbf87e6d0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269948"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="0f4a7-103">Določanje in upravljanje mer</span><span class="sxs-lookup"><span data-stu-id="0f4a7-103">Define and manage measures</span></span>

<span data-ttu-id="0f4a7-104">Mere vam pomagajo bolje razumeti vedenje strank in poslovno uspešnost tako, da vam prikažejo relevantne vrednosti iz [poenotenih profilov](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="0f4a7-104">Measures help you to better understand customer behaviors and business performance by retrieving relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="0f4a7-105">Podjetje na primer želi videti *skupno porabo na stranko* za razumevanje zgodovine nakupov posameznih strank.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-105">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history.</span></span> <span data-ttu-id="0f4a7-106">Ali izmeriti *celotno prodajo podjetja* za razumevanje združenega prihodka na ravni celotnega podjetja.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-106">Or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="0f4a7-107">Mere so ustvarjene z graditeljem mer, platformo za poizvedbe po podatkih z različnimi operatorji in enostavnimi možnostmi preslikave.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="0f4a7-108">Omogoča filtriranje podatkov, združevanje rezultatov v skupine, zaznavanje [poti odnosov entitet](relationships.md) in predogled rezultatov.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="0f4a7-109">Uporabite graditelja mer za načrtovanje poslovnih dejavnosti s poizvedbami po podatkih o strankah in pridobivanjem vpogledov.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="0f4a7-110">Ustvarjanje na primer mer za *skupno porabo na stranko* in *skupni donos na stranko* pomaga prepoznati skupino strank z visoko porabo, ki pa so hkrati zelo donosne.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="0f4a7-111">Mogoče je [ustvariti segment](segments.md) za spodbujanje drugih priporočenih dejanj.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="create-a-measure"></a><span data-ttu-id="0f4a7-112">Ustvarjanje mere</span><span class="sxs-lookup"><span data-stu-id="0f4a7-112">Create a measure</span></span>

<span data-ttu-id="0f4a7-113">V tem razdelku je opisano ustvarjanje novega mere od začetka.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="0f4a7-114">Mero lahko sestavite z atributi podatkov iz podatkovnih entitet, ki imajo nastavljen odnos za povezavo z entiteto stranke.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="0f4a7-115">Pri vpogledih v občinstvo izberite **Mere**.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="0f4a7-116">Izberite **Novo**.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-116">Select **New**.</span></span>

1. <span data-ttu-id="0f4a7-117">Izberite možnost **Uredi ime** in navedite **ime** za mero.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="0f4a7-118">Če ima nova konfiguracija mere samo dve polji, na primer, CustomerID in en izračun, bodo izhodni podatki dodani kot nov stolpec v sistemsko ustvarjeni entiteti z imenom Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="0f4a7-119">Vrednost mere pa boste lahko videli v enotnem profilu stranke.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="0f4a7-120">Druge mere ustvarijo lastne entitete.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="0f4a7-121">V območju za konfiguracijo izberite združevalno funkcijo s spustnega menija **Izberi funkcijo**.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="0f4a7-122">Združevalne funkcije vključujejo:</span><span class="sxs-lookup"><span data-stu-id="0f4a7-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="0f4a7-123">**Vsota**</span><span class="sxs-lookup"><span data-stu-id="0f4a7-123">**Sum**</span></span>
   - <span data-ttu-id="0f4a7-124">**Povprečje**</span><span class="sxs-lookup"><span data-stu-id="0f4a7-124">**Average**</span></span>
   - <span data-ttu-id="0f4a7-125">**Število**</span><span class="sxs-lookup"><span data-stu-id="0f4a7-125">**Count**</span></span>
   - <span data-ttu-id="0f4a7-126">**Št. enoličnih**</span><span class="sxs-lookup"><span data-stu-id="0f4a7-126">**Count Unique**</span></span>
   - <span data-ttu-id="0f4a7-127">**Maksimum**</span><span class="sxs-lookup"><span data-stu-id="0f4a7-127">**Max**</span></span>
   - <span data-ttu-id="0f4a7-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="0f4a7-128">**Min**</span></span>
   - <span data-ttu-id="0f4a7-129">**Najprej**: vzame prvo vrednost podatkovnega zapisa</span><span class="sxs-lookup"><span data-stu-id="0f4a7-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="0f4a7-130">**Zadnje**: vzame zadnjo vrednost, ki je bila dodana v podatkovni zapis</span><span class="sxs-lookup"><span data-stu-id="0f4a7-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operatorji za izračun mer.":::

1. <span data-ttu-id="0f4a7-132">Izberite možnost **Dodaj atribut**, da izberete podatke, ki jih potrebujete za izdelavo te mere.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="0f4a7-133">Izberite zavihek **Atributi**.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="0f4a7-134">Podatkovna entiteta: izberite entiteto, ki vključuje atribut, ki ga želite izmeriti.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="0f4a7-135">Atribut podatkov: izberite atribut, ki ga želite uporabiti v združevalni funkciji za izračun mere.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="0f4a7-136">Naenkrat lahko izberete le en atribut.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="0f4a7-137">Atribut podatkov lahko izberete tudi iz obstoječe mere tako, da odprete zavihek **Ukrepi**. Poiščete lahko tudi ime entitete ali mere.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="0f4a7-138">Izberite možnost **Dodaj**, da meri dodate izbrani atribut.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Izberite atribut, ki ga želite uporabiti pri izračunih.":::

1. <span data-ttu-id="0f4a7-140">Če želite zgraditi bolj zapletene mere, lahko v funkcijo mere dodate več atributov ali uporabite matematične operatorje.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Ustvarjanje zapletene mere z matematičnimi operatorji.":::

1. <span data-ttu-id="0f4a7-142">Če želite dodati filtre, v konfiguracijskem območju izberite možnost **Filter**.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="0f4a7-143">V razdelku **Dodaj atribut** na podoknu **Filtri** izberite atribut, ki ga želite uporabiti za ustvarjanje filtrov.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="0f4a7-144">Nastavite operatorje filtrov, da določite filter za vsak izbrani atribut.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="0f4a7-145">Izberite možnost **Dodaj**, da meri dodate filter.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="0f4a7-146">Če želite dodati razsežnosti, v območju za konfiguracijo izberite možnost **Razsežnosti**.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="0f4a7-147">Dimenzije bodo prikazane kot stolpci v entiteti izhodnih mer.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="0f4a7-148">Izberite možnost **Uredi razsežnosti**, da dodate atribute podatkov, po katerih želite vrednosti mer razvrstiti v skupine.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="0f4a7-149">Na primer po mestu ali spolu.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-149">For example, city or gender.</span></span> <span data-ttu-id="0f4a7-150">Privzeto je razsežnost *CustomerID* izbrana za ustvarjanje *ukrepov na ravni kupca*.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="0f4a7-151">Če želite ustvariti *ukrepe na ravni podjetja*, lahko odstranite privzeto dimenzijo.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="0f4a7-152">Izberite možnost **Končano**, da meri dodate razsežnosti.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="0f4a7-153">Če med podatkovno entiteto, ki ste jo preslikali, in entiteto stranke obstaja več poti, morate izbrati eno od prepoznanih [poti odnosov entitet](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="0f4a7-153">If there are multiple paths between the data entity you mapped and the Customer entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="0f4a7-154">Rezultati mere se lahko razlikujejo glede na izbrano pot.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-154">Measure results can vary depending on the selected path.</span></span>
   1. <span data-ttu-id="0f4a7-155">Izberite možnost **Podatkovne nastavitve** in izberite pot entitete, ki naj bo uporabljena za prepoznavanje mere.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-155">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span>
   1. <span data-ttu-id="0f4a7-156">Izberite možnost **Končano**, da uporabite izbor.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-156">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Izberite pot entitete za mero.":::

1. <span data-ttu-id="0f4a7-158">Če želite dodati več izračunov za mero, izberite možnost **Nov izračun**.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-158">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="0f4a7-159">Entitete z isto potjo lahko uporabite samo za nove izračune.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-159">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="0f4a7-160">Dodatni izračuni bodo prikazani kot novi stolpci v entiteti izhodnih mer.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-160">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="0f4a7-161">V izračunu izberite tri pike **...**, da **podvojite**, **preimenujete** ali **odstranite** izračun iz mere.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-161">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="0f4a7-162">Na območju **predogleda** boste videli podatkovno shemo entitete izhodnih mer, vključno s filtri in razsežnostmi.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-162">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="0f4a7-163">Predogled se dinamično odziva na spremembe v konfiguraciji.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-163">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="0f4a7-164">Izberite možnost **Zaženi** za izračun rezultatov za konfigurirano mero.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-164">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="0f4a7-165">Izberite možnost **Shrani in zapri**, če želite obdržati trenutno konfiguracijo in mero zagnati pozneje.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-165">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="0f4a7-166">Na strani **Mere** si na seznamu oglejte novo ustvarjeno mero.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-166">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="0f4a7-167">Upravljajte svoje mere</span><span class="sxs-lookup"><span data-stu-id="0f4a7-167">Manage your measures</span></span>

<span data-ttu-id="0f4a7-168">Ko [ustvarite mero](#create-a-measure), boste na strani **Mere** videli seznam mer.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-168">After [creating a measure](#create-a-measure), you see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="0f4a7-169">Našli boste podatke o vrsti mere, ustvarjalcu, datumu ustvarjanja, statusu in stanju.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-169">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="0f4a7-170">Ko izberete mero s seznama, si lahko ogledate izhodne podatke in jih prenesete kot datoteko .CSV.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-170">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="0f4a7-171">Če želite hkrati osvežiti vse svoje mere, izberite **Osveži vse**, ne da bi izbrali posamezno mero.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-171">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0f4a7-172">![Dejanja za upravljanje posameznih mer](media/measure-actions.png "Dejanja za upravljanje posameznih mer")</span><span class="sxs-lookup"><span data-stu-id="0f4a7-172">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="0f4a7-173">Na seznamu izberite mero za naslednje možnosti:</span><span class="sxs-lookup"><span data-stu-id="0f4a7-173">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="0f4a7-174">Za prikaz podrobnosti izberite ime mere.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-174">Select the measure name to see its details.</span></span>
- <span data-ttu-id="0f4a7-175">Izberete lahko možnost **Uredi** in uredite konfiguracijo mere.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-175">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="0f4a7-176">**Osveži** mero na podlagi najnovejših podatkov.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-176">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="0f4a7-177">Mero lahko preimenujete prek možnosti **Preimenuj**.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-177">**Rename** the measure.</span></span>
- <span data-ttu-id="0f4a7-178">Za brisanje mere je na voljo **Izbriši**.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-178">**Delete** the measure.</span></span>
- <span data-ttu-id="0f4a7-179">**Aktiviraj** ali **deaktiviraj**.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-179">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="0f4a7-180">Nedejavne mere se med [načrtovano osvežitvijo](system.md#schedule-tab) ne bodo osvežile.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-180">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="0f4a7-181">Na voljo je [šest vrst stanja](system.md#status-types) za opravila/postopke.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-181">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="0f4a7-182">Poleg tega je večina postopkov [odvisna od drugih nadaljnjih postopkov](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="0f4a7-182">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="0f4a7-183">Izberete lahko stanje postopka in si ogledate podrobnosti o poteku celotnega posla.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-183">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="0f4a7-184">Ko za enega izmed poslov izberete **Prikaži podrobnosti**, se prikažejo dodatne informacije: čas obdelave, zadnji datum obdelave ter vse napake in opozorila, povezana z opravilom.</span><span class="sxs-lookup"><span data-stu-id="0f4a7-184">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="0f4a7-185">Naslednji korak</span><span class="sxs-lookup"><span data-stu-id="0f4a7-185">Next step</span></span>

<span data-ttu-id="0f4a7-186">Z obstoječimi merami lahko ustvarite [segment stranke](segments.md).</span><span class="sxs-lookup"><span data-stu-id="0f4a7-186">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]