---
title: Eksperimentiranje s strojnim učenjem Azure
description: Uporabite modele, ki temeljijo na strojnem učenju Azure, v storitvi Dynamics 365 Customer Insights.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: edd2cf488b52cef87b09b90336e48fdc7f470a68
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597439"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="70fe9-103">Uporaba modelov, ki temeljijo na strojnem učenju Azure</span><span class="sxs-lookup"><span data-stu-id="70fe9-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="70fe9-104">Združeni podatki v storitvi Dynamics 365 Customer Insights so vir za gradnjo modelov strojnega učenja, ki lahko ustvarijo dodatne vpoglede v poslovanje.</span><span class="sxs-lookup"><span data-stu-id="70fe9-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="70fe9-105">Customer Insights se integrira s studiom za strojno učenje (klasični način) in storitvijo Strojno učenje Azure, da lahko uporabljate lastne modele po meri.</span><span class="sxs-lookup"><span data-stu-id="70fe9-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="70fe9-106">Glejte [Eksperimentiranje s studiom za strojno učenje (klasični način)](machine-learning-studio-experiments.md) za primere poskusov, ustvarjenih v studiu za strojno učenje (klasični način).</span><span class="sxs-lookup"><span data-stu-id="70fe9-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="70fe9-107">Zahteve</span><span class="sxs-lookup"><span data-stu-id="70fe9-107">Prerequisites</span></span>

- <span data-ttu-id="70fe9-108">Dostop do storitve Customer Insights</span><span class="sxs-lookup"><span data-stu-id="70fe9-108">Access to Customer Insights</span></span>
- <span data-ttu-id="70fe9-109">Aktivna naročnina na storitev Azure Enterprise</span><span class="sxs-lookup"><span data-stu-id="70fe9-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="70fe9-110">Poenoteni profili strank</span><span class="sxs-lookup"><span data-stu-id="70fe9-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="70fe9-111">[Izvoz entitete v shrambo zbirke dvojiških podatkov Azure](export-azure-blob-storage.md) je konfiguriran</span><span class="sxs-lookup"><span data-stu-id="70fe9-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="70fe9-112">Nastavitev delovnega prostora za strojno učenje Azure</span><span class="sxs-lookup"><span data-stu-id="70fe9-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="70fe9-113">Glejte razdelek za [ustvarjanje delovnega prostora za strojno učenje Azure](/azure/machine-learning/concept-workspace#-create-a-workspace), če želite spoznati različne možnosti ustvarjanja delovnega prostora.</span><span class="sxs-lookup"><span data-stu-id="70fe9-113">See [create a Azure Machine Learning workspace](/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="70fe9-114">Za najboljšo zmogljivost ustvarite delovni prostor v območju Azure, ki je geografsko najbližje vašemu okolju Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="70fe9-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="70fe9-115">Dostopajte do delovnega prostora prek [studia za strojno učenje Azure](https://ml.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="70fe9-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="70fe9-116">Obstaja več [načinov interakcije](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) z delovnim prostorom.</span><span class="sxs-lookup"><span data-stu-id="70fe9-116">There are several [ways to interact](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="70fe9-117">Delo z oblikovalnikom za strojno učenje Azure</span><span class="sxs-lookup"><span data-stu-id="70fe9-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="70fe9-118">Oblikovalnik za strojno učenje Azure ponuja vizualno delovno območje, kamor lahko povlečete in spustite nabore podatkov in module, podobno kot pri studiu za strojno učenje (klasični način).</span><span class="sxs-lookup"><span data-stu-id="70fe9-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="70fe9-119">Prodajni lijak paketa, ustvarjen v oblikovalniku, je mogoče integrirati s storitvijo Customer Insights, če sta ustrezno konfigurirana.</span><span class="sxs-lookup"><span data-stu-id="70fe9-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="70fe9-120">Delo s SDK-jem za strojno učenje Azure</span><span class="sxs-lookup"><span data-stu-id="70fe9-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="70fe9-121">Podatkovni znanstveniki in razvijalci umetne inteligence uporabljajo [SDK za strojno učenje Azure](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) za ustvarjanje potekov dela za strojno učenje.</span><span class="sxs-lookup"><span data-stu-id="70fe9-121">Data scientists and AI developers use the [Azure Machine Learning SDK](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) to build machine learning workflows.</span></span> <span data-ttu-id="70fe9-122">Trenutno modelov, naučenih z uporabo SDK-ja, ni mogoče neposredno integrirati s storitvijo Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="70fe9-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="70fe9-123">Za integracijo s storitvijo Customer Insights je potreben prodajni lijak za sklepanje glede paketov, ki uporablja ta model.</span><span class="sxs-lookup"><span data-stu-id="70fe9-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="70fe9-124">Zahteve za prodajni lijak paketa za namene integracije s storitvijo Customer Insights</span><span class="sxs-lookup"><span data-stu-id="70fe9-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="70fe9-125">Konfiguracija nabora podatkov</span><span class="sxs-lookup"><span data-stu-id="70fe9-125">Dataset Configuration</span></span>

<span data-ttu-id="70fe9-126">Ustvariti morate nabore podatkov, da boste lahko uporabili podatke entitete iz storitve Customer Insights v prodajnem lijaku za sklepanje glede paketov.</span><span class="sxs-lookup"><span data-stu-id="70fe9-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="70fe9-127">Te nabore podatkov je treba registrirati v delovnem prostoru.</span><span class="sxs-lookup"><span data-stu-id="70fe9-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="70fe9-128">Trenutno podpiramo samo [tabelarične nabore podatkov](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) v obliki .csv.</span><span class="sxs-lookup"><span data-stu-id="70fe9-128">Currently, we only support [tabular datasets](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="70fe9-129">Nabore podatkov, ki ustrezajo podatkom entitete, je treba razvrstiti kot parametre prodajnega lijaka.</span><span class="sxs-lookup"><span data-stu-id="70fe9-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="70fe9-130">Parametri nabora podatkov v oblikovalniku</span><span class="sxs-lookup"><span data-stu-id="70fe9-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="70fe9-131">V oblikovalniku odprite možnost **Izbira stolpcev v naboru podatkov** in izberite **Nastavi kot parameter prodajnega lijaka**, pri čemer navedete ime parametra.</span><span class="sxs-lookup"><span data-stu-id="70fe9-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="70fe9-132">![Razvrstitev parametrov nabora podatkov v oblikovalniku](media/intelligence-designer-dataset-parameters.png "Razvrstitev parametrov nabora podatkov v oblikovalniku")</span><span class="sxs-lookup"><span data-stu-id="70fe9-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="70fe9-133">Parameter nabora podatkov v SDK-ju (Python)</span><span class="sxs-lookup"><span data-stu-id="70fe9-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="70fe9-134">Prodajni lijak za sklepanje glede paketov</span><span class="sxs-lookup"><span data-stu-id="70fe9-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="70fe9-135">V oblikovalniku se lahko za ustvarjanje ali posodabljanje prodajnega lijaka za sklepanje uporablja prodajni lijak za usposabljanje.</span><span class="sxs-lookup"><span data-stu-id="70fe9-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="70fe9-136">Trenutno so podprti samo prodajni lijaki za sklepanje glede paketov.</span><span class="sxs-lookup"><span data-stu-id="70fe9-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="70fe9-137">Z uporabo SDK-ja lahko objavite prodajni lijak pri končni točki.</span><span class="sxs-lookup"><span data-stu-id="70fe9-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="70fe9-138">Trenutno se Customer Insights integrira s privzetim prodajnim lijakom pri končni točki prodajnega lijaka glede paketov v delovnem prostoru za strojno učenje.</span><span class="sxs-lookup"><span data-stu-id="70fe9-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="70fe9-139">Uvoz podatkov prodajnega lijaka v Customer Insights</span><span class="sxs-lookup"><span data-stu-id="70fe9-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="70fe9-140">Oblikovalnik zagotavlja [modul za izvoz podatkov](/azure/machine-learning/algorithm-module-reference/export-data), ki omogoča izvoz izhoda prodajnega lijaka v shrambo Azure.</span><span class="sxs-lookup"><span data-stu-id="70fe9-140">The designer provides the [Export Data module](/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="70fe9-141">Trenutno mora modul uporabljati vrsto shrambe podatkov **Shramba zbirke dvojiških podatkov Azure** in nastaviti parameter **Shramba podatkov** in relativno **pot**.</span><span class="sxs-lookup"><span data-stu-id="70fe9-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="70fe9-142">Customer Insights preglasi oba parametra med izvajanjem prodajnega lijaka s shrambo podatkov in potjo, ki je dostopna izdelku.</span><span class="sxs-lookup"><span data-stu-id="70fe9-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="70fe9-143">![Konfiguracija modula za izvoz podatkov](media/intelligence-designer-importdata.png "Konfiguracija modula za izvoz podatkov")</span><span class="sxs-lookup"><span data-stu-id="70fe9-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="70fe9-144">Ob zapisu izhodnih podatkov za sklepanje s kod, lahko izhodne podatke naložite v pot znotraj *registrirane shrambe podatkov* v delovnem prostoru.</span><span class="sxs-lookup"><span data-stu-id="70fe9-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="70fe9-145">Če so določeni parametri poti in shrambe podatkov v prodajnem lijaku, bo lahko Customer Insights prebral in uvozil izhodne podatke za sklepanje.</span><span class="sxs-lookup"><span data-stu-id="70fe9-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="70fe9-146">Trenutno je podprt en sam niz tabelaričnih izhodnih podatkov v obliki zapisa csv.</span><span class="sxs-lookup"><span data-stu-id="70fe9-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="70fe9-147">Pot mora vsebovati imenik in ime datoteke.</span><span class="sxs-lookup"><span data-stu-id="70fe9-147">The path must include the directory and filename.</span></span>

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```


[!INCLUDE[footer-include](../includes/footer-banner.md)]