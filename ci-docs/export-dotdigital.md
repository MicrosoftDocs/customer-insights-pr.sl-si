---
title: Izvoz segmentov v DotDigital (predogledna različica)
description: Naučite se, kako konfigurirati povezavo in izvažati v DotDigital.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8f3e3378dce9177c6645b91140884ae135540243
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725006"
---
# <a name="export-segments-to-dotdigital-preview"></a>Izvoz segmentov v DotDigital (predogledna različica)

Izvozite segmente poenotenih profilov strank v adresarje DotDigital ter jih uporabite za akcije, e-poštno trženje ter sestavljanje segmentov strank s storitvijo DotDigital.

## <a name="prerequisites"></a>Zahteve

- A [Račun DotDigital](https://dotdigital.com/) in an [Uporabnik API-ja](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user).
- DotDigital ID od a [novo](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) ali obstoječi adresar v DotDigital. ID lahko najdete v URL-ju, ko izberete in odprete adresar.
- [Konfigurirani segmenti](segments.md) v Customer Insights.
- Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.

## <a name="known-limitations"></a>Znane omejitve

- Zasebna povezava v kombinaciji z Bring your own storage (BYOS) ni podprta.
- Do 1 milijon profilov strank na izvoz v DotDigital, ki lahko zaradi omejitev na strani ponudnika traja do tri ure. Število profilov strank, ki jih lahko izvozite v DotDigital, je odvisno od vaše pogodbe z DotDigital.
- Samo segmenti.

## <a name="set-up-connection-to-dotdigital"></a>Nastavitev povezave s storitvijo DotDigital

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajte povezavo** in izberite **DotDigital**.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Privzeto jo lahko uporabljajo samo skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vnesite **uporabniško ime in geslo za DotDigital API**.

1. Vpišite **ID adresarja DotDigital**.

1. Preglejte [zasebnost podatkov in skladnost](connections.md#data-privacy-and-compliance) in izberite **strinjam se**.

1. Izberite **Povežite se** za inicializacijo povezave.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite **Dodaj izvoz**.

1. V polju **Povezava za izvoz** izberite povezavo v razdelku DotDigital. Če ni na voljo nobena povezava, se obrnite na skrbnika.

1. Vnesite ime za izvoz.

1. V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje, ki predstavlja e-poštni naslov stranke.

1. Po želji izvoz **ime**, **·**, **ime**, **·**, in **Poštna številka**.

1. Izberite segmente, ki jih želite izvoziti.

1. Izberite **Shrani**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

V DotDigital poiščite svoje segmente v [DotDigital adresarji](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

[!INCLUDE [footer-include](includes/footer-banner.md)]
