---
title: Izvoz podatkov storitve Customer Insights na platformo Adobe Experience Platform
description: Naučite se, kako uporabljati segmente vpogleda občinstva v storitvi Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 1045d0e373fd5ea8987684e51bd9a07b7b535ee3
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305544"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="66b48-103">Uporaba segmentov storitve Customer Insights na platformi Adobe Experience Platform (predogledna različica)</span><span class="sxs-lookup"><span data-stu-id="66b48-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="66b48-104">Kot uporabnik vpogleda občinstva v storitvi Dynamics 365 Customer Insights ste morda ustvarili segmente, da bi z njihovo pomočjo, in sicer z izborom relevantnejšega ciljnega občinstva, izpopolnili svoje trženjske akcije.</span><span class="sxs-lookup"><span data-stu-id="66b48-104">As a user of audience insights in Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="66b48-105">Če želite uporabiti segment iz vpogledov v občinstvo na platformi Adobe Experience Platform in v aplikacijah, kot je Adobe Campaign Standard, morate slediti nekaj korakom, ki so opisani v tem članku.</span><span class="sxs-lookup"><span data-stu-id="66b48-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Diagram postopka korakov, opisanih v tem članku.":::

## <a name="prerequisites"></a><span data-ttu-id="66b48-107">Zahteve</span><span class="sxs-lookup"><span data-stu-id="66b48-107">Prerequisites</span></span>

-   <span data-ttu-id="66b48-108">Licenca za Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="66b48-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="66b48-109">Licenca za Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="66b48-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="66b48-110">Licenca aplikacije Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="66b48-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="66b48-111">Račun za shrambo zbirke dvojiških podatkov Azure</span><span class="sxs-lookup"><span data-stu-id="66b48-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="66b48-112">Pregled akcije</span><span class="sxs-lookup"><span data-stu-id="66b48-112">Campaign Overview</span></span>

<span data-ttu-id="66b48-113">Da boste bolje razumeli, kako lahko uporabite segmente iz vpogledov v občinstvo na platformi Adobe Experience Platform, si oglejmo izmišljeno vzorčno akcijo.</span><span class="sxs-lookup"><span data-stu-id="66b48-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="66b48-114">Predpostavimo, da vaše podjetje ponuja mesečno naročninsko storitev za vaše stranke v ZDA.</span><span class="sxs-lookup"><span data-stu-id="66b48-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="66b48-115">Želeli boste prepoznati stranke, ki še niso podaljšale naročnine, vendar morajo to storiti v naslednjih osmih dneh.</span><span class="sxs-lookup"><span data-stu-id="66b48-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="66b48-116">Če želite obdržati te stranke, jim pošljite promocijsko ponudbo po e-pošti prek platforme Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="66b48-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="66b48-117">V tem primeru želimo promocijsko e-poštno akcijo izvesti enkrat.</span><span class="sxs-lookup"><span data-stu-id="66b48-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="66b48-118">Ta članek ne zajema primerov uporabe večkratne izvedbe akcije.</span><span class="sxs-lookup"><span data-stu-id="66b48-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="66b48-119">Določanje ciljnega občinstva</span><span class="sxs-lookup"><span data-stu-id="66b48-119">Identify your target audience</span></span>

<span data-ttu-id="66b48-120">V našem scenariju predpostavljamo, da so e-poštni naslovi strank na voljo v vpogledih v občinstvo in da so bile njihove promocijske nastavitve analizirane za prepoznavanje članov segmenta.</span><span class="sxs-lookup"><span data-stu-id="66b48-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="66b48-121">[Segment, ki ste ga opredelili v vpogledih v občinstvo](segments.md), se imenuje **ChurnProneCustomers** in tem strankam nameravate poslati e-poštno promocijo.</span><span class="sxs-lookup"><span data-stu-id="66b48-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Posnetek zaslona strani s segmenti z ustvarjenim segmentom ChurnProneCustomers.":::

<span data-ttu-id="66b48-123">E-poštno sporočilo, ki ga želite poslati, bo vsebovalo ime, priimek in končni datum naročnine stranke.</span><span class="sxs-lookup"><span data-stu-id="66b48-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="66b48-124">Stranke obvešča o popustu, ki ga bodo dobile, če bodo svojo naročnino podaljšale, še preden se konča.</span><span class="sxs-lookup"><span data-stu-id="66b48-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="66b48-125">Izvoz ciljnega občinstva</span><span class="sxs-lookup"><span data-stu-id="66b48-125">Export your target audience</span></span>

<span data-ttu-id="66b48-126">Ko je ciljno občinstvo določeno, lahko konfiguriramo izvoz iz vpogledov v občinsto v račun za shrambo zbirke dvojiških podatkov Azure.</span><span class="sxs-lookup"><span data-stu-id="66b48-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="66b48-127">Konfiguriranje povezave</span><span class="sxs-lookup"><span data-stu-id="66b48-127">Configure a connection</span></span>

1. <span data-ttu-id="66b48-128">Odprite razdelek **Skrbnik** > **Povezave**.</span><span class="sxs-lookup"><span data-stu-id="66b48-128">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="66b48-129">Izberite možnost **Dodaj povezavo**, nato pa **zbirka dvojiških podatkov Azure**, ali pa izberite možnost **Nastavitev** na ploščici za **zbirko dvojiških podatkov Azure** ter konfigurirajte povezavo.</span><span class="sxs-lookup"><span data-stu-id="66b48-129">Select **Add connection** and choose **Azure Blob Storage** or select **Set up** in the **Azure Blob Storage** tile to configure the connection.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Konfiguracijska ploščica za shrambo zbirke dvojiških podatkov Azure."::: 

1. <span data-ttu-id="66b48-131">Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="66b48-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="66b48-132">Ime in vrsta povezave opisujeta to povezavo.</span><span class="sxs-lookup"><span data-stu-id="66b48-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="66b48-133">Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.</span><span class="sxs-lookup"><span data-stu-id="66b48-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="66b48-134">Izberite, kdo lahko uporablja to povezavo.</span><span class="sxs-lookup"><span data-stu-id="66b48-134">Choose who can use this connection.</span></span> <span data-ttu-id="66b48-135">Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki.</span><span class="sxs-lookup"><span data-stu-id="66b48-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="66b48-136">Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="66b48-136">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="66b48-137">Da bi ustvarili račun za shrambo zbirke dvojiških podatkov, v katerega želite izvoziti segment, vnesite **Ime računa**, **Ključ računa** in **Vsebnik**.</span><span class="sxs-lookup"><span data-stu-id="66b48-137">Enter **Account name**, **Account key**, and **Container** for your Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Posnetek zaslona konfiguracije računa za shrambo."::: 
   
    - <span data-ttu-id="66b48-139">Za več informacij o iskanju imena računa in ključa računa shrambe zbirke dvojiških podatkov si oglejte [Upravljanje nastavitev računa za shrambo na portalu Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="66b48-139">To learn more about how to find the Blob Storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="66b48-140">Če želite izvedeti, kako ustvariti vsebnik, glejte [Ustvarjanje vsebnika](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="66b48-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="66b48-141">Izberite možnost **Shrani**, da dokončate povezavo.</span><span class="sxs-lookup"><span data-stu-id="66b48-141">Select **Save** to complete the connection.</span></span> 

### <a name="configure-an-export"></a><span data-ttu-id="66b48-142">Konfiguriranje izvoza</span><span class="sxs-lookup"><span data-stu-id="66b48-142">Configure an export</span></span>

<span data-ttu-id="66b48-143">Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave.</span><span class="sxs-lookup"><span data-stu-id="66b48-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="66b48-144">Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="66b48-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="66b48-145">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="66b48-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="66b48-146">Izberite možnost **Dodaj izvoz** za ustvarjanje novega izvoza.</span><span class="sxs-lookup"><span data-stu-id="66b48-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="66b48-147">V polju **Povezava za izvoz** izberite povezavo v razdelku Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="66b48-147">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="66b48-148">Če se vam poimenovanje tega odseka ne prikaže, to pomeni, da vam ni na voljo nobena tovrstna povezava.</span><span class="sxs-lookup"><span data-stu-id="66b48-148">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="66b48-149">Izberite segment, ki ga želite izvoziti.</span><span class="sxs-lookup"><span data-stu-id="66b48-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="66b48-150">V tem primeru je to **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="66b48-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Posnetek zaslona uporabniškega vmesnika za izbiro segmenta, ko je izbran segment ChurnProneCustomers.":::

1. <span data-ttu-id="66b48-152">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="66b48-152">Select **Save**.</span></span>

<span data-ttu-id="66b48-153">Ko shranite cilj za izvoz, ga najdete v razdelku **Podatki** > **Izvoz**.</span><span class="sxs-lookup"><span data-stu-id="66b48-153">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="66b48-154">Zdaj lahko [izvozite segment na zahtevo](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="66b48-154">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="66b48-155">Izvoz se bo zagnal tudi z vsakim [načrtovanim osveževanjem](system.md).</span><span class="sxs-lookup"><span data-stu-id="66b48-155">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="66b48-156">Prepričajte se, da je število zapisov v izvoženem segmentu znotraj dovoljene omejitve vaše licence Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="66b48-156">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="66b48-157">Izvoženi podatki so shranjeni v vsebniku za shrambo zbirke dvojiških podatkov Azure, ki ste ga konfigurirali zgoraj.</span><span class="sxs-lookup"><span data-stu-id="66b48-157">Exported data is stored in the Azure Blob Storage container you configured above.</span></span> <span data-ttu-id="66b48-158">V vsebniku se samodejno ustvari naslednja pot do mape:</span><span class="sxs-lookup"><span data-stu-id="66b48-158">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="66b48-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="66b48-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="66b48-160">Primer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="66b48-160">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="66b48-161">*model.json* za izvožene entitete se nahaja na ravni *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="66b48-161">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="66b48-162">Primer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="66b48-162">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="66b48-163">Določanje podatkovnega modela Experience Data Model (XDM) na platformi Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="66b48-163">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="66b48-164">Preden lahko izvožene podatke iz vpogledov v občinstvo uporabimo na platformi Adobe Experience Platform, moramo določiti shemo podatkovnega modela Experience Data Model in [konfigurirati podatke za profil stranke v realnem času](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="66b48-164">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="66b48-165">Spoznajte [XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) in [osnove sestave shem](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="66b48-165">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="66b48-166">Uvoz podatkov na platformo Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="66b48-166">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="66b48-167">Zdaj, ko je vse na svojem mestu, moramo iz vpogledov v občinstvo na platformo Adobe Experience Platform uvoziti pripravljene podatke o občinstvu za ustvarjanje profilov.</span><span class="sxs-lookup"><span data-stu-id="66b48-167">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="66b48-168">Najprej [ustvarite izvorno povezavo za shrambo zbirke dvojiških podatkov Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="66b48-168">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="66b48-169">Ko določite izvorne povezave, [konfigurirajte podatkovni tok](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) za paketno povezavo shranjevanja v oblaku, da uvozite izhod segmenta iz vpogledov v občinstvo na platformo Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="66b48-169">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="66b48-170">Ustvarjanje občinstva v aplikaciji Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="66b48-170">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="66b48-171">Za pošiljanje e-poštnega sporočila za to akcijo bomo uporabili aplikacijo Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="66b48-171">To send the email for this campaign, we'll use Adobe Campaign Standard.</span></span> <span data-ttu-id="66b48-172">Po uvozu podatkov na platformo Adobe Experience Platform moramo v aplikaciji Adobe Campaign Standard [ustvariti občinstvo](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission), pri čemer uporabimo podatke na platformi Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="66b48-172">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>


<span data-ttu-id="66b48-173">Preberite, kako v aplikaciji Adobe Campaign Standard [uporabite graditelja segmentov](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html), da določite občinstvo na podlagi podatkov na platformi Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="66b48-173">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="66b48-174">Ustvarjanje in pošiljanje e-poštnih sporočil z aplikacijo Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="66b48-174">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="66b48-175">Ustvarite e-poštno vsebino ter [preskusite in pošljite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-poštno sporočilo.</span><span class="sxs-lookup"><span data-stu-id="66b48-175">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Vzorec e-poštnega sporočila s ponudbo za obnovitev iz aplikacije Adobe Campaign Standard.":::
