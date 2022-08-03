---
title: Izvoz segmentov v Snapchat (predogledna različica)
description: Naučite se, kako konfigurirati povezavo in izvažati v Snapchat.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 85443dcb54ebd58182997fbb56a738901f2a051f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195402"
---
# <a name="export-segments-to-snapchat-preview"></a>Izvoz segmentov v Snapchat (predogledna različica)

Izvozite segmente poenotenih profilov strank v Snapchat in jih uporabite za oglaševanje.

## <a name="prerequisites"></a>Zahteve

- A [Snapchat Business račun](https://business.snapchat.com/), a [Račun Snapchat Ads](https://ads.snapchat.com/) in ustrezne skrbniške poverilnice. Biti morate vsaj član računa organizacije in upravitelj podatkov določenega računa za oglase.
- Vsaj en upravitelj občinstvo v Snapchatu občinstvo vrste SAM (Snap občinstvo Match).
- The [ID segmenta Snapchat/občinstvo](https://businesshelp.snapchat.com/s/article/custom-audiences). ID občinstvo lahko najdete v URL-ju po izbiri občinstvo v Snapchat občinstvo Managerju.
- [Konfigurirani segmenti](segments.md) v Customer Insights.
- Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.

## <a name="known-limitations"></a>Znane omejitve

- Do 1 milijon profilov strank, katerih dokončanje lahko traja do 15 minut.
- Samo segmenti.

## <a name="set-up-connection-to-snapchat"></a>Nastavitev povezave s storitvijo Snapchat

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajte povezavo** in izberite **Snapchat**.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Privzeto jo lahko uporabljajo samo skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Preglejte [zasebnost podatkov in skladnost](connections.md#data-privacy-and-compliance) in izberite **strinjam se**.

1. Izberite **Povežite se** za inicializacijo povezave.

1. Izberite **Preverjanje pristnosti z aplikacijo Snapchat** in vnesite skrbniške poverilnice za Snapchat.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite **Dodaj izvoz**.

1. V polju **Povezava za izvoz** izberite povezavo v razdelku Snapchat. Če ni na voljo nobena povezava, se obrnite na skrbnika.

1. Vnesite ime za izvoz.

1. Vnesite **ID segmenta Snapchat/občinstvo**.

1. V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje, ki predstavlja e-poštni naslov stranke.

1. Izberite segmente, ki jih želite izvoziti.

1. Izberite **Shrani**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
