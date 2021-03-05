---
title: Povezovanje podatkov Common Data Model z računom Azure Data Lake
description: Delo s podatki Common Data Model z uporabo storitve Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 247e4d9c47ff2373065ebf3c6d554323e45a120b
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267880"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="e08b8-103">Povezava z mapo Common Data Model z uporabo računa Azure Data Lake</span><span class="sxs-lookup"><span data-stu-id="e08b8-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="e08b8-104">V tem članku so informacije o vključitvi podatkov iz mape Common Data Model z vašim računom Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="e08b8-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="e08b8-105">Pomembni premisleki</span><span class="sxs-lookup"><span data-stu-id="e08b8-105">Important considerations</span></span>

- <span data-ttu-id="e08b8-106">Podatki v vaši shrambi Azure Data Lake morajo upoštevati standard Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="e08b8-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="e08b8-107">Druge oblike zapisa trenutno niso podprte.</span><span class="sxs-lookup"><span data-stu-id="e08b8-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="e08b8-108">Vključevanje podatkov podpira zgolj račune za shrambo Azure Data Lake *Gen2*.</span><span class="sxs-lookup"><span data-stu-id="e08b8-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="e08b8-109">Računov za shrambo Azure Data Lake Gen1 ne morete uporabljati za vključevanje podatkov.</span><span class="sxs-lookup"><span data-stu-id="e08b8-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="e08b8-110">Če želite preveriti pristnost z glavnim imenom storitve Azure, preverite, ali je konfiguriran v najemniku.</span><span class="sxs-lookup"><span data-stu-id="e08b8-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="e08b8-111">Za več informacij glejte [Povezovanje vpogledov v občinstvo in računa Azure Data Lake Storage Gen2 z glavnim imenom storitve Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="e08b8-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="e08b8-112">Azure Data Lake, ki ga želite povezati in od katerega želite vključiti podatke, mora biti v isti regiji Azure kot okolje Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e08b8-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="e08b8-113">Povezave do mape Common Data Model iz jezera podatkov v drugi regiji Azure niso podprte.</span><span class="sxs-lookup"><span data-stu-id="e08b8-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="e08b8-114">Če želite ugotoviti območje Azure v okolju, izberite **Skrbnik** > **Sistem** > **Vizitka** v razdelku vpogledov v občinstvo.</span><span class="sxs-lookup"><span data-stu-id="e08b8-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="e08b8-115">Podatki, shranjeni v spletnih storitvah, se lahko shranijo na drugem mestu kot na mestu, kjer se podatki obdelujejo ali shranjujejo v storitvi Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e08b8-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="e08b8-116"> Z uvažanjem podatkov ali povezovanjem s podatki, shranjenimi v spletnih storitvah, se strinjate, da se podatki lahko prenesejo in shranijo v storitvi Dynamics 365 Customer Insights. [Več o tem preberite v Microsoftovem središču zaupanja.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="e08b8-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="e08b8-117">Vzpostavitev povezave z mapo Common Data Model</span><span class="sxs-lookup"><span data-stu-id="e08b8-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="e08b8-118">Pri vpogledih v občinstvo izberite **Podatki** > **Viri podatkov**.</span><span class="sxs-lookup"><span data-stu-id="e08b8-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="e08b8-119">Izberite **Dodaj vir podatkov**.</span><span class="sxs-lookup"><span data-stu-id="e08b8-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="e08b8-120">Izberite **Vzpostavitev povezave z mapo Common Data Model**, vnesite **ime** za vir podatkov in izberite **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="e08b8-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span> <span data-ttu-id="e08b8-121">Smernice za poimenovanje:</span><span class="sxs-lookup"><span data-stu-id="e08b8-121">Name guidelines:</span></span> 
   - <span data-ttu-id="e08b8-122">Začnite s črko.</span><span class="sxs-lookup"><span data-stu-id="e08b8-122">Start with a letter.</span></span>
   - <span data-ttu-id="e08b8-123">Uporabljajte samo črke in številke.</span><span class="sxs-lookup"><span data-stu-id="e08b8-123">Use letters and numbers only.</span></span> <span data-ttu-id="e08b8-124">Posebni znaki in presledki niso dovoljeni.</span><span class="sxs-lookup"><span data-stu-id="e08b8-124">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="e08b8-125">Uporabite od 3 do 64 znakov.</span><span class="sxs-lookup"><span data-stu-id="e08b8-125">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="e08b8-126">Izbirate lahko med možnostjo, ki temelji na viru, in možnostjo preverjanja pristnosti, ki temelji na naročnini.</span><span class="sxs-lookup"><span data-stu-id="e08b8-126">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="e08b8-127">Za več informacij glejte [Povezovanje vpogledov v občinstvo in računa Azure Data Lake Storage Gen2 z glavnim imenom storitve Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="e08b8-127">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="e08b8-128">Vnesite podatke **vsebnika** in izberite **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="e08b8-128">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e08b8-129">![Pogovorno okno za vnos novih podrobnosti povezave za Azure Data Lake](media/enter-new-storage-details.png)
   > </span><span class="sxs-lookup"><span data-stu-id="e08b8-129">![Dialog box to enter new connection details for Azure Data Lake](media/enter-new-storage-details.png)
   > </span></span>[!NOTE]
<span data-ttu-id="e08b8-130">Za povezavo in ustvarjanje vira podatkov potrebujete eno od naslednjih vlog bodisi zgoraj omenjenemu vsebniku ali računu za shranjevanje:</span><span class="sxs-lookup"><span data-stu-id="e08b8-130">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="e08b8-131">Bralnik podatkov shrambe zbirke dvojiških podatkov</span><span class="sxs-lookup"><span data-stu-id="e08b8-131">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="e08b8-132">Lastnik podatkov shrambe zbirke dvojiških podatkov</span><span class="sxs-lookup"><span data-stu-id="e08b8-132">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="e08b8-133">Sodelujoči v shrambi zbirke dvojiških podatkov</span><span class="sxs-lookup"><span data-stu-id="e08b8-133">Storage Blob Data Contributor</span></span>

1. <span data-ttu-id="e08b8-134">V pogovornem oknu **Izberite mapo Common Data Model** izberite datoteko model.json ali manifest.json, iz katere želite uvoziti podatke, in izberite možnost **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="e08b8-134">In the **Select a Common Data Model folder** dialog, select the model.json or manifest.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="e08b8-135">Vsaka datoteka model.json ali manifest.json, povezana z drugim virom podatkov v okolju, ne bo prikazana na seznamu.</span><span class="sxs-lookup"><span data-stu-id="e08b8-135">Any model.json or manifest.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="e08b8-136">V izbrani datoteki model.json ali manifest.json boste prejeli seznam razpoložljivih entitet.</span><span class="sxs-lookup"><span data-stu-id="e08b8-136">You'll get a list of available entities in the selected model.json or manifest.json file.</span></span> <span data-ttu-id="e08b8-137">Oglejte si ga in izberite možnost s seznama razpoložljivih entitet, nato pa izberite možnost **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="e08b8-137">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="e08b8-138">Vse izbrane entitete bodo vključene iz novega vira podatkov.</span><span class="sxs-lookup"><span data-stu-id="e08b8-138">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e08b8-139">![Pogovorno okno s seznamom entitet iz datoteke model.json](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="e08b8-139">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="e08b8-140">Navedite, za katere podatkovne entitete želite omogočiti profiliranje podatkov, in izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="e08b8-140">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="e08b8-141">Profiliranje podatkov omogoča analitiko in druge zmogljivosti.</span><span class="sxs-lookup"><span data-stu-id="e08b8-141">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="e08b8-142">Izberete lahko celotno entiteto, pri čemer se izbere vse atribute iz entitete, ali izberete določene atribute po svoji izbiri.</span><span class="sxs-lookup"><span data-stu-id="e08b8-142">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="e08b8-143">Privzeto nobena entiteta ni omogočena za profiliranje podatkov.</span><span class="sxs-lookup"><span data-stu-id="e08b8-143">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e08b8-144">![Pogovorno okno, ki prikazuje profiliranje podatkov](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="e08b8-144">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="e08b8-145">Ko shranite svoje nastavitve, se odpre stran **Viri podatkov**.</span><span class="sxs-lookup"><span data-stu-id="e08b8-145">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="e08b8-146">Zdaj bi se vam morala prikazati povezava mape Common Data Model kot vir podatkov.</span><span class="sxs-lookup"><span data-stu-id="e08b8-146">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="e08b8-147">Datoteka model.json ali manifest.json se lahko v istem okolju poveže samo z enim virom podatkov.</span><span class="sxs-lookup"><span data-stu-id="e08b8-147">A model.json file or manifest.json can only associate with one data source in the same environment.</span></span> <span data-ttu-id="e08b8-148">Vendar pa je isto datoteko model.json ali ali manifest.json mogoče uporabiti za vire podatkov v več okoljih.</span><span class="sxs-lookup"><span data-stu-id="e08b8-148">However, the same model.json or manifest.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="e08b8-149">Urejanje vira podatkov mape Common Data Model</span><span class="sxs-lookup"><span data-stu-id="e08b8-149">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="e08b8-150">Lahko posodobite ključ za dostop za račun za shrambo, ki vsebuje mapo Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="e08b8-150">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="e08b8-151">Prav tako lahko spremenite datoteko model.json ali manifest.json.</span><span class="sxs-lookup"><span data-stu-id="e08b8-151">You may also change the model.json or manifest.json file.</span></span> <span data-ttu-id="e08b8-152">Če se želite povezati z drugim vsebnikom iz računa za shrambo ali spremeniti ime računa, [ustvarite novo povezavo vira podatkov](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="e08b8-152">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="e08b8-153">Pri vpogledih v občinstvo izberite **Podatki** > **Viri podatkov**.</span><span class="sxs-lookup"><span data-stu-id="e08b8-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="e08b8-154">Izberite tri pike poleg vira podatkov, ki ga želite posodobiti.</span><span class="sxs-lookup"><span data-stu-id="e08b8-154">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="e08b8-155">Na seznamu izberite možnost **Uredi**.</span><span class="sxs-lookup"><span data-stu-id="e08b8-155">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="e08b8-156">Po želji posodobite **Ključ za dostop** in izberite **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="e08b8-156">Optionally, update the **Access key** and select **Next**.</span></span>

   ![Pogovorno okno za urejanje in posodobitev ključa za dostop za obstoječi vir podatkov](media/edit-access-key.png)

5. <span data-ttu-id="e08b8-158">Po želji lahko posodobitev opravite prek povezave s ključem kupca s povezavo, ki temelji na viru ali naročnini.</span><span class="sxs-lookup"><span data-stu-id="e08b8-158">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="e08b8-159">Za več informacij glejte [Povezovanje vpogledov v občinstvo in računa Azure Data Lake Storage Gen2 z glavnim imenom storitve Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="e08b8-159">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="e08b8-160">Ob posodobitvi povezave ne morete spremeniti podatkov **vsebnika**.</span><span class="sxs-lookup"><span data-stu-id="e08b8-160">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]

   > ![Pogovorno okno za vnos podrobnosti povezave za Azure Data Lake v obstoječem računu za shrambo](media/enter-existing-storage-details.png)

   > [!NOTE]
   > <span data-ttu-id="e08b8-162">Za povezavo in ustvarjanje vira podatkov potrebujete eno od naslednjih vlog bodisi zgoraj omenjenemu vsebniku ali računu za shranjevanje:</span><span class="sxs-lookup"><span data-stu-id="e08b8-162">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="e08b8-163">Bralnik podatkov shrambe zbirke dvojiških podatkov</span><span class="sxs-lookup"><span data-stu-id="e08b8-163">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="e08b8-164">Lastnik podatkov shrambe zbirke dvojiških podatkov</span><span class="sxs-lookup"><span data-stu-id="e08b8-164">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="e08b8-165">Sodelujoči v shrambi zbirke dvojiških podatkov</span><span class="sxs-lookup"><span data-stu-id="e08b8-165">Storage Blob Data Contributo</span></span>


6. <span data-ttu-id="e08b8-166">Izberete lahko tudi drugo datoteko model.json ali manifest.json z drugim naborom entitet iz vsebnika.</span><span class="sxs-lookup"><span data-stu-id="e08b8-166">Optionally, choose a different model.json or manifest.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="e08b8-167">Po želji lahko izberete dodatne entitete za vključitev.</span><span class="sxs-lookup"><span data-stu-id="e08b8-167">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="e08b8-168">Če ne obstajajo odvisnosti, lahko tudi odstranite vse izbrane entitete.</span><span class="sxs-lookup"><span data-stu-id="e08b8-168">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="e08b8-169">Če obstajajo odvisnosti za obstoječo datoteko model.json ali manifest.json in nabor entitet, se prikaže sporočilo o napaki, vi pa ne morete izbrati druge datoteke model.json ali manifest.json.</span><span class="sxs-lookup"><span data-stu-id="e08b8-169">If there are dependencies on the existing model.json or manifest.json file and the set of entities, you'll see an error message and can't select a different model.json or manifest.json file.</span></span> <span data-ttu-id="e08b8-170">Odstranite te odvisnosti, preden spremenite datoteko model.json ali manifest.json oziroma ustvarite nov vir podatkov z datoteko model.json ali manifest.json, ki jo želite uporabiti, da se izognete odstranjevanju odvisnosti.</span><span class="sxs-lookup"><span data-stu-id="e08b8-170">Remove those dependencies before changing the model.json or manifest.json file or create a new data source with the model.json or manifest.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="e08b8-171">Po želji lahko izberete dodatne atribute ali entitete, da omogočite profiliranje podatkov ali onemogočite že izbrane.</span><span class="sxs-lookup"><span data-stu-id="e08b8-171">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   


[!INCLUDE[footer-include](../includes/footer-banner.md)]