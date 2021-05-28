---
title: Izvoz podatkov iz rešitve Customer Insights v storitev Azure Synapse Analytics
description: Preberite, kako konfigurirati povezavo s storitvijo Azure Synapse Analytics.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977397"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="6e413-103">Izvoz podatkov v storitev Azure Synapse Analytics (predogledna različica)</span><span class="sxs-lookup"><span data-stu-id="6e413-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="6e413-104">Azure Synapse je analitična storitev, ki pospeši čas za vpogled v podatkovna skladišča in sisteme masovnih podatkov.</span><span class="sxs-lookup"><span data-stu-id="6e413-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="6e413-105">Podatke iz rešitve Customer Insights lahko uvozite in uporabite v storitvi [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span><span class="sxs-lookup"><span data-stu-id="6e413-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6e413-106">Zahteve</span><span class="sxs-lookup"><span data-stu-id="6e413-106">Prerequisites</span></span>

<span data-ttu-id="6e413-107">Za konfiguriranje povezave iz rešitve Customer Insights v storitev Azure Synapse morajo biti izpolnjene naslednje zahteve.</span><span class="sxs-lookup"><span data-stu-id="6e413-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="6e413-108">Prepričajte se, da ste nastavili vse **dodelitve vlog**, kot je opisano.</span><span class="sxs-lookup"><span data-stu-id="6e413-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="6e413-109">Zahteve v rešitvi Customer Insights</span><span class="sxs-lookup"><span data-stu-id="6e413-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="6e413-110">Imeti morate vlogo **skrbnika** v vpogledih v občinstvo.</span><span class="sxs-lookup"><span data-stu-id="6e413-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="6e413-111">Preberite več o [nastavitvi uporabniških dovoljenj v vpogledih v občinstvo](permissions.md#assign-roles-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="6e413-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="6e413-112">V storitvi Azure:</span><span class="sxs-lookup"><span data-stu-id="6e413-112">In Azure:</span></span> 

- <span data-ttu-id="6e413-113">Aktivna naročnina na Azure.</span><span class="sxs-lookup"><span data-stu-id="6e413-113">An active Azure subscription.</span></span>

- <span data-ttu-id="6e413-114">Če uporabljate nov račun za Azure Data Lake Storage Gen2, *glavno ime storitve za vpoglede v občinstvo* potrebuje dovoljenja **sodelujočega za podatke shrambe zbirke dvojiških podatkov**.</span><span class="sxs-lookup"><span data-stu-id="6e413-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="6e413-115">Preberite več o [povezovanju z računom za Azure Data Lake Storage Gen2 z glavnim imenom storitve Azure za vpoglede v občinstvo](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="6e413-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="6e413-116">Data Lake Storage Gen2 **mora imeti** omogočen [hierarhičen imenski prostor](/azure/storage/blobs/data-lake-storage-namespace).</span><span class="sxs-lookup"><span data-stu-id="6e413-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="6e413-117">V skupini virov se nahaja delovni prostor Azure Synapse, *glavno ime storitve* in *uporabnik za vpoglede v občinstvo* pa morajo imeti dodeljena vsaj dovoljenja za **branje**.</span><span class="sxs-lookup"><span data-stu-id="6e413-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="6e413-118">Če želite več informacij, glejte razdelek [Dodelitev vlog Azure s portalom Azure](/azure/role-based-access-control/role-assignments-portal).</span><span class="sxs-lookup"><span data-stu-id="6e413-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="6e413-119">*Uporabnik* potrebuje dovoljenje **sodelujočega v shrambi zbirke dvojiških podatkov** za račun Azure Data Lake Storage Gen2, kjer se nahajajo podatki, ki so povezani z delovnim prostorom Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="6e413-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="6e413-120">Preberite več o [uporabi portala Azure za dodelitev vloge Azure za dostop do zbirke dvojiških podatkov in podatkov o čakalni vrsti](/azure/storage/common/storage-auth-aad-rbac-portal) ter [sodelujočem v shrambi zbirke dvojiških podatkov](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="6e413-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="6e413-121">*[Upravljana identiteta za delovni prostor Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* potrebuje dovoljenje **sodelujočega v shrambi zbirke dvojiških podatkov** za račun Azure Data Lake Storage Gen2, kjer se nahajajo podatki, ki so povezani z delovnim prostorom Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="6e413-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="6e413-122">Preberite več o [uporabi portala Azure za dodelitev vloge Azure za dostop do zbirke dvojiških podatkov in podatkov o čakalni vrsti](/azure/storage/common/storage-auth-aad-rbac-portal) ter [sodelujočem v shrambi zbirke dvojiških podatkov](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="6e413-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="6e413-123">*Glavno ime storitve za vpoglede v občinstvo* potrebuje v delovnem prostoru Azure Synapse dodeljeno vlogo **skrbnika za Synapse**.</span><span class="sxs-lookup"><span data-stu-id="6e413-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="6e413-124">Če želite več informacij, glejte razdelek [Kako nastaviti nadzor dostopa za delovni prostor Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).</span><span class="sxs-lookup"><span data-stu-id="6e413-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="6e413-125">Nastavitev povezave in izvoz v storitev Azure Synapse</span><span class="sxs-lookup"><span data-stu-id="6e413-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="6e413-126">Konfiguriranje povezave</span><span class="sxs-lookup"><span data-stu-id="6e413-126">Configure a connection</span></span>

1. <span data-ttu-id="6e413-127">Odprite razdelek **Skrbnik** > **Povezave**.</span><span class="sxs-lookup"><span data-stu-id="6e413-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="6e413-128">Za konfiguracijo izberite možnost **Dodaj povezavo** in izberite **Azure Synapse Analytics** ali pa izberite možnost **Nastavitev** na ploščici **Azure Synapse Analytics**.</span><span class="sxs-lookup"><span data-stu-id="6e413-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="6e413-129">Svoji povezavi dodelite prepoznavno ime v polju Prikazno ime.</span><span class="sxs-lookup"><span data-stu-id="6e413-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="6e413-130">Ime in vrsta povezave opisujeta to povezavo.</span><span class="sxs-lookup"><span data-stu-id="6e413-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="6e413-131">Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.</span><span class="sxs-lookup"><span data-stu-id="6e413-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="6e413-132">Izberite, kdo lahko uporablja to povezavo.</span><span class="sxs-lookup"><span data-stu-id="6e413-132">Choose who can use this connection.</span></span> <span data-ttu-id="6e413-133">Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki.</span><span class="sxs-lookup"><span data-stu-id="6e413-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="6e413-134">Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="6e413-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="6e413-135">Izberite ali poiščite naročnino, v kateri želite uporabiti podatke Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="6e413-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="6e413-136">Takoj ko je naročnina izbrana, lahko izberete tudi **Delovni prostor**, **Račun za shranjevanje** in **Vsebnik**.</span><span class="sxs-lookup"><span data-stu-id="6e413-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="6e413-137">Izberite možnost **Shrani**, da shranite povezavo.</span><span class="sxs-lookup"><span data-stu-id="6e413-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="6e413-138">Konfiguriranje izvoza</span><span class="sxs-lookup"><span data-stu-id="6e413-138">Configure an export</span></span>

<span data-ttu-id="6e413-139">Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave.</span><span class="sxs-lookup"><span data-stu-id="6e413-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="6e413-140">Če želite več informacij, glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="6e413-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="6e413-141">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="6e413-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6e413-142">Izberite možnost **Dodaj izvoz** za ustvarjanje novega izvoza.</span><span class="sxs-lookup"><span data-stu-id="6e413-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="6e413-143">V polju **Povezava za izvoz** izberite povezavo v razdelku **Azure Synapse Analytics**.</span><span class="sxs-lookup"><span data-stu-id="6e413-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="6e413-144">Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna [povezava](connections.md).</span><span class="sxs-lookup"><span data-stu-id="6e413-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="6e413-145">Zagotovite prepoznavno **prikazno ime** za vaš izvoz in **ime baze podatkov**.</span><span class="sxs-lookup"><span data-stu-id="6e413-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="6e413-146">Izberite, katere entitete želite izvoziti v storitev Azure Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="6e413-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="6e413-147">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="6e413-147">Select **Save**.</span></span>

<span data-ttu-id="6e413-148">S shranjevanjem izvoza se ta ne zažene takoj.</span><span class="sxs-lookup"><span data-stu-id="6e413-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="6e413-149">Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6e413-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="6e413-150">Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="6e413-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="6e413-151">Posodobitev izvoza</span><span class="sxs-lookup"><span data-stu-id="6e413-151">Update an export</span></span>

1. <span data-ttu-id="6e413-152">Odprite razdelek **Podatki** > **Izvozi**.</span><span class="sxs-lookup"><span data-stu-id="6e413-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6e413-153">Izberite možnost **Uredi** za izvoz, ki ga želite posodobiti.</span><span class="sxs-lookup"><span data-stu-id="6e413-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="6e413-154">**Dodajte** ali **odstranite** entitete iz izbora.</span><span class="sxs-lookup"><span data-stu-id="6e413-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="6e413-155">Če iz izbora odstranite entitete, se te ne izbrišejo iz baze podatkov Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="6e413-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="6e413-156">Vendar prihodnje osvežitve podatkov ne bodo posodobile odstranjenih entitet v tej bazi podatkov.</span><span class="sxs-lookup"><span data-stu-id="6e413-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="6e413-157">**Spreminjanje imena baze podatkov** ustvari novo bazo podatkov Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="6e413-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="6e413-158">Baza podatkov z imenom, ki je bilo konfigurirano prej, v prihodnjih osvežitvah ne bo prejemala nobenih posodobitev.</span><span class="sxs-lookup"><span data-stu-id="6e413-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>
