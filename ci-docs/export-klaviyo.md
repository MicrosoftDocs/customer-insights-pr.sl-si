---
title: Izvoz segmentov v Klaviyo (predogled)
description: Preberite, kako konfigurirate povezavo in podatke izvozite v storitev Klaviyo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6e45ca5827afa29d97a746bd1a474c2346cc32d2
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196782"
---
# <a name="export-segments-to-klaviyo-preview"></a>Izvoz segmentov v Klaviyo (predogled)

Segmente poenotenih profilov strank izvozite v storitev Klaviyo in jih uporabite za trženjske dejavnosti.

## <a name="prerequisites"></a>Zahteve

- A [Klaviyo račun](https://www.klaviyo.com/) in ustrezne skrbniške poverilnice.
- A [Klaviyo API ključ](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys).
- A [Klaviyo List ID](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID).
- [Konfigurirani segmenti](segments.md) v Customer Insights.
- Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.

## <a name="known-limitations"></a>Znane omejitve

- Do 1 milijon profilov strank na izvoz v Klaviyo, ki lahko traja do 20 minut. Število profilov strank, ki jih lahko izvozite v Klaviyo, je odvisno od vaše pogodbe s Klaviyo.
- Samo segmenti.

## <a name="set-up-connection-to-klaviyo"></a>Vzpostavitev povezave s storitvijo Klaviyo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajte povezavo** in izberite **klavijo**.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Privzeto jo lahko uporabljajo samo skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Podajte svoj ključ za API Klaviyo za nadaljevanje prijave.

1. Preglejte [zasebnost podatkov in skladnost](connections.md#data-privacy-and-compliance) in izberite **strinjam se**.

1. Izberite **Povežite se** za inicializacijo povezave.

1. Izberite **Preverjanje pristnosti s storitvijo Klaviyo** in skrbniku zagotovite poverilnice za storitev Klaviyo.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite **Dodaj izvoz**.

1. V polju **Povezava za izvoz**, in sicer v razdelku Klaviyo, izberite povezavo. Če ni na voljo nobena povezava, se obrnite na skrbnika.

1. Vnesite ime za izvoz.

1. Vpišite **Klaviyo List ID**.

1. V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje, ki predstavlja e-poštni naslov stranke.

1. Izberite segmente, ki jih želite izvoziti.

1. Izberite **Shrani**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
