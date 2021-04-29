---
title: Izvoz podatkov Customer Insights v shrambo zbirke dvojiških podatkov Azure
description: Naučite se, kako konfigurirati povezavo in izvažati v shrambo zbirke dvojiških podatkov.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 294feff2f77c3756fbadb36c90aab430454f5967
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760255"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="204d7-103">Izvoz seznamov segmentov in drugih podatkov v shrambo zbirke dvojiških podatkov Azure (predogledna različica)</span><span class="sxs-lookup"><span data-stu-id="204d7-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="204d7-104">Podatke iz storitve Customer Insights shranite v shrambi zbirke dvojiških podatkov Azure ali jih uporabite za prenos podatkov v druge aplikacije.</span><span class="sxs-lookup"><span data-stu-id="204d7-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="204d7-105">Nastavitev povezave s shrambo zbirke dvojiških podatkov Azure</span><span class="sxs-lookup"><span data-stu-id="204d7-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="204d7-106">Odprite razdelek **Skrbnik** > **Povezave**.</span><span class="sxs-lookup"><span data-stu-id="204d7-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="204d7-107">Izberite **Dodajanje povezave** in izberite **Shramba zbirke dvojiških podatkov Azure** za konfiguracijo povezave.</span><span class="sxs-lookup"><span data-stu-id="204d7-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="204d7-108">Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="204d7-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="204d7-109">Ime in vrsta povezave opisujeta to povezavo.</span><span class="sxs-lookup"><span data-stu-id="204d7-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="204d7-110">Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.</span><span class="sxs-lookup"><span data-stu-id="204d7-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="204d7-111">Izberite, kdo lahko uporablja to povezavo.</span><span class="sxs-lookup"><span data-stu-id="204d7-111">Choose who can use this connection.</span></span> <span data-ttu-id="204d7-112">Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki.</span><span class="sxs-lookup"><span data-stu-id="204d7-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="204d7-113">Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="204d7-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="204d7-114">Vnesite **Ime računa**, **Ključ računa** in **Vsebnik** za svoj račun zbirke dvojiških podatkov.</span><span class="sxs-lookup"><span data-stu-id="204d7-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="204d7-115">Za več informacij o iskanju imena računa in ključa računa shrambe Blob glejte razdelek [Upravljanje nastavitev računa shrambe v portalu Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="204d7-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="204d7-116">Če želite izvedeti, kako ustvariti vsebnik, glejte [Ustvarjanje vsebnika](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="204d7-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="204d7-117">Izberite možnost **Shrani**, da dokončate povezavo.</span><span class="sxs-lookup"><span data-stu-id="204d7-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="204d7-118">Konfiguriranje izvoza</span><span class="sxs-lookup"><span data-stu-id="204d7-118">Configure an export</span></span>

<span data-ttu-id="204d7-119">Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave.</span><span class="sxs-lookup"><span data-stu-id="204d7-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="204d7-120">Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="204d7-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="204d7-121">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="204d7-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="204d7-122">Za ustvarjanje novega izvoza izberite **Dodaj cilj**.</span><span class="sxs-lookup"><span data-stu-id="204d7-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="204d7-123">V polju **Povezava za izvoz** izberite povezavo v razdelku Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="204d7-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="204d7-124">Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.</span><span class="sxs-lookup"><span data-stu-id="204d7-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="204d7-125">Izberite polje poleg vsake entitete, ki jo želite izvoziti na ta cilj.</span><span class="sxs-lookup"><span data-stu-id="204d7-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="204d7-126">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="204d7-126">Select **Save**.</span></span>

<span data-ttu-id="204d7-127">S shranjevanjem izvoza se ta ne zažene takoj.</span><span class="sxs-lookup"><span data-stu-id="204d7-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="204d7-128">Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="204d7-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="204d7-129">Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="204d7-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="204d7-130">Izvoženi podatki so shranjeni v vsebniku za shrambo zbirke dvojiških podatkov, ki ste ga konfigurirali.</span><span class="sxs-lookup"><span data-stu-id="204d7-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="204d7-131">Naslednje poti map se samodejno ustvarijo v vašem vsebniku:</span><span class="sxs-lookup"><span data-stu-id="204d7-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="204d7-132">Za entitete vira in entitete, ki jih ustvari sistem: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="204d7-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="204d7-133">Primer: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="204d7-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="204d7-134">Datoteka model.json za izvožene entitete bo na ravni %ExportDestinationName%</span><span class="sxs-lookup"><span data-stu-id="204d7-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="204d7-135">Primer: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="204d7-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
