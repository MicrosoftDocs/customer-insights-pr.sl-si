---
title: Vpogledi v segmente za obstoječe segmente
description: Pridobite vpogled v obstoječe segmente, da vidite razlike in skupne značilnosti.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: article
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 92e1b05dd08588a5da446af5b17b2d6ce57490ce
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406992"
---
# <a name="segment-insights-preview"></a><span data-ttu-id="ac46a-103">Vpogled v segmente (predogledna različica)</span><span class="sxs-lookup"><span data-stu-id="ac46a-103">Segment insights (preview)</span></span>

<span data-ttu-id="ac46a-104">Odkrijte dodatne informacije in vpogled v obstoječe segmente.</span><span class="sxs-lookup"><span data-stu-id="ac46a-104">Discover additional information and insights around your existing segments.</span></span> <span data-ttu-id="ac46a-105">Ugotovite, kako se dva segmenta razlikujeta ali kaj imata skupnega.</span><span class="sxs-lookup"><span data-stu-id="ac46a-105">Find out what differentiates two segments or what they have in common.</span></span>

## <a name="segment-overlap"></a><span data-ttu-id="ac46a-106">Prekrivanje segmentov</span><span class="sxs-lookup"><span data-stu-id="ac46a-106">Segment overlap</span></span>

<span data-ttu-id="ac46a-107">Analiza prekrivanja segmentov pokaže, koliko strank in katere stranke so skupne dvema ali več segmentom.</span><span class="sxs-lookup"><span data-stu-id="ac46a-107">Segment overlap analysis shows how many and which customers are common to two or more segments.</span></span> <span data-ttu-id="ac46a-108">Kako se na primer segment pogostih strank prekriva s segmentom, ki vsebuje stranke, zadovoljne z vašo storitvijo ali izdelkom.</span><span class="sxs-lookup"><span data-stu-id="ac46a-108">For example, how a segment of frequent customers overlaps with a segment that contains customers that are satisfied with your service or product.</span></span>
<span data-ttu-id="ac46a-109">Analizirate lahko tudi, kako se prekrivanje spreminja za posamezne atribute.</span><span class="sxs-lookup"><span data-stu-id="ac46a-109">You can also analyze how the overlap changes for specific attributes.</span></span>

### <a name="run-an-overlap-analysis"></a><span data-ttu-id="ac46a-110">Izvedite analizo prekrivanja</span><span class="sxs-lookup"><span data-stu-id="ac46a-110">Run an overlap analysis</span></span>

1. <span data-ttu-id="ac46a-111">V razdelku **Segmenti** izberite zavihek **Vpogled (predogled)**.</span><span class="sxs-lookup"><span data-stu-id="ac46a-111">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="ac46a-112">Izberite **Novo** in nato izberite možnost **Prekrivanje** v podoknu **Izbira vrste vpogleda**.</span><span class="sxs-lookup"><span data-stu-id="ac46a-112">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="ac46a-113">Izberite segmente, ki vas zanimajo, nato izberite **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="ac46a-113">Choose the segments of interest and select **Next**.</span></span>

1. <span data-ttu-id="ac46a-114">Izbirno lahko izberete eno ali več polj, ki vas zanimajo, da analizirate prekrivanje za posamezne vrednosti polj, nato izberite **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="ac46a-114">Optionally, choose one or more fields of interest to analyze overlaps for every possible field value and select **Next**.</span></span>

1. <span data-ttu-id="ac46a-115">Navedite ime za analizo prekrivanja, izbirno ime za prikaz in opis.</span><span class="sxs-lookup"><span data-stu-id="ac46a-115">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="ac46a-116">Za začetek analize izberite možnost **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="ac46a-116">Select **Save** to start the analysis.</span></span> <span data-ttu-id="ac46a-117">Analiza prekrivanja je pripravljena, ko se stanje »Osveževanje« spremeni v stanje »Uspešno«.</span><span class="sxs-lookup"><span data-stu-id="ac46a-117">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-an-overlap-analysis"></a><span data-ttu-id="ac46a-118">Ogled in optimizacija analize prekrivanja</span><span class="sxs-lookup"><span data-stu-id="ac46a-118">View and optimize an overlap analysis</span></span>

<span data-ttu-id="ac46a-119">Po končani analizi poiščite podrobnosti o tem vpogledu v razdelku **Segmenti** > **Vpogled (predogled)**.</span><span class="sxs-lookup"><span data-stu-id="ac46a-119">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Podrobnosti vpogleda v prekrivanje segmentov":::

<span data-ttu-id="ac46a-121">Izberite vpogled za prikaz rezultatov analize:</span><span class="sxs-lookup"><span data-stu-id="ac46a-121">Select an insight to see the analysis results:</span></span>

- <span data-ttu-id="ac46a-122">Število članov, ki se prekrivajo v segmentih, izbranih za analizo.</span><span class="sxs-lookup"><span data-stu-id="ac46a-122">The number of members overlapping the segments selected for analysis.</span></span>
- <span data-ttu-id="ac46a-123">Število članov, vključenih v enega od segmentov, ne pa v ostale segmente.</span><span class="sxs-lookup"><span data-stu-id="ac46a-123">The number of members included in one of the segments but not in the rest of the segments.</span></span>
- <span data-ttu-id="ac46a-124">Če ste med konfiguriranjem analize prekrivanja izbrali polja, jih boste našli na ustreznih zavihkih.</span><span class="sxs-lookup"><span data-stu-id="ac46a-124">If you selected fields while configuring the overlap analysis, you'll find them in the corresponding tabs.</span></span> <span data-ttu-id="ac46a-125">S spustnim menijem za filtriranje lahko izberete katero koli stopnjo zanimanja in v spodnji tabeli se bodo prikazali ustrezni podatki.</span><span class="sxs-lookup"><span data-stu-id="ac46a-125">You can use the filter drop-down to select any attribute level of interest and the table at the bottom will show the corresponding data.</span></span>

## <a name="segment-differentiators"></a><span data-ttu-id="ac46a-126">Diferenciatorji segmentov</span><span class="sxs-lookup"><span data-stu-id="ac46a-126">Segment differentiators</span></span>

<span data-ttu-id="ac46a-127">Diferenciatorji segmentov vam pomagajo ugotoviti, kako se segment razlikuje od ostalih strank ali od drugega segmenta.</span><span class="sxs-lookup"><span data-stu-id="ac46a-127">Segment differentiators help you find out what differentiates a segment from the rest of your customers or from another segment.</span></span> <span data-ttu-id="ac46a-128">Samo izberite segment in sistem bo določil atribute profila in mere, po katerih se izbrani segment razlikuje.</span><span class="sxs-lookup"><span data-stu-id="ac46a-128">You just have to select a segment and the system will identify profile attributes and measures that distinguish the selected segment.</span></span>

### <a name="run-a-differentiator-analysis"></a><span data-ttu-id="ac46a-129">Zagon analize diferenciatorjev</span><span class="sxs-lookup"><span data-stu-id="ac46a-129">Run a differentiator analysis</span></span>

1. <span data-ttu-id="ac46a-130">V razdelku **Segmenti** izberite zavihek **Vpogled (predogled)**.</span><span class="sxs-lookup"><span data-stu-id="ac46a-130">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="ac46a-131">Izberite **Novo** in nato izberite možnost **Prekrivanje** v podoknu **Izbira vrste vpogleda**.</span><span class="sxs-lookup"><span data-stu-id="ac46a-131">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="ac46a-132">Izberite segment, ki ga želite analizirati, kot **Primarni segment** in nato izberite **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="ac46a-132">Choose the segment you want to analyze as **Primary segment** and select **Next**.</span></span>

1. <span data-ttu-id="ac46a-133">Izberite **Vse stranke** ali **Sekundarni segment** za primerjavo s primarnim segmentom, nato izberite **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="ac46a-133">Choose **All customers** or a **Secondary segment** to compare your primary segment with and select **Next**.</span></span>

1. <span data-ttu-id="ac46a-134">Po želji izberite eno ali več področij, ki vas zanimajo, da analizo osredotočite na posamezne atribute, in izberite **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="ac46a-134">Optionally, choose one or more fields of interest to focus the analysis on specific attributes and select **Next**.</span></span>

1. <span data-ttu-id="ac46a-135">Navedite ime za analizo prekrivanja, izbirno ime za prikaz in opis.</span><span class="sxs-lookup"><span data-stu-id="ac46a-135">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="ac46a-136">Za začetek analize izberite možnost **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="ac46a-136">Select **Save** to start the analysis.</span></span> <span data-ttu-id="ac46a-137">Analiza prekrivanja je pripravljena, ko se stanje »Osveževanje« spremeni v stanje »Uspešno«.</span><span class="sxs-lookup"><span data-stu-id="ac46a-137">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-a-differentiators-analysis"></a><span data-ttu-id="ac46a-138">Ogled in optimizacija analize diferenciatorjev</span><span class="sxs-lookup"><span data-stu-id="ac46a-138">View and optimize a differentiators analysis</span></span>

<span data-ttu-id="ac46a-139">Po končani analizi poiščite podrobnosti o tem vpogledu v razdelku **Segmenti** > **Vpogled (predogled)**.</span><span class="sxs-lookup"><span data-stu-id="ac46a-139">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Podrobnosti vpogleda v diferenciatorje segmentov":::

<span data-ttu-id="ac46a-141">Izberite vpogled za prikaz rezultatov analize.</span><span class="sxs-lookup"><span data-stu-id="ac46a-141">Select an insight to see the analysis results.</span></span> <span data-ttu-id="ac46a-142">Analiza diferenciatorjev ima dva zavihka.</span><span class="sxs-lookup"><span data-stu-id="ac46a-142">A differentiator analysis includes two tabs.</span></span> <span data-ttu-id="ac46a-143">Na zavihku **Atributi** je seznam atributov profila, ki so obravnavani kot diferenciatorji.</span><span class="sxs-lookup"><span data-stu-id="ac46a-143">The **Attributes** tab lists profile attributes considered as differentiators.</span></span> <span data-ttu-id="ac46a-144">Na zavihku **Mere** je seznam diferenciatorjev.</span><span class="sxs-lookup"><span data-stu-id="ac46a-144">The **Measures** tab lists differentiators.</span></span> <span data-ttu-id="ac46a-145">Oba zavihka vsebuje naslednje podrobnosti:</span><span class="sxs-lookup"><span data-stu-id="ac46a-145">Each tab includes the following details:</span></span>

- <span data-ttu-id="ac46a-146">Seznam diferenciatorjev, razvrščenih po oceni razlike.</span><span class="sxs-lookup"><span data-stu-id="ac46a-146">Ranked list of differentiators, sorted by difference score.</span></span>
- <span data-ttu-id="ac46a-147">**Ocena razlike** za posamezne diferenciatorje.</span><span class="sxs-lookup"><span data-stu-id="ac46a-147">The **Difference score** for each differentiator.</span></span> <span data-ttu-id="ac46a-148">Ocena razlike predstavlja stopnjo razlikovanja atributa med dvema segmentoma.</span><span class="sxs-lookup"><span data-stu-id="ac46a-148">The difference score represents the degree of difference of an attribute between two segments.</span></span> <span data-ttu-id="ac46a-149">Večja kot je ocena razlike, bolj se atributi med dvema segmentoma razlikujejo.</span><span class="sxs-lookup"><span data-stu-id="ac46a-149">The higher the difference score, the more the attributes differ between the two segments.</span></span> <span data-ttu-id="ac46a-150">Izberite oceno, da odprete podokno **Ocena razlike** s porazdelitvijo vrednosti za želen atribut.</span><span class="sxs-lookup"><span data-stu-id="ac46a-150">Select a score to open the **Difference score** pane with the distributions of values for that attribute.</span></span>

## <a name="manage-segment-insights"></a><span data-ttu-id="ac46a-151">Upravljanje vpogledov v segmente</span><span class="sxs-lookup"><span data-stu-id="ac46a-151">Manage segment insights</span></span>

<span data-ttu-id="ac46a-152">Za vpoglede lahko v ukazni vrstici uporabite naslednje možnosti:</span><span class="sxs-lookup"><span data-stu-id="ac46a-152">You can use the following options on your insights from the command bar:</span></span>

- <span data-ttu-id="ac46a-153">**Nazaj**, da se vrnete na seznam vpogledov</span><span class="sxs-lookup"><span data-stu-id="ac46a-153">**Back** to return the list of insights</span></span>
- <span data-ttu-id="ac46a-154">**Osveži**, da znova zaženete analizo</span><span class="sxs-lookup"><span data-stu-id="ac46a-154">**Refresh** to run the analysis again</span></span>
- <span data-ttu-id="ac46a-155">**Izbriši**, da odstranite vpogled</span><span class="sxs-lookup"><span data-stu-id="ac46a-155">**Delete** to remove this insight</span></span>
