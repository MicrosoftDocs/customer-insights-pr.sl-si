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
# <a name="custom-machine-learning-models"></a>Modeli strojnega učenja po meri

Možnost **Obveščanje** > **Modeli po meri** vam omogoča upravljanje potekov dela v modelih storitve Strojno učenje Azure. Poteki dela vam pomagajo izbrati podatke, iz katerih želite ustvariti vpogled, in rezultate preslikati v vaše poenotene podatke o strankah. Za več informacij o izdelavi modelov strojnega učenja po meri glejte razdelek [Uporaba modelov, ki temeljijo na strojnem učenju Azure](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>Odgovorna umetna inteligenca

Predvidevanja ponujajo zmogljivosti za ustvarjanje boljših izkušenj strank, izboljšanje poslovnih zmogljivosti in virov prihodkov. Močno priporočamo, da vrednost predvidevanja uravnotežite z vplivom in pristranskostmi, ki bi jih lahko uvedli na etičen način. Preberite več o tem, kako Microsoft [obravnava odgovorno ravnanje umetne inteligence](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Preberete lahko tudi o [tehnikah in postopkih za odgovorno strojno učenje](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml), specifično za Strojno učenje Azure.

## <a name="prerequisites"></a>Zahteve

- Trenutno ta funkcija podpira spletne storitve, objavljene prek možnosti [studio za strojno učenje (klasični način)](https://studio.azureml.net) in [prodajni lijaki paketov za strojno učenje Azure](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).

- Za uporabo te funkcije potrebujete račun za shranjevanje Azure Data Lake Gen2, povezan z vašim primerkom studia Azure. Če želite več informacij, glejte [Ustvarjanje računa za shrambo Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)

## <a name="add-a-new-workflow"></a>Dodajanje novega poteka dela

1. Pomaknite se na možnost **Obveščanje** > **Modeli po meri** in izberite **Nov potek dela**.

1. Za svoj model po meri v polju **Ime** določite prepoznavno ime.

   > [!div class="mx-imgBorder"]
   > ![Posnetek zaslona podokna »Nov potek dela«](media/new-workflowv2.png "Posnetek zaslona podokna »Nov potek dela«")

1. V možnosti **Najemnik, ki vsebuje vašo spletno storitev** izberite organizacijo, v kateri je spletna storitev.

1. Če je vaša naročnina na Azure Machine Learning v drugem najemniku kot aplikacija Customer Insights, izberite možnost **Vpis** z vašimi poverilnicami za izbrano organizacijo.

1. Izberite **delovne prostore**, povezane z vašo spletno storitvijo. Na seznamu sta navedena dva razdelka, eden za Strojno učenje Azure različice 1 (Studio za strojno učenje (klasični način)) in Strojno učenje Azure različice 2 (Strojno učenje Azure). Če niste prepričani, kateri delovni prostor je pravi za vašo spletno storitev studia za strojno učenje (klasični način), izberite **Poljubno**.

1. Izberite spletno storitev studia za strojno učenje (klasični način) ali prodajni lijak za strojno učenje Azure na spustnem seznamu **Spletna storitev, ki vsebuje vaš model**. Nato izberite **Naprej**.
   - Preberite več o [objavi spletne storitve studia za strojno učenje (klasični način)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service).
   - Preberite več o [objavi prodajnega lijaka v storitvi Strojno učenje Azure z uporabo oblikovalnika](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) ali [SDK-jem](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). Vaš prodajni lijak mora biti objavljen v okviru [končne točke prodajnega lijaka](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. Za vsak **vnos spletne storitve** izberite ujemajočo se **entiteto** iz vpogledov v občinstvo in izberite **Naprej**.
   > [!NOTE]
   > Potek dela po meri modela uporablja hevristiko za preslikavo vnosnih polj spletnih storitev v atribute entitete na podlagi imena in podatkovne vrste polja. Napaka bo prikazana, če polja spletne storitve ni mogoče preslikati v entiteto.

   > [!div class="mx-imgBorder"]
   > ![Konfiguriranje poteka dela](media/intelligence-screen2-updated.png "Konfiguriranje poteka dela")
   
1. Pri koraku **Parametri izhodnih podatkov modela** nastavite naslednje lastnosti:
   - Studio za strojno učenje (klasični način)
      1. Vnesite izhodno **ime entitete**, v katero želite, da se stekajo izhodni rezultati spletne storitve.
   - Strojno učenje Azure
      1. Vnesite izhodno **ime entitete**, v katero želite, da se stekajo izhodni rezultati prodajnega lijaka.
      1. Izberite **Ime parametra shrambe izhodnih podatkov** za prodajni lijak paketov s spustnega seznama.
      1. Izberite **Ime parametra shrambe poti za izhodne podatke** za prodajni lijak paketov s spustnega seznama.
      
      > [!div class="mx-imgBorder"]
      > ![Podokno parametrov izhodnih podatkov modela](media/intelligence-screen3-outputparameters.png "Podokno parametrov izhodnih podatkov modela")

1. Na spustnem seznamu **ID stranke v rezultatih** izberite ujemajoč se atribut, ki prepozna stranke, in izberite **Shrani**.
   
   > [!div class="mx-imgBorder"]
   > ![Povezava rezultatov s podoknom podatkov o strankah](media/intelligence-screen4-relatetocustomer.png "Povezava rezultatov s podoknom podatkov o strankah")

1. Prikazal se bo zaslon **Potek dela shranjen** s podrobnostmi o poteku dela.    
   Če ste konfigurirali potek dela za prodajni lijak za strojno učenje Azure, se bodo vpogledi v občinstvo prilepili v delovni prostor, ki vsebuje prodajni lijak. Vpogledi v občinstvo bodo prejeli vlogo **sodelujočega** v delovnem prostoru Azure.

1. Izberite **Dokončano**.

1. Zdaj lahko potek dela zaženete na strani **Modeli po meri**.

## <a name="edit-a-workflow"></a>Urejanje poteka dela

1. Na strani **Modeli po meri** izberite navpične tri pike v stolpcu **Dejanja** poleg poteka dela, ki ste ga prej ustvarili, in izberite **Uredi**.

1. Prepoznavno ime poteka dela lahko posodobite v polju **Prikazno ime**, vendar ne morete spremeniti konfigurirane spletne storitve ali prodajnega lijaka. Izberite **Naprej**.

1. Za vsak **vnos spletne storitve** lahko posodobite ujemajočo se **entiteto** iz vpogledov v občinstvo. Nato izberite **Naprej**.

1. Pri koraku **Parametri izhodnih podatkov modela** nastavite naslednje lastnosti:
   - Studio za strojno učenje (klasični način)
      1. Vnesite izhodno **ime entitete**, v katero želite, da se stekajo izhodni rezultati spletne storitve.
   - Strojno učenje Azure
      1. Vnesite izhodno **ime entitete**, v katero želite, da se stekajo izhodni rezultati prodajnega lijaka.
      1. Izberite **Ime parametra shrambe izhodnih podatkov** za preskusni prodajni lijak.
      1. Izberite **Ime parametra poti za izhodne podatke** za preskusni prodajni lijak.

1. Na spustnem seznamu **ID stranke v rezultatih** izberite ujemajoč se atribut, ki prepozna stranke, in izberite **Shrani**.
   Prek izhodnih podatkov za sklepanje morate izbrati atribut z vrednostmi, podobnimi stolpcu ID stranke pri entiteti stranke. Če v naboru podatkov nimate takega stolpca, izberite atribut, ki enolično prepozna vrstico.

## <a name="run-a-workflow"></a>Zagon poteka dela

1. Na strani **Modeli po meri** izberite navpične tri pike v stolpcu **Dejanja** poleg poteka dela, ki ste ga prej ustvarili.

1. Izberite **Zaženi**.

Z vsakim načrtovanim osveževanjem se samodejno zažene tudi vaš potek dela. Preberite več o [nastavitvi načrtovanega osveževanja](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Brisanje poteka dela

1. Na strani **Modeli po meri** izberite navpične tri pike v stolpcu **Dejanja** poleg poteka dela, ki ste ga prej ustvarili.

1. Izberite možnost **Izbriši** in nato potrdite izbris.

Vaš potek dela bo izbrisan. [Entiteta](entities.md), ki je bila ustvarjena, ko ste ustvarili potek dela, se ohrani in si jo lahko ogledate na strani **Entitete**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]