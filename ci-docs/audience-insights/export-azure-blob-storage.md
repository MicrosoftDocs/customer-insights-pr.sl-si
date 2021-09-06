---
title: Izvoz podatkov Customer Insights v shrambo zbirke dvojiških podatkov Azure
description: Naučite se, kako konfigurirati povezavo in izvažati v shrambo zbirke dvojiških podatkov.
ms.date: 06/30/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b159f87276581f68e07bb73ffd257080eb3cb56422997b09a613bd7afa4e3980
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034748"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>Izvoz seznamov segmentov in drugih podatkov v shrambo zbirke dvojiških podatkov Azure (predogledna različica)

Podatke iz storitve Customer Insights shranite v shrambi zbirke dvojiških podatkov Azure ali jih uporabite za prenos podatkov v druge aplikacije.

## <a name="set-up-the-connection-to-blob-storage"></a>Nastavitev povezave s Shrambo zbirke dvojiških podatkov

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajanje povezave** in izberite **Shramba zbirke dvojiških podatkov Azure** za konfiguracijo povezave.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vnesite **Ime računa**, **Ključ računa** in **Vsebnik** za svoj račun Shrambe zbirke dvojiških podatkov.
    - Za več informacij o iskanju imena računa in ključa računa shrambe zbirke dvojiških podatkov si oglejte [Upravljanje nastavitev računa za shrambo na portalu Azure](/azure/storage/common/storage-account-manage).
    - Če želite izvedeti, kako ustvariti vsebnik, glejte [Ustvarjanje vsebnika](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Izberite možnost **Shrani**, da dokončate povezavo. 

## <a name="configure-an-export"></a>Konfiguriranje izvoza

Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave. Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

> [!IMPORTANT]
> Če ste vklopili nastavitev začasnega brisanja za račun Shrambe zbirke dvojiških podatkov Azure, izvozi ne bodo uspeli. Za izvoz podatkov v zbirko dvojiških podatkov izklopite začasno brisanje. Za več informacij glejte [Omogoči začasno brisanje zbirke dvojiških podatkov](/azure/storage/blobs/soft-delete-blob-enable.md)

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Za ustvarjanje novega izvoza izberite **Dodaj cilj**.

1. V polju **Povezava za izvoz** izberite povezavo v razdelku Azure Blob Storage. Če se vam poimenovanje tega odseka ne prikaže, to pomeni, da vam ni na voljo nobena tovrstna povezava.

1. Izberite polje poleg vsake entitete, ki jo želite izvoziti na ta cilj.

1. Izberite **Shrani**.

S shranjevanjem izvoza se ta ne zažene takoj.

Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab).     

Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand). 

Izvoženi podatki so shranjeni v vsebniku za Shrambo zbirke dvojiških podatkov, ki ste ga konfigurirali. Naslednje poti map se samodejno ustvarijo v vašem vsebniku:

- Za entitete vira in entitete, ki jih ustvari sistem:   
  `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`  
  - Primer: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
 
- Datoteka model.json za izvožene entitete bo na ravni %ExportDestinationName%.  
  - Primer: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE[footer-include](../includes/footer-banner.md)]
