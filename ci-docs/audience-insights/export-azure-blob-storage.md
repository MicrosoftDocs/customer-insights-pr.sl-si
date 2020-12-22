---
title: Izvozite podatke Customer Insights v shrambo zbirke dvojiških podatkov Azure
description: Naučite se konfigurirati povezavo s shrambo zbirke dvojiških podatkov Azure.
ms.date: 09/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 925b53260e7c633e17d7f172d2dd2d581e982e10
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667159"
---
# <a name="connector-for-azure-blob-storage-preview"></a><span data-ttu-id="854e4-103">Povezovalnik za shrambo zbirke dvojiških podatkov Azure (predogled)</span><span class="sxs-lookup"><span data-stu-id="854e4-103">Connector for Azure Blob storage (preview)</span></span>

<span data-ttu-id="854e4-104">Podatke iz storitve Customer Insights shranite v shrambo zbirke dvojiških podatkov Azure ali jih uporabite za prenos podatkov v druge aplikacije.</span><span class="sxs-lookup"><span data-stu-id="854e4-104">Store your Customer Insights data in an Azure Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-blob-storage"></a><span data-ttu-id="854e4-105">Konfiguracija povezovalnika za shrambo zbirke dvojiških podatkov Azure</span><span class="sxs-lookup"><span data-stu-id="854e4-105">Configure the connector for Azure Blob storage</span></span>

1. <span data-ttu-id="854e4-106">Pri vpogledih v občinstvo izberite **Skrbnik** > **Cilji izvoza**.</span><span class="sxs-lookup"><span data-stu-id="854e4-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="854e4-107">Pod možnostjo **Shramba zbirke dvojiških podatkov Azure** izberite **Nastavitev**.</span><span class="sxs-lookup"><span data-stu-id="854e4-107">Under **Azure Blob Storage**, select **Set up**.</span></span>

1. <span data-ttu-id="854e4-108">Vnesite **Ime računa**, **Ključ računa** in **Vsebnik** za svoj račun za shrambo zbirke dvojiških podatkov Azure.</span><span class="sxs-lookup"><span data-stu-id="854e4-108">Enter **Account name**, **Account key**, and **Container** for your Azure Blob storage account.</span></span>
    - <span data-ttu-id="854e4-109">Če želite izvedeti več o tem, kako najti ime in ključ računa za shrambo zbirke dvojiških podatkov Azure, glejte [Upravljanje nastavitev računa za shrambo na portalu storitve Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="854e4-109">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="854e4-110">Če želite izvedeti, kako ustvariti vsebnik, glejte [Ustvarjanje vsebnika](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="854e4-110">To learn how to create a container, see [Create a container](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="854e4-111">Dajte svojemu cilju prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="854e4-111">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="854e4-112">Izberite **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="854e4-112">Select **Next**.</span></span>

1. <span data-ttu-id="854e4-113">Izberite polje poleg vsake entitete, ki jo želite izvoziti na ta cilj.</span><span class="sxs-lookup"><span data-stu-id="854e4-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="854e4-114">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="854e4-114">Select **Save**.</span></span>

<span data-ttu-id="854e4-115">Izvoženi podatki so shranjeni v vsebniku za shrambo zbirke dvojiških podatkov Azure, ki ste ga konfigurirali.</span><span class="sxs-lookup"><span data-stu-id="854e4-115">Exported data is stored in the Azure Blob storage container you configured.</span></span> <span data-ttu-id="854e4-116">Naslednje poti map se samodejno ustvarijo v vašem vsebniku:</span><span class="sxs-lookup"><span data-stu-id="854e4-116">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="854e4-117">Za entitete vira in entitete, ki jih ustvari sistem: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="854e4-117">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="854e4-118">Primer: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="854e4-118">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="854e4-119">Model.json za izvožene entitete bo na ravni %ExportDestinationName%</span><span class="sxs-lookup"><span data-stu-id="854e4-119">The model.json for the exported entities will reside at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="854e4-120">Primer: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="854e4-120">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

## <a name="export-the-data"></a><span data-ttu-id="854e4-121">Izvoz podatkov</span><span class="sxs-lookup"><span data-stu-id="854e4-121">Export the data</span></span>

<span data-ttu-id="854e4-122">Lahko [izvozite podatke na zahtevo](/export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="854e4-122">You can [export data on demand](/export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="854e4-123">Izvoz se bo zagnal tudi z vsakim [načrtovanim osveževanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="854e4-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
