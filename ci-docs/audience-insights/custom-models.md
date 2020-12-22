---
title: Modeli strojnega učenja po meri | Microsoftovo gradivo
description: Uporabite modele po meri iz rešitve za strojno učenje Azure v aplikaciji Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: article
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ef248086b30b870359970529a7bfb37792be62d5
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668923"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="c79d8-103">Modeli strojnega učenja po meri</span><span class="sxs-lookup"><span data-stu-id="c79d8-103">Custom machine learning models</span></span>

<span data-ttu-id="c79d8-104">Možnost **Obveščanje** > **Modeli po meri** vam omogoča upravljanje potekov dela v modelih storitve Strojno učenje Azure.</span><span class="sxs-lookup"><span data-stu-id="c79d8-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="c79d8-105">Poteki dela vam pomagajo izbrati podatke, iz katerih želite ustvariti vpogled, in rezultate preslikati v vaše poenotene podatke o strankah.</span><span class="sxs-lookup"><span data-stu-id="c79d8-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="c79d8-106">Za več informacij o izdelavi modelov strojnega učenja po meri glejte razdelek [Uporaba modelov, ki temeljijo na strojnem učenju Azure](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="c79d8-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="c79d8-107">Odgovorna umetna inteligenca</span><span class="sxs-lookup"><span data-stu-id="c79d8-107">Responsible AI</span></span>

<span data-ttu-id="c79d8-108">Predvidevanja ponujajo zmogljivosti za ustvarjanje boljših izkušenj strank, izboljšanje poslovnih zmogljivosti in virov prihodkov.</span><span class="sxs-lookup"><span data-stu-id="c79d8-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="c79d8-109">Močno priporočamo, da vrednost predvidevanja uravnotežite z vplivom in pristranskostmi, ki bi jih lahko uvedli na etičen način.</span><span class="sxs-lookup"><span data-stu-id="c79d8-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="c79d8-110">Preberite več o tem, kako Microsoft [obravnava odgovorno ravnanje umetne inteligence](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="c79d8-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="c79d8-111">Preberete lahko tudi o [tehnikah in postopkih za odgovorno strojno učenje](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml), specifično za Strojno učenje Azure.</span><span class="sxs-lookup"><span data-stu-id="c79d8-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c79d8-112">Zahteve</span><span class="sxs-lookup"><span data-stu-id="c79d8-112">Prerequisites</span></span>

- <span data-ttu-id="c79d8-113">Trenutno ta funkcija podpira spletne storitve, objavljene prek možnosti [studio za strojno učenje (klasični način)](https://studio.azureml.net) in [prodajni lijaki paketov za strojno učenje Azure](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="c79d8-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="c79d8-114">Za uporabo te funkcije potrebujete račun za shranjevanje Azure Data Lake Gen2, povezan z vašim primerkom studia Azure.</span><span class="sxs-lookup"><span data-stu-id="c79d8-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="c79d8-115">Če želite več informacij, glejte [Ustvarjanje računa za shrambo Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="c79d8-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="c79d8-116">Dodajanje novega poteka dela</span><span class="sxs-lookup"><span data-stu-id="c79d8-116">Add a new workflow</span></span>

1. <span data-ttu-id="c79d8-117">Pomaknite se na možnost **Obveščanje** > **Modeli po meri** in izberite **Nov potek dela**.</span><span class="sxs-lookup"><span data-stu-id="c79d8-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="c79d8-118">Za svoj model po meri v polju **Ime** določite prepoznavno ime.</span><span class="sxs-lookup"><span data-stu-id="c79d8-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c79d8-119">![Posnetek zaslona podokna »Nov potek dela«](media/new-workflowv2.png "Posnetek zaslona podokna »Nov potek dela«")</span><span class="sxs-lookup"><span data-stu-id="c79d8-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="c79d8-120">V možnosti **Najemnik, ki vsebuje vašo spletno storitev** izberite organizacijo, v kateri je spletna storitev.</span><span class="sxs-lookup"><span data-stu-id="c79d8-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="c79d8-121">Če je vaša naročnina na Azure Machine Learning v drugem najemniku kot aplikacija Customer Insights, izberite možnost **Vpis** z vašimi poverilnicami za izbrano organizacijo.</span><span class="sxs-lookup"><span data-stu-id="c79d8-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="c79d8-122">Izberite **delovne prostore**, povezane z vašo spletno storitvijo.</span><span class="sxs-lookup"><span data-stu-id="c79d8-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="c79d8-123">Na seznamu sta navedena dva razdelka, eden za Strojno učenje Azure različice 1 (Studio za strojno učenje (klasični način)) in Strojno učenje Azure različice 2 (Strojno učenje Azure).</span><span class="sxs-lookup"><span data-stu-id="c79d8-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="c79d8-124">Če niste prepričani, kateri delovni prostor je pravi za vašo spletno storitev studia za strojno učenje (klasični način), izberite **Poljubno**.</span><span class="sxs-lookup"><span data-stu-id="c79d8-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="c79d8-125">Izberite spletno storitev studia za strojno učenje (klasični način) ali prodajni lijak za strojno učenje Azure na spustnem seznamu **Spletna storitev, ki vsebuje vaš model**.</span><span class="sxs-lookup"><span data-stu-id="c79d8-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="c79d8-126">Nato izberite **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="c79d8-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="c79d8-127">Preberite več o [objavi spletne storitve studia za strojno učenje (klasični način)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service).</span><span class="sxs-lookup"><span data-stu-id="c79d8-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="c79d8-128">Preberite več o [objavi prodajnega lijaka v storitvi Strojno učenje Azure z uporabo oblikovalnika](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) ali [SDK-jem](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="c79d8-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> 
     > [!NOTE]
     > <span data-ttu-id="c79d8-129">Vaš prodajni lijak mora biti objavljen v okviru [končne točke prodajnega lijaka](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="c79d8-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="c79d8-130">Za vsak **vnos spletne storitve** izberite ujemajočo se **entiteto** iz vpogledov v občinstvo in izberite **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="c79d8-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c79d8-131">![Konfiguriranje poteka dela](media/intelligence-screen2-updated.png "Konfiguriranje poteka dela")</span><span class="sxs-lookup"><span data-stu-id="c79d8-131">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="c79d8-132">Pri koraku **Parametri izhodnih podatkov modela** nastavite naslednje lastnosti:</span><span class="sxs-lookup"><span data-stu-id="c79d8-132">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="c79d8-133">Studio za strojno učenje (klasični način)</span><span class="sxs-lookup"><span data-stu-id="c79d8-133">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="c79d8-134">Vnesite izhodno **ime entitete**, v katero želite, da se stekajo izhodni rezultati spletne storitve.</span><span class="sxs-lookup"><span data-stu-id="c79d8-134">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="c79d8-135">Strojno učenje Azure</span><span class="sxs-lookup"><span data-stu-id="c79d8-135">Azure Machine Learning</span></span>
      1. <span data-ttu-id="c79d8-136">Vnesite izhodno **ime entitete**, v katero želite, da se stekajo izhodni rezultati prodajnega lijaka.</span><span class="sxs-lookup"><span data-stu-id="c79d8-136">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="c79d8-137">Izberite **Ime parametra shrambe izhodnih podatkov** za prodajni lijak paketov s spustnega seznama.</span><span class="sxs-lookup"><span data-stu-id="c79d8-137">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="c79d8-138">Izberite **Ime parametra shrambe poti za izhodne podatke** za prodajni lijak paketov s spustnega seznama.</span><span class="sxs-lookup"><span data-stu-id="c79d8-138">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="c79d8-139">![Podokno parametrov izhodnih podatkov modela](media/intelligence-screen3-outputparameters.png "Podokno parametrov izhodnih podatkov modela")</span><span class="sxs-lookup"><span data-stu-id="c79d8-139">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="c79d8-140">Na spustnem seznamu **ID stranke v rezultatih** izberite ujemajoč se atribut, ki prepozna stranke, in izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="c79d8-140">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c79d8-141">![Povezava rezultatov s podoknom podatkov o strankah](media/intelligence-screen4-relatetocustomer.png "Povezava rezultatov s podoknom podatkov o strankah")</span><span class="sxs-lookup"><span data-stu-id="c79d8-141">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="c79d8-142">Prikazal se bo zaslon **Potek dela shranjen** s podrobnostmi o poteku dela.</span><span class="sxs-lookup"><span data-stu-id="c79d8-142">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="c79d8-143">Če ste konfigurirali potek dela za prodajni lijak za strojno učenje Azure, se bodo vpogledi v občinstvo prilepili v delovni prostor, ki vsebuje prodajni lijak.</span><span class="sxs-lookup"><span data-stu-id="c79d8-143">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="c79d8-144">Vpogledi v občinstvo bodo prejeli vlogo **sodelujočega** v delovnem prostoru Azure.</span><span class="sxs-lookup"><span data-stu-id="c79d8-144">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="c79d8-145">Izberite **Dokončano**.</span><span class="sxs-lookup"><span data-stu-id="c79d8-145">Select **Done**.</span></span>

1. <span data-ttu-id="c79d8-146">Zdaj lahko potek dela zaženete na strani **Modeli po meri**.</span><span class="sxs-lookup"><span data-stu-id="c79d8-146">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="c79d8-147">Urejanje poteka dela</span><span class="sxs-lookup"><span data-stu-id="c79d8-147">Edit a workflow</span></span>

1. <span data-ttu-id="c79d8-148">Na strani **Modeli po meri** izberite navpične tri pike v stolpcu **Dejanja** poleg poteka dela, ki ste ga prej ustvarili, in izberite **Uredi**.</span><span class="sxs-lookup"><span data-stu-id="c79d8-148">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="c79d8-149">Prepoznavno ime poteka dela lahko posodobite v polju **Prikazno ime**, vendar ne morete spremeniti konfigurirane spletne storitve ali prodajnega lijaka.</span><span class="sxs-lookup"><span data-stu-id="c79d8-149">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="c79d8-150">Izberite **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="c79d8-150">Select **Next**.</span></span>

1. <span data-ttu-id="c79d8-151">Za vsak **vnos spletne storitve** lahko posodobite ujemajočo se **entiteto** iz vpogledov v občinstvo.</span><span class="sxs-lookup"><span data-stu-id="c79d8-151">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="c79d8-152">Nato izberite **Naprej**.</span><span class="sxs-lookup"><span data-stu-id="c79d8-152">Then, select **Next**.</span></span>

1. <span data-ttu-id="c79d8-153">Pri koraku **Parametri izhodnih podatkov modela** nastavite naslednje lastnosti:</span><span class="sxs-lookup"><span data-stu-id="c79d8-153">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="c79d8-154">Studio za strojno učenje (klasični način)</span><span class="sxs-lookup"><span data-stu-id="c79d8-154">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="c79d8-155">Vnesite izhodno **ime entitete**, v katero želite, da se stekajo izhodni rezultati spletne storitve.</span><span class="sxs-lookup"><span data-stu-id="c79d8-155">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="c79d8-156">Strojno učenje Azure</span><span class="sxs-lookup"><span data-stu-id="c79d8-156">Azure Machine Learning</span></span>
      1. <span data-ttu-id="c79d8-157">Vnesite izhodno **ime entitete**, v katero želite, da se stekajo izhodni rezultati prodajnega lijaka.</span><span class="sxs-lookup"><span data-stu-id="c79d8-157">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="c79d8-158">Izberite **Ime parametra shrambe izhodnih podatkov** za preskusni prodajni lijak.</span><span class="sxs-lookup"><span data-stu-id="c79d8-158">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="c79d8-159">Izberite **Ime parametra poti za izhodne podatke** za preskusni prodajni lijak.</span><span class="sxs-lookup"><span data-stu-id="c79d8-159">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="c79d8-160">Na spustnem seznamu **ID stranke v rezultatih** izberite ujemajoč se atribut, ki prepozna stranke, in izberite **Shrani**.</span><span class="sxs-lookup"><span data-stu-id="c79d8-160">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="c79d8-161">Prek izhodnih podatkov za sklepanje morate izbrati atribut z vrednostmi, podobnimi stolpcu ID stranke pri entiteti stranke.</span><span class="sxs-lookup"><span data-stu-id="c79d8-161">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="c79d8-162">Če v naboru podatkov nimate takega stolpca, izberite atribut, ki enolično prepozna vrstico.</span><span class="sxs-lookup"><span data-stu-id="c79d8-162">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="c79d8-163">Zagon poteka dela</span><span class="sxs-lookup"><span data-stu-id="c79d8-163">Run a workflow</span></span>

1. <span data-ttu-id="c79d8-164">Na strani **Modeli po meri** izberite navpične tri pike v stolpcu **Dejanja** poleg poteka dela, ki ste ga prej ustvarili.</span><span class="sxs-lookup"><span data-stu-id="c79d8-164">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="c79d8-165">Izberite **Zaženi**.</span><span class="sxs-lookup"><span data-stu-id="c79d8-165">Select **Run**.</span></span>

<span data-ttu-id="c79d8-166">Z vsakim načrtovanim osveževanjem se samodejno zažene tudi vaš potek dela.</span><span class="sxs-lookup"><span data-stu-id="c79d8-166">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="c79d8-167">Preberite več o [nastavitvi načrtovanega osveževanja](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c79d8-167">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="c79d8-168">Brisanje poteka dela</span><span class="sxs-lookup"><span data-stu-id="c79d8-168">Delete a workflow</span></span>

1. <span data-ttu-id="c79d8-169">Na strani **Modeli po meri** izberite navpične tri pike v stolpcu **Dejanja** poleg poteka dela, ki ste ga prej ustvarili.</span><span class="sxs-lookup"><span data-stu-id="c79d8-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="c79d8-170">Izberite možnost **Izbriši** in nato potrdite izbris.</span><span class="sxs-lookup"><span data-stu-id="c79d8-170">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="c79d8-171">Vaš potek dela bo izbrisan.</span><span class="sxs-lookup"><span data-stu-id="c79d8-171">Your workflow will be deleted.</span></span> <span data-ttu-id="c79d8-172">[Entiteta](entities.md), ki je bila ustvarjena, ko ste ustvarili potek dela, se ohrani in si jo lahko ogledate na strani **Entitete**.</span><span class="sxs-lookup"><span data-stu-id="c79d8-172">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>
