---
title: Izvoz podatkov storitve Customer Insights na platformo Adobe Experience Platform
description: Preberite, kako uporabljati segmente vpogleda v občinstvo na platformi Adobe Experience Platform.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596289"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="bd125-103">Uporaba segmentov storitve Customer Insights na platformi Adobe Experience Platform (predogledna različica)</span><span class="sxs-lookup"><span data-stu-id="bd125-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="bd125-104">Kot uporabnik vpogledov v občinstvo za Dynamics 365 Customer Insights ste morda ustvarili segmente za izboljšanje učinkovitosti svojih trženjskih akcij s ciljanjem na ustrezno občinstvo.</span><span class="sxs-lookup"><span data-stu-id="bd125-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="bd125-105">Če želite uporabiti segment iz vpogledov v občinstvo na platformi Adobe Experience Platform in v aplikacijah, kot je Adobe Campaign Standard, morate slediti nekaj korakom, ki so opisani v tem članku.</span><span class="sxs-lookup"><span data-stu-id="bd125-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Diagram postopka korakov, opisanih v tem članku.":::

## <a name="prerequisites"></a><span data-ttu-id="bd125-107">Zahteve</span><span class="sxs-lookup"><span data-stu-id="bd125-107">Prerequisites</span></span>

-   <span data-ttu-id="bd125-108">Licenca za Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="bd125-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="bd125-109">Licenca za Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="bd125-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="bd125-110">Licenca aplikacije Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="bd125-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="bd125-111">Račun za shrambo zbirke dvojiških podatkov Azure</span><span class="sxs-lookup"><span data-stu-id="bd125-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="bd125-112">Pregled akcije</span><span class="sxs-lookup"><span data-stu-id="bd125-112">Campaign Overview</span></span>

<span data-ttu-id="bd125-113">Da boste bolje razumeli, kako lahko uporabite segmente iz vpogledov v občinstvo na platformi Adobe Experience Platform, si oglejmo izmišljeno vzorčno akcijo.</span><span class="sxs-lookup"><span data-stu-id="bd125-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="bd125-114">Predpostavimo, da vaše podjetje ponuja mesečno naročninsko storitev za vaše stranke v ZDA.</span><span class="sxs-lookup"><span data-stu-id="bd125-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="bd125-115">Želeli boste prepoznati stranke, ki še niso podaljšale naročnine, vendar morajo to storiti v naslednjih osmih dneh.</span><span class="sxs-lookup"><span data-stu-id="bd125-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="bd125-116">Če želite obdržati te stranke, jim pošljite promocijsko ponudbo po e-pošti prek platforme Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="bd125-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="bd125-117">V tem primeru želimo promocijsko e-poštno akcijo izvesti enkrat.</span><span class="sxs-lookup"><span data-stu-id="bd125-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="bd125-118">Ta članek ne zajema primerov uporabe večkratne izvedbe akcije.</span><span class="sxs-lookup"><span data-stu-id="bd125-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="bd125-119">Določanje ciljnega občinstva</span><span class="sxs-lookup"><span data-stu-id="bd125-119">Identify your target audience</span></span>

<span data-ttu-id="bd125-120">V našem scenariju predpostavljamo, da so e-poštni naslovi strank na voljo v vpogledih v občinstvo in da so bile njihove promocijske nastavitve analizirane za prepoznavanje članov segmenta.</span><span class="sxs-lookup"><span data-stu-id="bd125-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="bd125-121">[Segment, ki ste ga opredelili v vpogledih v občinstvo](segments.md), se imenuje **ChurnProneCustomers** in tem strankam nameravate poslati e-poštno promocijo.</span><span class="sxs-lookup"><span data-stu-id="bd125-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Posnetek zaslona strani s segmenti z ustvarjenim segmentom ChurnProneCustomers.":::

<span data-ttu-id="bd125-123">E-poštno sporočilo, ki ga želite poslati, bo vsebovalo ime, priimek in končni datum naročnine stranke.</span><span class="sxs-lookup"><span data-stu-id="bd125-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="bd125-124">Stranke obvešča o popustu, ki ga bodo dobile, če bodo svojo naročnino podaljšale, še preden se konča.</span><span class="sxs-lookup"><span data-stu-id="bd125-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="bd125-125">Izvoz ciljnega občinstva</span><span class="sxs-lookup"><span data-stu-id="bd125-125">Export your target audience</span></span>

<span data-ttu-id="bd125-126">Ko je ciljno občinstvo določeno, lahko konfiguriramo izvoz iz vpogledov v občinsto v račun za shrambo zbirke dvojiških podatkov Azure.</span><span class="sxs-lookup"><span data-stu-id="bd125-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="bd125-127">Pri vpogledih v občinstvo izberite **Skrbnik** > **Cilji izvoza**.</span><span class="sxs-lookup"><span data-stu-id="bd125-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="bd125-128">Na ploščici **Shramba zbirke dvojiških podatkov Azure** izberite **Nastavitev**.</span><span class="sxs-lookup"><span data-stu-id="bd125-128">In the **Azure Blob Storage** tile, select **Set up**.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Konfiguracijska ploščica za shrambo zbirke dvojiških podatkov Azure.":::

1. <span data-ttu-id="bd125-130">Navedite **prikazno ime** za novi cilj izvoza ter vnesite **ime računa**, **ključ računa** in **vsebnik** računa za shrambo zbirke dvojiških podatkov Azure, kamor želite izvoziti segment.</span><span class="sxs-lookup"><span data-stu-id="bd125-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Posnetek zaslona konfiguracije računa za shrambo. "::: 

   - <span data-ttu-id="bd125-132">Če želite izvedeti več o tem, kako najti ime in ključ računa za shrambo zbirke dvojiških podatkov Azure, glejte [Upravljanje nastavitev računa za shrambo na portalu storitve Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="bd125-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="bd125-133">Če želite izvedeti, kako ustvariti vsebnik, glejte [Ustvarjanje vsebnika](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="bd125-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="bd125-134">Izberite **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="bd125-134">Select **Next**.</span></span>

1. <span data-ttu-id="bd125-135">Izberite segment, ki ga želite izvoziti.</span><span class="sxs-lookup"><span data-stu-id="bd125-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="bd125-136">V tem primeru je to **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="bd125-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Posnetek zaslona uporabniškega vmesnika za izbiro segmenta, ko je izbran segment ChurnProneCustomers.":::

1. <span data-ttu-id="bd125-138">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="bd125-138">Select **Save**.</span></span>

<span data-ttu-id="bd125-139">Ko shranite cilj izvoza, ga najdete v možnosti **Skrbnik** > **Izvozi** > **Moji cilji izvoza**.</span><span class="sxs-lookup"><span data-stu-id="bd125-139">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Posnetek zaslona z označenim seznamom izvozov in vzorčnim segmentom.":::

<span data-ttu-id="bd125-141">Zdaj lahko [izvozite segment na zahtevo](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="bd125-141">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="bd125-142">Izvoz se bo zagnal tudi z vsakim [načrtovanim osveževanjem](system.md).</span><span class="sxs-lookup"><span data-stu-id="bd125-142">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="bd125-143">Prepričajte se, da je število zapisov v izvoženem segmentu znotraj dovoljene omejitve vaše licence Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="bd125-143">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="bd125-144">Izvoženi podatki so shranjeni v vsebniku za shrambo zbirke dvojiških podatkov Azure, ki ste ga konfigurirali zgoraj.</span><span class="sxs-lookup"><span data-stu-id="bd125-144">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="bd125-145">V vsebniku se samodejno ustvari naslednja pot do mape:</span><span class="sxs-lookup"><span data-stu-id="bd125-145">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="bd125-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="bd125-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="bd125-147">Primer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="bd125-147">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="bd125-148">*model.json* za izvožene entitete se nahaja na ravni *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="bd125-148">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="bd125-149">Primer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="bd125-149">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="bd125-150">Določanje podatkovnega modela Experience Data Model (XDM) na platformi Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="bd125-150">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="bd125-151">Preden lahko izvožene podatke iz vpogledov v občinstvo uporabimo na platformi Adobe Experience Platform, moramo določiti shemo podatkovnega modela Experience Data Model in [konfigurirati podatke za profil stranke v realnem času](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="bd125-151">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="bd125-152">Spoznajte [XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) in [osnove sestave shem](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="bd125-152">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="bd125-153">Uvoz podatkov na platformo Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="bd125-153">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="bd125-154">Zdaj, ko je vse na svojem mestu, moramo iz vpogledov v občinstvo na platformo Adobe Experience Platform uvoziti pripravljene podatke o občinstvu za ustvarjanje profilov.</span><span class="sxs-lookup"><span data-stu-id="bd125-154">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="bd125-155">Najprej [ustvarite izvorno povezavo za shrambo zbirke dvojiških podatkov Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="bd125-155">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="bd125-156">Ko določite izvorne povezave, [konfigurirajte podatkovni tok](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) za paketno povezavo shranjevanja v oblaku, da uvozite izhod segmenta iz vpogledov v občinstvo na platformo Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="bd125-156">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="bd125-157">Ustvarjanje občinstva v aplikaciji Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="bd125-157">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="bd125-158">Za pošiljanje e-poštnega sporočila za to akcijo bomo uporabili aplikacijo Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="bd125-158">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="bd125-159">Po uvozu podatkov na platformo Adobe Experience Platform moramo v aplikaciji Adobe Campaign Standard [ustvariti občinstvo](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission), pri čemer uporabimo podatke na platformi Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="bd125-159">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="bd125-160">Preberite, kako v aplikaciji Adobe Campaign Standard [uporabite graditelja segmentov](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment), da določite občinstvo na podlagi podatkov na platformi Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="bd125-160">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="bd125-161">Ustvarjanje in pošiljanje e-poštnih sporočil z aplikacijo Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="bd125-161">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="bd125-162">Ustvarite e-poštno vsebino ter [preskusite in pošljite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-poštno sporočilo.</span><span class="sxs-lookup"><span data-stu-id="bd125-162">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Vzorec e-poštnega sporočila s ponudbo za obnovitev iz aplikacije Adobe Campaign Standard.":::