---
title: Vzorčni priročnik za predvidevanje vrednosti življenjske dobe stranke
description: Uporabite ta vzorčni priročnik, da preizkusite model za predvidevanje vrednosti življenjske dobe stranke.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 19c1fbadb79ba22c0dc11aa7c3b5b2415add70a7
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306369"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="91fea-103">Vzorčni priročnik za predvidevanje vrednosti življenjske dobe stranke (CLV)</span><span class="sxs-lookup"><span data-stu-id="91fea-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="91fea-104">Ta priročnik vam bo z vzorčnimi podatki v celoti razložil primer predvidevanja vrednosti življenjske dobe stranke (CLV) v Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="91fea-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="91fea-105">Scenarij</span><span class="sxs-lookup"><span data-stu-id="91fea-105">Scenario</span></span>

<span data-ttu-id="91fea-106">Contoso je podjetje, ki proizvaja visokokakovostno kavo in kavne aparate.</span><span class="sxs-lookup"><span data-stu-id="91fea-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="91fea-107">Izdelke prodajajo prek svoje spletne strani Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="91fea-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="91fea-108">Podjetje želi predvideti vrednost (prihodek), ki jo lahko njihove stranke ustvarijo v naslednjih 12 mesecih.</span><span class="sxs-lookup"><span data-stu-id="91fea-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="91fea-109">Poznavanje pričakovane vrednosti njihovih strank v naslednjih 12 mesecih jim pomaga usmeriti svoja tržna prizadevanja na stranke z visoko vrednostjo.</span><span class="sxs-lookup"><span data-stu-id="91fea-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="91fea-110">Zahteve</span><span class="sxs-lookup"><span data-stu-id="91fea-110">Prerequisites</span></span>

- <span data-ttu-id="91fea-111">Vsaj [dovoljenja za sodelavca](permissions.md) v vpogledih občinstva.</span><span class="sxs-lookup"><span data-stu-id="91fea-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="91fea-112">Priporočamo, da izvedete naslednje korake [v novem okolju](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="91fea-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="91fea-113">1. opravilo – vnos podatkov</span><span class="sxs-lookup"><span data-stu-id="91fea-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="91fea-114">Preglejte članke [o vnosu podatkov](data-sources.md) in [uvozu virov podatkov s konektorji Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="91fea-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="91fea-115">Z naslednjimi informacijami domnevamo, da ste na splošno seznanjeni z vnosom podatkov.</span><span class="sxs-lookup"><span data-stu-id="91fea-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="91fea-116">Vnos podatkov o strankah s platforme elektronskega poslovanja</span><span class="sxs-lookup"><span data-stu-id="91fea-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="91fea-117">Ustvarite vir podatkov z imenom **eCommerce**, izberite možnost uvoza in izberite povezovalnik **Besedilo/CSV**.</span><span class="sxs-lookup"><span data-stu-id="91fea-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="91fea-118">Vnesite URL za stike eCommerce [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span><span class="sxs-lookup"><span data-stu-id="91fea-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="91fea-119">Med urejanjem podatkov izberite **Pretvori** in nato **Uporabi prvo vrstico kot glavo**.</span><span class="sxs-lookup"><span data-stu-id="91fea-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="91fea-120">Posodobite vrsto podatkov za spodaj navedene stolpce:</span><span class="sxs-lookup"><span data-stu-id="91fea-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="91fea-121">**DateOfBirth**: datum</span><span class="sxs-lookup"><span data-stu-id="91fea-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="91fea-122">**CreatedOn**: datum/čas/časovni pas</span><span class="sxs-lookup"><span data-stu-id="91fea-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Pretvorite datum rojstva v datum.":::

1. <span data-ttu-id="91fea-124">V polju »Ime« v desnem podoknu preimenujte vir podatkov iz **Poizvedba** v **StikiEPoslovanja**.</span><span class="sxs-lookup"><span data-stu-id="91fea-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="91fea-125">**Shranite** vir podatkov.</span><span class="sxs-lookup"><span data-stu-id="91fea-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="91fea-126">Vnos podatkov o spletnem nakupu</span><span class="sxs-lookup"><span data-stu-id="91fea-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="91fea-127">Dodajte še nabor podatkov z istega vira podatkov **EPoslovanje**.</span><span class="sxs-lookup"><span data-stu-id="91fea-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="91fea-128">Znova izberite povezovalnik **Besedilo/CSV**.</span><span class="sxs-lookup"><span data-stu-id="91fea-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="91fea-129">Vnesite URL za podatke **Spletni nakupi** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="91fea-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="91fea-130">Med urejanjem podatkov izberite **Pretvori** in potem **Uporabi prvo vrstico kot glavo**.</span><span class="sxs-lookup"><span data-stu-id="91fea-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="91fea-131">Posodobite vrsto podatkov za spodaj navedene stolpce:</span><span class="sxs-lookup"><span data-stu-id="91fea-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="91fea-132">**PurchasedOn**: datum/čas</span><span class="sxs-lookup"><span data-stu-id="91fea-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="91fea-133">**TotalPrice**: valuta</span><span class="sxs-lookup"><span data-stu-id="91fea-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="91fea-134">V stranskem podoknu v polju **Ime** preimenujte svoj vir podatkov iz **Poizvedba** v **NakupiEPoslovanja**.</span><span class="sxs-lookup"><span data-stu-id="91fea-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="91fea-135">**Shranite** vir podatkov.</span><span class="sxs-lookup"><span data-stu-id="91fea-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="91fea-136">Vnos podatkov o strankah iz sheme za zvestobo</span><span class="sxs-lookup"><span data-stu-id="91fea-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="91fea-137">Ustvarite vir podatkov z imenom **ShemaZvestobe**, izberite možnost uvoza in izberite povezovalnik **Besedilo/CSV**.</span><span class="sxs-lookup"><span data-stu-id="91fea-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="91fea-138">Vnesite URL za stike za elektronsko poslovanje https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="91fea-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="91fea-139">Med urejanjem podatkov izberite **Pretvori** in potem **Uporabi prvo vrstico kot glavo**.</span><span class="sxs-lookup"><span data-stu-id="91fea-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="91fea-140">Posodobite vrsto podatkov za spodaj navedene stolpce:</span><span class="sxs-lookup"><span data-stu-id="91fea-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="91fea-141">**DateOfBirth**: datum</span><span class="sxs-lookup"><span data-stu-id="91fea-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="91fea-142">**RewardsPoints**: celo število</span><span class="sxs-lookup"><span data-stu-id="91fea-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="91fea-143">**CreatedOn**: datum/čas</span><span class="sxs-lookup"><span data-stu-id="91fea-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="91fea-144">V desnem podoknu v polju **Ime** preimenujte svoj vir podatkov iz **Poizvedba** v **zvesteStranke**.</span><span class="sxs-lookup"><span data-stu-id="91fea-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="91fea-145">**Shranite** vir podatkov.</span><span class="sxs-lookup"><span data-stu-id="91fea-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="91fea-146">Vnesite podatke o strankah iz ocen spletnih mest</span><span class="sxs-lookup"><span data-stu-id="91fea-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="91fea-147">Ustvarite vir podatkov z imenom **Spletno mesto**, izberite možnost uvoza in izberite povezovalnik **Besedilo/CSV**.</span><span class="sxs-lookup"><span data-stu-id="91fea-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="91fea-148">Vnesite URL za stike za elektronsko poslovanje https://aka.ms/CI-ILT/WebReviews.</span><span class="sxs-lookup"><span data-stu-id="91fea-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="91fea-149">Med urejanjem podatkov izberite **Pretvori** in potem **Uporabi prvo vrstico kot glavo**.</span><span class="sxs-lookup"><span data-stu-id="91fea-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="91fea-150">Posodobite vrsto podatkov za spodaj navedene stolpce:</span><span class="sxs-lookup"><span data-stu-id="91fea-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="91fea-151">**ReviewRating**: decimalno število</span><span class="sxs-lookup"><span data-stu-id="91fea-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="91fea-152">**ReviewDate**: datum</span><span class="sxs-lookup"><span data-stu-id="91fea-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="91fea-153">V polju »Ime« v desnem podoknu preimenujte vir podatkov iz **Poizvedba** na **Ocene**.</span><span class="sxs-lookup"><span data-stu-id="91fea-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="91fea-154">**Shranite** vir podatkov.</span><span class="sxs-lookup"><span data-stu-id="91fea-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="91fea-155">2. opravilo – poenotenje podatkov</span><span class="sxs-lookup"><span data-stu-id="91fea-155">Task 2 - Data unification</span></span>

<span data-ttu-id="91fea-156">Po uvozu podatkov se začne postopek poenotenja podatkov za ustvarjanje enotnega profila stranke.</span><span class="sxs-lookup"><span data-stu-id="91fea-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="91fea-157">Če želite več informacij, glejte [Poenotenje podatkov](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="91fea-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="91fea-158">Preslikava</span><span class="sxs-lookup"><span data-stu-id="91fea-158">Map</span></span>

1. <span data-ttu-id="91fea-159">Po vnosu podatkov preslikajte stike iz podatkov o elektronskem poslovanju in zvestobi v običajne vrste podatkov.</span><span class="sxs-lookup"><span data-stu-id="91fea-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="91fea-160">Izberite **Podatki** > **Poenotenje** > **Preslikava**.</span><span class="sxs-lookup"><span data-stu-id="91fea-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="91fea-161">Izberite entitete, ki predstavljajo profil stranke – **StikiEPoslovanja** in **zvesteStranke**.</span><span class="sxs-lookup"><span data-stu-id="91fea-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="91fea-162">Nato izberite **Uporabi**.</span><span class="sxs-lookup"><span data-stu-id="91fea-162">Then, select **Apply**.</span></span>

   ![Poenotenje virov podatkov o elektronskem poslovanju in zvestobi.](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="91fea-164">Izberite **IDstika** kot primarni ključ za **StikiEPoslovanja** in **ID zvestobe** kot primarni ključ za **zvesteStranke**.</span><span class="sxs-lookup"><span data-stu-id="91fea-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Poenotite IDzvestobe kot primarni ključ.](media/unify-loyaltyid.png)

1. <span data-ttu-id="91fea-166">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="91fea-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="91fea-167">Povezovanje</span><span class="sxs-lookup"><span data-stu-id="91fea-167">Match</span></span>

1. <span data-ttu-id="91fea-168">Izberite zavihek **Ujemanje** in izberite **Nastavi vrstni red**.</span><span class="sxs-lookup"><span data-stu-id="91fea-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="91fea-169">Na spustnem seznamu izberite možnost **Primarni** ter za primarni vir določite **eCommerceContacts: eCommerce** in vključite vse zapise.</span><span class="sxs-lookup"><span data-stu-id="91fea-169">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="91fea-170">Na spustnem seznamu izberite možnost **Entiteta 2**, nato pa **loyCustomers: LoyaltyScheme** in vključite vse zapise.</span><span class="sxs-lookup"><span data-stu-id="91fea-170">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Poenotenje ujemanja elektronskega poslovanja in zvestobe.](media/unify-match-order.png)

1. <span data-ttu-id="91fea-172">Izberite **Dodaj pravilo**</span><span class="sxs-lookup"><span data-stu-id="91fea-172">Select **Add rule**</span></span>

1. <span data-ttu-id="91fea-173">Dodajte svoj prvi pogoj z možnostjo FullName.</span><span class="sxs-lookup"><span data-stu-id="91fea-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="91fea-174">Za entiteto StikiEPoslovanja na spustnem seznamu izberite **FullName**.</span><span class="sxs-lookup"><span data-stu-id="91fea-174">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="91fea-175">Za entiteto zvesteStranke na spustnem seznamu izberite **FullName**.</span><span class="sxs-lookup"><span data-stu-id="91fea-175">For loyCustomers select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="91fea-176">Na spustnem seznamu izberite možnost **Normaliziraj**, nato pa **Vrsta (telefon, ime, naslov, ...)**.</span><span class="sxs-lookup"><span data-stu-id="91fea-176">Select the **Normalize** dropdown and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="91fea-177">Nastavite **Raven natančnosti**: **Osnovno** in **Vrednost**: **Visoko**.</span><span class="sxs-lookup"><span data-stu-id="91fea-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="91fea-178">Vnesite ime **FullName, Email** za novo pravilo.</span><span class="sxs-lookup"><span data-stu-id="91fea-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="91fea-179">Dodajte drugi pogoj za e-poštni naslov tako, da izberete **Dodaj pogoj**.</span><span class="sxs-lookup"><span data-stu-id="91fea-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="91fea-180">Za entiteto StikiEPoslovanja na spustnem seznamu izberite možnost **E-pošta**.</span><span class="sxs-lookup"><span data-stu-id="91fea-180">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   - <span data-ttu-id="91fea-181">Za entiteto zvesteStranke na spustnem seznamu izberite možnost **E-pošta**.</span><span class="sxs-lookup"><span data-stu-id="91fea-181">For entity loyCustomers, choose **EMail** in the dropdown.</span></span>
   - <span data-ttu-id="91fea-182">Pustite polje Normaliziraj prazno.</span><span class="sxs-lookup"><span data-stu-id="91fea-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="91fea-183">Nastavite **Raven natančnosti**: **Osnovno** in **Vrednost**: **Visoko**.</span><span class="sxs-lookup"><span data-stu-id="91fea-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Poenotenje pravila ujemanja za ime in e-pošto.](media/unify-match-rule.png)

1. <span data-ttu-id="91fea-185">Izberite **Dokončano**.</span><span class="sxs-lookup"><span data-stu-id="91fea-185">Select **Done**.</span></span>

1. <span data-ttu-id="91fea-186">Izberite **Shrani** in **Zaženi**.</span><span class="sxs-lookup"><span data-stu-id="91fea-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="91fea-187">Spajanje</span><span class="sxs-lookup"><span data-stu-id="91fea-187">Merge</span></span>

1. <span data-ttu-id="91fea-188">Odprite zavihek **Spajanje**.</span><span class="sxs-lookup"><span data-stu-id="91fea-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="91fea-189">Pri **IDstranke** za entiteto **zvesteStranke** spremenite prikazno ime v **ZVESTOBAIDstranke**, da se razlikuje od ostalih vnesenih ID-jev.</span><span class="sxs-lookup"><span data-stu-id="91fea-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![Preimenujte ID stika iz ID-ja zvestobe.](media/unify-merge-contactid.png)

1. <span data-ttu-id="91fea-191">Izberite **Shrani** in **Zaženi združevanje in postopke iz strežnika**.</span><span class="sxs-lookup"><span data-stu-id="91fea-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="91fea-192">3. naloga – Konfiguriranje predvidevanja vrednosti življenjske dobe stranke</span><span class="sxs-lookup"><span data-stu-id="91fea-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="91fea-193">Z vzpostavljenimi poenotenimi profili strank lahko zaženemo predvidevanje vrednosti življenjske dobe stranke.</span><span class="sxs-lookup"><span data-stu-id="91fea-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="91fea-194">Za podrobne korake glejte [Predvidevanje vrednosti življenjske dobe stranke (predogledna različica)](predict-customer-lifetime-value.md).</span><span class="sxs-lookup"><span data-stu-id="91fea-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="91fea-195">Odprite **Obveščanje**  > **Napovedi** in izberite **Model za izračun vrednosti življenjske dobe stranke**.</span><span class="sxs-lookup"><span data-stu-id="91fea-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="91fea-196">Preglejte informacije v stranskem podoknu in izberite **Začetek**.</span><span class="sxs-lookup"><span data-stu-id="91fea-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="91fea-197">Model poimenujte **Predvidevanje CLV OOB eCommerce**, izhodno entiteto pa **OOBeCommerceCLVPrediction**.</span><span class="sxs-lookup"><span data-stu-id="91fea-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="91fea-198">Določite nastavitve modela za model CLV:</span><span class="sxs-lookup"><span data-stu-id="91fea-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="91fea-199">**Časovno obdobje predvidevanja**: **12 mesecev ali 1 leto**.</span><span class="sxs-lookup"><span data-stu-id="91fea-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="91fea-200">Ta nastavitev določa, kako daleč v prihodnost lahko napovemo vrednost življenjske dobe stranke.</span><span class="sxs-lookup"><span data-stu-id="91fea-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="91fea-201">**Dejavne stranke**: navedite, kaj dejavne stranke pomenijo vašemu podjetju.</span><span class="sxs-lookup"><span data-stu-id="91fea-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="91fea-202">Nastavite zgodovinski časovni okvir, v katerem je morala stranka imeti vsaj eno transakcijo, da se je štela za dejavno.</span><span class="sxs-lookup"><span data-stu-id="91fea-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="91fea-203">Model bo življenjsko vrednost stranke napovedal samo za aktivne stranke.</span><span class="sxs-lookup"><span data-stu-id="91fea-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="91fea-204">Izberite možnost, po kateri model izračuna časovno obdobje na podlagi preteklih podatkov o transakcijah, ali pa določite časovni okvir</span><span class="sxs-lookup"><span data-stu-id="91fea-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="91fea-205">V tem vzorčnem priročniku smo izbrali, **naj model izračuna interval nakupov**, kar je privzeta možnost.</span><span class="sxs-lookup"><span data-stu-id="91fea-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="91fea-206">**Stranke z visoko vrednostjo**: stranke z visoko vrednostjo opredelite kot percentil strank, ki največ zapravijo.</span><span class="sxs-lookup"><span data-stu-id="91fea-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="91fea-207">Model uporablja te vhodne podatke za zagotavljanje rezultatov, ki ustrezajo vaši poslovni definiciji strank z visoko vrednostjo.</span><span class="sxs-lookup"><span data-stu-id="91fea-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="91fea-208">Izberete lahko, naj model določi stranke z visoko vrednostjo.</span><span class="sxs-lookup"><span data-stu-id="91fea-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="91fea-209">Pri tem je uporabljeno hevristično pravilo, ki izpelje percentil.</span><span class="sxs-lookup"><span data-stu-id="91fea-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="91fea-210">Stranke z visoko vrednostjo lahko opredelite tudi kot percentil strank, ki bodo največ zapravile.</span><span class="sxs-lookup"><span data-stu-id="91fea-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="91fea-211">V tem vzorčnem priročniku ročno definiramo stranke z visoko vrednostjo kot **zgornjih 30 % dejavnih strank, ki največ zapravijo** in izberite **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="91fea-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Korak nastavitev v vodeni izkušnji za model CLV.":::

1. <span data-ttu-id="91fea-213">V koraku **Zahtevani podatki** izberite **Dodajanje podatkov**, da zagotovite podatke o zgodovini transakcij.</span><span class="sxs-lookup"><span data-stu-id="91fea-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="91fea-214">Dodajte entiteto **eCommercePurchases : eCommerce** in preslikajte atribute, ki jih zahteva model:</span><span class="sxs-lookup"><span data-stu-id="91fea-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="91fea-215">ID transakcije: eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="91fea-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="91fea-216">Datum transakcije: eCommerce.eCommercePurchases.PurchasedOn</span><span class="sxs-lookup"><span data-stu-id="91fea-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="91fea-217">Znesek transakcije: eCommerce.eCommercePurchases.TotalPrice</span><span class="sxs-lookup"><span data-stu-id="91fea-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="91fea-218">ID izdelka: eCommerce.eCommercePurchases.ProductId</span><span class="sxs-lookup"><span data-stu-id="91fea-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="91fea-219">Izberite **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="91fea-219">Select **Next**.</span></span>

1. <span data-ttu-id="91fea-220">Nastavitev odnosa med entiteto **eCommercePurchases : eCommerce** in **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="91fea-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="91fea-221">V koraku **Dodatni podatki (izbirno)** lahko dodate več podatkov o dejavnosti stranke.</span><span class="sxs-lookup"><span data-stu-id="91fea-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="91fea-222">Ti podatki vam lahko pomagajo pridobiti več vpogledov v interakcije strank z vašim podjetjem, kar lahko prispeva k CLV.</span><span class="sxs-lookup"><span data-stu-id="91fea-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="91fea-223">Z dodajanjem ključnih interakcij strank, kot so spletni dnevniki, dnevniki storitev za stranke ali zgodovina podeljevanja nagrad, lahko izboljšate natančnost predvidevanja.</span><span class="sxs-lookup"><span data-stu-id="91fea-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="91fea-224">Izberite **Dodajanje podatkov**, da vključite več podatkov o dejavnostih strank.</span><span class="sxs-lookup"><span data-stu-id="91fea-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="91fea-225">Dodajte entiteto dejavnosti stranke in preslikajte imena polj v ustrezna polja, ki jih zahteva model:</span><span class="sxs-lookup"><span data-stu-id="91fea-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="91fea-226">Entiteta dejavnosti stranke: Reviews:Website</span><span class="sxs-lookup"><span data-stu-id="91fea-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="91fea-227">Primarni ključ: Website.Reviews.ReviewId</span><span class="sxs-lookup"><span data-stu-id="91fea-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="91fea-228">Časovni žig: Website.Reviews.ReviewDate</span><span class="sxs-lookup"><span data-stu-id="91fea-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="91fea-229">Dogodek (ime dejavnosti): Website.Reviews.ActivityTypeDisplay</span><span class="sxs-lookup"><span data-stu-id="91fea-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="91fea-230">Podrobnosti (znesek ali vrednost): Website.Reviews.ReviewRating</span><span class="sxs-lookup"><span data-stu-id="91fea-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="91fea-231">Izberite **Naprej** in konfigurirajte dejavnost in odnos med podatki o transakciji in podatki o stranki:</span><span class="sxs-lookup"><span data-stu-id="91fea-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="91fea-232">Vrsta dejavnosti: izberite obstoječo</span><span class="sxs-lookup"><span data-stu-id="91fea-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="91fea-233">Oznaka dejavnosti: Pregled</span><span class="sxs-lookup"><span data-stu-id="91fea-233">Activity label: Review</span></span>
   - <span data-ttu-id="91fea-234">Ustrezna nalepka: Website.Reviews.UserID</span><span class="sxs-lookup"><span data-stu-id="91fea-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="91fea-235">Entiteta stranke: eCommerceContacts:eCommerce</span><span class="sxs-lookup"><span data-stu-id="91fea-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="91fea-236">Odnos: WebsiteReviews</span><span class="sxs-lookup"><span data-stu-id="91fea-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="91fea-237">Izberite **Naprej** za nastavitev urnika modela.</span><span class="sxs-lookup"><span data-stu-id="91fea-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="91fea-238">Model mora redno trenirati, da se nauči novih vzorcev, ko so vneseni novi podatki.</span><span class="sxs-lookup"><span data-stu-id="91fea-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="91fea-239">Za ta primer izberite **Mesečno**.</span><span class="sxs-lookup"><span data-stu-id="91fea-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="91fea-240">Po pregledu vseh podrobnosti izberite **Shrani in zaženi**.</span><span class="sxs-lookup"><span data-stu-id="91fea-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="91fea-241">4. opravilo – preglejte rezultate modela in razlage</span><span class="sxs-lookup"><span data-stu-id="91fea-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="91fea-242">Model naj dokonča usposabljanje in ocenjevanje podatkov.</span><span class="sxs-lookup"><span data-stu-id="91fea-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="91fea-243">Nato lahko pregledate rezultate in razlage modela CLV.</span><span class="sxs-lookup"><span data-stu-id="91fea-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="91fea-244">Za več informacij glejte [Pregled stanja in rezultatov predvidevanja](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="91fea-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="91fea-245">5. naloga – Ustvarite segment strank z visoko vrednostjo</span><span class="sxs-lookup"><span data-stu-id="91fea-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="91fea-246">Z zagonom modela boste ustvarili novo entiteto, ki je navedena na zavihku **Podatki** > **Entitete**.</span><span class="sxs-lookup"><span data-stu-id="91fea-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="91fea-247">Na podlagi entitete, ki jo je ustvaril model, lahko ustvarite nov segment za stranko.</span><span class="sxs-lookup"><span data-stu-id="91fea-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="91fea-248">Izberite **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="91fea-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="91fea-249">Izberite **Novo** in izberite **Ustvari iz** > **Obveščanje**.</span><span class="sxs-lookup"><span data-stu-id="91fea-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Ustvarjanje segmenta z izhodnimi podatki modela.](media/segment-intelligence.png)

1. <span data-ttu-id="91fea-251">Izberite entiteto **OOBeCommerceCLVPrediction** in definirajte segment:</span><span class="sxs-lookup"><span data-stu-id="91fea-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="91fea-252">Polje: CLVScore</span><span class="sxs-lookup"><span data-stu-id="91fea-252">Field: CLVScore</span></span>
  - <span data-ttu-id="91fea-253">Operator: večje kot</span><span class="sxs-lookup"><span data-stu-id="91fea-253">Operator: greater than</span></span>
  - <span data-ttu-id="91fea-254">Vrednost: 1500</span><span class="sxs-lookup"><span data-stu-id="91fea-254">Value: 1500</span></span>

1. <span data-ttu-id="91fea-255">Izberite **Pregled** in **Shrani**, da shranite segment.</span><span class="sxs-lookup"><span data-stu-id="91fea-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="91fea-256">Zdaj imate segment, ki določa stranke, ki naj bi v naslednjih 12 mesecih ustvarile več kot 1500 $ prihodka.</span><span class="sxs-lookup"><span data-stu-id="91fea-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="91fea-257">Ta segment se dinamično posodablja, če je vnesenih več podatkov.</span><span class="sxs-lookup"><span data-stu-id="91fea-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="91fea-258">Za več informacij glejte [Ustvarjanje in upravljanje segmentov](segments.md).</span><span class="sxs-lookup"><span data-stu-id="91fea-258">For more information, see [Create and manage segments](segments.md).</span></span>
