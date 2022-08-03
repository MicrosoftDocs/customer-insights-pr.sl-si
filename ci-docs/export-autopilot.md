---
title: Izvoz segmentov v Autopilot (predogledna različica)
description: Naučite se, kako konfigurirati povezavo in izvažati v storitev Autopilot.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 449d2c5e32697e4a5d2c9dff4a5a1cbdb26aeb4d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195080"
---
# <a name="export-segments-to-autopilot-preview"></a>Izvoz segmentov v Autopilot (predogledna različica)

Izvozite segmente poenotenih profilov strank v storitev Autopilot in jih uporabite za e-poštno trženje v storitvi Autopilot.

## <a name="prerequisites-for-a-connection"></a>Predpogoji za povezavo

- An [Račun avtopilota](https://www.autopilothq.com/) in ustrezne skrbniške poverilnice.
- An [Ključ API za avtopilot](https://autopilot.docs.apiary.io/#)
- [Konfigurirani segmenti](segments.md) v Customer Insights.
- Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.

## <a name="known-limitations"></a>Znane omejitve

- Do 100.000 profilov strank na izvoz v Autopilot, ki lahko traja do nekaj ur. Število profilov strank, ki jih lahko izvozite v Autopilot, je odvisno od vaše pogodbe z Autopilotom.
- Samo segmenti.

## <a name="set-up-connection-to-autopilot"></a>Nastavitev povezave s storitvijo Autopilot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajte povezavo** in izberite **Avtopilot**.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Privzeto jo lahko uporabljajo samo skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vpišite ključ API-ja za storitev Autopilot.

1. Preglejte [zasebnost podatkov in skladnost](connections.md#data-privacy-and-compliance) in izberite **strinjam se**.

1. Izberite **Povežite se** za inicializacijo povezave.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite **Dodaj izvoz**.

1. V polju **Povezava za izvoz** izberite povezavo v razdelku Autopilot. Če ni na voljo nobena povezava, se obrnite na skrbnika.

1. Vnesite ime za izvoz.

1. V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje, ki predstavlja e-poštni naslov stranke.

1. Po želji izvozite druga polja, kot je npr **ime** in **priimek**.

1. Izberite segmente, ki jih želite izvoziti ob upoštevanju znanih omejitev.

1. Izberite **Shrani**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
