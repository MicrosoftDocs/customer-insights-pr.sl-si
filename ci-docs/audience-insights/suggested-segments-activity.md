---
title: Predlagani segmenti, ki temeljijo na dejavnosti.
description: Naj vam strojno učenje pomaga najti nove in zanimive segmente na podlagi dejavnosti strank.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034115"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="39d99-103">Predlagani segmenti, ki temeljijo na podatkih o dejavnosti (predogledna različica)</span><span class="sxs-lookup"><span data-stu-id="39d99-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="39d99-104">Odkrijte zanimive segmente svojih strank na podlagi podatkov o dejavnostih strank, ki so uvoženi v Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="39d99-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="39d99-105">Primeri podatkov o dejavnosti so transakcije, trajanje klica za podporo, nakupi ali vračila.</span><span class="sxs-lookup"><span data-stu-id="39d99-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="39d99-106">Za predlaganje segmentov se podatki o dejavnosti analizirajo glede na nedavnost, pogostost in denarno vrednost (ali trajanje).</span><span class="sxs-lookup"><span data-stu-id="39d99-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="39d99-107">Lahko pa tudi ustvarite [predlagane segmente za izboljšanje mere ali boljše razumevanje vplivov na atribut](suggested-segments.md).</span><span class="sxs-lookup"><span data-stu-id="39d99-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Zavihek Predlagani segmenti, ki prikazuje predloge segmentov za segmente, ki temeljijo na dejavnosti in atributih.":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="39d99-109">Razvrščanje strank po dejavnosti</span><span class="sxs-lookup"><span data-stu-id="39d99-109">Categorize customers by activity</span></span>

<span data-ttu-id="39d99-110">S [podatki o dejavnosti](activities.md), ki so na voljo v rešitvi Customer Insights, lahko ustvarimo predloge, ki predstavljajo skupine strank:</span><span class="sxs-lookup"><span data-stu-id="39d99-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="39d99-111">najbolj dejavne stranke</span><span class="sxs-lookup"><span data-stu-id="39d99-111">most active customers</span></span> 
- <span data-ttu-id="39d99-112">stranke, ki so opravile največ nakupov</span><span class="sxs-lookup"><span data-stu-id="39d99-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="39d99-113">stranke, ki so ustvarile največ prihodka</span><span class="sxs-lookup"><span data-stu-id="39d99-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="39d99-114">stranke, ki zadnje čase niso aktivne</span><span class="sxs-lookup"><span data-stu-id="39d99-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="39d99-115">stranke, ki pogosto komunicirajo z vašim podjetjem</span><span class="sxs-lookup"><span data-stu-id="39d99-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="39d99-116">Če imate trgovino na drobno, lahko izveste, katere stranke ustvarijo največ prihodka, in jih nagradite s kuponom.</span><span class="sxs-lookup"><span data-stu-id="39d99-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="39d99-117">Lahko pa prepoznate občasne stranke in jim ponudite, da se pridružijo programu nagrad, da bodo pogosteje obiskali vaše podjetje.</span><span class="sxs-lookup"><span data-stu-id="39d99-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="39d99-118">Če se ukvarjate z zdravstveno oskrbo in zagotavljate javno zdravstveno oskrbo ter je vaš cilj čim bolj zmanjšati stroške za posamezne bolnike.</span><span class="sxs-lookup"><span data-stu-id="39d99-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="39d99-119">To lahko dosežete tako, da z zagotavljanjem najboljše možne oskrbe v čim manj obiskih zmanjšate število ponavljajočih se obiskov.</span><span class="sxs-lookup"><span data-stu-id="39d99-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="39d99-120">V tem primeru je vaš cilj ohraniti nizko pogostost obiska in zmanjšati ponavljajoče se stroške za paciente.</span><span class="sxs-lookup"><span data-stu-id="39d99-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="39d99-121">Lahko pa prepoznate segmente pacientov, ki imajo pogoste sestanke in ponavljajoče se stroške, ter analizirate te primere za izboljšanje zdravljenja posameznika.</span><span class="sxs-lookup"><span data-stu-id="39d99-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="39d99-122">Zahtevani podatki</span><span class="sxs-lookup"><span data-stu-id="39d99-122">Required data</span></span>

<span data-ttu-id="39d99-123">Predlogi se ustvarijo na podlagi izbranih vhodnih podatkov.</span><span class="sxs-lookup"><span data-stu-id="39d99-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="39d99-124">Profili strank: vse stranke ali člani določenega segmenta.</span><span class="sxs-lookup"><span data-stu-id="39d99-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="39d99-125">Časovno obdobje: prejšnji mesec, lansko leto ali kateri koli časovni okvir po meri.</span><span class="sxs-lookup"><span data-stu-id="39d99-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="39d99-126">Vrsta dejavnosti: nakupi, maloprodajne transakcije, spletne transakcije, primeri podpore strankam, naročnine itd.</span><span class="sxs-lookup"><span data-stu-id="39d99-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="39d99-127">Entiteta v rešitvi Customer Insights, ki vsebuje podatke o dejavnosti: entiteta UnifiedActivity ali entiteta za določeno dejavnost.</span><span class="sxs-lookup"><span data-stu-id="39d99-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="39d99-128">Razsežnosti, ki jih je treba vključiti: nedavnost, pogostost ali denarna razsežnost, odvisno od vaših poslovnih potreb.</span><span class="sxs-lookup"><span data-stu-id="39d99-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="39d99-129">Ustvarjanje predlaganih segmentov</span><span class="sxs-lookup"><span data-stu-id="39d99-129">Generate suggested segments</span></span>

1. <span data-ttu-id="39d99-130">Izberite **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="39d99-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="39d99-131">Izberite zavihek **Predlogi (predogled)**.</span><span class="sxs-lookup"><span data-stu-id="39d99-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="39d99-132">Izberite možnost **Poiščite nove predloge** in **Oglejte si ali predvidevajte vedenje kupcev**.</span><span class="sxs-lookup"><span data-stu-id="39d99-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="39d99-133">Za zagon vodene izkušnje izberite gumb **Začni**.</span><span class="sxs-lookup"><span data-stu-id="39d99-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Prvi korak čarovnika za konfiguracijo za predlagani segment na podlagi dejavnosti.":::

1. <span data-ttu-id="39d99-135">Vnesite zahtevane vhodne podatke in za nadaljevanje izberite gumb **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="39d99-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="39d99-136">Izberite stranke: vključite vse stranke ali določen segment.</span><span class="sxs-lookup"><span data-stu-id="39d99-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="39d99-137">Izberite dejavnost: izberite vrsto dejavnosti in entitete, ki opisujejo dejavnost.</span><span class="sxs-lookup"><span data-stu-id="39d99-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="39d99-138">Nastavitve: nastavite časovno obdobje, ki ga želite upoštevati, dejavnike za predloge in preslikajte atribute.</span><span class="sxs-lookup"><span data-stu-id="39d99-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="39d99-139">Preglejte vnos in izberite možnost **Začni** za zagon modela in ustvarjanje predlogov.</span><span class="sxs-lookup"><span data-stu-id="39d99-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="39d99-140">To lahko traja nekaj minut, odvisno od števila profilov strank in izbranih dejavnosti.</span><span class="sxs-lookup"><span data-stu-id="39d99-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="39d99-141">Ko ustvarite predloge, jih lahko filtrirate po razsežnosti ali vrednosti, ki vas najbolj zanima.</span><span class="sxs-lookup"><span data-stu-id="39d99-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="39d99-142">Ogled podrobnosti predlaganega segmenta</span><span class="sxs-lookup"><span data-stu-id="39d99-142">View details of a suggested segment</span></span>

<span data-ttu-id="39d99-143">Ko so predlogi ustvarjeni, jih boste našli na v zavihku **Segmenti** > **Predlogi (predogledna različica)** v zavihku **Predlogi na podlagi dejavnosti**.</span><span class="sxs-lookup"><span data-stu-id="39d99-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="Razširjeno stransko podokno s podrobnimi podatki predlaganega segmenta.":::

<span data-ttu-id="39d99-145">Na predlaganem segmentu izberite možnost **Ogled predloga**, če si želite ogledati podrobnosti tega segmenta.</span><span class="sxs-lookup"><span data-stu-id="39d99-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="39d99-146">Stransko podokno vsebuje podrobnosti, kot je obseg posamezne razsežnosti v primerjavi s ciljno skupino.</span><span class="sxs-lookup"><span data-stu-id="39d99-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="39d99-147">Poudarja tudi število potencialnih članov v segmentu in ustrezen odstotek vseh kupcev.</span><span class="sxs-lookup"><span data-stu-id="39d99-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="39d99-148">Če želite predlog ohraniti kot segment, izberite možnost **Ustvari segment**.</span><span class="sxs-lookup"><span data-stu-id="39d99-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="39d99-149">Shranjevanje predloga kot segmenta</span><span class="sxs-lookup"><span data-stu-id="39d99-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="39d99-150">Odprite **Segmenti** > **Predlogi (predogled)**.</span><span class="sxs-lookup"><span data-stu-id="39d99-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="39d99-151">Izberite segment, ki ga želite shraniti.</span><span class="sxs-lookup"><span data-stu-id="39d99-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="39d99-152">V stranskem podoknu izberite možnost **Ustvari segment**.</span><span class="sxs-lookup"><span data-stu-id="39d99-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="39d99-153">Ko shranite segment, se bo prikazal na seznamu segmentov v zavihku **Vsi segmenti**. Zdaj ga lahko [osvežite ali izbrišete kot kateri koli drug segment](segments.md).</span><span class="sxs-lookup"><span data-stu-id="39d99-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="39d99-154">Podrobnosti segmenta ne morete urejati.</span><span class="sxs-lookup"><span data-stu-id="39d99-154">You can't edit the segment details.</span></span> <span data-ttu-id="39d99-155">Lahko pa spremenite merila vnosa za predloge in ustvarite različne predloge.</span><span class="sxs-lookup"><span data-stu-id="39d99-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="39d99-156">Osvežitev ali urejanje niza segmentov</span><span class="sxs-lookup"><span data-stu-id="39d99-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="39d99-157">Odprite zavihek **Segmenti** > **Predlogi (predogledna različica)** in poiščite segment v razdelku **Predlogi na podlagi dejavnosti**.</span><span class="sxs-lookup"><span data-stu-id="39d99-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="39d99-158">Izberite **Osveži predloge**, da osvežite predloge in obdržite konfigurirane atribute.</span><span class="sxs-lookup"><span data-stu-id="39d99-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="39d99-159">Ali izberite možnost **Urejanje predlogov**, če želite spreminjati konfigurirane atribute.</span><span class="sxs-lookup"><span data-stu-id="39d99-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="39d99-160">Sistem bo ponovil postopek, ustvaril predloge za segmente na podlagi najnovejših podatkov in nadomestil trenutne predloge.</span><span class="sxs-lookup"><span data-stu-id="39d99-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
