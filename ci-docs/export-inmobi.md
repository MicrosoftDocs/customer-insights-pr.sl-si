---
title: Izvozite podatke Customer Insights v InMobi
description: Naučite se konfigurirati povezavo in izvoziti v InMobi.
ms.date: 06/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8261c8adfe231792e70fc85432237cf73d5cd5a7
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9059620"
---
# <a name="export-segment-list-and-other-data-to-inmobi-preview"></a>Izvozi seznam segmentov in druge podatke v InMobi (predogled)

Izvozite sezname segmentov ali druge podatke iz svojega primerka Customer Insights v [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Zahteve

1. Imate [InMobi račun](https://www.inmobi.com/) in skrbniške poverilnice.
1. Imate ime računa za shranjevanje Azure Blob in ustrezen ključ računa. Za več informacij glejte [Upravljajte nastavitve računa za shranjevanje na portalu Azure](/azure/storage/common/storage-account-manage). V računu za shranjevanje je vsebnik za izvoz podatkov inMobi. Za več informacij glejte [Ustvarite vsebnik](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).
1. InMobi bo ustvaril neposredno povezavo z vašim Blob Storage in konfiguriral samodejni uvoz vaših podatkov v InMobi. Za začetek postopka se obrnite na svojega predstavnika InMobi.

## <a name="known-limitations"></a>Znane omejitve

1. Za Azure Blob Storage lahko izbirate med [Standardna zmogljivost in raven zmogljivosti Premium](/azure/storage/blobs/storage-blob-performance-tiers). Če izberete raven učinkovitosti delovanja Premium, izberite [bloki zbirke dvojiških podatkov premium kot vrsto računa](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-azure-blob-storage-and-configure-an-export"></a>Nastavite povezavo do Azure Blob Storage in konfigurirajte izvoz

1. Sledite navodilom za [nastavite povezavo z vašim Azure Blob Storage](export-azure-blob-storage.md).
2. Sledite navodilom za [konfigurirajte izvoz](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
