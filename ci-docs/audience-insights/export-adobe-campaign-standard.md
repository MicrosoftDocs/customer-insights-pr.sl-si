---
title: Izvoz podatkov iz storitve Customer Insights v aplikacijo Adobe Campaign Standard
description: Preberite, kako uporabljati segmente vpogleda v občinstvo v aplikaciji Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 917ab9559416f3ee0ffd66e471e590e8da3faffc
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305406"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="80b0c-103">Uporaba segmentov storitve Customer Insights v aplikaciji Adobe Campaign Standard (predogledna različica)</span><span class="sxs-lookup"><span data-stu-id="80b0c-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="80b0c-104">Kot uporabnik vpogleda občinstva v storitvi Dynamics 365 Customer Insights ste morda ustvarili segmente, da bi z njihovo pomočjo, in sicer z izborom relevantnejšega ciljnega občinstva, izpopolnili svoje trženjske akcije.</span><span class="sxs-lookup"><span data-stu-id="80b0c-104">As a user of audience insights in Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="80b0c-105">Če želite uporabiti segment iz vpogledov v občinstvo na platformi Adobe Experience Platform in v aplikacijah, kot je Adobe Campaign Standard, morate slediti nekaj korakom, ki so opisani v tem članku.</span><span class="sxs-lookup"><span data-stu-id="80b0c-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Diagram postopka korakov, opisanih v tem članku.":::

## <a name="prerequisites"></a><span data-ttu-id="80b0c-107">Zahteve</span><span class="sxs-lookup"><span data-stu-id="80b0c-107">Prerequisites</span></span>

-   <span data-ttu-id="80b0c-108">Licenca za Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="80b0c-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="80b0c-109">Licenca aplikacije Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="80b0c-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="80b0c-110">Račun za shrambo zbirke dvojiških podatkov Azure</span><span class="sxs-lookup"><span data-stu-id="80b0c-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="80b0c-111">Pregled akcije</span><span class="sxs-lookup"><span data-stu-id="80b0c-111">Campaign overview</span></span>

<span data-ttu-id="80b0c-112">Da boste bolje razumeli, kako lahko uporabite segmente iz vpogledov v občinstvo na platformi Adobe Experience Platform, si oglejmo izmišljeno vzorčno akcijo.</span><span class="sxs-lookup"><span data-stu-id="80b0c-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="80b0c-113">Predpostavimo, da vaše podjetje ponuja mesečno naročninsko storitev za vaše stranke v ZDA.</span><span class="sxs-lookup"><span data-stu-id="80b0c-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="80b0c-114">Želeli boste prepoznati stranke, ki še niso podaljšale naročnine, vendar morajo to storiti v naslednjih osmih dneh.</span><span class="sxs-lookup"><span data-stu-id="80b0c-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="80b0c-115">Če želite obdržati te stranke, jim pošljite promocijsko ponudbo po e-pošti prek aplikacije Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="80b0c-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="80b0c-116">V tem primeru želimo promocijsko e-poštno akcijo izvesti enkrat.</span><span class="sxs-lookup"><span data-stu-id="80b0c-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="80b0c-117">Ta članek ne zajema primerov uporabe večkratne izvedbe akcije.</span><span class="sxs-lookup"><span data-stu-id="80b0c-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="80b0c-118">Vendar lahko vpoglede v občinstvo in aplikacijo Adobe Campaign Standard nastavite tako, da delujejo tudi za ponavljajoči se scenarij akcije.</span><span class="sxs-lookup"><span data-stu-id="80b0c-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="80b0c-119">Določanje ciljnega občinstva</span><span class="sxs-lookup"><span data-stu-id="80b0c-119">Identify your target audience</span></span>

<span data-ttu-id="80b0c-120">V našem scenariju predpostavljamo, da so e-poštni naslovi strank na voljo v vpogledih v občinstvo in da so bile njihove promocijske nastavitve analizirane za prepoznavanje članov segmenta.</span><span class="sxs-lookup"><span data-stu-id="80b0c-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="80b0c-121">[Segment, ki ste ga opredelili v vpogledih v občinstvo](segments.md), se imenuje **ChurnProneCustomers** in tem strankam nameravate poslati e-poštno promocijo.</span><span class="sxs-lookup"><span data-stu-id="80b0c-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Posnetek zaslona strani s segmenti z ustvarjenim segmentom ChurnProneCustomers.":::

<span data-ttu-id="80b0c-123">E-poštno sporočilo, ki ga želite poslati, bo vsebovalo ime, priimek in končni datum naročnine stranke.</span><span class="sxs-lookup"><span data-stu-id="80b0c-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="80b0c-124">Stranke obvešča o popustu, ki ga bodo dobile, če bodo svojo naročnino podaljšale, še preden se konča.</span><span class="sxs-lookup"><span data-stu-id="80b0c-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="80b0c-125">Izvoz ciljnega občinstva</span><span class="sxs-lookup"><span data-stu-id="80b0c-125">Export your target audience</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="80b0c-126">Konfiguriranje povezave</span><span class="sxs-lookup"><span data-stu-id="80b0c-126">Configure a connection</span></span>

<span data-ttu-id="80b0c-127">Ko je ciljno občinstvo določeno, lahko konfiguriramo izvoz iz vpogledov v občinsto v račun za shrambo zbirke dvojiških podatkov Azure.</span><span class="sxs-lookup"><span data-stu-id="80b0c-127">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="80b0c-128">V pogledih v občinstvo odprite razdelek **Skrbnik** > **Povezave**.</span><span class="sxs-lookup"><span data-stu-id="80b0c-128">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="80b0c-129">Izberite možnost **Dodaj povezavo**, nato pa **Adobe Campaign** ter tako konfigurirajte povezavo, ali pa izberite možnost **Nastavitev** na ploščici za **Adobe Campaign**.</span><span class="sxs-lookup"><span data-stu-id="80b0c-129">Select **Add connection** and choose **Adobe Campaign** to configure the connection or select **Set up** in the **Adobe Campaign** tile.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Konfiguracijska ploščica za Adobe Campaign Standard.":::

1. <span data-ttu-id="80b0c-131">Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="80b0c-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="80b0c-132">Ime in vrsta povezave opisujeta to povezavo.</span><span class="sxs-lookup"><span data-stu-id="80b0c-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="80b0c-133">Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.</span><span class="sxs-lookup"><span data-stu-id="80b0c-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="80b0c-134">Izberite, kdo lahko uporablja to povezavo.</span><span class="sxs-lookup"><span data-stu-id="80b0c-134">Choose who can use this connection.</span></span> <span data-ttu-id="80b0c-135">Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki.</span><span class="sxs-lookup"><span data-stu-id="80b0c-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="80b0c-136">Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="80b0c-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="80b0c-137">Vnesite **Ime računa**, **Ključ računa** in **Vsebnik** računa Azure Blob Storage, kamor želite izvoziti segment.</span><span class="sxs-lookup"><span data-stu-id="80b0c-137">Enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Posnetek zaslona konfiguracije računa za shrambo."::: 

   - <span data-ttu-id="80b0c-139">Če želite izvedeti več o tem, kako do imena in ključa računa shrambe zbirke dvojiških podatkov Azure, si oglejte [Upravljanje nastavitev računa za shrambo na portalu storitve Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="80b0c-139">To learn more about how to find the Azure Blob Storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="80b0c-140">Če želite izvedeti, kako ustvariti vsebnik, glejte [Ustvarjanje vsebnika](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="80b0c-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="80b0c-141">Izberite možnost **Shrani**, da dokončate povezavo.</span><span class="sxs-lookup"><span data-stu-id="80b0c-141">Select **Save** to complete the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="80b0c-142">Konfiguriranje izvoza</span><span class="sxs-lookup"><span data-stu-id="80b0c-142">Configure an export</span></span>

<span data-ttu-id="80b0c-143">Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave.</span><span class="sxs-lookup"><span data-stu-id="80b0c-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="80b0c-144">Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="80b0c-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="80b0c-145">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="80b0c-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="80b0c-146">Izberite možnost **Dodaj izvoz** za ustvarjanje novega izvoza.</span><span class="sxs-lookup"><span data-stu-id="80b0c-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="80b0c-147">V polju **Povezava za izvoz** izberite povezavo iz razdelka Adobe Campaign.</span><span class="sxs-lookup"><span data-stu-id="80b0c-147">In the **Connection for export** field, choose a connection from the Adobe Campaign section.</span></span> <span data-ttu-id="80b0c-148">Če se vam poimenovanje tega odseka ne prikaže, to pomeni, da vam ni na voljo nobena tovrstna povezava.</span><span class="sxs-lookup"><span data-stu-id="80b0c-148">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="80b0c-149">Izberite segment, ki ga želite izvoziti.</span><span class="sxs-lookup"><span data-stu-id="80b0c-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="80b0c-150">V tem primeru je to **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="80b0c-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Posnetek zaslona uporabniškega vmesnika za izbiro segmenta, ko je izbran segment ChurnProneCustomers.":::

1. <span data-ttu-id="80b0c-152">Izberite **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="80b0c-152">Select **Next**.</span></span>

1. <span data-ttu-id="80b0c-153">Zdaj preslikamo **izvorna** polja iz segmenta vpogledov v občinstvo v ime **ciljnega** polja v shemi profilov Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="80b0c-153">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Preslikava polj za povezovalnik Adobe Campaign Standard.":::

   <span data-ttu-id="80b0c-155">Če želite dodati več atributov, izberite **Dodaj atribut**.</span><span class="sxs-lookup"><span data-stu-id="80b0c-155">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="80b0c-156">Ciljno ime je lahko drugačno od izvornega imena polja, zato lahko preslikate izhod segmenta iz vpogledov v občinstvo v aplikacijo Adobe Campaign Standard, če polja v sistemih nimajo enakega imena.</span><span class="sxs-lookup"><span data-stu-id="80b0c-156">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="80b0c-157">E-poštni naslov se uporablja kot polje identitete, vendar lahko uporabljate kateri koli drug identifikator iz profila stranke v vpogledih v občinstvo za preslikavo podatkov v aplikacijo Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="80b0c-157">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="80b0c-158">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="80b0c-158">Select **Save**.</span></span>

<span data-ttu-id="80b0c-159">Ko shranite cilj za izvoz, ga najdete v razdelku **Podatki** > **Izvoz**.</span><span class="sxs-lookup"><span data-stu-id="80b0c-159">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="80b0c-160">Zdaj lahko [izvozite segment na zahtevo](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="80b0c-160">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="80b0c-161">Izvoz se bo zagnal tudi z vsakim [načrtovanim osveževanjem](system.md).</span><span class="sxs-lookup"><span data-stu-id="80b0c-161">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="80b0c-162">Prepričajte se, da je število zapisov v izvoženem segmentu znotraj dovoljene omejitve vaše licence Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="80b0c-162">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="80b0c-163">Izvoženi podatki so shranjeni v vsebniku za shrambo zbirke dvojiških podatkov Azure, ki ste ga konfigurirali zgoraj.</span><span class="sxs-lookup"><span data-stu-id="80b0c-163">Exported data is stored in the Azure Blob Storage container you configured above.</span></span> <span data-ttu-id="80b0c-164">V vsebniku se samodejno ustvari naslednja pot do mape:</span><span class="sxs-lookup"><span data-stu-id="80b0c-164">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="80b0c-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp% .csv*</span><span class="sxs-lookup"><span data-stu-id="80b0c-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="80b0c-166">Primer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="80b0c-166">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="80b0c-167">Konfiguracija aplikacije Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="80b0c-167">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="80b0c-168">Ko je segment iz vpogledov v občinstvo izvožen, vsebuje stolpce, ki ste jih izbrali pri določanju cilja izvoza v prejšnjem koraku.</span><span class="sxs-lookup"><span data-stu-id="80b0c-168">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="80b0c-169">Te podatke je mogoče uporabiti za [ustvarjanje profilov v aplikaciji Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="80b0c-169">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="80b0c-170">Če želimo segment uporabiti v aplikaciji Adobe Campaign Standard, moramo razširiti shemo profilov v aplikaciji Adobe Campaign Standard, da bo vključevala še dve dodatni polji.</span><span class="sxs-lookup"><span data-stu-id="80b0c-170">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="80b0c-171">Preberite, kako [razširite vir profila](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) z novimi polji v aplikaciji Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="80b0c-171">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="80b0c-172">V tem primeru gre za polja *Ime in datum segmenta (izbirno)*.</span><span class="sxs-lookup"><span data-stu-id="80b0c-172">In our example, these fields are *Segment Name and Segment Date (optional)*.</span></span>

<span data-ttu-id="80b0c-173">Ta polja bomo uporabili za prepoznavanje profilov v aplikaciji Adobe Campaign Standard, na katere želimo ciljati pri tej akciji.</span><span class="sxs-lookup"><span data-stu-id="80b0c-173">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="80b0c-174">Če v aplikaciji Adobe Campaign Standard ni drugih zapisov, razen tistega, ki ga boste uvozili, lahko ta korak preskočite.</span><span class="sxs-lookup"><span data-stu-id="80b0c-174">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="80b0c-175">Uvoz podatkov v aplikacijo Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="80b0c-175">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="80b0c-176">Zdaj, ko je vse na svojem mestu, moramo iz vpogledov v občinstvo v aplikacijo Adobe Campaign Standard uvoziti pripravljene podatke o občinstvu za ustvarjanje profilov.</span><span class="sxs-lookup"><span data-stu-id="80b0c-176">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="80b0c-177">Preberite, [kako uvoziti profile v aplikacijo Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) s potekom dela.</span><span class="sxs-lookup"><span data-stu-id="80b0c-177">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="80b0c-178">Potek dela uvoza na spodnji sliki je konfiguriran, da se zažene na vsakih osem ur, in išče izvožene segmente vpogleda občinstva (datoteka .csv v shrambi zbirke dvojiških podatkov Azure).</span><span class="sxs-lookup"><span data-stu-id="80b0c-178">The import workflow in the image below has been configured to run every eight hours and look for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="80b0c-179">Potek dela izvleče vsebino datoteke .csv v določenem vrstnem redu stolpcev.</span><span class="sxs-lookup"><span data-stu-id="80b0c-179">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="80b0c-180">Ta potek dela je bil zgrajen tako, da izvaja osnovno obravnavanje napak in zagotavlja, da ima vsak zapis e-poštni naslov, preden podatke hidrira v aplikacijo Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="80b0c-180">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="80b0c-181">Potek dela prav tako iz imena dokumenta izvleče ime segmenta, preden ga vstavi v podatke profila storitve Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="80b0c-181">The workflow also extracts the segment name from the filename before upserting into Adobe Campaign Standard profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Posnetek zaslona poteka dela uvoza v uporabniškem vmesniku aplikacije Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="80b0c-183">Pridobivanje občinstva v aplikaciji Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="80b0c-183">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="80b0c-184">Ko so podatki uvoženi v aplikacijo Adobe Campaign Standard, [lahko ustvarite potek dela](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) in [poizvedbo](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) stranke na podlagi *Imena segmenta* in *Datuma segmenta*, da izberete profile, ki so bili določeni za našo vzorčno akcijo.</span><span class="sxs-lookup"><span data-stu-id="80b0c-184">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="80b0c-185">Ustvarjanje in pošiljanje e-poštnih sporočil z aplikacijo Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="80b0c-185">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="80b0c-186">Ustvarite e-poštno vsebino ter [preskusite in pošljite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-poštno sporočilo.</span><span class="sxs-lookup"><span data-stu-id="80b0c-186">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Vzorec e-poštnega sporočila s ponudbo za obnovitev iz aplikacije Adobe Campaign Standard.":::
