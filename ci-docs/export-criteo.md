---
title: Izvoz segmentov v Criteo (predogled)
description: Naučite se konfigurirati povezavo in izvoziti v Criteo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 811752da943cd5e40608d48644a1744c7971d3c8
ms.sourcegitcommit: 40ae3322ac95913e485607494754dd03814e42bb
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/11/2022
ms.locfileid: "9760046"
---
# <a name="export-segments-to-criteo-preview"></a>Izvoz segmentov v Criteo (predogled)

Izvozite segmente poenotenih profilov strank za ustvarjanje kampanj, zagotavljanje e-poštnega trženja in uporabo posebnih skupin strank s Criteo.

## <a name="prerequisites"></a>Zahteve

- A [Račun Criteo Dynamics Retargeting](https://www.criteo.com/login/) in ustrezne skrbniške poverilnice.
- [Konfigurirani segmenti](segments.md).
- Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.

## <a name="known-limitations"></a>Znane omejitve

- Do 1 milijon profilov strank na izvoz v Criteo, ki lahko traja do 30 minut. Število profilov strank, ki jih lahko izvozite v Criteo, je odvisno od vaše pogodbe s Criteo.
- Samo segmenti.

## <a name="set-up-connection-to-criteo"></a>Nastavite povezavo s Criteo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajte povezavo** in izberite **Criteo**.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Privzeto jo lahko uporabljajo samo skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Preglejte [zasebnost podatkov in skladnost](connections.md#data-privacy-and-compliance) in izberite **strinjam se** .

1. Izberite **Povežite se** za inicializacijo povezave.

1. Izberite **Preverjanje pristnosti s Criteo** in navedite svoje skrbniško uporabniško ime in poverilnice za Criteo.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite **Dodaj izvoz** .

1. V **Povezava za izvoz** izberite povezavo v razdelku Criteo. Če ni na voljo nobena povezava, se obrnite na skrbnika.

1. Vnesite ime za izvoz.

1. V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje, ki predstavlja e-poštni naslov stranke.

1. Izberite segmente, ki jih želite izvoziti.

1. Izberite **Shrani**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
