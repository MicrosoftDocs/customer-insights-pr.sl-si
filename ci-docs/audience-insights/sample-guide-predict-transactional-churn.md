---
title: Vzorčni vodnik za predvidevanje izgube glede transakcij
description: S tem vzorčnim vodnikom preizkusite vnaprej pripravljeni model za predvidevanje izgube glede transakcij.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 81540ad2f490cf566f031233543b3cb6aa838033
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269810"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a><span data-ttu-id="6d1e2-103">Vzorčni vodnik za predvidevanje izgube glede transakcij (predogled)</span><span class="sxs-lookup"><span data-stu-id="6d1e2-103">Transactional churn prediction (preview) sample guide</span></span>

<span data-ttu-id="6d1e2-104">S spodnjimi podatki vam bomo v tem vodniku razložili celovit primer predvidevanja izgube glede transakcij v storitvi Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-104">This guide will walk you through an end to end example of Transactional Churn prediction in Customer Insights using the data provided below.</span></span> <span data-ttu-id="6d1e2-105">Vsi podatki, uporabljeni v tem priročniku, niso resnični podatki o strankah in so del nabora podatkov Contoso, ki ga najdemo v *predstavitvenem* okolju v okviru naročnine Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-105">All data used in this guide is not real customer data and is part of the Contoso dataset found in the *Demo* environment within your Customer Insights Subscription.</span></span>

## <a name="scenario"></a><span data-ttu-id="6d1e2-106">Scenarij</span><span class="sxs-lookup"><span data-stu-id="6d1e2-106">Scenario</span></span>

<span data-ttu-id="6d1e2-107">Contoso je podjetje, ki proizvaja visokokakovostno kavo in kavne avtomate, ki jih prodaja prek njihovega spletnega mesta Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-107">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="6d1e2-108">Njihov cilj je vedeti, katere stranke, ki običajno redno kupujejo njihove izdelke, ne bodo več aktivne stranke v naslednjih 60 dneh.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-108">Their goal is to know which customers who typically purchase their products on a regular basis, will stop being active customers in the next 60 days.</span></span> <span data-ttu-id="6d1e2-109">Znanje o tem, katere stranke se bodo **verjetno izgubile**, jim lahko pomaga, da bolje izkoristijo tržna prizadevanja tako, da se osredotočijo na njihovo ohranitev.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6d1e2-110">Zahteve</span><span class="sxs-lookup"><span data-stu-id="6d1e2-110">Prerequisites</span></span>

- <span data-ttu-id="6d1e2-111">Vsaj [dovoljenja sodelavcev](permissions.md) v storitvi Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="6d1e2-112">Priporočamo, da izvedete naslednje korake [v novem okolju](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="6d1e2-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="6d1e2-113">1. opravilo – vnos podatkov</span><span class="sxs-lookup"><span data-stu-id="6d1e2-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="6d1e2-114">Preglejte specifične članke [o vnosu podatkov](data-sources.md) in [uvozu virov podatkov z uporabo povezovalnikov Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="6d1e2-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="6d1e2-115">Z naslednjimi informacijami domnevamo, da ste na splošno seznanjeni z vnosom podatkov.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="6d1e2-116">Vnos podatkov o strankah s platforme elektronskega poslovanja</span><span class="sxs-lookup"><span data-stu-id="6d1e2-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="6d1e2-117">Ustvarite vir podatkov z imenom **EPoslovanje**, izberite možnost uvoza in izberite povezovalnik **Besedilo/CSV**.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="6d1e2-118">Vnesite URL za stike za elektronsko poslovanje https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="6d1e2-119">Med urejanjem podatkov izberite **Pretvori** in potem **Uporabi prvo vrstico kot glavo**.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="6d1e2-120">Posodobite vrsto podatkov za spodaj navedene stolpce:</span><span class="sxs-lookup"><span data-stu-id="6d1e2-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="6d1e2-121">**DateOfBirth**: datum</span><span class="sxs-lookup"><span data-stu-id="6d1e2-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="6d1e2-122">**CreatedOn**: datum/čas/časovni pas</span><span class="sxs-lookup"><span data-stu-id="6d1e2-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="6d1e2-123">![Spremeni datum rojstva v datum](media/ecommerce-dob-date.PNG "Spremeni datum rojstva v datum")</span><span class="sxs-lookup"><span data-stu-id="6d1e2-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="6d1e2-124">V polju **Ime** v desnem podoknu preimenujte vir podatkov iz **Poizvedba** v **StikiEPoslovanja**</span><span class="sxs-lookup"><span data-stu-id="6d1e2-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="6d1e2-125">Shranite vir podatkov.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-125">Save the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="6d1e2-126">Vnos podatkov o spletnem nakupu</span><span class="sxs-lookup"><span data-stu-id="6d1e2-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="6d1e2-127">Dodajte še nabor podatkov z istega vira podatkov **EPoslovanje**.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="6d1e2-128">Znova izberite povezovalnik **Besedilo/CSV**.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="6d1e2-129">Vnesite URL za podatke **Spletni nakupi** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="6d1e2-130">Med urejanjem podatkov izberite **Pretvori** in potem **Uporabi prvo vrstico kot glavo**.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="6d1e2-131">Posodobite vrsto podatkov za spodaj navedene stolpce:</span><span class="sxs-lookup"><span data-stu-id="6d1e2-131">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="6d1e2-132">**PurchasedOn**: datum/čas</span><span class="sxs-lookup"><span data-stu-id="6d1e2-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="6d1e2-133">**TotalPrice**: valuta</span><span class="sxs-lookup"><span data-stu-id="6d1e2-133">**TotalPrice**: Currency</span></span>
   
1. <span data-ttu-id="6d1e2-134">V desnem podoknu v polju **Ime** preimenujte svoj vir podatkov iz **Poizvedba** v **NakupiEPoslovanja**.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="6d1e2-135">Shranite vir podatkov.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-135">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="6d1e2-136">Vnos podatkov o strankah iz sheme za zvestobo</span><span class="sxs-lookup"><span data-stu-id="6d1e2-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="6d1e2-137">Ustvarite vir podatkov z imenom **ShemaZvestobe**, izberite možnost uvoza in izberite povezovalnik **Besedilo/CSV**.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="6d1e2-138">Vnesite URL za stike za elektronsko poslovanje https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="6d1e2-139">Med urejanjem podatkov izberite **Pretvori** in potem **Uporabi prvo vrstico kot glavo**.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="6d1e2-140">Posodobite vrsto podatkov za spodaj navedene stolpce:</span><span class="sxs-lookup"><span data-stu-id="6d1e2-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="6d1e2-141">**DateOfBirth**: datum</span><span class="sxs-lookup"><span data-stu-id="6d1e2-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="6d1e2-142">**RewardsPoints**: celo število</span><span class="sxs-lookup"><span data-stu-id="6d1e2-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="6d1e2-143">**CreatedOn**: datum/čas</span><span class="sxs-lookup"><span data-stu-id="6d1e2-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="6d1e2-144">V desnem podoknu v polju **Ime** preimenujte svoj vir podatkov iz **Poizvedba** v **zvesteStranke**.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="6d1e2-145">Shranite vir podatkov.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-145">Save the data source.</span></span>


## <a name="task-2---data-unification"></a><span data-ttu-id="6d1e2-146">2. opravilo – poenotenje podatkov</span><span class="sxs-lookup"><span data-stu-id="6d1e2-146">Task 2 - Data unification</span></span>

<span data-ttu-id="6d1e2-147">Po vnosu podatkov začnemo s postopkom **Preslikava/ujemanje/spajanje** za izdelavo poenotenega profila stranke.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-147">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="6d1e2-148">Če želite več informacij, glejte [Poenotenje podatkov](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="6d1e2-148">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="6d1e2-149">Preslikava</span><span class="sxs-lookup"><span data-stu-id="6d1e2-149">Map</span></span>

1. <span data-ttu-id="6d1e2-150">Po vnosu podatkov preslikajte stike iz podatkov o elektronskem poslovanju in zvestobi v običajne vrste podatkov.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-150">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="6d1e2-151">Izberite **Podatki** > **Poenotenje** > **Preslikava**.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-151">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="6d1e2-152">Izberite entitete, ki predstavljajo profil stranke – **StikiEPoslovanja** in **zvesteStranke**.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-152">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="Poenotenje virov podatkov o elektronskem poslovanju in zvestobi.":::

1. <span data-ttu-id="6d1e2-154">Izberite **IDstika** kot primarni ključ za **StikiEPoslovanja** in **ID zvestobe** kot primarni ključ za **zvesteStranke**.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-154">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Poenotite IDzvestobe kot primarni ključ.":::

### <a name="match"></a><span data-ttu-id="6d1e2-156">Povezovanje</span><span class="sxs-lookup"><span data-stu-id="6d1e2-156">Match</span></span>

1. <span data-ttu-id="6d1e2-157">Izberite zavihek **Ujemanje** in izberite **Nastavi vrstni red**.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-157">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="6d1e2-158">Na spustnem seznamu **Primarno** izberite **StikiEPoslovanja: EPoslovanje** kot primarni vir in vključite vse zapise.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-158">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="6d1e2-159">Na spustnem seznamu **Entiteta 2** izberite **zvesteStranke: ShemaZvestobe** in vključite vse zapise.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-159">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Poenotenje ujemanja elektronskega poslovanja in zvestobe.":::

1. <span data-ttu-id="6d1e2-161">Izberite **Ustvarjanje novega pravila**.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-161">Select **Create a new rule**</span></span>

1. <span data-ttu-id="6d1e2-162">Dodajte svoj prvi pogoj z možnostjo FullName.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-162">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="6d1e2-163">Za StikiEPoslovanja izberite **FullName** v spustnem meniju.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-163">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="6d1e2-164">Za zvesteStranke izberite **FullName** v spustnem meniju.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-164">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="6d1e2-165">Izberite spustni meni **Normaliziraj** in izberite **Vrsta (telefon, ime, naslov, ...)**.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-165">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="6d1e2-166">Nastavite **Raven natančnosti**: **Osnovno** in **Vrednost**: **Visoko**.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-166">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="6d1e2-167">Vnesite ime **FullName, Email** za novo pravilo.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-167">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="6d1e2-168">Dodajte drugi pogoj za e-poštni naslov tako, da izberete **Dodaj pogoj**.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-168">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="6d1e2-169">Za StikiEPoslovanja entitete izberite **E-pošta** v spustnem meniju.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-169">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="6d1e2-170">Za zvesteStranke entitete izberite **E-pošta** v spustnem meniju.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-170">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="6d1e2-171">Pustite polje Normaliziraj prazno.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-171">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="6d1e2-172">Nastavite **Raven natančnosti**: **Osnovno** in **Vrednost**: **Visoko**.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-172">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Poenotenje pravila ujemanja za ime in e-pošto.":::

7. <span data-ttu-id="6d1e2-174">Izberite **Shrani** in **Zaženi**.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-174">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="6d1e2-175">Spajanje</span><span class="sxs-lookup"><span data-stu-id="6d1e2-175">Merge</span></span>

1. <span data-ttu-id="6d1e2-176">Odprite zavihek **Spajanje**.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-176">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="6d1e2-177">Pri **IDstranke** za entiteto **zvesteStranke** spremenite prikazno ime v **ZVESTOBAIDstranke**, da se razlikuje od ostalih vnesenih ID-jev.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-177">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="Preimenujte ID stika iz ID-ja zvestobe.":::

1. <span data-ttu-id="6d1e2-179">Izberite **Shrani** in **Zaženi**, da začnete postopek spajanja.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-179">Select **Save** and **Run** to start the Merge Process.</span></span>



## <a name="task-3---configure-transaction-churn-prediction"></a><span data-ttu-id="6d1e2-180">3. opravilo – konfiguracija predvidevanja izgube glede transakcij</span><span class="sxs-lookup"><span data-stu-id="6d1e2-180">Task 3 - Configure transaction churn prediction</span></span>

<span data-ttu-id="6d1e2-181">Z vzpostavljenimi poenotenimi profili strank lahko zdaj zaženemo predvidevanje izgube naročnin.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-181">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="6d1e2-182">Za podrobne korake glejte članek [Predvidevanje izgube naročnin (predogled)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="6d1e2-182">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="6d1e2-183">Odprite **Obveščanje** > **Odkrivanje** in izberite uporabo možnosti **Model izgube strank**.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-183">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="6d1e2-184">Izberite možnost **Transakcijsko** in izberite **Začetek**.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-184">Select the **Transactional** option and select **Get started**.</span></span>

1. <span data-ttu-id="6d1e2-185">Poimenujte model **Predvidevanje izgube glede transakcij elektronskega poslovanja OOB** in izhodno entiteto **PredvidevanjeIzgubeElektronskegaPoslovanjaOOB**.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-185">Name the model **OOB eCommerce Transaction Churn Prediction** and the output entity **OOBeCommerceChurnPrediction**.</span></span>

1. <span data-ttu-id="6d1e2-186">Določite dva pogoja za model izgube:</span><span class="sxs-lookup"><span data-stu-id="6d1e2-186">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="6d1e2-187">**Okno za predvidevanja**: **vsaj 60** dni.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-187">**Prediction window**: **at least 60** days.</span></span> <span data-ttu-id="6d1e2-188">Ta nastavitev določa, kako daleč v prihodnost želimo predvideti izgubo stranke.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-188">This setting defines how far into the future do we want to predict customer churn.</span></span>

   * <span data-ttu-id="6d1e2-189">**Opredelitev izgube**: **vsaj 60** dni.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-189">**Churn definition**: **at least 60** days.</span></span> <span data-ttu-id="6d1e2-190">Trajanje brez nakupa, po katerem se šteje, da je stranka izgubljena.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-190">The duration without purchase after which a customer is considered churned.</span></span>

     :::image type="content" source="media/model-levers.PNG" alt-text="Izberite časovno obdobje za predvidevanje modela in opredelitev izgube.":::

1. <span data-ttu-id="6d1e2-192">Za zgodovino nakupov izberite **Zgodovina nakupov (priporočeno)** in nato **Dodajanje podatkov**.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-192">Select **Purchase History (required)** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="6d1e2-193">Dodajte entiteto **NakupiEPoslovanja: EPoslovanje** in preslikajte polja iz elektronskega poslovanja v ustrezna polja, ki jih zahteva model.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-193">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="6d1e2-194">Pridružite entiteto **NakupiEPoslovanja: EPoslovanje** z entiteto **StikiEPoslovanja: EPoslovanje**.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-194">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Pridružite se entitetam elektronskega poslovanja.":::

1. <span data-ttu-id="6d1e2-196">Izberite **Naprej** za nastavitev urnika modela.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-196">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="6d1e2-197">Model se mora redno usposabljati, da se nauči novih vzorcev, ko vnese nove podatke.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-197">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="6d1e2-198">V tem primeru izberite **Mesečno**.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-198">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="6d1e2-199">Po pregledu vseh podrobnosti izberite **Shrani in zaženi**.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-199">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="6d1e2-200">4. opravilo – preglejte rezultate modela in razlage</span><span class="sxs-lookup"><span data-stu-id="6d1e2-200">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="6d1e2-201">Model naj dokonča usposabljanje in ocenjevanje podatkov.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-201">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="6d1e2-202">Zdaj si lahko ogledate razlage modela izgube naročnine.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-202">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="6d1e2-203">Za več informacij glejte [Pregled stanja in rezultatov predvidevanja](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="6d1e2-203">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="6d1e2-204">5. opravilo – ustvarjanje segmenta strank z visokim tveganjem izgube</span><span class="sxs-lookup"><span data-stu-id="6d1e2-204">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="6d1e2-205">Z zagonom produkcijskega modela ustvarite novo entiteto, ki jo lahko vidite v razdelku **Podatki** > **Entitete**.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-205">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="6d1e2-206">Na podlagi entitete, ki jo je ustvaril model, lahko ustvarite nov segment.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-206">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="6d1e2-207">Izberite **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-207">Go to **Segments**.</span></span> <span data-ttu-id="6d1e2-208">Izberite **Novo** in izberite **Ustvari iz** > **Obveščanje**.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-208">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Ustvarjanje segmenta z izhodnimi podatki modela.":::

1. <span data-ttu-id="6d1e2-210">Izberite končno točko **PredvidevanjeIzgubeNaročnineOOB** in definirajte segment:</span><span class="sxs-lookup"><span data-stu-id="6d1e2-210">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="6d1e2-211">Polje: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="6d1e2-211">Field: ChurnScore</span></span>
   - <span data-ttu-id="6d1e2-212">Operator: večje kot</span><span class="sxs-lookup"><span data-stu-id="6d1e2-212">Operator: greater than</span></span>
   - <span data-ttu-id="6d1e2-213">Vrednost: 0,6</span><span class="sxs-lookup"><span data-stu-id="6d1e2-213">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Nastavite segment izgube naročnine.":::

<span data-ttu-id="6d1e2-215">Zdaj imate segment, ki se dinamično posodablja, v katerem so prepoznane stranke z visokim tveganjem izgube za to naročniško dejavnost.</span><span class="sxs-lookup"><span data-stu-id="6d1e2-215">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="6d1e2-216">Za več informacij glejte [Ustvarjanje in upravljanje segmentov](segments.md).</span><span class="sxs-lookup"><span data-stu-id="6d1e2-216">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]