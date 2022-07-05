---
title: Izvozi podatke v Azure Data Lake Storage Gen2 (predogled)
description: Preberite o konfiguraciji povezave s storitvijo Azure Data Lake Storage Gen2.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: c2446fba425203d2910b82134b73543a73c7ecf8
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082669"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>Izvozi podatke v Azure Data Lake Storage Gen2 (predogled)

Podatke iz storitve Customer Insights shranite v račun Data Lake Storage Gen2 ali jih uporabite za prenos podatkov v druge aplikacije.

## <a name="known-limitations"></a>Znane omejitve

1. Za storitev Azure Data Lake Storage Gen2 lahko izbirate med [ravnjo standardne učinkovitosti delovanja in učinkovitosti delovanja Premium](/azure/storage/blobs/create-data-lake-storage-account), ko ustvarjate račun za shranjevanje za jezero podatkov. Če izberete raven učinkovitosti delovanja Premium, izberite bloke zbirke dvojiških podatkov za različico premium kot vrsto računa.

## <a name="set-up-the-connection-to-azure-data-lake-storage-gen2"></a>Nastavitev povezave s storitvijo Azure Data Lake Storage Gen2

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajanje povezave** in izberite **Azure Data Lake Gen 2** za konfiguracijo povezave.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vnesite **ime računa**, **ključ računa** in **vsebnik** za storitev Azure Data Lake Storage Gen2.
    - Če želite izvedeti, kako ustvariti račun za shrambo za uporabo v storitvi Azure Data Lake Storage Gen2, glejte razdelek [Ustvarjanje računa za shrambo](/azure/storage/blobs/create-data-lake-storage-account). 
    - Za več informacij imenu računa in ključa računa shrambe Azure Data Lake Gen2 glejte [Upravljanje nastavitev računa shrambe v portalu Azure](/azure/storage/common/storage-account-manage).

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

Ta izvoz lahko konfigurirate, če imate dostop do tovrstne povezave. Za več informacij glejte razdelek [Dovoljenja, potrebna za konfiguriranje izvoza](export-destinations.md#set-up-a-new-export).

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite možnost **Dodaj izvoz** za ustvarjanje novega izvoza.

1. V polju **Povezava za izvoz** izberite povezavo v razdelku **Azure Data Lake**. Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.

1. Izberite polje poleg vsake entitete, ki jo želite izvoziti na ta cilj.

1. Izberite **Shrani**.

S shranjevanjem izvoza se ta ne zažene takoj.

Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab).
Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand).

Izvoženi podatki so shranjeni v vsebniku za shrambo Azure Data Lake Gen 2, ki ste ga konfigurirali.

> [!TIP]
> Izvoz entitet, ki vsebujejo veliko količino podatkov, lahko pri vsakem izvozu povzroči več datotek CSV v isti mapi. Delitev izvozov se zgodi zaradi učinkovitosti, da se zmanjša čas, potreben za dokončanje izvoza.

[!INCLUDE [footer-include](includes/footer-banner.md)]
