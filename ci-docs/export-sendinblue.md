---
title: Izvoz segmentov v Sendinblue (predogledna različica)
description: Naučite se, kako konfigurirati povezavo in podatke izvoziti v Sendinblue.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 816a3b242fadaa5a75db878adf0a76baf638e41c
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196966"
---
# <a name="export-segments-to-sendinblue-preview"></a>Izvoz segmentov v Sendinblue (predogledna različica)

Za ustvarjanje akcij, zagotovitev e-poštnega trženja in uporabo določenih skupin strank s storitvijo Sendinblue izvozite segmente poenotenih profilov strank.

## <a name="prerequisites"></a>Zahteve

- A [Račun Sendinblue](https://www.sendinblue.com/) in ustrezne skrbniške poverilnice.
- A [API ključ SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key).
- Obstoječi seznami v Sendinblue in ustrezni ID-ji.
- [Konfigurirani segmenti](segments.md).
- Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.

## <a name="known-limitations"></a>Znane omejitve

- Do 1 milijon profilov strank na izvoz v Sendinblue, ki lahko traja do 90 minut. Število profilov strank, ki jih lahko izvozite v Sendinblue, je odvisno od vaše pogodbe s Sendinblue.
- Samo segmenti.

## <a name="set-up-connection-to-sendinblue"></a>Vzpostavite povezavo s storitvijo Sendinblue

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajte povezavo** in izberite **Sendinblue**.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Privzeto je storitev namenjena samo skrbnikom. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vpišite **API ključ SendinBlue**.

1. Preglejte [zasebnost podatkov in skladnost](connections.md#data-privacy-and-compliance) in izberite **strinjam se**.

1. Izberite **Povežite se** za inicializacijo povezave.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite **Dodaj izvoz**.

1. V polju **Povezava za izvoz**, in sicer v razdelku Sendinblue, izberite povezavo. Če ni na voljo nobena povezava, se obrnite na skrbnika.

1. Vnesite ime za izvoz.

1. Vpišite **ID seznama Sendinblue**.

1. V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje, ki predstavlja e-poštni naslov stranke.

1. Po želji izvoz **ime**, **·**, in **Telefon** za ustvarjanje bolj prilagojenih e-poštnih sporočil. Izberite **Dodaj atribut** za preslikavo teh polj.

1. Izberite segmente, ki jih želite izvoziti.

1. Izberite **Shrani**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
