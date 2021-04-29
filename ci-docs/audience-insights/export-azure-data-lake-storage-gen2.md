---
title: Izvoz podatkov Customer Insights v storitev Azure Data Lake Storage Gen2
description: Preberite o konfiguraciji povezave s storitvijo Azure Data Lake Storage Gen2.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760071"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="e5765-103">Nastavitev povezave s storitvijo Azure Data Lake Storage Gen2 (predogledna različica)</span><span class="sxs-lookup"><span data-stu-id="e5765-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="e5765-104">Odprite razdelek **Skrbnik** > **Povezave**.</span><span class="sxs-lookup"><span data-stu-id="e5765-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e5765-105">Izberite **Dodajanje povezave** in izberite **Azure Data Lake Gen 2** za konfiguracijo povezave.</span><span class="sxs-lookup"><span data-stu-id="e5765-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="e5765-106">Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="e5765-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e5765-107">Ime in vrsta povezave opisujeta to povezavo.</span><span class="sxs-lookup"><span data-stu-id="e5765-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e5765-108">Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.</span><span class="sxs-lookup"><span data-stu-id="e5765-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e5765-109">Izberite, kdo lahko uporablja to povezavo.</span><span class="sxs-lookup"><span data-stu-id="e5765-109">Choose who can use this connection.</span></span> <span data-ttu-id="e5765-110">Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki.</span><span class="sxs-lookup"><span data-stu-id="e5765-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e5765-111">Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e5765-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e5765-112">Vnesite **ime računa**, **ključ računa** in **vsebnik** za storitev Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="e5765-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="e5765-113">Če želite izvedeti, kako ustvariti račun za shrambo za uporabo v storitvi Azure Data Lake Storage Gen2, glejte razdelek [Ustvarjanje računa za shrambo](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="e5765-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="e5765-114">Za več informacij imenu računa in ključa računa shrambe Azure Data Lake Gen2 glejte [Upravljanje nastavitev računa shrambe v portalu Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="e5765-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="e5765-115">Izberite možnost **Shrani**, da dokončate povezavo.</span><span class="sxs-lookup"><span data-stu-id="e5765-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="e5765-116">Konfiguriranje izvoza</span><span class="sxs-lookup"><span data-stu-id="e5765-116">Configure an export</span></span>

<span data-ttu-id="e5765-117">Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave.</span><span class="sxs-lookup"><span data-stu-id="e5765-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e5765-118">Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e5765-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e5765-119">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="e5765-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e5765-120">Izberite možnost **Dodaj izvoz** za ustvarjanje novega izvoza.</span><span class="sxs-lookup"><span data-stu-id="e5765-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="e5765-121">V polju **Povezava za izvoz** izberite povezavo v razdelku **Azure Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="e5765-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="e5765-122">Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.</span><span class="sxs-lookup"><span data-stu-id="e5765-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e5765-123">Izberite polje poleg vsake entitete, ki jo želite izvoziti na ta cilj.</span><span class="sxs-lookup"><span data-stu-id="e5765-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="e5765-124">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="e5765-124">Select **Save**.</span></span>

<span data-ttu-id="e5765-125">S shranjevanjem izvoza se ta ne zažene takoj.</span><span class="sxs-lookup"><span data-stu-id="e5765-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e5765-126">Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e5765-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e5765-127">Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e5765-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="e5765-128">Izvoženi podatki so shranjeni v vsebniku za shrambo Azure Data Lake Gen 2, ki ste ga konfigurirali.</span><span class="sxs-lookup"><span data-stu-id="e5765-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
