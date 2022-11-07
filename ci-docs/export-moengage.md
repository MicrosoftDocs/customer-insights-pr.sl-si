---
title: Izvozi segmente v MoEngage
description: Naučite se konfigurirati povezavo in izvoziti v MoEngage.
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: df38e9e88a9c116252fba26983b5f3711b46f051
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725286"
---
# <a name="export-segments-to-moengage-preview"></a>Izvozi segmente v MoEngage (predogled)

Izvozite segmente poenotenih profilov strank v MoEngage in jih uporabite za e-poštno trženje v MoEngage.

## <a name="prerequisites-for-a-connection"></a>Predpogoji za povezavo

- [MoEngage račun](https://www.moengage.com/) in ustrezne skrbniške poverilnice.
- Ključ MoEngage API iz Nastavitve > API v MoEngage.
- [Konfigurirani segmenti](segments.md) v Customer Insights.

## <a name="known-limitations"></a>Znane omejitve

- Zasebna povezava v kombinaciji z Bring your own storage (BYOS) ni podprta.
- Do 100.000 profilov strank na izvoz v MoEngage, kar lahko traja do 15 minut. Število profilov strank, ki jih lahko izvozite v MoEngage, je odvisno od vaše pogodbe z MoEngage.
- Samo segmenti.

## <a name="set-up-connection-to-moengage"></a>Nastavite povezavo z MoEngage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajte povezavo** in izberite **MoEngage** za konfiguracijo povezave.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vpišite [MoEngage Data API ID in API ključ](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY).

1. Preglejte [zasebnost podatkov in skladnost](connections.md#data-privacy-and-compliance) in izberite **strinjam se**.

1. Izberite **Povežite se** za inicializacijo povezave z MoEngage.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite možnost **Dodaj izvoz** za ustvarjanje novega izvoza.

1. V **Povezava za izvoz** izberite povezavo v razdelku MoEngage. Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.

1. V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje, ki predstavlja e-poštni naslov stranke. Ponovite iste korake za druga neobvezna polja.

1. Izberite segmente, ki jih želite izvoziti. Ustvarili bomo enega ali več segmentov z enakim imenom kot izbrani segmenti v MoEngage pod **Segmenti** > **Segmenti po meri**.

1. Izberite **Shrani**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
