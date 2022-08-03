---
title: Izvozi segmente v Adobe Experience Platform (predogled)
description: Naučite se uporabljati segmente Customer Insights v Adobe Experience Platform.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: fcb43e0956c6d1f0ef36b222dd2b718906364244
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195310"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Izvozi segmente v Adobe Experience Platform (predogled)

Izvozite segmente, ki ciljajo na ustrezne ciljne skupine, v Adobe Experience Platform.

:::image type="content" source="media/AEP-flow.png" alt-text="Diagram postopka korakov, opisanih v tem članku.":::

## <a name="prerequisites"></a>Zahteve

- An Adobe Experience Platform dovoljenje.
- An Adobe Standardna licenca oglaševalske akcije.
- An [Račun Azure Blob Storage](/azure/storage/blobs/create-data-lake-storage-account) ime in ključ računa. Za iskanje imena in ključa glejte [Upravljajte nastavitve računa za shranjevanje na portalu Azure](/azure/storage/common/storage-account-manage).
- An [Vsebnik za shranjevanje podatkov Azure Blob](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>Pregled akcije

Da bi bolje razumeli, kako lahko uporabite segmente iz storitve Customer Insights v Adobe Experience Platform, poglejmo fiktivno vzorčno akcijo.

Predpostavimo, da vaše podjetje ponuja mesečno naročninsko storitev za vaše stranke v ZDA. Želeli boste prepoznati stranke, ki še niso podaljšale naročnine, vendar morajo to storiti v naslednjih osmih dneh. Če želite obdržati te stranke, jim po e-pošti pošljite promocijsko ponudbo z uporabo aplikacije Adobe Experience Platform.

V tem primeru želimo promocijsko e-poštno akcijo izvesti enkrat. Ta članek ne zajema primerov uporabe večkratne izvedbe akcije.

## <a name="identify-your-target-audience"></a>Določanje ciljnega občinstva

V našem scenariju predvidevamo, da so e-poštni naslovi strank na voljo v Customer Insights in da so bile njihove promocijske nastavitve analizirane, da bi identificirali člane segmenta.

The [segment, ki ste ga definirali v Customer Insights](segments.md) je poklican **ChurnProneCustomers** in tem strankam nameravate poslati e-poštno promocijo.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Posnetek zaslona strani s segmenti z ustvarjenim segmentom ChurnProneCustomers.":::

E-poštno sporočilo, ki ga želite poslati, bo vsebovalo ime, priimek in končni datum naročnine stranke. Stranke obvešča o popustu, ki ga bodo dobile, če bodo svojo naročnino podaljšale, še preden se konča.

## <a name="export-your-target-audience"></a>Izvoz ciljnega občinstva

Konfigurirali bomo izvoz iz storitve Customer Insights v račun Azure Blob Storage.

### <a name="set-up-connection-to-azure-blob-storage"></a>Nastavite povezavo z Azure Blob Storage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajte povezavo** in izberite **Azure Blob Storage**.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Privzeto jo lahko uporabljajo samo skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Da bi ustvarili račun za shrambo zbirke dvojiških podatkov, v katerega želite izvoziti segment, vnesite **Ime računa**, **Ključ računa** in **Vsebnik**.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Posnetek zaslona konfiguracije računa za shrambo.":::

1. Preglejte [zasebnost podatkov in skladnost](connections.md#data-privacy-and-compliance) in izberite **strinjam se**.

1. Izberite možnost **Shrani**, da dokončate povezavo.

### <a name="configure-an-export"></a>Konfiguriranje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite **Dodaj izvoz**.

1. V polju **Povezava za izvoz** izberite povezavo v razdelku Azure Blob Storage. Če ni na voljo nobena povezava, se obrnite na skrbnika.

1. Vnesite ime za izvoz.

1. Izberite segment, ki ga želite izvoziti. V tem primeru je to **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Posnetek zaslona uporabniškega vmesnika za izbiro segmenta, ko je izbran segment ChurnProneCustomers.":::

1. Izberite **Shrani**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Prepričajte se, da je število zapisov v izvoženem segmentu znotraj dovoljene meje vaše licence za aplikacijo Adobe Campaign Standard.

Izvoženi podatki so shranjeni v vsebniku Azure Blob Storage, ki ste ga konfigurirali. Naslednje poti map se samodejno ustvarijo v vašem vsebniku:

- Za entitete vira in entitete, ki jih ustvari sistem:  

  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

  Primer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

- *model.json* za izvožene entitete se nahaja na ravni *%ExportDestinationName%*.

  Primer: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Določite Experience Data Model (XDM) v storitvi Adobe Experience Platform

Preden lahko izvožene podatke iz Customer Insights uporabite znotraj Adobe Experience Platform, definirajte shemo Experience Data Model in [konfigurirajte podatke za profil stranke v realnem času](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Spoznajte [XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) in [osnove sestave shem](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Uvoz podatkov v aplikacijo Adobe Experience Platform

Uvozite pripravljene občinstvo podatke iz Customer Insights v Adobe Experience Platform.

1. [Ustvarite izvorno povezavo Azure Blob Storage](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).

1. [Konfigurirajte tok podatkov](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) za paketno povezavo shrambe v oblaku, v katero uvozite izhod segmenta iz Customer Insights Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Ustvarjanje občinstva v aplikaciji Adobe Campaign Standard

Za pošiljanje e-poštnega sporočila za to akcijo bomo uporabili aplikacijo Adobe Campaign Standard.

1. [Ustvarite občinstvo](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) v Adobe Standardna oglaševalska akcija z uporabo podatkov v Adobe Experience Platform.

1. [Uporabite graditelj segmentov](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) v Adobe Standard oglaševalske akcije za definiranje občinstvo na podlagi podatkov v Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Ustvarjanje in pošiljanje e-poštnega sporočila z uporabo aplikacije Adobe Campaign Standard

Ustvarite e-poštno vsebino ter [preskusite in pošljite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) e-poštno sporočilo.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Vzorec e-poštnega sporočila s ponudbo za podaljšanje iz aplikacije Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
