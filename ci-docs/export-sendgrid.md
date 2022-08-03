---
title: Izvoz segmentov v SendGrid (predogledna različica)
description: Naučite se, kako konfigurirati povezavo in izvažati v SendGrid.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f2990ad410dda0cbf952f82f3fc30b3a53a7bcd4
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197012"
---
# <a name="export-segments-to-sendgrid-preview"></a>Izvoz segmentov v SendGrid (predogledna različica)

Izvozite segmente poenotenih profilov strank v seznam strank storitve SendGrid in jih uporabite za akcije ter e-poštno trženje v storitvi SendGrid.

## <a name="prerequisites"></a>Zahteve

- A [Račun SendGrid](https://sendgrid.com/) in ustrezne skrbniške poverilnice.
- [Obstoječi seznami stikov v SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts) in ustrezne ID-je.
- A [Ključ API-ja SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).
- [Konfigurirani segmenti](segments.md) v Customer Insights.
- Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.

## <a name="known-limitations"></a>Znane omejitve

- Skupaj do 100.000 profilov strank v SendGrid, kar lahko traja do nekaj ur. Število profilov strank, ki jih lahko izvozite v SendGrid, je odvisno od vaše pogodbe s SendGrid.
- Samo segmenti.

## <a name="set-up-connection-to-sendgrid"></a>Nastavitev povezave s storitvijo SendGrid

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajte povezavo** in izberite **SendGrid**.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Privzeto jo lahko uporabljajo samo skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vpišite **Ključ API-ja SendGrid**.

1. Preglejte [zasebnost podatkov in skladnost](connections.md#data-privacy-and-compliance) in izberite **strinjam se**.

1. Izberite **Povežite se** za inicializacijo povezave.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite **Dodaj izvoz**.

1. V polju **Povezava za izvoz** izberite povezavo v razdelku SendGrid. Če ni na voljo nobena povezava, se obrnite na skrbnika.

1. Vnesite ime za izvoz.

1. Vpišite **ID seznama SendGrid**.

1. V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje, ki predstavlja e-poštni naslov stranke.

1. Po želji izberite polja, kot je npr **ime**, **·**, **/regija**, **·**, **·**, in **Poštna številka**.

1. Izberite segmente, ki jih želite izvoziti, ob upoštevanju znanih omejitev.

1. Izberite **Shrani**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
