---
title: Izvoz podatkov Customer Insights v HubSpot
description: Naučite se konfigurirati povezavo in izvoziti v HubSpot.
ms.date: 09/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0281be288b2c4d9e5da7ad8e2ed25f7b51b8498e
ms.sourcegitcommit: f959c85871777e5f4eab289e91b2fd114cd72153
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 09/23/2022
ms.locfileid: "9588939"
---
# <a name="export-segments-to-hubspot-preview"></a>Izvoz segmentov v HubSpot (predogled)

Izvozite segmente poenotenih profilov strank v HubSpot in jih uporabite za e-poštno trženje.

## <a name="prerequisites-for-a-connection"></a>Predpogoji za povezavo

- A [račun HubSpot](https://www.hubspot.com/) in ustrezne skrbniške poverilnice.
- [API ključ](https://knowledge.hubspot.com/Integrations/How-do-I-get-my-HubSpot-API-key) iz HubSpot.
- [Konfigurirani segmenti](segments.md) v Customer Insights.

## <a name="known-limitations"></a>Znane omejitve

- Do 100.000 profilov strank na izvoz v HubSpot, ki lahko traja do 15 minut. Število profilov strank, ki jih lahko izvozite v HubSpot, je odvisno in omejeno na vašo pogodbo s HubSpot.
- Samo segmenti.

## <a name="set-up-connection-to-hubspot"></a>Nastavite povezavo s HubSpot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajte povezavo** in izberite **HubSpot** za konfiguracijo povezave.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Če ne izvedete nobenih dejanj, so privzeto izbrani Skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ob pozivu vnesite svoje poverilnice za HubSpot.

1. Preglejte [zasebnost podatkov in skladnost](connections.md#data-privacy-and-compliance) in izberite **strinjam se**.

1. Izberite **Povežite se** za inicializacijo povezave s HubSpot.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite možnost **Dodaj izvoz** za ustvarjanje novega izvoza.

1. V **Povezava za izvoz** izberite povezavo v razdelku HubSpot. Če imena tega razdelka ne vidite, za vas ni na voljo nobena tovrstna povezava.

1. V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje, ki predstavlja e-poštni naslov stranke. Ponovite iste korake za druga neobvezna polja.

1. Izberite segmente, ki jih želite izvoziti.

1. Izberite **Shrani**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
