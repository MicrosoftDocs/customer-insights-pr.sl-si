---
title: Izvoz podatkov iz storitve Customer Insights v storitev Adobe Experience Platform
description: Preberite, kako uporabite segmente vpogledov občinstva v aplikaciji Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: fac976a49b1b5c5485b75e1262135738c913bd2230be7df8aa0ec12c59734053
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032137"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Uporaba segmentov iz aplikacije Customer Insights v aplikaciji Adobe Experience Platform (predogledna različica)

Kot uporabnik vpogleda občinstva v storitvi Dynamics 365 Customer Insights ste morda ustvarili segmente, da bi z njihovo pomočjo, in sicer z izborom relevantnejšega ciljnega občinstva, izpopolnili svoje trženjske akcije. Če želite uporabiti segment iz vpogledov občinstva v storitvi Adobe Experience Platform in aplikacijah, kot je Adobe Campaign Standard, morate slediti korakom, opisanih v tem članku.

:::image type="content" source="media/AEP-flow.png" alt-text="Diagram postopka korakov, opisanih v tem članku.":::

## <a name="prerequisites"></a>Zahteve

-   Licenca za Dynamics 365 Customer Insights
-   Licenca za Adobe Experience Platform
-   Licenca za aplikacijo Adobe Campaign Standard
-   Račun za shrambo zbirke dvojiških podatkov Azure

## <a name="campaign-overview"></a>Pregled akcije

Če želite bolje razumeti, kako lahko uporabite segmente iz vpogledov občinstva v storitvi Adobe Experience Platform, si poglejte izmišljeno vzorčno akcijo.

Predpostavimo, da vaše podjetje ponuja mesečno naročninsko storitev za vaše stranke v ZDA. Želeli boste prepoznati stranke, ki še niso podaljšale naročnine, vendar morajo to storiti v naslednjih osmih dneh. Če želite obdržati te stranke, jim po e-pošti pošljite promocijsko ponudbo z uporabo aplikacije Adobe Experience Platform.

V tem primeru želimo promocijsko e-poštno akcijo izvesti enkrat. Ta članek ne zajema primerov uporabe večkratne izvedbe akcije.

## <a name="identify-your-target-audience"></a>Določanje ciljnega občinstva

V našem scenariju predpostavljamo, da so e-poštni naslovi strank na voljo v vpogledih v občinstvo in da so bile njihove promocijske nastavitve analizirane za prepoznavanje članov segmenta.

[Segment, ki ste ga opredelili v vpogledih v občinstvo](segments.md), se imenuje **ChurnProneCustomers** in tem strankam nameravate poslati e-poštno promocijo.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Posnetek zaslona strani s segmenti z ustvarjenim segmentom ChurnProneCustomers.":::

E-poštno sporočilo, ki ga želite poslati, bo vsebovalo ime, priimek in končni datum naročnine stranke. Stranke obvešča o popustu, ki ga bodo dobile, če bodo svojo naročnino podaljšale, še preden se konča.

## <a name="export-your-target-audience"></a>Izvoz ciljnega občinstva

Ko je ciljno občinstvo določeno, lahko konfiguriramo izvoz iz vpogledov v občinsto v račun za shrambo zbirke dvojiških podatkov Azure.

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

Preden se lahko izvoženi podatki iz vpogledov občinstva uporabijo v storitvi Adobe Experience Platform, moramo določiti shemo modela Experience Data Model in [konfigurirati podatke za sprotni profil stranke](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Spoznajte [XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) in [osnove sestave shem](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Uvoz podatkov v aplikacijo Adobe Experience Platform

Zdaj ko je vse pripravljeno, moramo uvoziti pripravljene podatke o občinstvu iz vpogledov občinstva v storitev Adobe Experience Platform.

Najprej [ustvarite izvorno povezavo za shrambo zbirke dvojiških podatkov Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Ko določite izvorno povezavo, [konfigurirajte podatkovni tok](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) za paketno povezavo za shrambo v oblaku, da uvozite izhod segmenta iz vpogledov občinstva v storitev Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Ustvarjanje občinstva v aplikaciji Adobe Campaign Standard

Za pošiljanje e-poštnega sporočila za to akcijo bomo uporabili aplikacijo Adobe Campaign Standard. Po uvozu podatkov v storitev Adobe Experience Platform moramo [ustvariti občinstvo](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) v aplikaciji Adobe Campaign Standard z uporabo podatkov v storitvi Adobe Experience Platform.


Preberite, kako [uporabiti graditelja segmentov](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) v aplikaciji Adobe Campaign Standard za opredelitev občinstva na podlagi podatkov v storitvi Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Ustvarjanje in pošiljanje e-poštnega sporočila z uporabo aplikacije Adobe Campaign Standard

Ustvarite e-poštno vsebino ter [preskusite in pošljite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-poštno sporočilo.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Vzorec e-poštnega sporočila s ponudbo za podaljšanje iz aplikacije Adobe Campaign Standard.":::
