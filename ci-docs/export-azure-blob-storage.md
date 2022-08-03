---
title: Izvoz podatkov v shrambo blob Azure (predogled)
description: Naučite se, kako konfigurirati povezavo in izvažati v shrambo zbirke dvojiških podatkov.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22593ed05f403a40fe494e30f807b57658594f01
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195724"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Izvoz podatkov v shrambo blob Azure (predogled)

Podatke iz storitve Customer Insights shranite v shrambi zbirke dvojiških podatkov Azure ali jih uporabite za prenos podatkov v druge aplikacije.

## <a name="prerequisites"></a>Zahteve

- An [Račun Azure Blob Storage](/azure/storage/blobs/create-data-lake-storage-account) ime in ključ računa. Za iskanje imena in ključa glejte [Upravljajte nastavitve računa za shranjevanje na portalu Azure](/azure/storage/common/storage-account-manage).
- An [Vsebnik za shranjevanje podatkov Azure Blob](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Znane omejitve

- Za Azure Blob Storage izberite med [Standardna zmogljivost in raven zmogljivosti Premium](/azure/storage/blobs/storage-blob-performance-tiers). Če izberete raven učinkovitosti delovanja Premium, izberite [bloki zbirke dvojiških podatkov premium kot vrsto računa](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-blob-storage"></a>Nastavite povezavo s shrambo Blob Storage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajte povezavo** in izberite **Azure Blob Storage**.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Privzeto jo lahko uporabljajo samo skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vnesite **Ime računa**, **Ključ računa** in **Vsebnik** za svoj račun Shrambe zbirke dvojiških podatkov.

1. Preglejte [zasebnost podatkov in skladnost](connections.md#data-privacy-and-compliance) in izberite **strinjam se**.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

Če želite konfigurirati ta izvoz, morate imeti [dovoljenje](export-destinations.md#set-up-a-new-export) za to vrsto povezave.

> [!IMPORTANT]
> Če ste vklopili [nastavitev mehkega brisanja](/azure/storage/blobs/soft-delete-blob-enable) za račun Azure Blob Storage izvozi ne bodo uspeli. Za izvoz podatkov v zbirko dvojiških podatkov izklopite začasno brisanje.

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite **Dodaj izvoz**.

1. V polju **Povezava za izvoz** izberite povezavo v razdelku Azure Blob Storage. Če ni na voljo nobena povezava, se obrnite na skrbnika.

1. Vnesite ime za izvoz.

1. Vnesite ime mape za shrambo Blob.

1. Izberite polje poleg vsake entitete, ki jo želite izvoziti na ta cilj.

1. Izberite **Shrani**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Izvoženi podatki so shranjeni v vsebniku za Shrambo zbirke dvojiških podatkov, ki ste ga konfigurirali. Naslednje poti map se samodejno ustvarijo v vašem vsebniku:

- Za entitete vira in entitete, ki jih ustvari sistem:   
  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*  

  Primer: Dynamics365CustomerInsights/CustomerInsights_ abcd1234-4312-11f4-93dc-24f72f43e7d5 /BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv
  
  > [!TIP]
  > Izvoz entitet, ki vsebujejo veliko količino podatkov, lahko povzroči več datotek CSV v isti mapi za vsak izvoz. Razdelitev izvozov se zgodi zaradi učinkovitosti, da se zmanjša čas, potreben za dokončanje izvoza.

- Model.json za izvožene entitete se nahaja na *%ExportDestinationName%* raven.  
  
  Primer: Dynamics365CustomerInsights/CustomerInsights_ abcd1234-4312-11f4-93dc-24f72f43e7d5 /BlobExport/model.json

[!INCLUDE [footer-include](includes/footer-banner.md)]
