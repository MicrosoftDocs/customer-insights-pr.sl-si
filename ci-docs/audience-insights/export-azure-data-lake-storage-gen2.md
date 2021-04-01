---
title: Izvoz podatkov Customer Insights v storitev Azure Data Lake Storage Gen2
description: Preberite o konfiguraciji povezave s storitvijo Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596660"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="cbd80-103">Povezovalnik za storitev Azure Data Lake Storage Gen2 (predogled)</span><span class="sxs-lookup"><span data-stu-id="cbd80-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="cbd80-104">Podatke iz storitve Customer Insights shranite v storitvi Azure Data Lake Storage Gen2 ali jih uporabite za prenos podatkov v druge aplikacije.</span><span class="sxs-lookup"><span data-stu-id="cbd80-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="cbd80-105">Konfiguriranje priključka za Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="cbd80-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="cbd80-106">Pri vpogledih v občinstvo izberite **Skrbnik** > **Cilji izvoza**.</span><span class="sxs-lookup"><span data-stu-id="cbd80-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="cbd80-107">Pod razdelkom **Azure Data Lake Storage Gen2** izberite možnost **Nastavi**.</span><span class="sxs-lookup"><span data-stu-id="cbd80-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="cbd80-108">Dajte svojemu cilju prepoznavno ime v polju **Prikazno ime**.</span><span class="sxs-lookup"><span data-stu-id="cbd80-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="cbd80-109">Vnesite **ime računa**, **ključ računa** in **vsebnik** za storitev Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="cbd80-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="cbd80-110">Če želite izvedeti, kako ustvariti račun za shrambo za uporabo v storitvi Azure Data Lake Storage Gen2, glejte razdelek [Ustvarjanje računa za shrambo](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="cbd80-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="cbd80-111">Če želite izvedeti več o iskanju imena in ključa računa za shrambo Azure Data Lake Gen2, glejte razdelek [Upravljanje nastavitev računa za shrambo na portalu Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="cbd80-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="cbd80-112">Izberite **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="cbd80-112">Select **Next**.</span></span>

1. <span data-ttu-id="cbd80-113">Izberite polje poleg vsake entitete, ki jo želite izvoziti na ta cilj.</span><span class="sxs-lookup"><span data-stu-id="cbd80-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="cbd80-114">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="cbd80-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="cbd80-115">Izvoz podatkov</span><span class="sxs-lookup"><span data-stu-id="cbd80-115">Export the data</span></span>

<span data-ttu-id="cbd80-116">Lahko [izvozite podatke na zahtevo](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="cbd80-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="cbd80-117">Izvoz se bo zagnal tudi z vsakim [načrtovanim osveževanjem](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="cbd80-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>