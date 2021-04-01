---
title: Povezovanje računa Azure Data Lake Storage Gen2 z glavnim imenom storitve
description: Uporabite glavno ime storitve Azure za vpoglede v občinstvo, da se povežete z lastnim jezerom podatkov, ko ga priložite vpogledom v občinstvo.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c670b0065a2833a6dc311d9e86d2b351140382ce
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596519"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="de57b-103">Povezovanje računa Azure Data Lake Storage Gen2 z glavnim imenom storitve Azure za vpoglede v občinstvo</span><span class="sxs-lookup"><span data-stu-id="de57b-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="de57b-104">Avtomatizirana orodja, ki uporabljajo storitve Azure, bi morala imeti vedno omejena dovoljenja.</span><span class="sxs-lookup"><span data-stu-id="de57b-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="de57b-105">Namesto da bi se v aplikacije vpisali kot uporabnik s vsemi pravicami, Azure ponuja glavno ime storitve.</span><span class="sxs-lookup"><span data-stu-id="de57b-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="de57b-106">Preberite nadaljevanje, če želite izvedeti, kako povezati vpogled v občinstvo z računom Azure Data Lake Storage Gen2, ki uporablja glavno ime storitve Azure namesto ključev računa za shranjevanje.</span><span class="sxs-lookup"><span data-stu-id="de57b-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="de57b-107">Z glavnim imenom storitve lahko varno [dodate ali uredite mapo Common Data Model kot vir podatkov](connect-common-data-model.md) ali [ustvarite novo oz. posodobite obstoječe okolje](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="de57b-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="de57b-108">Račun za shrambo Azure Data Lake Gen2, ki namerava uporabiti glavno ime storitve, mora imeti [omogočeno funkcijo hierarhičnega imenskega prostora (HNS)](/azure/storage/blobs/data-lake-storage-namespace).</span><span class="sxs-lookup"><span data-stu-id="de57b-108">The Azure Data Lake Gen2 storage account that intends to use the service principal must have [Hierarchical Name Space (HNS) enabled](/azure/storage/blobs/data-lake-storage-namespace).</span></span>
> - <span data-ttu-id="de57b-109">Za izdelavo glavnega imena storitve potrebujete skrbniška dovoljenja za naročnino Azure.</span><span class="sxs-lookup"><span data-stu-id="de57b-109">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="de57b-110">Ustvarjanje glavnega imena storitve Azure za vpoglede v občinstvo</span><span class="sxs-lookup"><span data-stu-id="de57b-110">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="de57b-111">Preden ustvarite novega glavnega imena storitve za vpoglede v občinstvo, preverite, ali ta že obstaja v vaši organizaciji.</span><span class="sxs-lookup"><span data-stu-id="de57b-111">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="de57b-112">Poiščite obstoječega glavnega imena storitve</span><span class="sxs-lookup"><span data-stu-id="de57b-112">Look for an existing service principal</span></span>

1. <span data-ttu-id="de57b-113">Odprite [skrbniški portal Azure](https://portal.azure.com) in se vpišite v svojo organizacijo.</span><span class="sxs-lookup"><span data-stu-id="de57b-113">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="de57b-114">Izberite **Azure Active Directory** pri storitvah Azure.</span><span class="sxs-lookup"><span data-stu-id="de57b-114">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="de57b-115">Pod možnostjo **Upravljanje** izberite **Aplikacije za podjetja**.</span><span class="sxs-lookup"><span data-stu-id="de57b-115">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="de57b-116">Poiščite ID lastne aplikacije za vpoglede v občinstvo `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` ali ime `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="de57b-116">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="de57b-117">Če najdete ustrezen zapis, to pomeni, da glavno ime storitve za vpoglede v občinstvo obstaja.</span><span class="sxs-lookup"><span data-stu-id="de57b-117">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="de57b-118">Ni vam ga treba ustvariti znova.</span><span class="sxs-lookup"><span data-stu-id="de57b-118">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Posnetek zaslona, ki prikazuje obstoječe glavno ime storitve.":::
   
6. <span data-ttu-id="de57b-120">Če se ne vrnejo nobeni rezultati, ustvarite novo glavno ime storitve.</span><span class="sxs-lookup"><span data-stu-id="de57b-120">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="de57b-121">Ustvari novo glavno ime storitve</span><span class="sxs-lookup"><span data-stu-id="de57b-121">Create a new service principal</span></span>

1. <span data-ttu-id="de57b-122">Namestite najnovejšo različico **Azure Active Directory PowerShell for Graph**.</span><span class="sxs-lookup"><span data-stu-id="de57b-122">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="de57b-123">Za več informacij glejte [Namestitev storitve Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="de57b-123">For more information, see [Install Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="de57b-124">V računalniku izberite tipko Windows na tipkovnici in poiščite možnosti **Windows PowerShell** in **Zaženi kot skrbnik**.</span><span class="sxs-lookup"><span data-stu-id="de57b-124">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="de57b-125">V oknu PowerShell, ki se odpre, vnesite `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="de57b-125">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="de57b-126">Ustvarite glavno ime storitve za vpoglede v občinstvo z modulom Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="de57b-126">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="de57b-127">V oknu PowerShell vnesite `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="de57b-127">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="de57b-128">Zamenjajte vaš ID najemnika z dejanskim ID-jem vašega najemnika, kjer želite ustvariti glavno ime storitve.</span><span class="sxs-lookup"><span data-stu-id="de57b-128">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="de57b-129">Parameter z imenom okolja `AzureEnvironmentName` je izbiren.</span><span class="sxs-lookup"><span data-stu-id="de57b-129">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="de57b-130">Vnesite `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="de57b-130">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="de57b-131">Ta ukaz ustvari glavno ime storitve za vpoglede v občinstvo izbranega najemnika.</span><span class="sxs-lookup"><span data-stu-id="de57b-131">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="de57b-132">Dodelite dovoljenja glavnemu imenu storitve za dostop do računa za shranjevanje</span><span class="sxs-lookup"><span data-stu-id="de57b-132">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="de57b-133">Pojdite na portal Azure, da dodelite dovoljenja glavnemu imenu storitve za račun za shranjevanje, ki ga želite uporabiti pri vpogledih v občinstvo.</span><span class="sxs-lookup"><span data-stu-id="de57b-133">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="de57b-134">Odprite [skrbniški portal Azure](https://portal.azure.com) in se vpišite v svojo organizacijo.</span><span class="sxs-lookup"><span data-stu-id="de57b-134">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="de57b-135">Odprite račun za shranjevanje, do katerega želite, da ima glavno ime storitve dostop za vpoglede v občinstvo.</span><span class="sxs-lookup"><span data-stu-id="de57b-135">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="de57b-136">Izberite **Nadzor dostopa (IAM)** v podoknu za krmarjenje in izberite **Dodaj** > **Dodaj dodelitev vloge**.</span><span class="sxs-lookup"><span data-stu-id="de57b-136">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Posnetek zaslona, ki prikazuje portal Azure med dodajanjem dodelitve vloge.":::
   
1. <span data-ttu-id="de57b-138">V podoknu **Dodaj dodelitev vloge** nastavite naslednje lastnosti:</span><span class="sxs-lookup"><span data-stu-id="de57b-138">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="de57b-139">Vloga: *Sodelujoči v shrambi zbirke dvojiških podatkov*</span><span class="sxs-lookup"><span data-stu-id="de57b-139">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="de57b-140">Dodeli dostop za: *uporabnik, skupina ali glavno ime storitve*</span><span class="sxs-lookup"><span data-stu-id="de57b-140">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="de57b-141">Izberite: *Dynamics 365 AI for Customer Insights* ([glavno ime storitve, ki ste ga ustvarili](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="de57b-141">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="de57b-142">Izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="de57b-142">Select **Save**.</span></span>

<span data-ttu-id="de57b-143">Uvedba sprememb lahko traja do 15 minut.</span><span class="sxs-lookup"><span data-stu-id="de57b-143">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="de57b-144">V priponko računa za shranjevanje za vpoglede v občinstvo vnesite ID vira Azure ali podrobnosti o naročnini za Azure.</span><span class="sxs-lookup"><span data-stu-id="de57b-144">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="de57b-145">Priložite račun za shrambo Azure Data Lake v vpoglede v občinstvo, da [shranite izhodne podatke](manage-environments.md) ali to [uporabite kot vir podatkov](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="de57b-145">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="de57b-146">Če izberete možnost Azure Data Lake, lahko izbirate med pristopom na podlagi virov ali na podlagi naročnine.</span><span class="sxs-lookup"><span data-stu-id="de57b-146">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="de57b-147">Upoštevajte naslednja navodila, da posredujete zahtevane podatke o izbranem pristopu.</span><span class="sxs-lookup"><span data-stu-id="de57b-147">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resource-based-storage-account-connection"></a><span data-ttu-id="de57b-148">Povezava računa za shrambo na podlagi vira</span><span class="sxs-lookup"><span data-stu-id="de57b-148">Resource-based storage account connection</span></span>

1. <span data-ttu-id="de57b-149">Odprite [skrbniški portal Azure](https://portal.azure.com), se vpišite v svojo naročnino in odprite račun za shranjevanje.</span><span class="sxs-lookup"><span data-stu-id="de57b-149">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="de57b-150">Odprite **Nastavitve** > **Lastnosti** v podoknu za krmarjenje.</span><span class="sxs-lookup"><span data-stu-id="de57b-150">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="de57b-151">Kopirajte vrednost ID-ja vira računa za shranjevanje.</span><span class="sxs-lookup"><span data-stu-id="de57b-151">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopirajte ID vira računa za shranjevanje.":::

1. <span data-ttu-id="de57b-153">Pri vpogledih v občinstvo vstavite ID vira v polje vira, prikazano na zaslonu povezave z računom za shranjevanje.</span><span class="sxs-lookup"><span data-stu-id="de57b-153">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Vnesite podatke za ID vira računa za shranjevanje.":::   
   
1. <span data-ttu-id="de57b-155">Nadaljujte s preostalimi koraki pri vpogledih v občinstvo, da pripnete račun za shranjevanje.</span><span class="sxs-lookup"><span data-stu-id="de57b-155">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="de57b-156">Povezava računa za shranjevanje na podlagi naročnine</span><span class="sxs-lookup"><span data-stu-id="de57b-156">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="de57b-157">Odprite [skrbniški portal Azure](https://portal.azure.com), se vpišite v svojo naročnino in odprite račun za shranjevanje.</span><span class="sxs-lookup"><span data-stu-id="de57b-157">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="de57b-158">Odprite **Nastavitve** > **Lastnosti** v podoknu za krmarjenje.</span><span class="sxs-lookup"><span data-stu-id="de57b-158">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="de57b-159">Preglejte **naročnino**, **skupino virov** in **ime** računa za shranjevanje, da se prepričate, da ste izbrali prave vrednosti pri vpogledih v občinstvo.</span><span class="sxs-lookup"><span data-stu-id="de57b-159">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="de57b-160">Pri vpogledih v občinstvo izberite vrednosti ali ustrezna polja, ko pripnete račun za shranjevanje.</span><span class="sxs-lookup"><span data-stu-id="de57b-160">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>
   
1. <span data-ttu-id="de57b-161">Nadaljujte s preostalimi koraki pri vpogledih v občinstvo, da pripnete račun za shranjevanje.</span><span class="sxs-lookup"><span data-stu-id="de57b-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]