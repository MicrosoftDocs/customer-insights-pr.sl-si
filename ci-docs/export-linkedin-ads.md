---
title: Izvoz segmentov v LinkedIn Ads (predogledna različica)
description: Naučite se, kako konfigurirati povezavo in izvažati v LinkedIn Ads.
ms.date: 08/12/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 06eb915e352ad545f95e96e6108be0f81f43a451
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725328"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Izvoz segmentov v LinkedIn Ads (predogledna različica)

Izvozite segmente poenotenih profilov strank v LinkedIn Ads, da ustvarite ujemajoče se ciljne skupine. Uporabite ujemajoče se ciljne skupine za ciljanje podjetij in stikov.

## <a name="prerequisites"></a>Zahteve

- A [LinkedIn Campaign Manager račun](https://business.linkedin.com/marketing-solutions/ads) in ustrezne skrbniške poverilnice.
- A [LinkedIn Campaign Manager ID računa](https://www.linkedin.com/help/lms/answer/a424270).
- [Konfigurirani segmenti](segments.md) v Customer Insights.
- Izvoženi segmenti potrebujejo vsaj eno posebno polje, odvisno od vaše izbire [ciljanje stikov](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) oz [ciljanje na podjetje](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) na LinkedInu. Možna polja so navedena v **Ujemanje podatkov** korak kdaj [konfiguracijo izvoza](#configure-an-export).

## <a name="known-limitations"></a>Znane omejitve

- Zasebna povezava v kombinaciji z Bring your own storage (BYOS) ni podprta.
- Do 100.000 profilov strank na izvoz v LinkedIn Ads, ki lahko traja do 10 minut.
- Samo segmenti. Segment mora vsebovati vsaj 300 edinstvenih profilov.

## <a name="set-up-connection-to-linkedin-ads"></a>Nastavite povezavo z oglasi LinkedIn

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajte povezavo** in izberite **LinkedIn oglasi**.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Privzeto jo lahko uporabljajo samo skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zagotovite svoje LinkedIn Campaign Manager ID računa.

1. Preglejte [zasebnost podatkov in skladnost](connections.md#data-privacy-and-compliance) in izberite **strinjam se**.

1. Izberite **Povežite se** za inicializacijo povezave.

1. Izberite **Preverjanje pristnosti z aplikacijo LinkedIn** in vnesite svoje skrbniške poverilnice za LinkedIn Campaign Manager.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite **Dodaj izvoz**.

1. V polju **Povezava za izvoz** izberite povezavo iz razdelka LinkedIn Ads. Če ni na voljo nobena povezava, se obrnite na skrbnika.

1. Vnesite ime za izvoz.

1. Izberite, ali želite izvoziti podatke za [ciljanje na stike](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) ali [ciljanje na podjetja](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) v orodju LinkedIn.

1. V razdelku **Ujemanje podatkov** za ciljanje stikov izberite vsaj eno polje, ki predstavlja e-poštni naslov stranke, ID oglasa Apple, ID oglasa Google, ID uporabnika Google ali ime in priimek. Če izberete ciljanje podjetja, izberite vsaj eno polje, ki predstavlja ime podjetja, e-poštno domeno, URL strani LinkedIn, simbol zaloge ali spletno mesto.

1. Po želji dodajte polja za nadaljnjo opredelitev izvoza. Izberite **Dodaj atribut** za preslikavo teh polj.

1. Izberite segmente, ki jih želite izvoziti. Ujemajoče se ciljne skupine v LinkedIn Campaign Manager bodo samodejno ustvarjene z imenom segmentov za izvoz. Vsak segment bo prikazal ločeno ciljno skupino.

1. Izberite **Shrani**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
