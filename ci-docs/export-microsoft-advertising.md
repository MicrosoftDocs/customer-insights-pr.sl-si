---
title: Izvoz segmentov v Microsoft Advertising (predogledna različica)
description: Naučite se, kako konfigurirati povezavo in izvažati v storitev Microsoft Advertising.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 44217e7823ffbe14d232b3e33de1b4ea6ed69dcf
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196552"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Izvoz segmentov v Microsoft Advertising (predogledna različica)

Izvozite segmente Customer Insights v Microsoft Advertising, da ustvarite ciljne skupine za storitev Customer Match. Uporabite te ciljne skupine za svoje oglaševalske akcije.

## <a name="prerequisites"></a>Zahteve

- A [Račun Microsoft Advertising](https://ads.microsoft.com/) in ustrezne skrbniške poverilnice.
- ID stranke in ID računa Microsoft Advertising. Poiščite ID stranke (`cid`) in ID računa (`aid`) v parametrih URL-ja, ko ste prijavljeni v Microsoft Advertising.
- Pogoji uporabe Povezovanja strank so sprejeti.
- [Konfigurirani segmenti](segments.md) v Customer Insights.
- Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.

## <a name="known-limitations"></a>Znane omejitve

- Do 500.000 profilov strank na izvoz v Microsoft Advertising, kar lahko traja do 10 minut.
- Samo segmenti.

## <a name="set-up-connection-to-microsoft-advertising"></a>Nastavite povezavo z Microsoft Advertising

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajte povezavo** in izberite **Microsoftovo oglaševanje**.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Privzeto so nastavljeni skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vnesite **ID stranke Microsoft Advertising**.

1. Preglejte [zasebnost podatkov in skladnost](connections.md#data-privacy-and-compliance) in izberite **strinjam se**.

1. Izberite **Povežite se** za inicializacijo povezave.

1. Izberite **Preverjanje pristnosti s storitvijo Microsoft Advertising** in vnesite skrbniške poverilnice za Microsoft Advertising.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite **Dodaj izvoz**.

1. V polju **Povezava za izvoz** izberite povezavo v razdelku Microsoft Advertising. Če ni na voljo nobena povezava, se obrnite na skrbnika.

1. Vnesite ime za izvoz.

1. Izberite segmente, ki jih želite izvoziti. Ciljne skupine storitve Customer Match v programu Microsoft Advertising se samodejno ustvarijo z imeni segmentov, ki so izbrani za izvoz. Vsak segment bo prikazal ločeno ciljno skupino za storitev Customer Match.

1. Vpišite **ID stranke Microsoft Advertising in ID računa**.

1. V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje z e-poštnim naslovom stranke.

1. Izberite **Shrani**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
