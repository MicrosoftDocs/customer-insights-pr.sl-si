---
title: Eksperimentiranje s strojnim učenjem Azure
description: Uporabite modele, ki temeljijo na strojnem učenju Azure, v storitvi Dynamics 365 Customer Insights.
ms.date: 12/02/2021
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3c3bed3dca40be748140a8b339191e6a42725714
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228908"
---
# <a name="use-azure-machine-learning-based-models"></a>Uporaba modelov, ki temeljijo na strojnem učenju Azure

Združeni podatki v storitvi Dynamics 365 Customer Insights so vir za gradnjo modelov strojnega učenja, ki lahko ustvarijo dodatne vpoglede v poslovanje. Storitev Customer Insights se integrira s strojnim učenjem Azure, da uporabi vaše lastne modele po meri.

## <a name="prerequisites"></a>Zahteve

- Dostop do storitve Customer Insights
- Aktivna naročnina na storitev Azure Enterprise
- [Poenoteni profili strank](data-unification.md)
- [Izvoz entitete v shrambo zbirke dvojiških podatkov Azure](export-azure-blob-storage.md) je konfiguriran

## <a name="set-up-azure-machine-learning-workspace"></a>Nastavitev delovnega prostora za strojno učenje Azure

1. Glejte razdelek za [ustvarjanje delovnega prostora za strojno učenje Azure](/azure/machine-learning/concept-workspace#-create-a-workspace), če želite spoznati različne možnosti ustvarjanja delovnega prostora. Za najboljšo zmogljivost ustvarite delovni prostor v območju Azure, ki je geografsko najbližje vašemu okolju Customer Insights.

1. Dostopajte do delovnega prostora prek [studia za strojno učenje Azure](https://ml.azure.com/). Obstaja več [načinov interakcije](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) z delovnim prostorom.

## <a name="work-with-azure-machine-learning-designer"></a>Delo z oblikovalnikom za strojno učenje Azure

Oblikovalec Azure Strojno učenje ponuja vizualno platno, kamor lahko povlečete in spustite nabore podatkov in module. Prodajni lijak paketa, ustvarjen v oblikovalniku, je mogoče integrirati s storitvijo Customer Insights, če sta ustrezno konfigurirana. 
   
## <a name="working-with-azure-machine-learning-sdk"></a>Delo s SDK-jem za strojno učenje Azure

Podatkovni znanstveniki in razvijalci umetne inteligence uporabljajo [SDK za strojno učenje Azure](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) za ustvarjanje potekov dela za strojno učenje. Trenutno modelov, naučenih z uporabo SDK-ja, ni mogoče neposredno integrirati s storitvijo Customer Insights. Za integracijo s storitvijo Customer Insights je potreben prodajni lijak za sklepanje glede paketov, ki uporablja ta model.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Zahteve za prodajni lijak paketa za namene integracije s storitvijo Customer Insights

### <a name="dataset-configuration"></a>Konfiguracija nabora podatkov

Ustvariti morate nabore podatkov, da boste lahko uporabili podatke entitete iz storitve Customer Insights v prodajnem lijaku za sklepanje glede paketov. Te nabore podatkov je treba registrirati v delovnem prostoru. Trenutno podpiramo samo [tabelarične nabore podatkov](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) v obliki .csv. Nabore podatkov, ki ustrezajo podatkom entitete, je treba razvrstiti kot parametre prodajnega lijaka.
   
* Parametri nabora podatkov v oblikovalniku
   
     V oblikovalniku odprite možnost **Izbira stolpcev v naboru podatkov** in izberite **Nastavi kot parameter prodajnega lijaka**, pri čemer navedete ime parametra.

     > [!div class="mx-imgBorder"]
     > ![Parametrizacija nabora podatkov v oblikovalniku.](media/intelligence-designer-dataset-parameters.png "Razvrstitev parametrov nabora podatkov v oblikovalniku")
   
* Parameter nabora podatkov v SDK-ju (Python)
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Prodajni lijak za sklepanje glede paketov
  
* V oblikovalniku se lahko za ustvarjanje ali posodabljanje prodajnega lijaka za sklepanje uporablja prodajni lijak za usposabljanje. Trenutno so podprti samo prodajni lijaki za sklepanje glede paketov.

* Z uporabo SDK-ja lahko objavite prodajni lijak pri končni točki. Trenutno se Customer Insights integrira s privzetim prodajnim lijakom pri končni točki prodajnega lijaka glede paketov v delovnem prostoru za strojno učenje.
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Uvoz podatkov prodajnega lijaka v Customer Insights

* Oblikovalnik zagotavlja [modul za izvoz podatkov](/azure/machine-learning/algorithm-module-reference/export-data), ki omogoča izvoz izhoda prodajnega lijaka v shrambo Azure. Trenutno mora modul uporabljati vrsto shrambe podatkov **Shramba zbirke dvojiških podatkov Azure** in nastaviti parameter **Shramba podatkov** in relativno **pot**. Customer Insights preglasi oba parametra med izvajanjem prodajnega lijaka s shrambo podatkov in potjo, ki je dostopna izdelku.
   > [!div class="mx-imgBorder"]
   > ![Konfiguracija modula za izvoz podatkov.](media/intelligence-designer-importdata.png "Konfiguracija modula za izvoz podatkov")
   
* Ob zapisu izhodnih podatkov za sklepanje s kod, lahko izhodne podatke naložite v pot znotraj *registrirane shrambe podatkov* v delovnem prostoru. Če so določeni parametri poti in shrambe podatkov v prodajnem lijaku, bo lahko Customer Insights prebral in uvozil izhodne podatke za sklepanje. Trenutno je podprt en sam niz tabelaričnih izhodnih podatkov v obliki zapisa csv. Pot mora vsebovati imenik in ime datoteke.

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