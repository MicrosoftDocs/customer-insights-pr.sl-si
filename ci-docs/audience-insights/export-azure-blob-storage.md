---
title: Izvozite podatke Customer Insights v shrambo zbirke dvojiških podatkov Azure
description: Naučite se konfigurirati povezavo s shrambo zbirke dvojiških podatkov Azure.
ms.date: 09/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 925b53260e7c633e17d7f172d2dd2d581e982e10
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667159"
---
# <a name="connector-for-azure-blob-storage-preview"></a>Povezovalnik za shrambo zbirke dvojiških podatkov Azure (predogled)

Podatke iz storitve Customer Insights shranite v shrambo zbirke dvojiških podatkov Azure ali jih uporabite za prenos podatkov v druge aplikacije.

## <a name="configure-the-connector-for-azure-blob-storage"></a>Konfiguracija povezovalnika za shrambo zbirke dvojiških podatkov Azure

1. Pri vpogledih v občinstvo izberite **Skrbnik** > **Cilji izvoza**.

1. Pod možnostjo **Shramba zbirke dvojiških podatkov Azure** izberite **Nastavitev**.

1. Vnesite **Ime računa**, **Ključ računa** in **Vsebnik** za svoj račun za shrambo zbirke dvojiških podatkov Azure.
    - Če želite izvedeti več o tem, kako najti ime in ključ računa za shrambo zbirke dvojiških podatkov Azure, glejte [Upravljanje nastavitev računa za shrambo na portalu storitve Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).
    - Če želite izvedeti, kako ustvariti vsebnik, glejte [Ustvarjanje vsebnika](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Dajte svojemu cilju prepoznavno ime v polju **Prikazno ime**.

1. Izberite **Naprej**.

1. Izberite polje poleg vsake entitete, ki jo želite izvoziti na ta cilj.

1. Izberite **Shrani**.

Izvoženi podatki so shranjeni v vsebniku za shrambo zbirke dvojiških podatkov Azure, ki ste ga konfigurirali. Naslednje poti map se samodejno ustvarijo v vašem vsebniku:

- Za entitete vira in entitete, ki jih ustvari sistem: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Primer: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- Model.json za izvožene entitete bo na ravni %ExportDestinationName%
  - Primer: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>Izvoz podatkov

Lahko [izvozite podatke na zahtevo](/export-destinations.md#export-data-on-demand). Izvoz se bo zagnal tudi z vsakim [načrtovanim osveževanjem](system.md#schedule-tab).
