---
title: Vzorčni vodnik za predvidevanje priporočil za izdelke
description: Uporabite ta vzorčni vodnik, da preskusite model predvidevanja priporočil za vnaprej pripravljene izdelke.
ms.date: 02/10/2021
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ee873d9b7caa5f891cb2d5b8c665dec90ad0e59
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270534"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="965a6-103">Vzorčni vodnik za predvidevanje priporočil za izdelke (predogled)</span><span class="sxs-lookup"><span data-stu-id="965a6-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="965a6-104">S pomočjo spodnjih vzorčnih podatkov vas bomo vodili skozi celotni primer predvidevanja priporočil za izdelke.</span><span class="sxs-lookup"><span data-stu-id="965a6-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="965a6-105">Scenarij</span><span class="sxs-lookup"><span data-stu-id="965a6-105">Scenario</span></span>

<span data-ttu-id="965a6-106">Contoso je podjetje, ki proizvaja visokokakovostno kavo in kavne avtomate, ki jih prodaja prek njihovega spletnega mesta Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="965a6-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="965a6-107">Njihov cilj je razumeti, katere izdelke priporočiti svojim rednim strankam.</span><span class="sxs-lookup"><span data-stu-id="965a6-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="965a6-108">Če vedo, katere izdelke stranke bolj **verjetno kupujejo**, si prihranijo tržna prizadevanja, saj se lahko osredotočijo na določene izdelke.</span><span class="sxs-lookup"><span data-stu-id="965a6-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="965a6-109">Zahteve</span><span class="sxs-lookup"><span data-stu-id="965a6-109">Prerequisites</span></span>

- <span data-ttu-id="965a6-110">Vsaj [dovoljenja sodelavcev](permissions.md) v storitvi Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="965a6-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="965a6-111">Priporočamo, da izvedete naslednje korake [v novem okolju](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="965a6-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="965a6-112">1. opravilo – vnos podatkov</span><span class="sxs-lookup"><span data-stu-id="965a6-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="965a6-113">Preglejte specifične članke [o vnosu podatkov](data-sources.md) in [uvozu virov podatkov z uporabo povezovalnikov Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="965a6-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="965a6-114">Z naslednjimi informacijami domnevamo, da ste na splošno seznanjeni z vnosom podatkov.</span><span class="sxs-lookup"><span data-stu-id="965a6-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="965a6-115">Vnos podatkov o strankah s platforme elektronskega poslovanja</span><span class="sxs-lookup"><span data-stu-id="965a6-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="965a6-116">Ustvarite vir podatkov z imenom **EPoslovanje**, izberite možnost uvoza in izberite povezovalnik **Besedilo/CSV**.</span><span class="sxs-lookup"><span data-stu-id="965a6-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="965a6-117">Vnesite URL za stike za elektronsko poslovanje https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="965a6-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="965a6-118">Med urejanjem podatkov izberite **Pretvori** in potem **Uporabi prvo vrstico kot glavo**.</span><span class="sxs-lookup"><span data-stu-id="965a6-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="965a6-119">Posodobite vrsto podatkov za spodaj navedene stolpce:</span><span class="sxs-lookup"><span data-stu-id="965a6-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="965a6-120">**DateOfBirth**: datum</span><span class="sxs-lookup"><span data-stu-id="965a6-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="965a6-121">**CreatedOn**: datum/čas/časovni pas</span><span class="sxs-lookup"><span data-stu-id="965a6-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Pretvorite datum rojstva v datum.":::

5. <span data-ttu-id="965a6-123">V polju »Ime« v desnem podoknu preimenujte vir podatkov iz **Poizvedba** v **StikiEPoslovanja**.</span><span class="sxs-lookup"><span data-stu-id="965a6-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="965a6-124">**Shranite** vir podatkov.</span><span class="sxs-lookup"><span data-stu-id="965a6-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="965a6-125">Vnos podatkov o spletnem nakupu</span><span class="sxs-lookup"><span data-stu-id="965a6-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="965a6-126">Dodajte še nabor podatkov z istega vira podatkov **EPoslovanje**.</span><span class="sxs-lookup"><span data-stu-id="965a6-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="965a6-127">Znova izberite povezovalnik **Besedilo/CSV**.</span><span class="sxs-lookup"><span data-stu-id="965a6-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="965a6-128">Vnesite URL za podatke **Spletni nakupi** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="965a6-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="965a6-129">Med urejanjem podatkov izberite **Pretvori** in potem **Uporabi prvo vrstico kot glavo**.</span><span class="sxs-lookup"><span data-stu-id="965a6-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="965a6-130">Posodobite vrsto podatkov za spodaj navedene stolpce:</span><span class="sxs-lookup"><span data-stu-id="965a6-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="965a6-131">**PurchasedOn**: datum/čas</span><span class="sxs-lookup"><span data-stu-id="965a6-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="965a6-132">**TotalPrice**: valuta</span><span class="sxs-lookup"><span data-stu-id="965a6-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="965a6-133">V stranskem podoknu v polju **Ime** preimenujte svoj vir podatkov iz **Poizvedba** v **NakupiEPoslovanja**.</span><span class="sxs-lookup"><span data-stu-id="965a6-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="965a6-134">Shranite vir podatkov.</span><span class="sxs-lookup"><span data-stu-id="965a6-134">Save the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="965a6-135">Vnos podatkov o strankah iz sheme za zvestobo</span><span class="sxs-lookup"><span data-stu-id="965a6-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="965a6-136">Ustvarite vir podatkov z imenom **ShemaZvestobe**, izberite možnost uvoza in izberite povezovalnik **Besedilo/CSV**.</span><span class="sxs-lookup"><span data-stu-id="965a6-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="965a6-137">Vnesite URL za stike za elektronsko poslovanje https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="965a6-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="965a6-138">Med urejanjem podatkov izberite **Pretvori** in potem **Uporabi prvo vrstico kot glavo**.</span><span class="sxs-lookup"><span data-stu-id="965a6-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="965a6-139">Posodobite vrsto podatkov za spodaj navedene stolpce:</span><span class="sxs-lookup"><span data-stu-id="965a6-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="965a6-140">**DateOfBirth**: datum</span><span class="sxs-lookup"><span data-stu-id="965a6-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="965a6-141">**RewardsPoints**: celo število</span><span class="sxs-lookup"><span data-stu-id="965a6-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="965a6-142">**CreatedOn**: datum/čas</span><span class="sxs-lookup"><span data-stu-id="965a6-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="965a6-143">V desnem podoknu v polju **Ime** preimenujte svoj vir podatkov iz **Poizvedba** v **zvesteStranke**.</span><span class="sxs-lookup"><span data-stu-id="965a6-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="965a6-144">Shranite vir podatkov.</span><span class="sxs-lookup"><span data-stu-id="965a6-144">Save the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="965a6-145">2. opravilo – poenotenje podatkov</span><span class="sxs-lookup"><span data-stu-id="965a6-145">Task 2 - Data unification</span></span>

<span data-ttu-id="965a6-146">Po vnosu podatkov začnemo s postopkom **Preslikava/ujemanje/spajanje** za izdelavo poenotenega profila stranke.</span><span class="sxs-lookup"><span data-stu-id="965a6-146">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="965a6-147">Če želite več informacij, glejte [Poenotenje podatkov](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="965a6-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="965a6-148">Preslikava</span><span class="sxs-lookup"><span data-stu-id="965a6-148">Map</span></span>

1. <span data-ttu-id="965a6-149">Po vnosu podatkov preslikajte stike iz podatkov o elektronskem poslovanju in zvestobi v običajne vrste podatkov.</span><span class="sxs-lookup"><span data-stu-id="965a6-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="965a6-150">Izberite **Podatki** > **Poenotenje** > **Preslikava**.</span><span class="sxs-lookup"><span data-stu-id="965a6-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="965a6-151">Izberite entitete, ki predstavljajo profil stranke – **StikiEPoslovanja** in **zvesteStranke**.</span><span class="sxs-lookup"><span data-stu-id="965a6-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![Poenotenje virov podatkov o elektronskem poslovanju in zvestobi.](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="965a6-153">Izberite **IDstika** kot primarni ključ za **StikiEPoslovanja** in **ID zvestobe** kot primarni ključ za **zvesteStranke**.</span><span class="sxs-lookup"><span data-stu-id="965a6-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Poenotite IDzvestobe kot primarni ključ.](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="965a6-155">Povezovanje</span><span class="sxs-lookup"><span data-stu-id="965a6-155">Match</span></span>

1. <span data-ttu-id="965a6-156">Izberite zavihek **Ujemanje** in izberite **Nastavi vrstni red**.</span><span class="sxs-lookup"><span data-stu-id="965a6-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="965a6-157">Na spustnem seznamu **Primarno** izberite **StikiEPoslovanja: EPoslovanje** kot primarni vir in vključite vse zapise.</span><span class="sxs-lookup"><span data-stu-id="965a6-157">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="965a6-158">Na spustnem seznamu **Entiteta 2** izberite **zvesteStranke: ShemaZvestobe** in vključite vse zapise.</span><span class="sxs-lookup"><span data-stu-id="965a6-158">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Poenotenje ujemanja elektronskega poslovanja in zvestobe.](media/unify-match-order.png)

4. <span data-ttu-id="965a6-160">Izberite **Ustvarjanje novega pravila**.</span><span class="sxs-lookup"><span data-stu-id="965a6-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="965a6-161">Dodajte svoj prvi pogoj z možnostjo FullName.</span><span class="sxs-lookup"><span data-stu-id="965a6-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="965a6-162">Za StikiEPoslovanja izberite **FullName** v spustnem meniju.</span><span class="sxs-lookup"><span data-stu-id="965a6-162">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="965a6-163">Za zvesteStranke izberite **FullName** v spustnem meniju.</span><span class="sxs-lookup"><span data-stu-id="965a6-163">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="965a6-164">Izberite spustni meni **Normaliziraj** in izberite **Vrsta (telefon, ime, naslov, ...)**.</span><span class="sxs-lookup"><span data-stu-id="965a6-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="965a6-165">Nastavite **Raven natančnosti**: **Osnovno** in **Vrednost**: **Visoko**.</span><span class="sxs-lookup"><span data-stu-id="965a6-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="965a6-166">Vnesite ime **FullName, Email** za novo pravilo.</span><span class="sxs-lookup"><span data-stu-id="965a6-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="965a6-167">Dodajte drugi pogoj za e-poštni naslov tako, da izberete **Dodaj pogoj**.</span><span class="sxs-lookup"><span data-stu-id="965a6-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="965a6-168">Za StikiEPoslovanja entitete izberite **E-pošta** v spustnem meniju.</span><span class="sxs-lookup"><span data-stu-id="965a6-168">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="965a6-169">Za zvesteStranke entitete izberite **E-pošta** v spustnem meniju.</span><span class="sxs-lookup"><span data-stu-id="965a6-169">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="965a6-170">Pustite polje Normaliziraj prazno.</span><span class="sxs-lookup"><span data-stu-id="965a6-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="965a6-171">Nastavite **Raven natančnosti**: **Osnovno** in **Vrednost**: **Visoko**.</span><span class="sxs-lookup"><span data-stu-id="965a6-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Poenotenje pravila ujemanja za ime in e-pošto.](media/unify-match-rule.png)

7. <span data-ttu-id="965a6-173">Izberite **Shrani** in **Zaženi**.</span><span class="sxs-lookup"><span data-stu-id="965a6-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="965a6-174">Spajanje</span><span class="sxs-lookup"><span data-stu-id="965a6-174">Merge</span></span>

1. <span data-ttu-id="965a6-175">Odprite zavihek **Spajanje**.</span><span class="sxs-lookup"><span data-stu-id="965a6-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="965a6-176">Pri **IDstranke** za entiteto **zvesteStranke** spremenite prikazno ime v **ZVESTOBAIDstranke**, da se razlikuje od ostalih vnesenih ID-jev.</span><span class="sxs-lookup"><span data-stu-id="965a6-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![Preimenujte ID stika iz ID-ja zvestobe.](media/unify-merge-contactid.png)

1. <span data-ttu-id="965a6-178">Izberite **Shrani** in **Zaženi**, da začnete postopek spajanja.</span><span class="sxs-lookup"><span data-stu-id="965a6-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="965a6-179">3. opravilo – konfiguracija predvidevanja priporočil za izdelke</span><span class="sxs-lookup"><span data-stu-id="965a6-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="965a6-180">Z vzpostavljenimi poenotenimi profili strank lahko zdaj zaženemo predvidevanje izgube naročnin.</span><span class="sxs-lookup"><span data-stu-id="965a6-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="965a6-181">V razdelku **Obveščanje** > **Predvidevanje** izberite **Priporočilo za izdelke**.</span><span class="sxs-lookup"><span data-stu-id="965a6-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="965a6-182">Izberite **Začetek**.</span><span class="sxs-lookup"><span data-stu-id="965a6-182">Select **Get started**.</span></span>

1. <span data-ttu-id="965a6-183">Poimenujte model **Model predvidevanja priporočil za vnaprej pripravljene izdelke** in izhodno entiteto **ModelPredvidevanjaPriporočilZaVnaprejPripravljeneIzdelke**.</span><span class="sxs-lookup"><span data-stu-id="965a6-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="965a6-184">Določite tri pogoje za model:</span><span class="sxs-lookup"><span data-stu-id="965a6-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="965a6-185">**Število izdelkov**: nastavite to vrednost na **5**.</span><span class="sxs-lookup"><span data-stu-id="965a6-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="965a6-186">Ta nastavitev določi, koliko izdelkov želite priporočiti svojim strankam.</span><span class="sxs-lookup"><span data-stu-id="965a6-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="965a6-187">**Ali želite predlagati izdelke, ki so jih vaše stranke nedavno kupile?**: izberite **Da**, če želite, da so v priporočilu vključeni izdelki, ki so jih stranke že kupile.</span><span class="sxs-lookup"><span data-stu-id="965a6-187">**Suggest products customers have recently purchased?**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="965a6-188">**Obdobje zajema podatkov:** izberite vsaj **365 dni**.</span><span class="sxs-lookup"><span data-stu-id="965a6-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="965a6-189">Ta nastavitev določa obdobje zajema podatkov strankine dejavnosti, ki ga bo model upošteval pri vnosu priporočil.</span><span class="sxs-lookup"><span data-stu-id="965a6-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Oblikujte nastavitve za model s priporočili za izdelke.":::

1. <span data-ttu-id="965a6-191">Za zgodovino nakupov izberite **Zahtevani podatki** in nato **Dodajanje podatkov**.</span><span class="sxs-lookup"><span data-stu-id="965a6-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="965a6-192">Dodajte entiteto **NakupiEPoslovanja: EPoslovanje** in preslikajte polja iz elektronskega poslovanja v ustrezna polja, ki jih zahteva model.</span><span class="sxs-lookup"><span data-stu-id="965a6-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="965a6-193">Pridružite entiteto **NakupiEPoslovanja: EPoslovanje** z entiteto **StikiEPoslovanja: EPoslovanje**.</span><span class="sxs-lookup"><span data-stu-id="965a6-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![Pridružite se entitetam elektronskega poslovanja.](media/model-purchase-join.png)

1. <span data-ttu-id="965a6-195">Izberite **Naprej** za nastavitev urnika modela.</span><span class="sxs-lookup"><span data-stu-id="965a6-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="965a6-196">Model se mora redno usposabljati, da se nauči novih vzorcev, ko vnese nove podatke.</span><span class="sxs-lookup"><span data-stu-id="965a6-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="965a6-197">V tem primeru izberite **Mesečno**.</span><span class="sxs-lookup"><span data-stu-id="965a6-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="965a6-198">Po pregledu vseh podrobnosti izberite **Shrani in zaženi**.</span><span class="sxs-lookup"><span data-stu-id="965a6-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="965a6-199">4. opravilo – preglejte rezultate modela in razlage</span><span class="sxs-lookup"><span data-stu-id="965a6-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="965a6-200">Model naj dokonča usposabljanje in ocenjevanje podatkov.</span><span class="sxs-lookup"><span data-stu-id="965a6-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="965a6-201">Zdaj lahko pregledate pojasnila modela s priporočili za izdelke.</span><span class="sxs-lookup"><span data-stu-id="965a6-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="965a6-202">Za več informacij glejte [Pregled stanja in rezultatov predvidevanja](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="965a6-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="965a6-203">5. opravilo – ustvarjanje segmenta najbolj prodajanih izdelkov</span><span class="sxs-lookup"><span data-stu-id="965a6-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="965a6-204">Z zagonom produkcijskega modela ustvarite novo entiteto, ki jo lahko vidite v razdelku **Podatki** > **Entitete**.</span><span class="sxs-lookup"><span data-stu-id="965a6-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="965a6-205">Na podlagi entitete, ki jo je ustvaril model, lahko ustvarite nov segment.</span><span class="sxs-lookup"><span data-stu-id="965a6-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="965a6-206">Izberite **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="965a6-206">Go to **Segments**.</span></span> <span data-ttu-id="965a6-207">Izberite **Novo** in izberite **Ustvari iz** > **Obveščanje**.</span><span class="sxs-lookup"><span data-stu-id="965a6-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Ustvarjanje segmenta z izhodnimi podatki modela.](media/segment-intelligence.png)

1. <span data-ttu-id="965a6-209">Izberite končno točko **ModelPredvidevanjaPriporočilZaVnaprejPripravljeneIzdelke** in določite segment:</span><span class="sxs-lookup"><span data-stu-id="965a6-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="965a6-210">Polje: IDIzdelka</span><span class="sxs-lookup"><span data-stu-id="965a6-210">Field: ProductID</span></span>
   - <span data-ttu-id="965a6-211">Operator: vrednost</span><span class="sxs-lookup"><span data-stu-id="965a6-211">Operator: Value</span></span>
   - <span data-ttu-id="965a6-212">Vrednost: izberite najboljše tri ID-je izdelka</span><span class="sxs-lookup"><span data-stu-id="965a6-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Ustvarite segment iz rezultatov modela.":::

<span data-ttu-id="965a6-214">Sedaj imate dinamično posodobljen segment, ki prepozna stranke, ki so bolj pripravljene kupiti tri najbolj priporočene izdelke.</span><span class="sxs-lookup"><span data-stu-id="965a6-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="965a6-215">Za več informacij glejte [Ustvarjanje in upravljanje segmentov](segments.md).</span><span class="sxs-lookup"><span data-stu-id="965a6-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]