---
title: Izvoz segmentov v Marketo (predogledna različica)
description: Naučite se, kako konfigurirati povezavo in izvažati v Marketo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: cba40b74b86a40fc41db856760c9361b755a8864
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724960"
---
# <a name="export-segments-to-marketo-preview"></a>Izvoz segmentov v Marketo (predogledna različica)

Izvozite segmente poenotenih profilov strank, da akcije, zagotovite e-poštno trženje in uporabite določene skupine strank s storitvijo Marketo.

## <a name="prerequisites"></a>Zahteve

- A [Marketo račun](https://login.marketo.com/) in ustrezne skrbniške poverilnice.
- A [ID odjemalca Marketo, skrivnost odjemalca in ime gostitelja REST končna točka](https://developers.marketo.com/rest-api/authentication/).
- [Obstoječi seznami v Marketu](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) in ustrezne ID-je.
- [Konfigurirani segmenti](segments.md).
- Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.

## <a name="known-limitations"></a>Znane omejitve

- Zasebna povezava v kombinaciji z Bring your own storage (BYOS) ni podprta.
- Do 1 milijon profilov strank na izvoz v Marketo, kar lahko traja do 3 ure. Število profilov strank, ki jih lahko izvozite v Marketo, je odvisno od vaše pogodbe s Marketom.
- Samo segmenti.

## <a name="set-up-connection-to-marketo"></a>Nastavitev povezave s storitvijo Marketo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajte povezavo** in izberite **Marketo**.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Privzeto jo lahko uporabljajo samo skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vpišite **ID odjemalca Marketo, skrivnost odjemalca in ime gostitelja REST končna točka**. Ime gostitelja za končno točko REST je samo ime gostitelja, brez https://. Primer: xyz-abc-123.mktorest.com.

1. Preglejte [zasebnost podatkov in skladnost](connections.md#data-privacy-and-compliance) in izberite **strinjam se**.

1. Izberite **Povežite se** za inicializacijo povezave.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite **Dodaj izvoz**.

1. V polju **Povezava za izvoz** izberite povezavo v razdelku Marketo. Če ni na voljo nobena povezava, se obrnite na skrbnika.

1. Vnesite ime za izvoz.

1. Vpišite **ID seznama Marketo**. ID seznama je zgolj številčna vrednost. Na primer, če je ID vašega seznama Marketo ST12345A7, odstranite znak pred in za številkami in vnesite *12345*.

1. V **Ujemanje podatkov** izberite vsaj eno polje, ki predstavlja e-poštni naslov stranke ali ID stranke Marketo.

1. Po želji izvoz **ime**, **·**, **·**, **·**, in **Država/regija** za ustvarjanje bolj prilagojenih e-poštnih sporočil. Izberite **Dodaj atribut** za preslikavo teh polj.

1. Izberite segmente, ki jih želite izvoziti.

1. Izberite **Shrani**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

V Marketu poiščite svoje segmente pod [Marketo seznami](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

[!INCLUDE [footer-include](includes/footer-banner.md)]
