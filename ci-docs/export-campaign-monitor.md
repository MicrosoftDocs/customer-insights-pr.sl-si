---
title: Izvoz segmentov v Campaign Monitor (predogledna različica)
description: Naučite se, kako konfigurirati povezavo in izvažati v Campaign Monitor.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c04fc26dc690cf32b45913257e82b9a0f617185
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196322"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Izvoz segmentov v Campaign Monitor (predogledna različica)

Izvozite segmente poenotenih profilov strank v Campaign Monitor in jih uporabite za tržne dejavnosti.

## <a name="prerequisites"></a>Zahteve

- A [Račun Campaign Monitor](https://www.campaignmonitor.com/) in ustrezne skrbniške poverilnice.
- A [ID seznama nadzornika oglaševalske akcije](https://www.campaignmonitor.com/api/getting-started/#your-list-id).
- A [Ustvarjen ključ API](https://www.campaignmonitor.com/api/getting-started/) od **Nastavitve računa** v Campaign Monitor, da pridobite ID seznama API.
- [Konfigurirani segmenti](segments.md) v Customer Insights.
- Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.

## <a name="known-limitations"></a>Znane omejitve

- Do 1 milijon profilov strank na izvoz v Campaign Monitor, ki lahko traja do 20 minut. Število profilov strank, ki jih lahko izvozite v Campaign Monitor, je odvisno od vaše pogodbe s Campaign Monitor.
- Samo segmenti.

## <a name="set-up-connection-to-campaign-monitor"></a>Nastavitev povezave s storitvijo Campaign Monitor

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajte povezavo** in izberite **Nadzornik oglaševalske akcije**.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Privzeto jo lahko uporabljajo samo skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Preglejte [zasebnost podatkov in skladnost](connections.md#data-privacy-and-compliance) in izberite **strinjam se**.

1. Izberite **Poveži** za inicializiranje povezave s storitvijo Campaign Monitor.

1. Izberite **Preverjanje pristnosti s storitvijo Campaign Monitor** in vnesite skrbniške poverilnice za Campaign Monitor.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite možnost **Dodaj izvoz** za ustvarjanje novega izvoza.

1. V polju **Povezava za izvoz** izberite povezavo v razdelku Campaign Monitor. Če ni na voljo nobena povezava, se obrnite na skrbnika.

1. Vnesite ime za izvoz.

1. Vpišite **ID seznama nadzornika oglaševalske akcije**.

1. V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje, ki predstavlja e-poštni naslov stranke. To je obvezno za izvoz segmentov Campaign Monitor.

1. Izberite segmente, ki jih želite izvoziti.

1. Izberite **Shrani**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
