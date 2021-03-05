---
title: Vzorčni vodnik za predvidevanje izgube naročnin
description: S tem vzorčnim vodnikom preizkusite vnaprej pripravljeni model za predvidevanje izgube naročnin.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3f1019ace424f89320c5a0d5058e928f4cbc7e62
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269867"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="c2b55-103">Vzorčni vodnik za predvidevanje izgube naročnin (predogled)</span><span class="sxs-lookup"><span data-stu-id="c2b55-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="c2b55-104">S spodnjimi vzorčnimi podatki vam bomo razložili celovit primer predvidevanja izgube naročnin.</span><span class="sxs-lookup"><span data-stu-id="c2b55-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="c2b55-105">Scenarij</span><span class="sxs-lookup"><span data-stu-id="c2b55-105">Scenario</span></span>

<span data-ttu-id="c2b55-106">Contoso je podjetje, ki proizvaja visokokakovostno kavo in kavne avtomate, ki jih prodaja prek njihovega spletnega mesta Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="c2b55-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="c2b55-107">Pred kratkim so začeli naročniško dejavnost, s katero so stranke redno dobivale kavo.</span><span class="sxs-lookup"><span data-stu-id="c2b55-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="c2b55-108">Njihov cilj je razumeti, katere naročene stranke bi lahko v naslednjih nekaj mesecih odpovedale naročnino.</span><span class="sxs-lookup"><span data-stu-id="c2b55-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="c2b55-109">Znanje o tem, katere stranke se bodo **verjetno izgubile**, jim lahko pomaga, da bolje izkoristijo tržna prizadevanja tako, da se osredotočijo na njihovo ohranitev.</span><span class="sxs-lookup"><span data-stu-id="c2b55-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c2b55-110">Zahteve</span><span class="sxs-lookup"><span data-stu-id="c2b55-110">Prerequisites</span></span>

- <span data-ttu-id="c2b55-111">Vsaj [dovoljenja sodelavcev](permissions.md) v storitvi Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c2b55-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="c2b55-112">Priporočamo, da izvedete naslednje korake [v novem okolju](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="c2b55-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="c2b55-113">1. opravilo – vnos podatkov</span><span class="sxs-lookup"><span data-stu-id="c2b55-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="c2b55-114">Preglejte specifične članke [o vnosu podatkov](data-sources.md) in [uvozu virov podatkov z uporabo povezovalnikov Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="c2b55-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="c2b55-115">Z naslednjimi informacijami domnevamo, da ste na splošno seznanjeni z vnosom podatkov.</span><span class="sxs-lookup"><span data-stu-id="c2b55-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="c2b55-116">Vnos podatkov o strankah s platforme elektronskega poslovanja</span><span class="sxs-lookup"><span data-stu-id="c2b55-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="c2b55-117">Ustvarite vir podatkov z imenom **EPoslovanje**, izberite možnost uvoza in izberite povezovalnik **Besedilo/CSV**.</span><span class="sxs-lookup"><span data-stu-id="c2b55-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="c2b55-118">Vnesite URL za stike za elektronsko poslovanje https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="c2b55-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="c2b55-119">Med urejanjem podatkov izberite **Pretvori** in potem **Uporabi prvo vrstico kot glavo**.</span><span class="sxs-lookup"><span data-stu-id="c2b55-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="c2b55-120">Posodobite vrsto podatkov za spodaj navedene stolpce:</span><span class="sxs-lookup"><span data-stu-id="c2b55-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="c2b55-121">**DateOfBirth**: datum</span><span class="sxs-lookup"><span data-stu-id="c2b55-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="c2b55-122">**CreatedOn**: datum/čas/časovni pas</span><span class="sxs-lookup"><span data-stu-id="c2b55-122">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Pretvorite datum rojstva v datum.":::

1. <span data-ttu-id="c2b55-124">V polju **Ime** v desnem podoknu preimenujte vir podatkov iz **Poizvedba** v **StikiEPoslovanja**</span><span class="sxs-lookup"><span data-stu-id="c2b55-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="c2b55-125">Shranite vir podatkov.</span><span class="sxs-lookup"><span data-stu-id="c2b55-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="c2b55-126">Vnos podatkov o strankah iz sheme za zvestobo</span><span class="sxs-lookup"><span data-stu-id="c2b55-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="c2b55-127">Ustvarite vir podatkov z imenom **ShemaZvestobe**, izberite možnost uvoza in izberite povezovalnik **Besedilo/CSV**.</span><span class="sxs-lookup"><span data-stu-id="c2b55-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="c2b55-128">Vnesite URL za stike za elektronsko poslovanje https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="c2b55-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="c2b55-129">Med urejanjem podatkov izberite **Pretvori** in potem **Uporabi prvo vrstico kot glavo**.</span><span class="sxs-lookup"><span data-stu-id="c2b55-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="c2b55-130">Posodobite vrsto podatkov za spodaj navedene stolpce:</span><span class="sxs-lookup"><span data-stu-id="c2b55-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="c2b55-131">**DateOfBirth**: datum</span><span class="sxs-lookup"><span data-stu-id="c2b55-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="c2b55-132">**RewardsPoints**: celo število</span><span class="sxs-lookup"><span data-stu-id="c2b55-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="c2b55-133">**CreatedOn**: datum/čas</span><span class="sxs-lookup"><span data-stu-id="c2b55-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="c2b55-134">V desnem podoknu v polju **Ime** preimenujte svoj vir podatkov iz **Poizvedba** v **zvesteStranke**.</span><span class="sxs-lookup"><span data-stu-id="c2b55-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="c2b55-135">Shranite vir podatkov.</span><span class="sxs-lookup"><span data-stu-id="c2b55-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="c2b55-136">Vnos podatkov o naročnini</span><span class="sxs-lookup"><span data-stu-id="c2b55-136">Ingest subscription information</span></span>

1. <span data-ttu-id="c2b55-137">Ustvarite vir podatkov z imenom **ZgodovinaNaročnin**, izberite možnost uvoza in izberite povezovalnik **Besedilo/CSV**.</span><span class="sxs-lookup"><span data-stu-id="c2b55-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="c2b55-138">Vnesite URL za stike za elektronsko poslovanje https://aka.ms/ciadchurnsubscriptionhistory.</span><span class="sxs-lookup"><span data-stu-id="c2b55-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="c2b55-139">Med urejanjem podatkov izberite **Pretvori** in potem **Uporabi prvo vrstico kot glavo**.</span><span class="sxs-lookup"><span data-stu-id="c2b55-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="c2b55-140">Posodobite vrsto podatkov za spodaj navedene stolpce:</span><span class="sxs-lookup"><span data-stu-id="c2b55-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="c2b55-141">**SubscriptionID**: celo število</span><span class="sxs-lookup"><span data-stu-id="c2b55-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="c2b55-142">**SubscriptionAmount**: valuta</span><span class="sxs-lookup"><span data-stu-id="c2b55-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="c2b55-143">**SubscriptionEndDate**: datum/čas</span><span class="sxs-lookup"><span data-stu-id="c2b55-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="c2b55-144">**SubscriptionStartDate**: datum/čas</span><span class="sxs-lookup"><span data-stu-id="c2b55-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="c2b55-145">**TransactionDate**: datum/čas</span><span class="sxs-lookup"><span data-stu-id="c2b55-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="c2b55-146">**IsRecurring**: True/False</span><span class="sxs-lookup"><span data-stu-id="c2b55-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="c2b55-147">**Is_auto_renew**: True/False</span><span class="sxs-lookup"><span data-stu-id="c2b55-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="c2b55-148">**RecurringFrequencyInMonths**: celo število</span><span class="sxs-lookup"><span data-stu-id="c2b55-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="c2b55-149">V desnem podoknu v polju **Ime** preimenujte svoj vir podatkov iz **Poizvedba** v **SubscriptionHistory**.</span><span class="sxs-lookup"><span data-stu-id="c2b55-149">In the **Name** field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="c2b55-150">Shranite vir podatkov.</span><span class="sxs-lookup"><span data-stu-id="c2b55-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="c2b55-151">Vnesite podatke o strankah iz ocen spletnih mest</span><span class="sxs-lookup"><span data-stu-id="c2b55-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="c2b55-152">Ustvarite vir podatkov z imenom **Spletno mesto**, izberite možnost uvoza in izberite povezovalnik **Besedilo/CSV**.</span><span class="sxs-lookup"><span data-stu-id="c2b55-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="c2b55-153">Vnesite URL za stike za elektronsko poslovanje https://aka.ms/ciadclasswebsite.</span><span class="sxs-lookup"><span data-stu-id="c2b55-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="c2b55-154">Med urejanjem podatkov izberite **Pretvori** in potem **Uporabi prvo vrstico kot glavo**.</span><span class="sxs-lookup"><span data-stu-id="c2b55-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="c2b55-155">Posodobite vrsto podatkov za spodaj navedene stolpce:</span><span class="sxs-lookup"><span data-stu-id="c2b55-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="c2b55-156">**ReviewRating**: celo število</span><span class="sxs-lookup"><span data-stu-id="c2b55-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="c2b55-157">**ReviewDate**: datum</span><span class="sxs-lookup"><span data-stu-id="c2b55-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="c2b55-158">V polju »Ime« v desnem podoknu preimenujte vir podatkov iz **Poizvedba** v **spletneOcene**.</span><span class="sxs-lookup"><span data-stu-id="c2b55-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="c2b55-159">2. opravilo – poenotenje podatkov</span><span class="sxs-lookup"><span data-stu-id="c2b55-159">Task 2 - Data unification</span></span>

<span data-ttu-id="c2b55-160">Po vnosu podatkov začnemo s postopkom **Preslikava/ujemanje/spajanje** za izdelavo poenotenega profila stranke.</span><span class="sxs-lookup"><span data-stu-id="c2b55-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="c2b55-161">Če želite več informacij, glejte [Poenotenje podatkov](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="c2b55-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="c2b55-162">Preslikava</span><span class="sxs-lookup"><span data-stu-id="c2b55-162">Map</span></span>

1. <span data-ttu-id="c2b55-163">Po vnosu podatkov preslikajte stike iz podatkov o elektronskem poslovanju in zvestobi v običajne vrste podatkov.</span><span class="sxs-lookup"><span data-stu-id="c2b55-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="c2b55-164">Izberite **Podatki** > **Poenotenje** > **Preslikava**.</span><span class="sxs-lookup"><span data-stu-id="c2b55-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="c2b55-165">Izberite entitete, ki predstavljajo profil stranke – **StikiEPoslovanja** in **zvesteStranke**.</span><span class="sxs-lookup"><span data-stu-id="c2b55-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="Poenotenje virov podatkov o elektronskem poslovanju in zvestobi.":::

1. <span data-ttu-id="c2b55-167">Izberite **IDstika** kot primarni ključ za **StikiEPoslovanja** in **ID zvestobe** kot primarni ključ za **zvesteStranke**.</span><span class="sxs-lookup"><span data-stu-id="c2b55-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Poenotite IDzvestobe kot primarni ključ.":::

### <a name="match"></a><span data-ttu-id="c2b55-169">Povezovanje</span><span class="sxs-lookup"><span data-stu-id="c2b55-169">Match</span></span>

1. <span data-ttu-id="c2b55-170">Izberite zavihek **Ujemanje** in izberite **Nastavi vrstni red**.</span><span class="sxs-lookup"><span data-stu-id="c2b55-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="c2b55-171">Na spustnem seznamu **Primarno** izberite **StikiEPoslovanja: EPoslovanje** kot primarni vir in vključite vse zapise.</span><span class="sxs-lookup"><span data-stu-id="c2b55-171">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="c2b55-172">Na spustnem seznamu **Entiteta 2** izberite **zvesteStranke: ShemaZvestobe** in vključite vse zapise.</span><span class="sxs-lookup"><span data-stu-id="c2b55-172">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Poenotenje ujemanja elektronskega poslovanja in zvestobe.":::

1. <span data-ttu-id="c2b55-174">Izberite **Ustvarjanje novega pravila**.</span><span class="sxs-lookup"><span data-stu-id="c2b55-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="c2b55-175">Dodajte svoj prvi pogoj z možnostjo FullName.</span><span class="sxs-lookup"><span data-stu-id="c2b55-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="c2b55-176">Za StikiEPoslovanja izberite **FullName** v spustnem meniju.</span><span class="sxs-lookup"><span data-stu-id="c2b55-176">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="c2b55-177">Za zvesteStranke izberite **FullName** v spustnem meniju.</span><span class="sxs-lookup"><span data-stu-id="c2b55-177">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="c2b55-178">Izberite spustni meni **Normaliziraj** in izberite **Vrsta (telefon, ime, naslov, ...)**.</span><span class="sxs-lookup"><span data-stu-id="c2b55-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="c2b55-179">Nastavite **Raven natančnosti**: **Osnovno** in **Vrednost**: **Visoko**.</span><span class="sxs-lookup"><span data-stu-id="c2b55-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="c2b55-180">Vnesite ime **FullName, Email** za novo pravilo.</span><span class="sxs-lookup"><span data-stu-id="c2b55-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="c2b55-181">Dodajte drugi pogoj za e-poštni naslov tako, da izberete **Dodaj pogoj**.</span><span class="sxs-lookup"><span data-stu-id="c2b55-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="c2b55-182">Za StikiEPoslovanja entitete izberite **E-pošta** v spustnem meniju.</span><span class="sxs-lookup"><span data-stu-id="c2b55-182">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="c2b55-183">Za zvesteStranke entitete izberite **E-pošta** v spustnem meniju.</span><span class="sxs-lookup"><span data-stu-id="c2b55-183">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="c2b55-184">Pustite polje Normaliziraj prazno.</span><span class="sxs-lookup"><span data-stu-id="c2b55-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="c2b55-185">Nastavite **Raven natančnosti**: **Osnovno** in **Vrednost**: **Visoko**.</span><span class="sxs-lookup"><span data-stu-id="c2b55-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Poenotenje pravila ujemanja za ime in e-pošto.":::

7. <span data-ttu-id="c2b55-187">Izberite **Shrani** in **Zaženi**.</span><span class="sxs-lookup"><span data-stu-id="c2b55-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="c2b55-188">Spajanje</span><span class="sxs-lookup"><span data-stu-id="c2b55-188">Merge</span></span>

1. <span data-ttu-id="c2b55-189">Odprite zavihek **Spajanje**.</span><span class="sxs-lookup"><span data-stu-id="c2b55-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="c2b55-190">Pri **IDstranke** za entiteto **zvesteStranke** spremenite prikazno ime v **ZVESTOBAIDstranke**, da se razlikuje od ostalih vnesenih ID-jev.</span><span class="sxs-lookup"><span data-stu-id="c2b55-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="Preimenujte ID stika iz ID-ja zvestobe.":::

1. <span data-ttu-id="c2b55-192">Izberite **Shrani** in **Zaženi**, da začnete postopek spajanja.</span><span class="sxs-lookup"><span data-stu-id="c2b55-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="c2b55-193">3. opravilo – konfiguracija predvidevanja izgube naročnin</span><span class="sxs-lookup"><span data-stu-id="c2b55-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="c2b55-194">Z vzpostavljenimi poenotenimi profili strank lahko zdaj zaženemo predvidevanje izgube naročnin.</span><span class="sxs-lookup"><span data-stu-id="c2b55-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="c2b55-195">Za podrobne korake glejte članek [Predvidevanje izgube naročnin (predogled)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="c2b55-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="c2b55-196">Odprite **Obveščanje** > **Odkrivanje** in izberite uporabo možnosti **Model izgube strank**.</span><span class="sxs-lookup"><span data-stu-id="c2b55-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="c2b55-197">Izberite možnost **Naročnina** in izberite **Začetek**.</span><span class="sxs-lookup"><span data-stu-id="c2b55-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="c2b55-198">Poimenujte model **Predvidevanje izgube naročnine OOB** in izhodno entiteto **PredvidevanjeIzgubeNaročnineOOB**.</span><span class="sxs-lookup"><span data-stu-id="c2b55-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="c2b55-199">Določite dva pogoja za model izgube:</span><span class="sxs-lookup"><span data-stu-id="c2b55-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="c2b55-200">**Dnevi po koncu naročnine**: **vsaj 60** dni.</span><span class="sxs-lookup"><span data-stu-id="c2b55-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="c2b55-201">Če stranka v tem obdobju po preteku naročnine ne podaljša naročnine, se šteje za izgubljeno.</span><span class="sxs-lookup"><span data-stu-id="c2b55-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="c2b55-202">**Opredelitev izgube**: **vsaj 93** dni.</span><span class="sxs-lookup"><span data-stu-id="c2b55-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="c2b55-203">Trajanje, ki ga model predvideva, za stranke, ki bi se lahko izgubile.</span><span class="sxs-lookup"><span data-stu-id="c2b55-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="c2b55-204">Bolj kot gledate v prihodnost, manj natančni so rezultati.</span><span class="sxs-lookup"><span data-stu-id="c2b55-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Izberite časovno obdobje za predvidevanje modela in opredelitev izgube.":::

1. <span data-ttu-id="c2b55-206">Izberite **Dodajanje zahtevanih podatkov** in izberite **Dodajanje podatkov** za zgodovino naročnin.</span><span class="sxs-lookup"><span data-stu-id="c2b55-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="c2b55-207">Dodajte entiteto **Naročnina: ZgodovinaNaročnin** in preslikajte polja iz elektronskega poslovanja v ustrezna polja, ki jih zahteva model.</span><span class="sxs-lookup"><span data-stu-id="c2b55-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="c2b55-208">Združite entiteto **Naročnina: ZgodovinaNaročnin** z **StikiEPoslovanja: EPoslovanje**, poimenujte odnos **NaročninaEPoslovanja**.</span><span class="sxs-lookup"><span data-stu-id="c2b55-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Pridružite se entitetam elektronskega poslovanja.":::

1. <span data-ttu-id="c2b55-210">V razdelku Dejavnosti strank dodajte entiteto **spletneOcene: Spletno mesto** in preslikajte polja iz spletneOcene v ustrezna polja, ki jih zahteva model.</span><span class="sxs-lookup"><span data-stu-id="c2b55-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="c2b55-211">Primarni ključ: ReviewId</span><span class="sxs-lookup"><span data-stu-id="c2b55-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="c2b55-212">Časovni žig: ReviewDate</span><span class="sxs-lookup"><span data-stu-id="c2b55-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="c2b55-213">Dogodek: ReviewRating</span><span class="sxs-lookup"><span data-stu-id="c2b55-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="c2b55-214">Konfigurirajte dejavnost za ocene spletnih mest.</span><span class="sxs-lookup"><span data-stu-id="c2b55-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="c2b55-215">Izberite dejavnost **Preglej** in združite entiteto **spletneOcene: Spletno mesto** z **StikiEPoslovanja: EPoslovanje**.</span><span class="sxs-lookup"><span data-stu-id="c2b55-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="c2b55-216">Izberite **Naprej** za nastavitev urnika modela.</span><span class="sxs-lookup"><span data-stu-id="c2b55-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="c2b55-217">Model se mora redno usposabljati, da se nauči novih vzorcev, ko vnese nove podatke.</span><span class="sxs-lookup"><span data-stu-id="c2b55-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="c2b55-218">V tem primeru izberite **Mesečno**.</span><span class="sxs-lookup"><span data-stu-id="c2b55-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="c2b55-219">Po pregledu vseh podrobnosti izberite **Shrani in zaženi**.</span><span class="sxs-lookup"><span data-stu-id="c2b55-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="c2b55-220">4. opravilo – preglejte rezultate modela in razlage</span><span class="sxs-lookup"><span data-stu-id="c2b55-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="c2b55-221">Model naj dokonča usposabljanje in ocenjevanje podatkov.</span><span class="sxs-lookup"><span data-stu-id="c2b55-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="c2b55-222">Zdaj si lahko ogledate razlage modela izgube naročnine.</span><span class="sxs-lookup"><span data-stu-id="c2b55-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="c2b55-223">Za več informacij glejte [Pregled stanja in rezultatov predvidevanja](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="c2b55-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="c2b55-224">5. opravilo – ustvarjanje segmenta strank z visokim tveganjem izgube</span><span class="sxs-lookup"><span data-stu-id="c2b55-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="c2b55-225">Z zagonom produkcijskega modela ustvarite novo entiteto, ki jo lahko vidite v razdelku **Podatki** > **Entitete**.</span><span class="sxs-lookup"><span data-stu-id="c2b55-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="c2b55-226">Na podlagi entitete, ki jo je ustvaril model, lahko ustvarite nov segment.</span><span class="sxs-lookup"><span data-stu-id="c2b55-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="c2b55-227">Izberite **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="c2b55-227">Go to **Segments**.</span></span> <span data-ttu-id="c2b55-228">Izberite **Novo** in izberite **Ustvari iz** > **Obveščanje**.</span><span class="sxs-lookup"><span data-stu-id="c2b55-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Ustvarjanje segmenta z izhodnimi podatki modela.":::

1. <span data-ttu-id="c2b55-230">Izberite končno točko **PredvidevanjeIzgubeNaročnineOOB** in definirajte segment:</span><span class="sxs-lookup"><span data-stu-id="c2b55-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="c2b55-231">Polje: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="c2b55-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="c2b55-232">Operator: večje kot</span><span class="sxs-lookup"><span data-stu-id="c2b55-232">Operator: greater than</span></span>
   - <span data-ttu-id="c2b55-233">Vrednost: 0,6</span><span class="sxs-lookup"><span data-stu-id="c2b55-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Nastavite segment izgube naročnine.":::

<span data-ttu-id="c2b55-235">Zdaj imate segment, ki se dinamično posodablja, v katerem so prepoznane stranke z visokim tveganjem izgube za to naročniško dejavnost.</span><span class="sxs-lookup"><span data-stu-id="c2b55-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="c2b55-236">Za več informacij glejte [Ustvarjanje in upravljanje segmentov](segments.md).</span><span class="sxs-lookup"><span data-stu-id="c2b55-236">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]