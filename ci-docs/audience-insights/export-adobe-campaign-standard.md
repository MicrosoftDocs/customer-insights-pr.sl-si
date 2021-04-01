---
title: Izvoz podatkov iz storitve Customer Insights v aplikacijo Adobe Campaign Standard
description: Preberite, kako uporabljati segmente vpogleda v občinstvo v aplikaciji Adobe Campaign Standard.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596335"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="913b1-103">Uporaba segmentov storitve Customer Insights v aplikaciji Adobe Campaign Standard (predogledna različica)</span><span class="sxs-lookup"><span data-stu-id="913b1-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="913b1-104">Kot uporabnik vpogledov v občinstvo za Dynamics 365 Customer Insights ste morda ustvarili segmente za izboljšanje učinkovitosti svojih trženjskih akcij s ciljanjem na ustrezno občinstvo.</span><span class="sxs-lookup"><span data-stu-id="913b1-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="913b1-105">Če želite uporabiti segment iz vpogledov v občinstvo na platformi Adobe Experience Platform in v aplikacijah, kot je Adobe Campaign Standard, morate slediti nekaj korakom, ki so opisani v tem članku.</span><span class="sxs-lookup"><span data-stu-id="913b1-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Diagram postopka korakov, opisanih v tem članku.":::

## <a name="prerequisites"></a><span data-ttu-id="913b1-107">Zahteve</span><span class="sxs-lookup"><span data-stu-id="913b1-107">Prerequisites</span></span>

-   <span data-ttu-id="913b1-108">Licenca za Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="913b1-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="913b1-109">Licenca aplikacije Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="913b1-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="913b1-110">Račun za shrambo zbirke dvojiških podatkov Azure</span><span class="sxs-lookup"><span data-stu-id="913b1-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="913b1-111">Pregled akcije</span><span class="sxs-lookup"><span data-stu-id="913b1-111">Campaign Overview</span></span>

<span data-ttu-id="913b1-112">Da boste bolje razumeli, kako lahko uporabite segmente iz vpogledov v občinstvo na platformi Adobe Experience Platform, si oglejmo izmišljeno vzorčno akcijo.</span><span class="sxs-lookup"><span data-stu-id="913b1-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="913b1-113">Predpostavimo, da vaše podjetje ponuja mesečno naročninsko storitev za vaše stranke v ZDA.</span><span class="sxs-lookup"><span data-stu-id="913b1-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="913b1-114">Želeli boste prepoznati stranke, ki še niso podaljšale naročnine, vendar morajo to storiti v naslednjih osmih dneh.</span><span class="sxs-lookup"><span data-stu-id="913b1-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="913b1-115">Če želite obdržati te stranke, jim pošljite promocijsko ponudbo po e-pošti prek aplikacije Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="913b1-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="913b1-116">V tem primeru želimo promocijsko e-poštno akcijo izvesti enkrat.</span><span class="sxs-lookup"><span data-stu-id="913b1-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="913b1-117">Ta članek ne zajema primerov uporabe večkratne izvedbe akcije.</span><span class="sxs-lookup"><span data-stu-id="913b1-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="913b1-118">Vendar lahko vpoglede v občinstvo in aplikacijo Adobe Campaign Standard nastavite tako, da delujejo tudi za ponavljajoči se scenarij akcije.</span><span class="sxs-lookup"><span data-stu-id="913b1-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="913b1-119">Določanje ciljnega občinstva</span><span class="sxs-lookup"><span data-stu-id="913b1-119">Identify your target audience</span></span>

<span data-ttu-id="913b1-120">V našem scenariju predpostavljamo, da so e-poštni naslovi strank na voljo v vpogledih v občinstvo in da so bile njihove promocijske nastavitve analizirane za prepoznavanje članov segmenta.</span><span class="sxs-lookup"><span data-stu-id="913b1-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="913b1-121">[Segment, ki ste ga opredelili v vpogledih v občinstvo](segments.md), se imenuje **ChurnProneCustomers** in tem strankam nameravate poslati e-poštno promocijo.</span><span class="sxs-lookup"><span data-stu-id="913b1-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Posnetek zaslona strani s segmenti z ustvarjenim segmentom ChurnProneCustomers.":::

<span data-ttu-id="913b1-123">E-poštno sporočilo, ki ga želite poslati, bo vsebovalo ime, priimek in končni datum naročnine stranke.</span><span class="sxs-lookup"><span data-stu-id="913b1-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="913b1-124">Stranke obvešča o popustu, ki ga bodo dobile, če bodo svojo naročnino podaljšale, še preden se konča.</span><span class="sxs-lookup"><span data-stu-id="913b1-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="913b1-125">Izvoz ciljnega občinstva</span><span class="sxs-lookup"><span data-stu-id="913b1-125">Export your target audience</span></span>

<span data-ttu-id="913b1-126">Ko je ciljno občinstvo določeno, lahko konfiguriramo izvoz iz vpogledov v občinsto v račun za shrambo zbirke dvojiških podatkov Azure.</span><span class="sxs-lookup"><span data-stu-id="913b1-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="913b1-127">Pri vpogledih v občinstvo izberite **Skrbnik** > **Cilji izvoza**.</span><span class="sxs-lookup"><span data-stu-id="913b1-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="913b1-128">Na ploščici **Adobe Campaign** izberite **Nastavi**.</span><span class="sxs-lookup"><span data-stu-id="913b1-128">In the **Adobe Campaign** tile, select **Set up**.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Konfiguracijska ploščica za Adobe Campaign Standard.":::

1. <span data-ttu-id="913b1-130">Navedite **prikazno ime** za novi cilj izvoza ter vnesite **ime računa**, **ključ računa** in **vsebnik** računa za shrambo zbirke dvojiških podatkov Azure, kamor želite izvoziti segment.</span><span class="sxs-lookup"><span data-stu-id="913b1-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Posnetek zaslona konfiguracije računa za shrambo. "::: 

   - <span data-ttu-id="913b1-132">Če želite izvedeti več o tem, kako najti ime in ključ računa za shrambo zbirke dvojiških podatkov Azure, glejte [Upravljanje nastavitev računa za shrambo na portalu storitve Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="913b1-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="913b1-133">Če želite izvedeti, kako ustvariti vsebnik, glejte [Ustvarjanje vsebnika](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="913b1-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="913b1-134">Izberite **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="913b1-134">Select **Next**.</span></span>

1. <span data-ttu-id="913b1-135">Izberite segment, ki ga želite izvoziti.</span><span class="sxs-lookup"><span data-stu-id="913b1-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="913b1-136">V tem primeru je to **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="913b1-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Posnetek zaslona uporabniškega vmesnika za izbiro segmenta, ko je izbran segment ChurnProneCustomers.":::

1. <span data-ttu-id="913b1-138">Izberite **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="913b1-138">Select **Next**.</span></span>

1. <span data-ttu-id="913b1-139">Zdaj preslikamo **izvorna** polja iz segmenta vpogledov v občinstvo v ime **ciljnega** polja v shemi profilov Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="913b1-139">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Preslikava polj za povezovalnik Adobe Campaign Standard.":::

   <span data-ttu-id="913b1-141">Če želite dodati več atributov, izberite **Dodaj atribut**.</span><span class="sxs-lookup"><span data-stu-id="913b1-141">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="913b1-142">Ciljno ime je lahko drugačno od izvornega imena polja, zato lahko preslikate izhod segmenta iz vpogledov v občinstvo v aplikacijo Adobe Campaign Standard, če polja v sistemih nimajo enakega imena.</span><span class="sxs-lookup"><span data-stu-id="913b1-142">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="913b1-143">E-poštni naslov se uporablja kot polje identitete, vendar lahko uporabljate kateri koli drug identifikator iz profila stranke v vpogledih v občinstvo za preslikavo podatkov v aplikacijo Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="913b1-143">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="913b1-144">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="913b1-144">Select **Save**.</span></span>

<span data-ttu-id="913b1-145">Ko shranite cilj izvoza, ga najdete v možnosti **Skrbnik** > **Izvozi** > **Moji cilji izvoza**.</span><span class="sxs-lookup"><span data-stu-id="913b1-145">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Posnetek zaslona z označenim seznamom izvozov in vzorčnim segmentom.":::

<span data-ttu-id="913b1-147">Zdaj lahko [izvozite segment na zahtevo](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="913b1-147">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="913b1-148">Izvoz se bo zagnal tudi z vsakim [načrtovanim osveževanjem](system.md).</span><span class="sxs-lookup"><span data-stu-id="913b1-148">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="913b1-149">Prepričajte se, da je število zapisov v izvoženem segmentu znotraj dovoljene omejitve vaše licence Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="913b1-149">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="913b1-150">Izvoženi podatki so shranjeni v vsebniku za shrambo zbirke dvojiških podatkov Azure, ki ste ga konfigurirali zgoraj.</span><span class="sxs-lookup"><span data-stu-id="913b1-150">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="913b1-151">V vsebniku se samodejno ustvari naslednja pot do mape:</span><span class="sxs-lookup"><span data-stu-id="913b1-151">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="913b1-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp% .csv*</span><span class="sxs-lookup"><span data-stu-id="913b1-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="913b1-153">Primer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="913b1-153">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="913b1-154">Konfiguracija aplikacije Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="913b1-154">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="913b1-155">Ko je segment iz vpogledov v občinstvo izvožen, vsebuje stolpce, ki ste jih izbrali pri določanju cilja izvoza v prejšnjem koraku.</span><span class="sxs-lookup"><span data-stu-id="913b1-155">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="913b1-156">Te podatke je mogoče uporabiti za [ustvarjanje profilov v aplikaciji Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="913b1-156">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="913b1-157">Če želimo segment uporabiti v aplikaciji Adobe Campaign Standard, moramo razširiti shemo profilov v aplikaciji Adobe Campaign Standard, da bo vključevala še dve dodatni polji.</span><span class="sxs-lookup"><span data-stu-id="913b1-157">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="913b1-158">Preberite, kako [razširite vir profila](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) z novimi polji v aplikaciji Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="913b1-158">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="913b1-159">V našem primeru so to polja *Ime in datum segmenta (izbirno).*</span><span class="sxs-lookup"><span data-stu-id="913b1-159">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="913b1-160">Ta polja bomo uporabili za prepoznavanje profilov v aplikaciji Adobe Campaign Standard, na katere želimo ciljati pri tej akciji.</span><span class="sxs-lookup"><span data-stu-id="913b1-160">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="913b1-161">Če v aplikaciji Adobe Campaign Standard ni drugih zapisov, razen tistega, ki ga boste uvozili, lahko ta korak preskočite.</span><span class="sxs-lookup"><span data-stu-id="913b1-161">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="913b1-162">Uvoz podatkov v aplikacijo Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="913b1-162">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="913b1-163">Zdaj, ko je vse na svojem mestu, moramo iz vpogledov v občinstvo v aplikacijo Adobe Campaign Standard uvoziti pripravljene podatke o občinstvu za ustvarjanje profilov.</span><span class="sxs-lookup"><span data-stu-id="913b1-163">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="913b1-164">Preberite, [kako uvoziti profile v aplikacijo Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) s potekom dela.</span><span class="sxs-lookup"><span data-stu-id="913b1-164">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="913b1-165">Potek dela uvoza na spodnji sliki je konfiguriran za zagon vsakih 8 ur in išče izvožene segmente vpogledov v občinstvo (datoteka .csv v shrambi zbirke dvojiških podatkov Azure).</span><span class="sxs-lookup"><span data-stu-id="913b1-165">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="913b1-166">Potek dela izvleče vsebino datoteke .csv v določenem vrstnem redu stolpcev.</span><span class="sxs-lookup"><span data-stu-id="913b1-166">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="913b1-167">Ta potek dela je bil zgrajen tako, da izvaja osnovno obravnavanje napak in zagotavlja, da ima vsak zapis e-poštni naslov, preden podatke hidrira v aplikacijo Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="913b1-167">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="913b1-168">Potek dela izvleče tudi ime segmenta iz imena datoteke, preden ga vstavi v podatke profila ACS.</span><span class="sxs-lookup"><span data-stu-id="913b1-168">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Posnetek zaslona poteka dela uvoza v uporabniškem vmesniku aplikacije Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="913b1-170">Pridobivanje občinstva v aplikaciji Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="913b1-170">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="913b1-171">Ko so podatki uvoženi v aplikacijo Adobe Campaign Standard, [lahko ustvarite potek dela](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) in [poizvedbo](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) stranke na podlagi *Imena segmenta* in *Datuma segmenta*, da izberete profile, ki so bili določeni za našo vzorčno akcijo.</span><span class="sxs-lookup"><span data-stu-id="913b1-171">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="913b1-172">Ustvarjanje in pošiljanje e-poštnih sporočil z aplikacijo Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="913b1-172">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="913b1-173">Ustvarite e-poštno vsebino ter [preskusite in pošljite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-poštno sporočilo.</span><span class="sxs-lookup"><span data-stu-id="913b1-173">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Vzorec e-poštnega sporočila s ponudbo za obnovitev iz aplikacije Adobe Campaign Standard.":::