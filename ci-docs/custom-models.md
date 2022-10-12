---
title: Modeli strojnega učenja po meri | Microsoftovo gradivo
description: Uporabite modele po meri iz rešitve za strojno učenje Azure v aplikaciji Dynamics 365 Customer Insights.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
searchScope:
- ci-custom-models
- customerInsights
ms.openlocfilehash: 89553b511d249fd586e36a1c4944a977513b0643
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609766"
---
# <a name="custom-machine-learning-models"></a>Modeli strojnega učenja po meri

> [!NOTE]
> Podpora za Strojno učenje Studio (klasični) se bo končala 31. avgusta 2024. Priporočamo, da preidete na [Azure Strojno učenje](/azure/machine-learning/overview-what-is-azure-machine-learning) do tega datuma.
>
> Od 1. decembra 2021 ne boste več mogli ustvarjati novih (klasičnih) virov Strojno učenje Studio. Do 31. avgusta 2024 lahko še naprej uporabljate obstoječe vire Strojno učenje Studio (klasični). Za več informacij glejte [Preselite se na Azure Strojno učenje](/azure/machine-learning/migrate-overview).

Modeli po meri vam omogočajo upravljanje potekov dela na podlagi Strojno učenje modelov Azure. Poteki dela vam pomagajo izbrati podatke, iz katerih želite ustvariti vpogled, in rezultate preslikati v vaše poenotene podatke o strankah. Za več informacij o izdelavi modelov strojnega učenja po meri glejte razdelek [Uporaba modelov, ki temeljijo na strojnem učenju Azure](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Zahteve

- Spletne storitve, objavljene prek [Paketni cevovodi Azure Strojno učenje](/azure/machine-learning/concept-ml-pipelines).
- Cevovod mora biti objavljen pod a [cevovod končna točka](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).
- An [Račun za shranjevanje Azure Data Lake Gen2](/azure/storage/blobs/data-lake-storage-quickstart-create-account) povezan z vašim primerkom Azure Studio.
- Za delovne prostore Azure Strojno učenje s cevovodi, dovoljenja skrbnika za dostop lastnika ali uporabnika do delovnega prostora Azure Strojno učenje.

  > [!NOTE]
  > Podatki se prenašajo med vašimi primerki Customer Insights in izbranimi spletnimi storitvami Azure ali prodajnimi lijaki v poteku dela. Ko prenesete podatke v storitev Azure, se prepričajte, da je storitev konfigurirana za obdelavo podatkov za takšen način in lokacijo, ki sta potrebna za izpolnjevanje zakonskih zahtev ali zahtev za skladnost s predpisi, potrebnimi za te podatke, za vašo organizacijo.

## <a name="add-a-new-workflow"></a>Dodajanje novega poteka dela

1. Pomaknite se na možnost **Obveščanje** > **Modeli po meri** in izberite **Nov potek dela**.

1. Poskrbite za prepoznavnost **Ime**.

   :::image type="content" source="media/new-workflowv2.png" alt-text="Posnetek zaslona podokna »Nov potek dela«.":::

1. V možnosti **Najemnik, ki vsebuje vašo spletno storitev** izberite organizacijo, v kateri je spletna storitev.

1. Če je vaša naročnina na Azure Machine Learning v drugem najemniku kot aplikacija Customer Insights, izberite možnost **Vpis** z vašimi poverilnicami za izbrano organizacijo.

1. Izberite **delovne prostore**, povezane z vašo spletno storitvijo.

1. Izberite cevovod Azure Strojno učenje v **Spletna storitev, ki vsebuje vaš model** spustni meni. Nato izberite **Naprej**.
   Preberite več o [objavi prodajnega lijaka v storitvi Strojno učenje Azure z uporabo oblikovalnika](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) ali [SDK-jem](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).

1. Za vsak **vnos spletne storitve** izberite ujemajočo se **entiteto** iz aplikacije Customer Insights. Nato izberite **Naprej**.
   > [!NOTE]
   > Potek dela po meri modela uporablja hevristiko za preslikavo vnosnih polj spletnih storitev v atribute entitete na podlagi imena in podatkovne vrste polja. Napaka bo prikazana, če polja spletne storitve ni mogoče preslikati v entiteto.

   :::image type="content" source="media/intelligence-screen2-updated.png" alt-text="Konfiguriranje poteka dela.":::

1. Za **Izhodni parametri modela**, nastavite naslednje lastnosti:
   - **Ime entitete** za rezultate izhoda plinovoda
   - **Izhod shramba podatkov ime parametra** vašega paketnega cevovoda
   - **Ime parametra izhodne poti** vašega paketnega cevovoda

   :::image type="content" source="media/intelligence-screen3-outputparameters.png" alt-text="Podokno parametrov izhodnih podatkov modela.":::

1. Izberite ustrezni atribut iz **ID stranke v rezultatih** ki identificira stranke in izbrane **Shrani**.

   :::image type="content" source="media/intelligence-screen4-relatetocustomer.png" alt-text="Povezava rezultatov s podoknom podatkov o strankah.":::

   The **Potek dela shranjen** zaslon prikazuje podrobnosti o poteku dela. Če ste konfigurirali potek dela za Strojno učenje cevovod Azure, se Customer Insights poveže z delovnim prostorom, ki vsebuje cevovod. Customer Insights bo dobil a **sodelavec** vlogo v delovnem prostoru Azure.

1. Izberite **Dokončano**. The **Modeli po meri** prikazi strani.

1. Izberite navpično elipso (&vellip;) za potek dela in izberite **Teči**. Tudi vaš delovni tok teče samodejno z vsakim [načrtovano osveževanje](schedule-refresh.md).

## <a name="manage-an-existing-workflow"></a>Upravljajte obstoječi potek dela

Pojdi do **Inteligenca** > **Modeli po meri** za ogled potekov dela, ki ste jih ustvarili.

Izberite potek dela za ogled razpoložljivih dejanj.

- **Uredi** potek dela
- **Teči** potek dela
- [**Izbriši**](#delete-a-workflow) potek dela

### <a name="edit-a-workflow"></a>Urejanje poteka dela

1. Pojdi do **Inteligenca** > **Modeli po meri**.

1. Zraven poteka dela, ki ga želite posodobiti, izberite navpično elipso (&vellip;) in izberite **Uredi**.

1. spremeniti **prikazno ime** če je potrebno, in izberite **Naslednji**.

1. Za vsakogar **Vnos spletne storitve**, posodobite ujemanje **Entiteta** iz Customer Insight, če je potrebno. Nato izberite **Naprej**.

1. Za **Izhodni parametri modela**, spremenite kar koli od naslednjega:
   - **Ime entitete** za rezultate izhoda plinovoda
   - **Izhod shramba podatkov ime parametra** vašega paketnega cevovoda
   - **Ime parametra izhodne poti** vašega paketnega cevovoda

1. Spremenite ujemajoči se atribut iz **ID stranke v rezultatih** za identifikacijo strank. Prek izhodnih podatkov za sklepanje izberite atribut z vrednostmi, podobnimi stolpcu ID stranke pri entiteti stranke. Če v svojem nabor podatkov nimate takega stolpca, izberite atribut, ki edinstveno identificira vrstico.

1. Izberite **Shrani**

### <a name="delete-a-workflow"></a>Brisanje poteka dela

1. Pojdi do **Inteligenca** > **Modeli po meri**.

1. Zraven poteka dela, ki ga želite izbrisati, izberite navpično elipso (&vellip;) in izberite **Izbriši**.

1. Potrdite izbris.

Vaš potek dela bo izbrisan. The [entiteta](entities.md) ki je bil ustvarjen, ko ste ustvarili potek dela, obstaja in si ga lahko ogledate iz **podatki** > **Entitete** strani.

## <a name="view-the-results"></a>Oglejte si rezultate

Rezultati delovnega toka so shranjeni v imenu subjekta, definiranem za **Izhodni parametri modela**. Do teh podatkov dostopajte iz [**podatki** > **Entitete** strani](entities.md) ali z [API dostop](apis.md).

### <a name="api-access"></a>Dostop do API-ja

Za posebno poizvedbo OData za pridobitev podatkov iz entitete modela po meri uporabite naslednjo obliko:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Zamenjati`<your instance id>` z ID-jem vašega okolja Customer Insights, ki se prikaže v naslovni vrstici vašega brskalnika, ko dostopate do Customer Insights.

1. Zamenjati`<custom model output entity>` z imenom subjekta, ki ste ga navedli za **Izhodni parametri modela**.

1. Zamenjati`<guid value>` z ID-jem stranke, do katere želite dostopati. Ta ID je prikazan na [stran s profili strank](customer-profiles.md) v polju ID stranke.

## <a name="frequently-asked-questions"></a>Pogosta vprašanja

- Zakaj pri nastavitvi poteka dela modela po meri ne vidim svojega prodajnega lijaka?
  To težavo pogosto povzroča težava s konfiguracijo v prodajnem lijaku. Zagotovite, da je [vhodni parameter konfiguriran](azure-machine-learning-experiments.md#dataset-configuration) in da so [parametri izhodne podatkovne shrambe in poti](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) prav tako konfigurirani.

- Kaj pomeni napaka »Ne morem shraniti poteka dela obveščanja«? 
  Uporabniki to sporočilo o napaki običajno vidijo, če v delovnem prostoru nimajo skrbniških pravic za dostop lastnika ali uporabnika. Uporabnik potrebuje višjo raven dovoljenj, da storitvi Customer Insights omogoči obdelavo poteka dela kot storitev, namesto da uporablja uporabniške poverilnice za naslednje zagone poteka dela.

- Ali je podprta zasebna povezava končna točka / zasebna povezava za moj potek dela modela po meri?
  Customer Insights trenutno ne podpira zasebnega končna točka za modele po meri takoj po namestitvi, vendar je na voljo ročna rešitev. Za podrobnosti se obrnite na podporo.

## <a name="responsible-ai"></a>Odgovorna umetna inteligenca

Predvidevanja ponujajo zmogljivosti za ustvarjanje boljših izkušenj strank, izboljšanje poslovnih zmogljivosti in virov prihodkov. Močno priporočamo, da vrednost predvidevanja uravnotežite z vplivom in pristranskostmi, ki bi jih lahko uvedli na etičen način. Preberite več o tem, kako Microsoft [obravnava odgovorno ravnanje umetne inteligence](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Preberete lahko tudi o [tehnikah in postopkih za odgovorno strojno učenje](/azure/machine-learning/concept-responsible-ml), specifično za Strojno učenje Azure.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

[!INCLUDE [footer-include](includes/footer-banner.md)]
