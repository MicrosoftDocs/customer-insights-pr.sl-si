---
title: Izvoz podatkov storitve Customer Insights na platformo Adobe Experience Platform
description: Preberite, kako uporabljati segmente vpogleda v občinstvo na platformi Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 884f4d30f354bed29909d57be84dce4c8e46965a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760121"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Uporaba segmentov storitve Customer Insights na platformi Adobe Experience Platform (predogledna različica)

Kot uporabnik vpogledov v občinstvo za Dynamics 365 Customer Insights ste morda ustvarili segmente za izboljšanje učinkovitosti svojih trženjskih akcij s ciljanjem na ustrezno občinstvo. Če želite uporabiti segment iz vpogledov v občinstvo na platformi Adobe Experience Platform in v aplikacijah, kot je Adobe Campaign Standard, morate slediti nekaj korakom, ki so opisani v tem članku.

:::image type="content" source="media/AEP-flow.png" alt-text="Diagram postopka korakov, opisanih v tem članku.":::

## <a name="prerequisites"></a>Zahteve

-   Licenca za Dynamics 365 Customer Insights
-   Licenca za Adobe Experience Platform
-   Licenca aplikacije Adobe Campaign Standard
-   Račun za shrambo zbirke dvojiških podatkov Azure

## <a name="campaign-overview"></a>Pregled akcije

Da boste bolje razumeli, kako lahko uporabite segmente iz vpogledov v občinstvo na platformi Adobe Experience Platform, si oglejmo izmišljeno vzorčno akcijo.

Predpostavimo, da vaše podjetje ponuja mesečno naročninsko storitev za vaše stranke v ZDA. Želeli boste prepoznati stranke, ki še niso podaljšale naročnine, vendar morajo to storiti v naslednjih osmih dneh. Če želite obdržati te stranke, jim pošljite promocijsko ponudbo po e-pošti prek platforme Adobe Experience Platform.

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

1. Izberite možnost **Dodaj povezavo** in izberite shrambo **Azure Blob** oziroma na ploščici za shrambo **Azure Blob** izberite možnost **Nastavitev**.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Konfiguracijska ploščica za shrambo zbirke dvojiških podatkov Azure."::: za konfiguriranje povezave.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vnesite **Ime računa**, **Ključ računa** in **Vsebnik** računa za shrambo Blob, v katerega želite izvoziti segment.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Posnetek zaslona konfiguracije računa za shrambo. "::: 
   
    - Za več informacij o iskanju imena računa in ključa računa shrambe Blob glejte razdelek [Upravljanje nastavitev računa shrambe v portalu Azure](/azure/storage/common/storage-account-manage).
    - Če želite izvedeti, kako ustvariti vsebnik, glejte [Ustvarjanje vsebnika](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Izberite možnost **Shrani**, da dokončate povezavo. 

### <a name="configure-an-export"></a>Konfiguriranje izvoza

Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave. Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite možnost **Dodaj izvoz** za ustvarjanje novega izvoza.

1. V polju **Povezava za izvoz** izberite povezavo v razdelku Azure Blob Storage. Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.

1. Izberite segment, ki ga želite izvoziti. V tem primeru je to **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Posnetek zaslona uporabniškega vmesnika za izbiro segmenta, ko je izbran segment ChurnProneCustomers.":::

1. Izberite **Shrani**.

Ko shranite cilj za izvoz, ga najdete v razdelku **Podatki** > **Izvoz**.

Zdaj lahko [izvozite segment na zahtevo](export-destinations.md#run-exports-on-demand). Izvoz se bo zagnal tudi z vsakim [načrtovanim osveževanjem](system.md).

> [!NOTE]
> Prepričajte se, da je število zapisov v izvoženem segmentu znotraj dovoljene omejitve vaše licence Adobe Campaign Standard.

Izvoženi podatki so shranjeni v vsebniku za shrambo zbirke dvojiških podatkov Azure, ki ste ga konfigurirali zgoraj. V vsebniku se samodejno ustvari naslednja pot do mape:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Primer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

*model.json* za izvožene entitete se nahaja na ravni *%ExportDestinationName%*.

Primer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Določanje podatkovnega modela Experience Data Model (XDM) na platformi Adobe Experience Platform

Preden lahko izvožene podatke iz vpogledov v občinstvo uporabimo na platformi Adobe Experience Platform, moramo določiti shemo podatkovnega modela Experience Data Model in [konfigurirati podatke za profil stranke v realnem času](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Spoznajte [XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) in [osnove sestave shem](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Uvoz podatkov na platformo Adobe Experience Platform

Zdaj, ko je vse na svojem mestu, moramo iz vpogledov v občinstvo na platformo Adobe Experience Platform uvoziti pripravljene podatke o občinstvu za ustvarjanje profilov.

Najprej [ustvarite izvorno povezavo za shrambo zbirke dvojiških podatkov Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Ko določite izvorne povezave, [konfigurirajte podatkovni tok](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) za paketno povezavo shranjevanja v oblaku, da uvozite izhod segmenta iz vpogledov v občinstvo na platformo Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Ustvarjanje občinstva v aplikaciji Adobe Campaign Standard

Za pošiljanje e-poštnega sporočila za to akcijo bomo uporabili aplikacijo Adobe Campaign Standard. Po uvozu podatkov na platformo Adobe Experience Platform moramo v aplikaciji Adobe Campaign Standard [ustvariti občinstvo](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission), pri čemer uporabimo podatke na platformi Adobe Experience Platform.

Preberite, kako v aplikaciji Adobe Campaign Standard [uporabite graditelja segmentov](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment), da določite občinstvo na podlagi podatkov na platformi Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Ustvarjanje in pošiljanje e-poštnih sporočil z aplikacijo Adobe Campaign Standard

Ustvarite e-poštno vsebino ter [preskusite in pošljite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-poštno sporočilo.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Vzorec e-poštnega sporočila s ponudbo za obnovitev iz aplikacije Adobe Campaign Standard.":::
