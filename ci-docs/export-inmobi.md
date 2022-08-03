---
title: Izvoz podatkov Customer Insights v InMobi
description: Naučite se konfigurirati povezavo in izvoziti v InMobi.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195908"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>Izvoz podatkov Customer Insights v InMobi (predogled)

Izvozite sezname segmentov ali druge podatke iz svojega primerka Customer Insights v [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Zahteve

- An [račun InMobi](https://www.inmobi.com/) in skrbniške poverilnice.
- An [Račun Azure Blob Storage](/azure/storage/blobs/create-data-lake-storage-account) ime in ključ računa. Za iskanje imena in ključa glejte [Upravljajte nastavitve računa za shranjevanje na portalu Azure](/azure/storage/common/storage-account-manage).
- An [Vsebnik za shranjevanje podatkov Azure Blob](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) za izvoz podatkov InMobi.
- InMobi bo ustvaril neposredno povezavo z vašo shrambo Blob Storage in konfiguriral samodejni uvoz vaših podatkov v InMobi. Za začetek postopka se obrnite na predstavnika InMobi.

## <a name="known-limitations"></a>Znane omejitve

- Za Azure Blob Storage izberite med [Standardna zmogljivost in raven zmogljivosti Premium](/azure/storage/blobs/storage-blob-performance-tiers). Če izberete raven učinkovitosti delovanja Premium, izberite [bloki zbirke dvojiških podatkov premium kot vrsto računa](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-blob-storage"></a>Nastavite povezavo z Azure Blob Storage

[Nastavite povezavo s shrambo blob Azure](export-azure-blob-storage.md).

## <a name="configure-an-export"></a>Konfiguriranje izvoza

[Konfigurirajte izvoz](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
