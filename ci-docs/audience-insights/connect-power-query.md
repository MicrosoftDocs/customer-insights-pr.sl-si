---
title: Vključitev podatkov prek povezovalnika Power Query
description: Povezovalniki za podatkovne vire, ki temeljijo na Power Query.
ms.date: 09/29/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: b9a1b30e37c3792aa7bdfcfc177da9e8a32c324d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596933"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="71ee9-103">Povezava z virom podatkov Power Query</span><span class="sxs-lookup"><span data-stu-id="71ee9-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="71ee9-104">Power Query ponuja širok nabor povezovalnikov za uvoz podatkov.</span><span class="sxs-lookup"><span data-stu-id="71ee9-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="71ee9-105">Dynamics 365 Customer Insights podpira večino teh povezovalnikov.</span><span class="sxs-lookup"><span data-stu-id="71ee9-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="71ee9-106">Dodajanje virov podatkov na podlagi povezovalnikov Power Query običajno sledi korakom, opisanim v naslednjem razdelku.</span><span class="sxs-lookup"><span data-stu-id="71ee9-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="71ee9-107">Vendar pa so glede na povezovalnik, ki ga uporabljate, potrebne drugačne informacije.</span><span class="sxs-lookup"><span data-stu-id="71ee9-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="71ee9-108">Za več informacij glejte dokumentacijo o posameznih povezovalnikih v [sklicih na povezovalnike Power Query](/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="71ee9-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="71ee9-109">Ustvarjanje novega vira podatkov</span><span class="sxs-lookup"><span data-stu-id="71ee9-109">Create a new data source</span></span>

1. <span data-ttu-id="71ee9-110">Pri vpogledih v občinstvo izberite **Podatki** > **Viri podatkov**.</span><span class="sxs-lookup"><span data-stu-id="71ee9-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="71ee9-111">Izberite **Dodaj vir podatkov**.</span><span class="sxs-lookup"><span data-stu-id="71ee9-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="71ee9-112">Izberite način **Uvozi podatke** in nato **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="71ee9-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="71ee9-113">Vnesite **Ime** za vir podatkov in izberite **Naprej**, da ustvarite vir podatkov.</span><span class="sxs-lookup"><span data-stu-id="71ee9-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span> <span data-ttu-id="71ee9-114">Smernice za poimenovanje:</span><span class="sxs-lookup"><span data-stu-id="71ee9-114">Name guidelines:</span></span> 
   - <span data-ttu-id="71ee9-115">Začnite s črko.</span><span class="sxs-lookup"><span data-stu-id="71ee9-115">Start with a letter.</span></span>
   - <span data-ttu-id="71ee9-116">Uporabljajte samo črke in številke.</span><span class="sxs-lookup"><span data-stu-id="71ee9-116">Use letters and numbers only.</span></span> <span data-ttu-id="71ee9-117">Posebni znaki in presledki niso dovoljeni.</span><span class="sxs-lookup"><span data-stu-id="71ee9-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="71ee9-118">Uporabite od 3 do 64 znakov.</span><span class="sxs-lookup"><span data-stu-id="71ee9-118">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="71ee9-119">Izberite enega od [razpoložljivih povezovalnikov](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="71ee9-119">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="71ee9-120">Za ta primer izberemo povezovalnik **Besedilo/CSV**.</span><span class="sxs-lookup"><span data-stu-id="71ee9-120">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="71ee9-121">Vnesite zahtevane podrobnosti v **Nastavitve povezave** za izbrani povezovalnik in izberite **Naprej**, da si ogledate predogled podatkov.</span><span class="sxs-lookup"><span data-stu-id="71ee9-121">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="71ee9-122">Izberite **Pretvori podatke**.</span><span class="sxs-lookup"><span data-stu-id="71ee9-122">Select **Transform data**.</span></span> <span data-ttu-id="71ee9-123">V tem koraku boste dodali entitete v vir podatkov.</span><span class="sxs-lookup"><span data-stu-id="71ee9-123">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="71ee9-124">Entitete so nabori podatkov.</span><span class="sxs-lookup"><span data-stu-id="71ee9-124">Entities are datasets.</span></span> <span data-ttu-id="71ee9-125">Če imate zbirko podatkov, ki vključuje več naborov podatkov, je vsak nabor podatkov svoja entiteta.</span><span class="sxs-lookup"><span data-stu-id="71ee9-125">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="71ee9-126">Pogovorno okno **Power Query - Urejanje poizvedb** omogoča pregled in natančnejše določanje podatkov.</span><span class="sxs-lookup"><span data-stu-id="71ee9-126">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="71ee9-127">Entitete, ki jih sistemi, opredeljeni v izbranem viru podatkov, prikažejo v levem podoknu.</span><span class="sxs-lookup"><span data-stu-id="71ee9-127">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="71ee9-128">![Pogovorno okno urejanja poizvedb](media/data-manager-configure-edit-queries.png "Pogovorno okno urejanja poizvedb")</span><span class="sxs-lookup"><span data-stu-id="71ee9-128">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="71ee9-129">Podatke pa lahko tudi preoblikujete.</span><span class="sxs-lookup"><span data-stu-id="71ee9-129">You can also transform your data.</span></span> <span data-ttu-id="71ee9-130">Izberite entiteto, ki jo želite urediti ali preoblikovati.</span><span class="sxs-lookup"><span data-stu-id="71ee9-130">Select an entity to edit or transform.</span></span> <span data-ttu-id="71ee9-131">Uporabite možnosti v oknu Power Query, da uporabite pretvorbe.</span><span class="sxs-lookup"><span data-stu-id="71ee9-131">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="71ee9-132">Vsaka pretvorba je navedena pod **Uporabljeni koraki**.</span><span class="sxs-lookup"><span data-stu-id="71ee9-132">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="71ee9-133">Power Query ponuja številne vnaprej vgrajene možnosti preoblikovanja.</span><span class="sxs-lookup"><span data-stu-id="71ee9-133">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="71ee9-134">Če želite več informacij, glejte razdelek [Pretvorbe Power Query](/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="71ee9-134">For more information, see [Power Query Transformations](/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="71ee9-135">Virom podatkov lahko dodate dodatne entitete tako, da izberete **Pridobi podatke** v pogovornem oknu **Urejanje poizvedb**.</span><span class="sxs-lookup"><span data-stu-id="71ee9-135">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="71ee9-136">Ta preoblikovanja so zelo priporočljiva:</span><span class="sxs-lookup"><span data-stu-id="71ee9-136">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="71ee9-137">Če vnašate podatke iz datoteke CSV, prva vrstica pogosto vsebuje glave.</span><span class="sxs-lookup"><span data-stu-id="71ee9-137">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="71ee9-138">Pojdite na **Tabela pretvorb** in izberite **Uporabi glave kot prvo vrstico**.</span><span class="sxs-lookup"><span data-stu-id="71ee9-138">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="71ee9-139">Prepričajte se, da je vrsta podatkov pravilno nastavljena.</span><span class="sxs-lookup"><span data-stu-id="71ee9-139">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="71ee9-140">Izberite **Shrani** na dnu okna Power Query, da shranite pretvorbe.</span><span class="sxs-lookup"><span data-stu-id="71ee9-140">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="71ee9-141">Po shranjevanju boste našli svoj vir podatkov pod **Podatki** > **Viri podatkov**.</span><span class="sxs-lookup"><span data-stu-id="71ee9-141">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="71ee9-142">Na strani **Viri podatkov** boste opazili, da ima nov vir podatkov stanje **Osveževanje**.</span><span class="sxs-lookup"><span data-stu-id="71ee9-142">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="71ee9-143">Razpoložljivi viri podatkov Power Query</span><span class="sxs-lookup"><span data-stu-id="71ee9-143">Available Power Query data sources</span></span>

<span data-ttu-id="71ee9-144">Glejte [sklicevanje na povezovalnik Power Query](/power-query/connectors/) za posodobljen seznam povezovalnikov, ki jih lahko izberete za uvoz podatkov v Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="71ee9-144">See the [Power Query connector reference](/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="71ee9-145">Povezovalniki s kljukico v stolpcu **Customer Insights (podatkovni toki)** so na voljo za ustvarjanje novih virov podatkov, ki temeljijo na Power Query.</span><span class="sxs-lookup"><span data-stu-id="71ee9-145">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="71ee9-146">Preglejte dokumentacijo določenega povezovalnika, če želite izvedeti več o njegovih predpogojih, omejitvah in drugih podrobnostih.</span><span class="sxs-lookup"><span data-stu-id="71ee9-146">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="71ee9-147">Urejanje virov podatkov Power Query</span><span class="sxs-lookup"><span data-stu-id="71ee9-147">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="71ee9-148">Morda ne bo mogoče spreminjati virov podatkov, ki se trenutno uporabljajo v enem od procesov aplikacije (na primer *segmentacija*, *ujemanje* ali *spajanje*).</span><span class="sxs-lookup"><span data-stu-id="71ee9-148">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="71ee9-149">Na strani **Nastavitve** lahko spremljate potek posameznih dejavnih procesov.</span><span class="sxs-lookup"><span data-stu-id="71ee9-149">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="71ee9-150">Ko se proces zaključi, se lahko vrnete na stran **Viri podatkov** in opravite spremembe.</span><span class="sxs-lookup"><span data-stu-id="71ee9-150">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="71ee9-151">Pri vpogledih v občinstvo izberite **Podatki** > **Viri podatkov**.</span><span class="sxs-lookup"><span data-stu-id="71ee9-151">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="71ee9-152">Izberite navpične tri pike poleg vira podatkov, ki ga želite spremeniti, in na spustnem meniju izberite **Uredi**.</span><span class="sxs-lookup"><span data-stu-id="71ee9-152">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="71ee9-153">![Možnost urejanja](media/edit-option-data-sources.png "Možnost urejanja")</span><span class="sxs-lookup"><span data-stu-id="71ee9-153">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="71ee9-154">Uporabite svoje spremembe in pretvorbe v pogovornem oknu **Power Query - Urejanje poizvedb**, kot je opisano v razdelku [Ustvari nov vir podatkov](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="71ee9-154">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="71ee9-155">Izberite **Shrani** v Power Query po zaključitvi sprememb, da shranite spremembe.</span><span class="sxs-lookup"><span data-stu-id="71ee9-155">Select **Save** in Power Query after completing your edits to save your changes.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]