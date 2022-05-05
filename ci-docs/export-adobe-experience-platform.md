---
title: Izvoz podatkov iz storitve Customer Insights v storitev Adobe Experience Platform
description: Naučite se uporabljati segmente Customer Insights v Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 42a4e0c6bce67a63b449a541299620ef2f4a3259
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643740"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Uporaba segmentov iz aplikacije Customer Insights v aplikaciji Adobe Experience Platform (predogledna različica)

Kot uporabnik Dynamics 365 Customer Insights, ste morda ustvarili segmente, da bodo vaše marketinške kampanje učinkovitejše s ciljanjem na ustrezno občinstvo. Če želite uporabiti segment iz Customer Insights v Adobe Experience Platform in aplikacije, kot so Adobe Campaign Standard, morate slediti nekaj korakom, opisanim v tem članku.

:::image type="content" source="media/AEP-flow.png" alt-text="Diagram postopka korakov, opisanih v tem članku.":::

## <a name="prerequisites"></a>Zahteve

-   Licenca za Dynamics 365 Customer Insights
-   Licenca za Adobe Experience Platform
-   Licenca za aplikacijo Adobe Campaign Standard
-   Račun za shrambo zbirke dvojiških podatkov Azure

## <a name="campaign-overview"></a>Pregled akcije

Če želite bolje razumeti, kako lahko uporabite segmente iz Customer Insights v Adobe Experience Platform, poglejmo izmišljeno vzorčno kampanjo.

Predpostavimo, da vaše podjetje ponuja mesečno naročninsko storitev za vaše stranke v ZDA. Želeli boste prepoznati stranke, ki še niso podaljšale naročnine, vendar morajo to storiti v naslednjih osmih dneh. Če želite obdržati te stranke, jim po e-pošti pošljite promocijsko ponudbo z uporabo aplikacije Adobe Experience Platform.

V tem primeru želimo promocijsko e-poštno akcijo izvesti enkrat. Ta članek ne zajema primerov uporabe večkratne izvedbe akcije.

## <a name="identify-your-target-audience"></a>Določanje ciljnega občinstva

V našem scenariju predvidevamo, da so e-poštni naslovi strank na voljo v Customer Insights in da so bile analizirane njihove promocijske nastavitve, da se identificirajo člani segmenta.

The [segment, ki ste ga definirali v Customer Insights](segments.md) se imenuje **ChurnProneCustomers** in nameravate tem strankam poslati promocijo po e-pošti.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Posnetek zaslona strani s segmenti z ustvarjenim segmentom ChurnProneCustomers.":::

E-poštno sporočilo, ki ga želite poslati, bo vsebovalo ime, priimek in končni datum naročnine stranke. Stranke obvešča o popustu, ki ga bodo dobile, če bodo svojo naročnino podaljšale, še preden se konča.

## <a name="export-your-target-audience"></a>Izvoz ciljnega občinstva

Ko je naš cilj občinstvo identificiran, lahko konfiguriramo izvoz iz Customer Insights v račun Azure Blob Storage.

### <a name="configure-a-connection"></a>Konfiguriranje povezave

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite možnost **Dodaj povezavo**, nato pa **zbirka dvojiških podatkov Azure**, ali pa izberite možnost **Nastavitev** na ploščici za **zbirko dvojiških podatkov Azure** ter konfigurirajte povezavo.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Konfiguracijska ploščica za shrambo zbirke dvojiških podatkov Azure."::: 

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Da bi ustvarili račun za shrambo zbirke dvojiških podatkov, v katerega želite izvoziti segment, vnesite **Ime računa**, **Ključ računa** in **Vsebnik**.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Posnetek zaslona konfiguracije računa za shrambo."::: 
   
    - Za več informacij o iskanju imena računa in ključa računa shrambe zbirke dvojiških podatkov si oglejte [Upravljanje nastavitev računa za shrambo na portalu Azure](/azure/storage/common/storage-account-manage).
    - Če želite izvedeti, kako ustvariti vsebnik, glejte [Ustvarjanje vsebnika](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Izberite možnost **Shrani**, da dokončate povezavo. 

### <a name="configure-an-export"></a>Konfiguriranje izvoza

Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave. Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite možnost **Dodaj izvoz** za ustvarjanje novega izvoza.

1. V polju **Povezava za izvoz** izberite povezavo v razdelku Azure Blob Storage. Če se vam poimenovanje tega odseka ne prikaže, to pomeni, da vam ni na voljo nobena tovrstna povezava.

1. Izberite segment, ki ga želite izvoziti. V tem primeru je to **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Posnetek zaslona uporabniškega vmesnika za izbiro segmenta, ko je izbran segment ChurnProneCustomers.":::

1. Izberite **Shrani**.

Ko shranite cilj za izvoz, ga najdete v razdelku **Podatki** > **Izvoz**.

Zdaj lahko [izvozite segment na zahtevo](export-destinations.md#run-exports-on-demand). Izvoz se bo zagnal tudi z vsakim [načrtovanim osveževanjem](system.md).

> [!NOTE]
> Prepričajte se, da je število zapisov v izvoženem segmentu znotraj dovoljene meje vaše licence za aplikacijo Adobe Campaign Standard.

Izvoženi podatki so shranjeni v vsebniku za shrambo zbirke dvojiških podatkov Azure, ki ste ga konfigurirali zgoraj. V vsebniku se samodejno ustvari naslednja pot do mape:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Primer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

*model.json* za izvožene entitete se nahaja na ravni *%ExportDestinationName%*.

Primer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Določite Experience Data Model (XDM) v storitvi Adobe Experience Platform

Preden lahko izvožene podatke iz Customer Insights uporabite znotraj Adobe Experience Platform, moramo definirati shemo Experience Data Model in [konfigurirajte podatke za profil stranke v realnem času](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Spoznajte [XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) in [osnove sestave shem](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Uvoz podatkov v aplikacijo Adobe Experience Platform

Zdaj, ko je vse na svojem mestu, moramo uvoziti pripravljene podatke občinstvo iz Customer Insights v Adobe Experience Platform.

Najprej [ustvarite izvorno povezavo za shrambo zbirke dvojiških podatkov Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Ko določite izvorno povezavo, [konfigurirajte tok podatkov](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) za paketno povezavo za shranjevanje v oblaku za uvoz izhoda segmenta iz Customer Insights Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Ustvarjanje občinstva v aplikaciji Adobe Campaign Standard

Za pošiljanje e-poštnega sporočila za to akcijo bomo uporabili aplikacijo Adobe Campaign Standard. Po uvozu podatkov v storitev Adobe Experience Platform moramo [ustvariti občinstvo](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) v aplikaciji Adobe Campaign Standard z uporabo podatkov v storitvi Adobe Experience Platform.


Preberite, kako [uporabiti graditelja segmentov](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) v aplikaciji Adobe Campaign Standard za opredelitev občinstva na podlagi podatkov v storitvi Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Ustvarjanje in pošiljanje e-poštnega sporočila z uporabo aplikacije Adobe Campaign Standard

Ustvarite e-poštno vsebino ter [preskusite in pošljite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-poštno sporočilo.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Vzorec e-poštnega sporočila s ponudbo za podaljšanje iz aplikacije Adobe Campaign Standard.":::
