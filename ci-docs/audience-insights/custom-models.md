---
title: Modeli strojnega učenja po meri | Microsoftovo gradivo
description: Uporabite modele po meri iz rešitve za strojno učenje Azure v aplikaciji Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34489faaecc5da1ce3dd68d799b3e0e0d9672ab7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267254"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="40499-103">Modeli strojnega učenja po meri</span><span class="sxs-lookup"><span data-stu-id="40499-103">Custom machine learning models</span></span>

<span data-ttu-id="40499-104">Možnost **Obveščanje** > **Modeli po meri** vam omogoča upravljanje potekov dela v modelih storitve Strojno učenje Azure.</span><span class="sxs-lookup"><span data-stu-id="40499-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="40499-105">Poteki dela vam pomagajo izbrati podatke, iz katerih želite ustvariti vpogled, in rezultate preslikati v vaše poenotene podatke o strankah.</span><span class="sxs-lookup"><span data-stu-id="40499-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="40499-106">Za več informacij o izdelavi modelov strojnega učenja po meri glejte razdelek [Uporaba modelov, ki temeljijo na strojnem učenju Azure](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="40499-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="40499-107">Odgovorna umetna inteligenca</span><span class="sxs-lookup"><span data-stu-id="40499-107">Responsible AI</span></span>

<span data-ttu-id="40499-108">Predvidevanja ponujajo zmogljivosti za ustvarjanje boljših izkušenj strank, izboljšanje poslovnih zmogljivosti in virov prihodkov.</span><span class="sxs-lookup"><span data-stu-id="40499-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="40499-109">Močno priporočamo, da vrednost predvidevanja uravnotežite z vplivom in pristranskostmi, ki bi jih lahko uvedli na etičen način.</span><span class="sxs-lookup"><span data-stu-id="40499-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="40499-110">Preberite več o tem, kako Microsoft [obravnava odgovorno ravnanje umetne inteligence](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="40499-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="40499-111">Preberete lahko tudi o [tehnikah in postopkih za odgovorno strojno učenje](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml), specifično za Strojno učenje Azure.</span><span class="sxs-lookup"><span data-stu-id="40499-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="40499-112">Zahteve</span><span class="sxs-lookup"><span data-stu-id="40499-112">Prerequisites</span></span>

- <span data-ttu-id="40499-113">Trenutno ta funkcija podpira spletne storitve, objavljene prek možnosti [studio za strojno učenje (klasični način)](https://studio.azureml.net) in [prodajni lijaki paketov za strojno učenje Azure](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="40499-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="40499-114">Za uporabo te funkcije potrebujete račun za shranjevanje Azure Data Lake Gen2, povezan z vašim primerkom studia Azure.</span><span class="sxs-lookup"><span data-stu-id="40499-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="40499-115">Če želite več informacij, glejte [Ustvarjanje računa za shrambo Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="40499-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="40499-116">Dodajanje novega poteka dela</span><span class="sxs-lookup"><span data-stu-id="40499-116">Add a new workflow</span></span>

1. <span data-ttu-id="40499-117">Pomaknite se na možnost **Obveščanje** > **Modeli po meri** in izberite **Nov potek dela**.</span><span class="sxs-lookup"><span data-stu-id="40499-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="40499-118">Za svoj model po meri v polju **Ime** določite prepoznavno ime.</span><span class="sxs-lookup"><span data-stu-id="40499-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="40499-119">![Posnetek zaslona podokna »Nov potek dela«](media/new-workflowv2.png "Posnetek zaslona podokna »Nov potek dela«")</span><span class="sxs-lookup"><span data-stu-id="40499-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="40499-120">V možnosti **Najemnik, ki vsebuje vašo spletno storitev** izberite organizacijo, v kateri je spletna storitev.</span><span class="sxs-lookup"><span data-stu-id="40499-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="40499-121">Če je vaša naročnina na Azure Machine Learning v drugem najemniku kot aplikacija Customer Insights, izberite možnost **Vpis** z vašimi poverilnicami za izbrano organizacijo.</span><span class="sxs-lookup"><span data-stu-id="40499-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="40499-122">Izberite **delovne prostore**, povezane z vašo spletno storitvijo.</span><span class="sxs-lookup"><span data-stu-id="40499-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="40499-123">Na seznamu sta navedena dva razdelka, eden za Strojno učenje Azure različice 1 (Studio za strojno učenje (klasični način)) in Strojno učenje Azure različice 2 (Strojno učenje Azure).</span><span class="sxs-lookup"><span data-stu-id="40499-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="40499-124">Če niste prepričani, kateri delovni prostor je pravi za vašo spletno storitev studia za strojno učenje (klasični način), izberite **Poljubno**.</span><span class="sxs-lookup"><span data-stu-id="40499-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="40499-125">Izberite spletno storitev studia za strojno učenje (klasični način) ali prodajni lijak za strojno učenje Azure na spustnem seznamu **Spletna storitev, ki vsebuje vaš model**.</span><span class="sxs-lookup"><span data-stu-id="40499-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="40499-126">Nato izberite **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="40499-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="40499-127">Preberite več o [objavi spletne storitve studia za strojno učenje (klasični način)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service).</span><span class="sxs-lookup"><span data-stu-id="40499-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="40499-128">Preberite več o [objavi prodajnega lijaka v storitvi Strojno učenje Azure z uporabo oblikovalnika](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) ali [SDK-jem](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="40499-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> <span data-ttu-id="40499-129">Vaš prodajni lijak mora biti objavljen v okviru [končne točke prodajnega lijaka](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="40499-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="40499-130">Za vsak **vnos spletne storitve** izberite ujemajočo se **entiteto** iz vpogledov v občinstvo in izberite **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="40499-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="40499-131">Potek dela po meri modela uporablja hevristiko za preslikavo vnosnih polj spletnih storitev v atribute entitete na podlagi imena in podatkovne vrste polja.</span><span class="sxs-lookup"><span data-stu-id="40499-131">The custom model workflow will apply heuristics to map the web service input fields to the entity attributes based on the name and data type of the field.</span></span> <span data-ttu-id="40499-132">Napaka bo prikazana, če polja spletne storitve ni mogoče preslikati v entiteto.</span><span class="sxs-lookup"><span data-stu-id="40499-132">You'll see an error if a web service field can't be mapped to an entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="40499-133">![Konfiguriranje poteka dela](media/intelligence-screen2-updated.png "Konfiguriranje poteka dela")</span><span class="sxs-lookup"><span data-stu-id="40499-133">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>
   
1. <span data-ttu-id="40499-134">Pri koraku **Parametri izhodnih podatkov modela** nastavite naslednje lastnosti:</span><span class="sxs-lookup"><span data-stu-id="40499-134">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="40499-135">Studio za strojno učenje (klasični način)</span><span class="sxs-lookup"><span data-stu-id="40499-135">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="40499-136">Vnesite izhodno **ime entitete**, v katero želite, da se stekajo izhodni rezultati spletne storitve.</span><span class="sxs-lookup"><span data-stu-id="40499-136">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="40499-137">Strojno učenje Azure</span><span class="sxs-lookup"><span data-stu-id="40499-137">Azure Machine Learning</span></span>
      1. <span data-ttu-id="40499-138">Vnesite izhodno **ime entitete**, v katero želite, da se stekajo izhodni rezultati prodajnega lijaka.</span><span class="sxs-lookup"><span data-stu-id="40499-138">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="40499-139">Izberite **Ime parametra shrambe izhodnih podatkov** za prodajni lijak paketov s spustnega seznama.</span><span class="sxs-lookup"><span data-stu-id="40499-139">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="40499-140">Izberite **Ime parametra shrambe poti za izhodne podatke** za prodajni lijak paketov s spustnega seznama.</span><span class="sxs-lookup"><span data-stu-id="40499-140">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="40499-141">![Podokno parametrov izhodnih podatkov modela](media/intelligence-screen3-outputparameters.png "Podokno parametrov izhodnih podatkov modela")</span><span class="sxs-lookup"><span data-stu-id="40499-141">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="40499-142">Na spustnem seznamu **ID stranke v rezultatih** izberite ujemajoč se atribut, ki prepozna stranke, in izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="40499-142">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="40499-143">![Povezava rezultatov s podoknom podatkov o strankah](media/intelligence-screen4-relatetocustomer.png "Povezava rezultatov s podoknom podatkov o strankah")</span><span class="sxs-lookup"><span data-stu-id="40499-143">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="40499-144">Prikazal se bo zaslon **Potek dela shranjen** s podrobnostmi o poteku dela.</span><span class="sxs-lookup"><span data-stu-id="40499-144">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="40499-145">Če ste konfigurirali potek dela za prodajni lijak za strojno učenje Azure, se bodo vpogledi v občinstvo prilepili v delovni prostor, ki vsebuje prodajni lijak.</span><span class="sxs-lookup"><span data-stu-id="40499-145">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="40499-146">Vpogledi v občinstvo bodo prejeli vlogo **sodelujočega** v delovnem prostoru Azure.</span><span class="sxs-lookup"><span data-stu-id="40499-146">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="40499-147">Izberite **Dokončano**.</span><span class="sxs-lookup"><span data-stu-id="40499-147">Select **Done**.</span></span>

1. <span data-ttu-id="40499-148">Zdaj lahko potek dela zaženete na strani **Modeli po meri**.</span><span class="sxs-lookup"><span data-stu-id="40499-148">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="40499-149">Urejanje poteka dela</span><span class="sxs-lookup"><span data-stu-id="40499-149">Edit a workflow</span></span>

1. <span data-ttu-id="40499-150">Na strani **Modeli po meri** izberite navpične tri pike v stolpcu **Dejanja** poleg poteka dela, ki ste ga prej ustvarili, in izberite **Uredi**.</span><span class="sxs-lookup"><span data-stu-id="40499-150">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="40499-151">Prepoznavno ime poteka dela lahko posodobite v polju **Prikazno ime**, vendar ne morete spremeniti konfigurirane spletne storitve ali prodajnega lijaka.</span><span class="sxs-lookup"><span data-stu-id="40499-151">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="40499-152">Izberite **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="40499-152">Select **Next**.</span></span>

1. <span data-ttu-id="40499-153">Za vsak **vnos spletne storitve** lahko posodobite ujemajočo se **entiteto** iz vpogledov v občinstvo.</span><span class="sxs-lookup"><span data-stu-id="40499-153">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="40499-154">Nato izberite **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="40499-154">Then, select **Next**.</span></span>

1. <span data-ttu-id="40499-155">Pri koraku **Parametri izhodnih podatkov modela** nastavite naslednje lastnosti:</span><span class="sxs-lookup"><span data-stu-id="40499-155">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="40499-156">Studio za strojno učenje (klasični način)</span><span class="sxs-lookup"><span data-stu-id="40499-156">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="40499-157">Vnesite izhodno **ime entitete**, v katero želite, da se stekajo izhodni rezultati spletne storitve.</span><span class="sxs-lookup"><span data-stu-id="40499-157">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="40499-158">Strojno učenje Azure</span><span class="sxs-lookup"><span data-stu-id="40499-158">Azure Machine Learning</span></span>
      1. <span data-ttu-id="40499-159">Vnesite izhodno **ime entitete**, v katero želite, da se stekajo izhodni rezultati prodajnega lijaka.</span><span class="sxs-lookup"><span data-stu-id="40499-159">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="40499-160">Izberite **Ime parametra shrambe izhodnih podatkov** za preskusni prodajni lijak.</span><span class="sxs-lookup"><span data-stu-id="40499-160">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="40499-161">Izberite **Ime parametra poti za izhodne podatke** za preskusni prodajni lijak.</span><span class="sxs-lookup"><span data-stu-id="40499-161">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="40499-162">Na spustnem seznamu **ID stranke v rezultatih** izberite ujemajoč se atribut, ki prepozna stranke, in izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="40499-162">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="40499-163">Prek izhodnih podatkov za sklepanje morate izbrati atribut z vrednostmi, podobnimi stolpcu ID stranke pri entiteti stranke.</span><span class="sxs-lookup"><span data-stu-id="40499-163">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="40499-164">Če v naboru podatkov nimate takega stolpca, izberite atribut, ki enolično prepozna vrstico.</span><span class="sxs-lookup"><span data-stu-id="40499-164">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="40499-165">Zagon poteka dela</span><span class="sxs-lookup"><span data-stu-id="40499-165">Run a workflow</span></span>

1. <span data-ttu-id="40499-166">Na strani **Modeli po meri** izberite navpične tri pike v stolpcu **Dejanja** poleg poteka dela, ki ste ga prej ustvarili.</span><span class="sxs-lookup"><span data-stu-id="40499-166">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="40499-167">Izberite **Zaženi**.</span><span class="sxs-lookup"><span data-stu-id="40499-167">Select **Run**.</span></span>

<span data-ttu-id="40499-168">Z vsakim načrtovanim osveževanjem se samodejno zažene tudi vaš potek dela.</span><span class="sxs-lookup"><span data-stu-id="40499-168">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="40499-169">Preberite več o [nastavitvi načrtovanega osveževanja](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="40499-169">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="40499-170">Brisanje poteka dela</span><span class="sxs-lookup"><span data-stu-id="40499-170">Delete a workflow</span></span>

1. <span data-ttu-id="40499-171">Na strani **Modeli po meri** izberite navpične tri pike v stolpcu **Dejanja** poleg poteka dela, ki ste ga prej ustvarili.</span><span class="sxs-lookup"><span data-stu-id="40499-171">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="40499-172">Izberite možnost **Izbriši** in nato potrdite izbris.</span><span class="sxs-lookup"><span data-stu-id="40499-172">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="40499-173">Vaš potek dela bo izbrisan.</span><span class="sxs-lookup"><span data-stu-id="40499-173">Your workflow will be deleted.</span></span> <span data-ttu-id="40499-174">[Entiteta](entities.md), ki je bila ustvarjena, ko ste ustvarili potek dela, se ohrani in si jo lahko ogledate na strani **Entitete**.</span><span class="sxs-lookup"><span data-stu-id="40499-174">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]