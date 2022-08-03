---
title: Izvozi podatke v Azure Data Lake Storage Gen2 (predogled)
description: Preberite o konfiguraciji povezave s storitvijo Azure Data Lake Storage Gen2.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196460"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>Izvozi podatke v Azure Data Lake Storage Gen2 (predogled)

Podatke iz storitve Customer Insights shranite v račun Data Lake Storage Gen2 ali jih uporabite za prenos podatkov v druge aplikacije.

## <a name="prerequisites"></a>Zahteve

- A [račun za shranjevanje za uporabo z Azure Data Lake Gen2](/azure/storage/blobs/create-data-lake-storage-account). Če želite poiskati ime in ključ računa za shranjevanje, glejte [Upravljajte nastavitve računa za shranjevanje na portalu Azure](/azure/storage/common/storage-account-manage).
- An [Vsebnik za shranjevanje podatkov Azure Blob](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Znane omejitve

- Za Azure Data Lake Storage Gen2, izbiraj med [Standardna zmogljivost in raven zmogljivosti Premium](/azure/storage/blobs/create-data-lake-storage-account). Če izberete raven učinkovitosti delovanja Premium, izberite [bloki zbirke dvojiških podatkov premium kot vrsto računa](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>Nastavite povezavo z Azure Data Lake Storage Gen2

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajte povezavo** in izberite **Azure Data Lake Gen 2**.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Privzeto jo lahko uporabljajo samo skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vnesite **ime računa**, **ključ računa** in **vsebnik** za storitev Azure Data Lake Storage Gen2.

1. Preglejte [zasebnost podatkov in skladnost](connections.md#data-privacy-and-compliance) in izberite **strinjam se**.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite **Dodaj izvoz**.

1. V **Povezava za izvoz** izberite povezavo v razdelku Azure Data Lake. Če ni na voljo nobena povezava, se obrnite na skrbnika.

1. Vnesite ime za izvoz.

1. Vnesite ime mape za Azure Data Lake Storage Gen2 shranjevanje.

1. Izberite polje poleg vsake entitete, ki jo želite izvoziti na ta cilj.

1. Izberite **Shrani**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Izvoženi podatki so shranjeni v vsebniku za shrambo Azure Data Lake Gen 2, ki ste ga konfigurirali.

> [!TIP]
> Izvoz entitet, ki vsebujejo veliko količino podatkov, lahko povzroči več datotek CSV v isti mapi za vsak izvoz. Razdelitev izvozov se zgodi zaradi učinkovitosti, da se zmanjša čas, potreben za dokončanje izvoza.

[!INCLUDE [footer-include](includes/footer-banner.md)]
