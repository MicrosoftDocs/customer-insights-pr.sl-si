---
title: Izvozi segmente v Iterable (predogled)
description: Naučite se konfigurirati povezavo in izvoziti v Iterable.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 69e2bd207c98fc2530620018bf95dd869d1798f6
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724624"
---
# <a name="export-segments-to-iterable-preview"></a>Izvozi segmente v Iterable (predogled)

Izvozite segmente poenotenih profilov strank v Iterable in jih uporabite za marketinške aktivnosti.

## <a name="prerequisites"></a>Zahteve

- An [Ponovljiv račun](https://iterable.com/) in ustrezne skrbniške poverilnice.
- An [Ponovljivi ključ API](https://support.iterable.com/hc/en-us/articles/360043464871)
- [Konfigurirani segmenti](segments.md) v Customer Insights.
- Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.

## <a name="known-limitations"></a>Znane omejitve

- Zasebna povezava v kombinaciji z Bring your own storage (BYOS) ni podprta.
- Do 1 milijon profilov strank v Iterable, kar lahko traja do 30 minut. Število profilov strank, ki jih lahko izvozite v Iterable, je odvisno od vaše pogodbe z Iterable.
- Samo segmenti.

## <a name="set-up-connection-to-iterable"></a>Nastavite povezavo z Iterable

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajte povezavo** in izberite **Ponovljivo**.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Privzeto jo lahko uporabljajo samo skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Za nadaljevanje prijave vnesite svoj ključ API-ja Iterable.

1. Preglejte [zasebnost podatkov in skladnost](connections.md#data-privacy-and-compliance) in izberite **strinjam se**.

1. Izberite **Povežite se** za inicializacijo povezave.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite **Dodaj izvoz**.

1. V **Povezava za izvoz** izberite povezavo v razdelku Iterable. Če ni na voljo nobena povezava, se obrnite na skrbnika.

1. Vnesite ime za izvoz.

1. V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje, ki predstavlja e-poštni naslov stranke. Seznam, ustvarjen v Iterable, bo prejel popolnoma enako ime kot ime vašega segmenta Dynamics 365 Customer Insights.

1. Izberite segmente, ki jih želite izvoziti.

1. Izberite **Shrani**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
