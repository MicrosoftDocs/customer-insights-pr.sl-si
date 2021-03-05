---
title: Izvoz podatkov Customer Insights v storitev Azure Data Lake Storage Gen2
description: Preberite o konfiguraciji povezave s storitvijo Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477199"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>Povezovalnik za storitev Azure Data Lake Storage Gen2 (predogled)

Podatke iz storitve Customer Insights shranite v storitvi Azure Data Lake Storage Gen2 ali jih uporabite za prenos podatkov v druge aplikacije.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>Konfiguriranje priključka za Azure Data Lake Storage Gen2

1. Pri vpogledih v občinstvo izberite **Skrbnik** > **Cilji izvoza**.

1. Pod razdelkom **Azure Data Lake Storage Gen2** izberite možnost **Nastavi**.

1. Dajte svojemu cilju prepoznavno ime v polju **Prikazno ime**.

1. Vnesite **ime računa**, **ključ računa** in **vsebnik** za storitev Azure Data Lake Storage Gen2.
    - Če želite izvedeti, kako ustvariti račun za shrambo za uporabo v storitvi Azure Data Lake Storage Gen2, glejte razdelek [Ustvarjanje računa za shrambo](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account). 
    - Če želite izvedeti več o iskanju imena in ključa računa za shrambo Azure Data Lake Gen2, glejte razdelek [Upravljanje nastavitev računa za shrambo na portalu Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).

1. Izberite **Naprej**.

1. Izberite polje poleg vsake entitete, ki jo želite izvoziti na ta cilj.

1. Izberite **Shrani**.

## <a name="export-the-data"></a>Izvoz podatkov

Lahko [izvozite podatke na zahtevo](export-destinations.md#export-data-on-demand). Izvoz se bo zagnal tudi z vsakim [načrtovanim osveževanjem](system.md#schedule-tab).
