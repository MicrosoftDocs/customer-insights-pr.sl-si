---
title: Izvoz segmentov v Omnisend (predogledna različica)
description: Naučite se, kako konfigurirati povezavo in izvažati v Omnisend.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c23d6d3538c4df6006c14064f95379169af06622
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196184"
---
# <a name="export-segments-to-omnisend-preview"></a>Izvoz segmentov v Omnisend (predogledna različica)

Izvozite segmente poenotenih profilov strank v Omnisend in jih uporabite za tržne dejavnosti.

## <a name="prerequisites"></a>Zahteve

- An [Račun Omnisend](https://www.omnisend.com/) in ustrezne skrbniške poverilnice.
- An [Ključ Omnisend API](https://support.omnisend.com/en/articles/1061890-generating-api-key).
- [Konfigurirani segmenti](segments.md) v Customer Insights.
- Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.

## <a name="known-limitations"></a>Znane omejitve

- Do 1 milijon profilov strank na izvoz v Omnisend, ki lahko traja do štiri ure. Število profilov strank, ki jih lahko izvozite v storitev Omnisend, je odvisno od vaše pogodbe s storitvijo Omnisend.
- Samo segmenti.

## <a name="set-up-connection-to-omnisend"></a>Nastavitev povezave s storitvijo Omnisend

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajte povezavo** in izberite **Omnisend**.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Privzeto je storitev namenjena samo skrbnikom. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vpišite ključ API-ja za storitev Omnisend.

1. Preglejte [zasebnost podatkov in skladnost](connections.md#data-privacy-and-compliance) in izberite **strinjam se**.

1. Izberite **Povežite se** za inicializacijo povezave.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite **Dodaj izvoz**.

1. V polju **Povezava za izvoz** izberite povezavo v razdelku Omnisend. Če ni na voljo nobena povezava, se obrnite na skrbnika.

1. Vnesite ime za izvoz.

1. V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje, ki predstavlja e-poštni naslov stranke.

1. Po želji izvoz **ime**, **·**, **·**, **/regija**, **·**, **·**, in **Poštna številka** za ustvarjanje bolj prilagojenih e-poštnih sporočil. Izberite **Dodaj atribut** za preslikavo teh polj.

1. Izberite segmente, ki jih želite izvoziti.

1. Izberite **Shrani**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
