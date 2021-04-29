---
title: Izvoz podatkov Customer Insights v storitev Azure Data Lake Storage Gen2
description: Preberite o konfiguraciji povezave s storitvijo Azure Data Lake Storage Gen2.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760071"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a>Nastavitev povezave s storitvijo Azure Data Lake Storage Gen2 (predogledna različica)

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

Izvoz se izvede z vsako [načrtovano osvežitvijo](system.md#schedule-tab). Lahko tudi [izvozite podatke na zahtevo](export-destinations.md#run-exports-on-demand). 

Izvoženi podatki so shranjeni v vsebniku za shrambo Azure Data Lake Gen 2, ki ste ga konfigurirali. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
