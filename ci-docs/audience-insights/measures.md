---
title: Ustvarjanje in upravljanje mer
description: Določite mere za analizo in odraz uspešnosti vašega podjetja.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9a94a32a04f2a8beb661c27271fe96f23d998722
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887960"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="d249c-103">Določanje in upravljanje mer</span><span class="sxs-lookup"><span data-stu-id="d249c-103">Define and manage measures</span></span>

<span data-ttu-id="d249c-104">Ukrepi vam pomagajo bolje razumeti vedenje strank in poslovno uspešnost.</span><span class="sxs-lookup"><span data-stu-id="d249c-104">Measures help you to better understand customer behaviors and business performance.</span></span> <span data-ttu-id="d249c-105">Upoštevajo relevantne vrednosti iz [poenotenih profilov](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="d249c-105">They look at relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="d249c-106">Podjetje želi na primer videti *skupno porabo stranke*, da bi razumelo zgodovino nakupov stranke, ali izmeriti *skupno prodajo podjetja*, da bi razumelo skupni prihodek celotnega posla.</span><span class="sxs-lookup"><span data-stu-id="d249c-106">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="d249c-107">Mere so ustvarjene z graditeljem mer, platformo za poizvedbe po podatkih z različnimi operatorji in enostavnimi možnostmi preslikave.</span><span class="sxs-lookup"><span data-stu-id="d249c-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="d249c-108">Omogoča filtriranje podatkov, združevanje rezultatov v skupine, zaznavanje [poti odnosov entitet](relationships.md) in predogled rezultatov.</span><span class="sxs-lookup"><span data-stu-id="d249c-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="d249c-109">Uporabite graditelja mer za načrtovanje poslovnih dejavnosti s poizvedbami po podatkih o strankah in pridobivanjem vpogledov.</span><span class="sxs-lookup"><span data-stu-id="d249c-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="d249c-110">Ustvarjanje na primer mer za *skupno porabo na stranko* in *skupni donos na stranko* pomaga prepoznati skupino strank z visoko porabo, ki pa so hkrati zelo donosne.</span><span class="sxs-lookup"><span data-stu-id="d249c-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="d249c-111">Mogoče je [ustvariti segment](segments.md) za spodbujanje drugih priporočenih dejanj.</span><span class="sxs-lookup"><span data-stu-id="d249c-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="build-your-own-measure-from-scratch"></a><span data-ttu-id="d249c-112">Ustvarjanje ukrepa od začetka</span><span class="sxs-lookup"><span data-stu-id="d249c-112">Build your own measure from scratch</span></span>

<span data-ttu-id="d249c-113">V tem razdelku je opisano ustvarjanje novega mere od začetka.</span><span class="sxs-lookup"><span data-stu-id="d249c-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="d249c-114">Mero lahko sestavite z atributi podatkov iz podatkovnih entitet, ki imajo nastavljen odnos za povezavo z entiteto stranke.</span><span class="sxs-lookup"><span data-stu-id="d249c-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="d249c-115">Pri vpogledih v občinstvo izberite **Mere**.</span><span class="sxs-lookup"><span data-stu-id="d249c-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="d249c-116">Izberite **Novo** in nato še **Ustvarite si svojega**.</span><span class="sxs-lookup"><span data-stu-id="d249c-116">Select **New** and choose **Build your own**.</span></span>

1. <span data-ttu-id="d249c-117">Izberite možnost **Uredi ime** in navedite **ime** za mero.</span><span class="sxs-lookup"><span data-stu-id="d249c-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="d249c-118">Če ima nova konfiguracija mere samo dve polji, na primer, CustomerID in en izračun, bodo izhodni podatki dodani kot nov stolpec v sistemsko ustvarjeni entiteti z imenom Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="d249c-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="d249c-119">Vrednost mere pa boste lahko videli v enotnem profilu stranke.</span><span class="sxs-lookup"><span data-stu-id="d249c-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="d249c-120">Druge mere ustvarijo lastne entitete.</span><span class="sxs-lookup"><span data-stu-id="d249c-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="d249c-121">V območju za konfiguracijo izberite združevalno funkcijo s spustnega menija **Izberi funkcijo**.</span><span class="sxs-lookup"><span data-stu-id="d249c-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="d249c-122">Združevalne funkcije vključujejo:</span><span class="sxs-lookup"><span data-stu-id="d249c-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="d249c-123">**Vsota**</span><span class="sxs-lookup"><span data-stu-id="d249c-123">**Sum**</span></span>
   - <span data-ttu-id="d249c-124">**Povprečje**</span><span class="sxs-lookup"><span data-stu-id="d249c-124">**Average**</span></span>
   - <span data-ttu-id="d249c-125">**Število**</span><span class="sxs-lookup"><span data-stu-id="d249c-125">**Count**</span></span>
   - <span data-ttu-id="d249c-126">**Št. enoličnih**</span><span class="sxs-lookup"><span data-stu-id="d249c-126">**Count Unique**</span></span>
   - <span data-ttu-id="d249c-127">**Maksimum**</span><span class="sxs-lookup"><span data-stu-id="d249c-127">**Max**</span></span>
   - <span data-ttu-id="d249c-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="d249c-128">**Min**</span></span>
   - <span data-ttu-id="d249c-129">**Najprej**: vzame prvo vrednost podatkovnega zapisa</span><span class="sxs-lookup"><span data-stu-id="d249c-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="d249c-130">**Zadnje**: vzame zadnjo vrednost, ki je bila dodana v podatkovni zapis</span><span class="sxs-lookup"><span data-stu-id="d249c-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operatorji za izračun mer.":::

1. <span data-ttu-id="d249c-132">Izberite možnost **Dodaj atribut**, da izberete podatke, ki jih potrebujete za izdelavo te mere.</span><span class="sxs-lookup"><span data-stu-id="d249c-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="d249c-133">Izberite zavihek **Atributi**.</span><span class="sxs-lookup"><span data-stu-id="d249c-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="d249c-134">Podatkovna entiteta: izberite entiteto, ki vključuje atribut, ki ga želite izmeriti.</span><span class="sxs-lookup"><span data-stu-id="d249c-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="d249c-135">Atribut podatkov: izberite atribut, ki ga želite uporabiti v združevalni funkciji za izračun mere.</span><span class="sxs-lookup"><span data-stu-id="d249c-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="d249c-136">Naenkrat lahko izberete le en atribut.</span><span class="sxs-lookup"><span data-stu-id="d249c-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="d249c-137">Atribut podatkov lahko izberete tudi iz obstoječe mere tako, da odprete zavihek **Ukrepi**. Poiščete lahko tudi ime entitete ali mere.</span><span class="sxs-lookup"><span data-stu-id="d249c-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="d249c-138">Izberite možnost **Dodaj**, da meri dodate izbrani atribut.</span><span class="sxs-lookup"><span data-stu-id="d249c-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Izberite atribut, ki ga želite uporabiti pri izračunih.":::

1. <span data-ttu-id="d249c-140">Če želite zgraditi bolj zapletene mere, lahko v funkcijo mere dodate več atributov ali uporabite matematične operatorje.</span><span class="sxs-lookup"><span data-stu-id="d249c-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Ustvarjanje zapletene mere z matematičnimi operatorji.":::

1. <span data-ttu-id="d249c-142">Če želite dodati filtre, v konfiguracijskem območju izberite možnost **Filter**.</span><span class="sxs-lookup"><span data-stu-id="d249c-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="d249c-143">V razdelku **Dodaj atribut** na podoknu **Filtri** izberite atribut, ki ga želite uporabiti za ustvarjanje filtrov.</span><span class="sxs-lookup"><span data-stu-id="d249c-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="d249c-144">Nastavite operatorje filtrov, da določite filter za vsak izbrani atribut.</span><span class="sxs-lookup"><span data-stu-id="d249c-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="d249c-145">Izberite možnost **Dodaj**, da meri dodate filter.</span><span class="sxs-lookup"><span data-stu-id="d249c-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="d249c-146">Če želite dodati razsežnosti, v območju za konfiguracijo izberite možnost **Razsežnosti**.</span><span class="sxs-lookup"><span data-stu-id="d249c-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="d249c-147">Dimenzije bodo prikazane kot stolpci v entiteti izhodnih mer.</span><span class="sxs-lookup"><span data-stu-id="d249c-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="d249c-148">Izberite možnost **Uredi razsežnosti**, da dodate atribute podatkov, po katerih želite vrednosti mer razvrstiti v skupine.</span><span class="sxs-lookup"><span data-stu-id="d249c-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="d249c-149">Na primer po mestu ali spolu.</span><span class="sxs-lookup"><span data-stu-id="d249c-149">For example, city or gender.</span></span> <span data-ttu-id="d249c-150">Privzeto je razsežnost *CustomerID* izbrana za ustvarjanje *ukrepov na ravni kupca*.</span><span class="sxs-lookup"><span data-stu-id="d249c-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="d249c-151">Če želite ustvariti *ukrepe na ravni podjetja*, lahko odstranite privzeto dimenzijo.</span><span class="sxs-lookup"><span data-stu-id="d249c-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="d249c-152">Izberite možnost **Končano**, da meri dodate razsežnosti.</span><span class="sxs-lookup"><span data-stu-id="d249c-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="d249c-153">Če so v vaših podatkih vrednosti, ki jih morate zamenjati s celim številom, zamenjajte *null* na primer z *0* in izberite **Pravila**.</span><span class="sxs-lookup"><span data-stu-id="d249c-153">If there are values in your data that you need to replace with an integer, for example, replace *null* with *0*, select **Rules**.</span></span> <span data-ttu-id="d249c-154">Konfigurirajte pravilo in se prepričajte, da jih nadomestite le s celimi števili.</span><span class="sxs-lookup"><span data-stu-id="d249c-154">Configure the rule and make sure that you choose only whole numbers as replacements.</span></span>

1. <span data-ttu-id="d249c-155">Če med podatkovno entiteto, ki ste jo preslikali, in *entiteto* stranke obstaja več poti, morate izbrati eno od prepoznanih [poti odnosov entitet](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="d249c-155">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="d249c-156">Rezultati mere se lahko razlikujejo glede na izbrano pot.</span><span class="sxs-lookup"><span data-stu-id="d249c-156">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="d249c-157">Izberite možnost **Podatkovne nastavitve** in izberite pot entitete, ki naj bo uporabljena za prepoznavanje mere.</span><span class="sxs-lookup"><span data-stu-id="d249c-157">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="d249c-158">Če obstaja samo ena pot do entitete *stranke*, ta nadzor ne bo prikazan.</span><span class="sxs-lookup"><span data-stu-id="d249c-158">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="d249c-159">Izberite možnost **Končano**, da uporabite izbor.</span><span class="sxs-lookup"><span data-stu-id="d249c-159">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Izberite pot entitete za mero.":::

1. <span data-ttu-id="d249c-161">Če želite dodati več izračunov za mero, izberite možnost **Nov izračun**.</span><span class="sxs-lookup"><span data-stu-id="d249c-161">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="d249c-162">Entitete z isto potjo lahko uporabite samo za nove izračune.</span><span class="sxs-lookup"><span data-stu-id="d249c-162">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="d249c-163">Dodatni izračuni bodo prikazani kot novi stolpci v entiteti izhodnih mer.</span><span class="sxs-lookup"><span data-stu-id="d249c-163">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="d249c-164">V izračunu izberite tri pike **...**, da **podvojite**, **preimenujete** ali **odstranite** izračun iz mere.</span><span class="sxs-lookup"><span data-stu-id="d249c-164">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="d249c-165">Na območju **predogleda** boste videli podatkovno shemo entitete izhodnih mer, vključno s filtri in razsežnostmi.</span><span class="sxs-lookup"><span data-stu-id="d249c-165">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="d249c-166">Predogled se dinamično odziva na spremembe v konfiguraciji.</span><span class="sxs-lookup"><span data-stu-id="d249c-166">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="d249c-167">Izberite možnost **Zaženi** za izračun rezultatov za konfigurirano mero.</span><span class="sxs-lookup"><span data-stu-id="d249c-167">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="d249c-168">Izberite možnost **Shrani in zapri**, če želite obdržati trenutno konfiguracijo in mero zagnati pozneje.</span><span class="sxs-lookup"><span data-stu-id="d249c-168">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="d249c-169">Na strani **Mere** si na seznamu oglejte novo ustvarjeno mero.</span><span class="sxs-lookup"><span data-stu-id="d249c-169">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="use-a-template-to-build-a-measure"></a><span data-ttu-id="d249c-170">Uporaba predloge za izdelavo ukrepa</span><span class="sxs-lookup"><span data-stu-id="d249c-170">Use a template to build a measure</span></span>

<span data-ttu-id="d249c-171">Za ustvarjanje ukrepov lahko uporabite vnaprej določene predloge pogosto uporabljenih ukrepov.</span><span class="sxs-lookup"><span data-stu-id="d249c-171">You can use predefined templates of commonly used measures to create them.</span></span> <span data-ttu-id="d249c-172">Podrobni opisi predlog in vodena izkušnja vam pomagajo pri učinkovitem ustvarjanju ukrepov.</span><span class="sxs-lookup"><span data-stu-id="d249c-172">Detailed descriptions of the templates and a guided experience help you with efficient measure creation.</span></span> <span data-ttu-id="d249c-173">Predloge temeljijo na preslikanih podatkih iz entitete *Poenotena dejavnost*.</span><span class="sxs-lookup"><span data-stu-id="d249c-173">Templates build on mapped data from the *Unified Activity* entity.</span></span> <span data-ttu-id="d249c-174">Prepričajte se, da ste konfigurirali [dejavnosti strank](activities.md), preden ustvarite ukrep iz predloge.</span><span class="sxs-lookup"><span data-stu-id="d249c-174">So make sure you have configured [customer activities](activities.md) before you create a measure from a template.</span></span>

<span data-ttu-id="d249c-175">Razpoložljive predloge ukrepov:</span><span class="sxs-lookup"><span data-stu-id="d249c-175">Available measure templates:</span></span> 
- <span data-ttu-id="d249c-176">Povprečna vrednost transakcije (ATV)</span><span class="sxs-lookup"><span data-stu-id="d249c-176">Average transaction value (ATV)</span></span>
- <span data-ttu-id="d249c-177">Skupna vrednost transakcije</span><span class="sxs-lookup"><span data-stu-id="d249c-177">Total transaction value</span></span>
- <span data-ttu-id="d249c-178">Povprečni dnevni prihodek</span><span class="sxs-lookup"><span data-stu-id="d249c-178">Average daily revenue</span></span>
- <span data-ttu-id="d249c-179">Povprečni letni prihodek</span><span class="sxs-lookup"><span data-stu-id="d249c-179">Average yearly revenue</span></span>
- <span data-ttu-id="d249c-180">Število transakcij</span><span class="sxs-lookup"><span data-stu-id="d249c-180">Transaction count</span></span>
- <span data-ttu-id="d249c-181">Prislužene točke zvestobe</span><span class="sxs-lookup"><span data-stu-id="d249c-181">Loyalty points earned</span></span>
- <span data-ttu-id="d249c-182">Izkoriščene točke zvestobe</span><span class="sxs-lookup"><span data-stu-id="d249c-182">Loyalty points redeemed</span></span>
- <span data-ttu-id="d249c-183">Stanje točk zvestobe</span><span class="sxs-lookup"><span data-stu-id="d249c-183">Loyalty points balance</span></span>
- <span data-ttu-id="d249c-184">Življenjska doba dejavne stranke</span><span class="sxs-lookup"><span data-stu-id="d249c-184">Active customer lifespan</span></span>
- <span data-ttu-id="d249c-185">Trajanje članstva v programu zvestobe</span><span class="sxs-lookup"><span data-stu-id="d249c-185">Loyalty membership duration</span></span>
- <span data-ttu-id="d249c-186">Čas od zadnjega nakupa</span><span class="sxs-lookup"><span data-stu-id="d249c-186">Time since last purchase</span></span>

<span data-ttu-id="d249c-187">V naslednjem postopku so opisani koraki za ustvarjanje novega ukrepa s pomočjo predloge.</span><span class="sxs-lookup"><span data-stu-id="d249c-187">The following procedure outlines the steps to build a new measure using a template.</span></span>

1. <span data-ttu-id="d249c-188">Pri vpogledih v občinstvo izberite **Mere**.</span><span class="sxs-lookup"><span data-stu-id="d249c-188">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="d249c-189">Izberite **Novo** in nato **Izberi predlogo**.</span><span class="sxs-lookup"><span data-stu-id="d249c-189">Select **New** and select **Choose a template**.</span></span>

   :::image type="content" source="media/measure-use-template.png" alt-text="Posnetek zaslona spustnega menija pri ustvarjanju novega ukrepa s poudarjeno predlogo.":::

1. <span data-ttu-id="d249c-191">Poiščite predlogo, ki ustreza vašim potrebam, in izberite **Izberi predlogo**.</span><span class="sxs-lookup"><span data-stu-id="d249c-191">Find the template that fits your need and select **Choose template**.</span></span>

1. <span data-ttu-id="d249c-192">Preglejte zahtevane podatke in izberite **Začetek**, če imate na voljo vse podatke.</span><span class="sxs-lookup"><span data-stu-id="d249c-192">Review the required data and select **Get started** if you have all the data in place.</span></span>

1. <span data-ttu-id="d249c-193">V podoknu **Uredi ime** nastavite ime za vaš ukrep in izhodno entiteto.</span><span class="sxs-lookup"><span data-stu-id="d249c-193">In the **Edit name** pane, set the name for your measure and the output entity.</span></span> 

1. <span data-ttu-id="d249c-194">Izberite **Dokončano**.</span><span class="sxs-lookup"><span data-stu-id="d249c-194">Select **Done**.</span></span>

1. <span data-ttu-id="d249c-195">V razdelku **Nastavi časovno obdobje** določite časovni okvir podatkov, ki jih želite uporabiti.</span><span class="sxs-lookup"><span data-stu-id="d249c-195">In the **Set time period** section, define the time frame of the data to use.</span></span> <span data-ttu-id="d249c-196">Določite, ali želite z novim ukrepom zajeti celoten nabor podatkov, tako da izberete **Ves čas**.</span><span class="sxs-lookup"><span data-stu-id="d249c-196">Choose if you want the new measure to cover the entire data set by selecting **All time**.</span></span> <span data-ttu-id="d249c-197">Ali če želite, da se ukrep osredotoči na **Določeno časovno obdobje**.</span><span class="sxs-lookup"><span data-stu-id="d249c-197">Or if you want the measure to focus on a **Specific time period**.</span></span>

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Posnetek zaslona, ki prikazuje razdelek časovnega obdobja pri konfiguriranju ukrepa iz predloge.":::

1. <span data-ttu-id="d249c-199">V naslednjem razdelku izberite **Dodaj podatke**, če želite izbrati dejavnosti in preslikati ustrezne podatke iz vaše entitete *Poenotena dejavnost*.</span><span class="sxs-lookup"><span data-stu-id="d249c-199">In the next section, select **Add data** to choose the activities and map the corresponding data from your *Unified Activity* entity.</span></span>

    1. <span data-ttu-id="d249c-200">Korak 1 od 2: v razdelku **Vrsta dejavnosti** izberite vrsto entitete, ki jo želite uporabiti.</span><span class="sxs-lookup"><span data-stu-id="d249c-200">Step 1 of 2: Under **Activity type**, choose the type of the entity you want to use.</span></span> <span data-ttu-id="d249c-201">Za **Dejavnosti** izberite entitete, ki jih želite preslikati.</span><span class="sxs-lookup"><span data-stu-id="d249c-201">For **Activities**, select the entities you want to map.</span></span>
    1. <span data-ttu-id="d249c-202">Korak 2 od 2: izberite atribut v entiteti *Poenotena dejavnost* za komponento, ki jo zahteva formula.</span><span class="sxs-lookup"><span data-stu-id="d249c-202">Step 2 of 2: Choose the attribute from the *Unified Activity* entity for the component required by the formula.</span></span> <span data-ttu-id="d249c-203">Za povprečno vrednost transakcije je to na primer atribut, ki predstavlja vrednost transakcije.</span><span class="sxs-lookup"><span data-stu-id="d249c-203">For example, for Average transaction value, it's the attribute representing the Transaction value.</span></span> <span data-ttu-id="d249c-204">Za **Časovni žig dejavnosti** izberite atribut iz entitete poenotene dejavnosti, ki predstavlja datum in čas dejavnosti.</span><span class="sxs-lookup"><span data-stu-id="d249c-204">For **Activity timestamp**, choose the attribute from the Unified Activity entity that represents the date and time of the activity.</span></span>
   
1. <span data-ttu-id="d249c-205">Ko je preslikava podatkov uspešno zaključena, se prikaže stanje **Dokončano** skupaj z imenom preslikanih dejavnosti in atributov.</span><span class="sxs-lookup"><span data-stu-id="d249c-205">Once the data mapping is successful, you can see the status as **Complete** and the name of the mapped activities and attributes.</span></span>

   :::image type="content" source="media/measure-template-configured.png" alt-text="Posnetek zaslona dokončane konfiguracije predloge ukrepa.":::

1. <span data-ttu-id="d249c-207">Zdaj lahko izberete **Zaženi**, da izračunate rezultate ukrepa.</span><span class="sxs-lookup"><span data-stu-id="d249c-207">You can now select **Run** to calculate the results of the measure.</span></span> <span data-ttu-id="d249c-208">Če jih želite pozneje prilagoditi, izberite **Shrani osnutek**.</span><span class="sxs-lookup"><span data-stu-id="d249c-208">To refine it later, select **Save draft**.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="d249c-209">Upravljajte svoje mere</span><span class="sxs-lookup"><span data-stu-id="d249c-209">Manage your measures</span></span>

<span data-ttu-id="d249c-210">Seznam ukrepov najdete na strani **Ukrepi**.</span><span class="sxs-lookup"><span data-stu-id="d249c-210">You can find the list of measures on the **Measures** page.</span></span>

<span data-ttu-id="d249c-211">Našli boste podatke o vrsti mere, ustvarjalcu, datumu ustvarjanja, statusu in stanju.</span><span class="sxs-lookup"><span data-stu-id="d249c-211">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="d249c-212">Ko izberete mero s seznama, si lahko ogledate izhodne podatke in jih prenesete kot datoteko .CSV.</span><span class="sxs-lookup"><span data-stu-id="d249c-212">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="d249c-213">Če želite hkrati osvežiti vse svoje mere, izberite **Osveži vse**, ne da bi izbrali posamezno mero.</span><span class="sxs-lookup"><span data-stu-id="d249c-213">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d249c-214">![Dejanja za upravljanje posameznih mer](media/measure-actions.png "Dejanja za upravljanje posameznih mer")</span><span class="sxs-lookup"><span data-stu-id="d249c-214">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="d249c-215">Na seznamu izberite mero za naslednje možnosti:</span><span class="sxs-lookup"><span data-stu-id="d249c-215">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="d249c-216">Za prikaz podrobnosti izberite ime mere.</span><span class="sxs-lookup"><span data-stu-id="d249c-216">Select the measure name to see its details.</span></span>
- <span data-ttu-id="d249c-217">Izberete lahko možnost **Uredi** in uredite konfiguracijo mere.</span><span class="sxs-lookup"><span data-stu-id="d249c-217">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="d249c-218">**Osveži** mero na podlagi najnovejših podatkov.</span><span class="sxs-lookup"><span data-stu-id="d249c-218">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="d249c-219">Mero lahko preimenujete prek možnosti **Preimenuj**.</span><span class="sxs-lookup"><span data-stu-id="d249c-219">**Rename** the measure.</span></span>
- <span data-ttu-id="d249c-220">Za brisanje mere je na voljo **Izbriši**.</span><span class="sxs-lookup"><span data-stu-id="d249c-220">**Delete** the measure.</span></span>
- <span data-ttu-id="d249c-221">**Aktiviraj** ali **deaktiviraj**.</span><span class="sxs-lookup"><span data-stu-id="d249c-221">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="d249c-222">Nedejavne mere se med [načrtovano osvežitvijo](system.md#schedule-tab) ne bodo osvežile.</span><span class="sxs-lookup"><span data-stu-id="d249c-222">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="d249c-223">Na voljo je [šest vrst stanja](system.md#status-types) za opravila/postopke.</span><span class="sxs-lookup"><span data-stu-id="d249c-223">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="d249c-224">Poleg tega je večina postopkov [odvisna od drugih nadaljnjih postopkov](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="d249c-224">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="d249c-225">Izberete lahko stanje postopka in si ogledate podrobnosti o poteku celotnega posla.</span><span class="sxs-lookup"><span data-stu-id="d249c-225">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="d249c-226">Ko za enega izmed poslov izberete **Prikaži podrobnosti**, se prikažejo dodatne informacije: čas obdelave, zadnji datum obdelave ter vse napake in opozorila, povezana z opravilom.</span><span class="sxs-lookup"><span data-stu-id="d249c-226">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="d249c-227">Naslednji korak</span><span class="sxs-lookup"><span data-stu-id="d249c-227">Next step</span></span>

<span data-ttu-id="d249c-228">Z obstoječimi merami lahko ustvarite [segment stranke](segments.md).</span><span class="sxs-lookup"><span data-stu-id="d249c-228">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]