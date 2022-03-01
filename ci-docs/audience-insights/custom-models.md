---
title: Modeli strojnega učenja po meri | Microsoftovo gradivo
description: Uporabite modele po meri iz rešitve za strojno učenje Azure v aplikaciji Dynamics 365 Customer Insights.
ms.date: 12/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 47e2e5109ef8f21a782f6c8f87088009f8a40fdf
ms.sourcegitcommit: 58651d33e0a7d438a2587c9ceeaf7ff58ae3b648
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 12/02/2021
ms.locfileid: "7881804"
---
# <a name="custom-machine-learning-models"></a>Modeli strojnega učenja po meri

> [!NOTE]
> Podpora za Strojno učenje Studio (klasični) bo prenehala 31. avgusta 2024. Priporočamo prehod na [Azure Strojno učenje](/azure/machine-learning/overview-what-is-azure-machine-learning) do tega datuma.
>
> Od 1. decembra 2021 ne boste mogli ustvarjati novih virov Strojno učenje Studio (klasičnih). Do 31. avgusta 2024 lahko še naprej uporabljate obstoječe vire Strojno učenje Studio (klasične). Za več informacij glejte [Preselitev v Azure Strojno učenje](/azure/machine-learning/migrate-overview).


Možnost **Obveščanje** > **Modeli po meri** vam omogoča upravljanje potekov dela v modelih storitve Strojno učenje Azure. Poteki dela vam pomagajo izbrati podatke, iz katerih želite ustvariti vpogled, in rezultate preslikati v vaše poenotene podatke o strankah. Za več informacij o izdelavi modelov strojnega učenja po meri glejte razdelek [Uporaba modelov, ki temeljijo na strojnem učenju Azure](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>Odgovorna umetna inteligenca

Predvidevanja ponujajo zmogljivosti za ustvarjanje boljših izkušenj strank, izboljšanje poslovnih zmogljivosti in virov prihodkov. Močno priporočamo, da vrednost predvidevanja uravnotežite z vplivom in pristranskostmi, ki bi jih lahko uvedli na etičen način. Preberite več o tem, kako Microsoft [obravnava odgovorno ravnanje umetne inteligence](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Preberete lahko tudi o [tehnikah in postopkih za odgovorno strojno učenje](/azure/machine-learning/concept-responsible-ml), specifično za Strojno učenje Azure.

## <a name="prerequisites"></a>Zahteve

- Ta funkcija podpira spletne storitve, objavljene prek [Azure Strojno učenje paketni cevovodi](/azure/machine-learning/concept-ml-pipelines).

- Za uporabo te funkcije potrebujete račun za shranjevanje Azure Data Lake Gen2, povezan z vašim primerkom studia Azure. Če želite več informacij, glejte [Ustvarjanje računa za shrambo Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-quickstart-create-account).

- Za delovne prostore za strojno učenje Azure s prodajnimi lijaki potrebujete skrbniška dovoljenja za dostop lastnika ali uporabnika do delovnega prostora za strojno učenje Azure.

   > [!NOTE]
   > Podatki se prenašajo med vašimi primerki Customer Insights in izbranimi spletnimi storitvami Azure ali prodajnimi lijaki v poteku dela. Ko prenesete podatke v storitev Azure, se prepričajte, da je storitev konfigurirana za obdelavo podatkov za takšen način in lokacijo, ki sta potrebna za izpolnjevanje zakonskih zahtev ali zahtev za skladnost s predpisi, potrebnimi za te podatke, za vašo organizacijo.

## <a name="add-a-new-workflow"></a>Dodajanje novega poteka dela

1. Pomaknite se na možnost **Obveščanje** > **Modeli po meri** in izberite **Nov potek dela**.

1. Za svoj model po meri v polju **Ime** določite prepoznavno ime.

   > [!div class="mx-imgBorder"]
   > ![Posnetek zaslona podokna »Nov potek dela«.](media/new-workflowv2.png "Posnetek zaslona podokna »Nov potek dela«")

1. V možnosti **Najemnik, ki vsebuje vašo spletno storitev** izberite organizacijo, v kateri je spletna storitev.

1. Če je vaša naročnina na Azure Machine Learning v drugem najemniku kot aplikacija Customer Insights, izberite možnost **Vpis** z vašimi poverilnicami za izbrano organizacijo.

1. Izberite **delovne prostore**, povezane z vašo spletno storitvijo. 

1. Izberite cevovod Azure Strojno učenje v **Spletna storitev, ki vsebuje vaš model** spustni meni. Nato izberite **Naprej**.    
   Preberite več o [objavi prodajnega lijaka v storitvi Strojno učenje Azure z uporabo oblikovalnika](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) ali [SDK-jem](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). Vaš prodajni lijak mora biti objavljen v okviru [končne točke prodajnega lijaka](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. Za vsak **vnos spletne storitve** izberite ujemajočo se **entiteto** iz vpogledov v občinstvo in izberite **Naprej**.
   > [!NOTE]
   > Potek dela po meri modela uporablja hevristiko za preslikavo vnosnih polj spletnih storitev v atribute entitete na podlagi imena in podatkovne vrste polja. Napaka bo prikazana, če polja spletne storitve ni mogoče preslikati v entiteto.

   > [!div class="mx-imgBorder"]
   > ![Konfiguriranje poteka dela.](media/intelligence-screen2-updated.png "Konfiguriranje poteka dela")

1. Pri koraku **Parametri izhodnih podatkov modela** nastavite naslednje lastnosti:
      1. Vnesite izhodno **ime entitete**, v katero želite, da se stekajo izhodni rezultati prodajnega lijaka.
      1. Izberite **Ime parametra shrambe izhodnih podatkov** za prodajni lijak paketov s spustnega seznama.
      1. Izberite **Ime parametra shrambe poti za izhodne podatke** za prodajni lijak paketov s spustnega seznama.

      > [!div class="mx-imgBorder"]
      > ![Podokno parametrov izhodnih podatkov modela.](media/intelligence-screen3-outputparameters.png "Podokno parametrov izhodnih podatkov modela")

1. Na spustnem seznamu **ID stranke v rezultatih**, na katerem so navedene stranke, izberite ujemajoči atribut, nato pa možnost **Shrani**.

   > [!div class="mx-imgBorder"]
   > ![Povezava rezultatov s podoknom podatkov o strankah.](media/intelligence-screen4-relatetocustomer.png "Povezava rezultatov s podoknom podatkov o strankah")

1. Prikazal se bo zaslon **Potek dela shranjen** s podrobnostmi o poteku dela.    
   Če ste konfigurirali potek dela za prodajni lijak za strojno učenje Azure, se bodo vpogledi v občinstvo prilepili v delovni prostor, ki vsebuje prodajni lijak. Vpogledi v občinstvo bodo prejeli vlogo **sodelujočega** v delovnem prostoru Azure.

1. Izberite **Dokončano**.

1. Zdaj lahko potek dela zaženete na strani **Modeli po meri**.

## <a name="edit-a-workflow"></a>Urejanje poteka dela

1. Na strani **Modeli po meri** izberite navpične tri pike v stolpcu **Dejanja** poleg poteka dela, ki ste ga prej ustvarili, in izberite **Uredi**.

1. Prepoznavno ime poteka dela lahko posodobite v polju **Prikazno ime**, vendar ne morete spremeniti konfigurirane spletne storitve ali prodajnega lijaka. Izberite **Naprej**.

1. Za vsak **vnos spletne storitve** lahko posodobite ujemajočo se **entiteto** iz vpogledov v občinstvo. Nato izberite **Naprej**.

1. Pri koraku **Parametri izhodnih podatkov modela** nastavite naslednje lastnosti:
      1. Vnesite izhodno **ime entitete**, v katero želite, da se stekajo izhodni rezultati prodajnega lijaka.
      1. Izberite **Ime parametra shrambe izhodnih podatkov** za preskusni prodajni lijak.
      1. Izberite **Ime parametra poti za izhodne podatke** za preskusni prodajni lijak.

1. Na spustnem seznamu **ID stranke v rezultatih**, na katerem so navedene stranke, izberite ujemajoči atribut, nato pa možnost **Shrani**.
   Prek izhodnih podatkov za sklepanje izberite atribut z vrednostmi, podobnimi stolpcu ID stranke pri entiteti stranke. Če v naboru podatkov nimate takega stolpca, izberite atribut, ki enolično prepozna vrstico.

## <a name="run-a-workflow"></a>Zagon poteka dela

1. Na strani **Modeli po meri** izberite navpične tri pike v stolpcu **Dejanja** poleg poteka dela, ki ste ga prej ustvarili.

1. Izberite **Zaženi**.

Z vsakim načrtovanim osveževanjem se samodejno zažene tudi vaš potek dela. Preberite več o [nastavitvi načrtovanega osveževanja](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Brisanje poteka dela

1. Na strani **Modeli po meri** izberite navpične tri pike v stolpcu **Dejanja** poleg poteka dela, ki ste ga prej ustvarili.

1. Izberite možnost **Izbriši** in nato potrdite izbris.

Vaš potek dela bo izbrisan. [Entiteta](entities.md), ki je bila ustvarjena, ko ste ustvarili potek dela, se ohrani in si jo lahko ogledate na strani **Entitete**.

## <a name="results"></a>Rezultati

Rezultati poteka dela so shranjeni v entiteti, konfigurirani med fazo parametrov izhodnih podatkov modela. Do teh podatkov lahko dostopate na [strani entitet](entities.md) ali z [dostopom do API-ja](apis.md).

### <a name="api-access"></a>Dostop do API-ja

Za posebno poizvedbo OData za pridobitev podatkov iz entitete modela po meri uporabite naslednjo obliko:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Zamenjajte `<your instance id>` z ID-jem okolja Customer Insights, ki ga najdete v naslovni vrstici brskalnika, ko dostopate do Customer Insights.

1. Zamenjajte `<custom model output entity>` z imenom entitete, ki ste ga navedli pri koraku »Parametri izhodnih podatkov modela« pri konfiguraciji modela po meri.

1. Zamenjajte `<guid value>` z ID-jem stranke, za katero želite dostopati do zapisa. Običajno lahko ta ID najdete na [strani s profili strank](customer-profiles.md) v polju CustomerID.

## <a name="frequently-asked-questions"></a>Pogosta vprašanja

- Zakaj pri nastavitvi poteka dela modela po meri ne vidim svojega prodajnega lijaka?    
  To težavo pogosto povzroča težava s konfiguracijo v prodajnem lijaku. Zagotovite, da je [vhodni parameter konfiguriran](azure-machine-learning-experiments.md#dataset-configuration) in da so [parametri izhodne podatkovne shrambe in poti](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) prav tako konfigurirani.

- Kaj pomeni napaka »Ne morem shraniti poteka dela obveščanja«?    
  Uporabniki to sporočilo o napaki običajno vidijo, če v delovnem prostoru nimajo skrbniških pravic za dostop lastnika ali uporabnika. Uporabnik potrebuje višjo raven dovoljenj, da storitvi Customer Insights omogoči obdelavo poteka dela kot storitev, namesto da uporablja uporabniške poverilnice za naslednje zagone poteka dela.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
