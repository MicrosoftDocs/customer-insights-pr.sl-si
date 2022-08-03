---
title: Izvoz segmentov v Google Ads (predogledna različica)
description: Naučite se, kako konfigurirati povezavo in izvažati v Google Ads.
ms.date: 07/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: fd7498ecf17ef8a3a8f22dcc49ae204bef88b47f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196598"
---
# <a name="export-segments-to-google-ads-preview"></a>Izvoz segmentov v Google Ads (predogledna različica)

Segmente poenotenih profilov strank izvozite na seznam občinstva Google Ads in jih uporabite za oglaševanje v iskalniku Google, v storitvah Gmail, YouTube in v iskalnem omrežju Google.

## <a name="prerequisites"></a>Zahteve

- A [račun Google Ads](https://ads.google.com/) in ustrezne skrbniške poverilnice.
- A [ID stranke Google Ads](https://support.google.com/google-ads/answer/1704344).
- Zahteve za [Politika povezovanja strank](https://support.google.com/adspolicy/answer/6299717) so izpolnjeni.
- Zahteve za [velikosti seznamov za ponovno trženje](https://support.google.com/google-ads/answer/7558048) so izpolnjeni.
- [Konfigurirani segmenti](segments.md).
- Poenoteni profili strank v izvoženih segmentih vsebujejo polja, ki predstavljajo e-poštni naslov, telefon, ID mobilnega oglaševalca, ID uporabnika tretje osebe ali naslov.

## <a name="known-limitations"></a>Znane omejitve

- Izvozite do 1 milijon profilov strank na izvoz v Google Ads, kar lahko zaradi omejitev na strani ponudnika traja do 30 minut.
- Samo segmenti.
- Ujemanje v Google Ads lahko traja do 48 ur.

## <a name="set-up-connection-to-google-ads"></a>Nastavitev povezave s storitvijo Google Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajte povezavo** in izberite **Google Ads**.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Privzeto jo lahko uporabljajo samo skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vnesite svoj ID stranke Google Ads.

1. Preglejte [zasebnost podatkov in skladnost](connections.md#data-privacy-and-compliance) in izberite **strinjam se**.

1. Izberite **Preverjanje pristnosti s storitvijo Google Ads** in vnesite svoje poverilnice za Google Ads.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite **Dodaj izvoz**.

1. V polju **Povezava za izvoz** izberite povezavo v razdelku Google Ads. Če ni na voljo nobena povezava, se obrnite na skrbnika.

1. Vnesite ime za izvoz.

1. Izberite, ali želite uporabiti obstoječo občinstvo ali ustvariti novo:
   - Če želite posodobiti obstoječi Google Ads občinstvo, vnesite svoj [Google Ads občinstvo ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns).
   - Če želite ustvariti nov občinstvo, pustite polje Google občinstvo ID prazno. Customer Insights bo samodejno ustvaril nov občinstvo v vašem računu Google Ads in uporabil ime izvoženega segmenta.

1. V **Ujemanje podatkov** izberite eno ali več podatkovnih polj za izvoz in izberite polje, ki predstavlja ustrezna podatkovna polja v Customer Insights.

1. Izberite segmente, ki jih želite izvoziti.

1. Izberite **Shrani**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
