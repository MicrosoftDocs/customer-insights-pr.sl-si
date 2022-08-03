---
title: Izvoz segmentov v Constant Contact (predogledna različica)
description: Naučite se, kako konfigurirati povezavo in izvažati v Constant Contact.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4d2ec29c194dc481ee40048b8ecbed813291b4d2
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196506"
---
# <a name="export-segments-to-constant-contact-preview"></a>Izvoz segmentov v Constant Contact (predogledna različica)

Izvozite segmente poenotenih profilov strank v Constant Contact in jih uporabite za tržne dejavnosti.

## <a name="prerequisites"></a>Zahteve

- A [Račun Constant Contact](https://www.constantcontact.com/account-home) in ustrezne skrbniške poverilnice.
- A [ID stalnega seznama stikov](https://app.constantcontact.com/pages/contacts/ui#lists). Odprite seznam v storitvi Constant Contact, da najdete ID seznama v URL-ju.
- [Konfigurirani segmenti](segments.md) v Customer Insights.
- Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.

## <a name="known-limitations"></a>Znane omejitve

- Do 1 milijon profilov strank na izvoz v Constant Contact, ki lahko traja do eno uro. Število profilov strank, ki jih lahko izvozite v Constant Contact, je odvisno od vaše pogodbe s Constant Contact.
- Samo segmenti.

## <a name="set-up-connection-to-constant-contact"></a>Nastavitev povezave s storitvijo Constant Contact

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajte povezavo** in izberite **Stalni stik**.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Privzeto jo lahko uporabljajo samo skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Preglejte [zasebnost podatkov in skladnost](connections.md#data-privacy-and-compliance) in izberite **strinjam se**.

1. Izberite **Povežite se** za inicializacijo povezave.

1. Izberite **Preverjanje pristnosti s storitvijo Constant Contact** in skrbniku zagotovite poverilnice Constant Contact.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite **Dodaj izvoz**.

1. V polju **Povezava za izvoz** izberite povezavo v razdelku Constant Contact. Če ni na voljo nobena povezava, se obrnite na skrbnika.

1. Vnesite ime za izvoz.

1. Vpišite **ID stalnega seznama stikov**.

1. V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje, ki predstavlja e-poštni naslov stranke.

1. Po želji izvoz **ime** in **priimek** kot dodatna polja za ustvarjanje bolj prilagojenih e-poštnih sporočil. Izberite **Dodaj atribut** za preslikavo teh polj.

1. Izberite segmente, ki jih želite izvoziti.

1. Izberite **Shrani**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
