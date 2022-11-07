---
title: Izvoz segmentov v RollWorks (predogledna različica)
description: Naučite se, kako konfigurirati povezavo in izvažati v RollWorks.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d857bf5d11de86521c4a9d4fc665c020496d89d2
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725145"
---
# <a name="export-segments-to-rollworks-preview"></a>Izvoz segmentov v RollWorks (predogledna različica)

Izvozite segmente poenotenih profilov strank v RollWorks in jih uporabite za oglaševanje.

## <a name="prerequisites"></a>Zahteve

- A [račun RollWorks](https://www.rollworks.com/) in ustrezne skrbniške poverilnice.
- A [ID oglaševalca RollWorks](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).
- [Konfigurirani segmenti](segments.md) v Customer Insights.
- Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.

## <a name="known-limitations"></a>Znane omejitve

- Zasebna povezava v kombinaciji z Bring your own storage (BYOS) ni podprta.
- Do 250.000 profilov strank na izvoz v RollWorks, ki lahko traja do 10 minut. Število profilov strank, ki jih lahko izvozite v RollWorks, je odvisno od vaše pogodbe z RollWorks.
- Samo segmenti.

## <a name="set-up-connection-to-rollworks"></a>Nastavitev povezave s storitvijo RollWorks

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajte povezavo** in izberite **RollWorks**.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo.  Privzeto jo lahko uporabljajo samo skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Preglejte [zasebnost podatkov in skladnost](connections.md#data-privacy-and-compliance) in izberite **strinjam se**.

1. Izberite **Povežite se** za inicializacijo povezave.

1. Izberite **Preverjanje pristnosti s platformo RollWorks** in vnesite skrbniške poverilnice za RollWorks.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite **Dodaj izvoz**.

1. V polju **Povezava za izvoz** izberite povezavo v razdelku RollWorks. Če ni na voljo nobena povezava, se obrnite na skrbnika.

1. Vnesite ime za izvoz.

1. Vpišite **ID oglaševalca RollWorks**.

1. V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje, ki predstavlja e-poštni naslov stranke.

1. Izberite segmente, ki jih želite izvoziti.

1. Izberite **Shrani**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
