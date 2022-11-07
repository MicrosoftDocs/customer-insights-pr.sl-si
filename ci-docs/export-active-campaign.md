---
title: Izvozite segmente v ActiveCampaign
description: Naučite se, kako konfigurirati povezavo in podatke izvoziti v ActiveCampaign.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e62888a6d618fb1154890e607d8c23d3767d35f7
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725420"
---
# <a name="export-segments-to-activecampaign-preview"></a>Izvoz segmentov v ActiveCampaign (predogledna različica)

Segmente poenotenih profilov strank izvozite v ActiveCampaign in jih uporabite za trženjske dejavnosti.

## <a name="prerequisites"></a>Zahteve

- An [Račun ActiveCampaign](https://www.activecampaign.com/) in ustrezne skrbniške poverilnice.
- An [ID seznama ActiveCampaign](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).
- An [Ključ API ActiveCampaign](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) in REST končna točka Ime gostitelja.
- [Konfigurirani segmenti](segments.md) v Customer Insights.
- Poenoteni profili strank v izvoženih segmentih vsebujejo polje, ki predstavlja e-poštni naslov.

## <a name="known-limitations"></a>Znane omejitve

- Zasebna povezava v kombinaciji z Bring your own storage (BYOS) ni podprta.
- Do 1 milijon profilov strank na izvoz v ActiveCampaign, ki lahko traja do 90 minut. Število profilov strank, ki jih lahko izvozite v storitev ActiveCampaign, je odvisno od vaše pogodbe s storitvijo ActiveCampaign.
- Samo segmenti.

## <a name="set-up-connection-to-activecampaign"></a>Vzpostavite povezavo s storitvijo ActiveCampaign

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Izberite **Dodajte povezavo** in izberite **ActiveCampaign**.

1. Svoji povezavi dodelite prepoznavno ime v polju **Prikazno ime**. Ime in vrsta povezave opisujeta to povezavo. Priporočamo, da izberete ime, ki pojasnjuje namen in cilj povezave.

1. Izberite, kdo lahko uporablja to povezavo. Privzeto jo lahko uporabljajo samo skrbniki. Za več informacij glejte razdelek [Omogočanje uporabe povezav za izvoze podatkov za sodelavce](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vpišite ključ API za ActiveCampaign in ime gostitelja končne točke REST. Ime gostitelja za končno točko REST je samo ime gostitelja, brez https://.

1. Preglejte [zasebnost podatkov in skladnost](connections.md#data-privacy-and-compliance) in izberite **strinjam se**.

1. Izberite **Povežite se** za inicializacijo povezave.

1. Izberite **Dodajte sebe kot uporabnika za izvoz** in vnesite svoje poverilnice Customer Insights.

1. Izberite možnost **Shrani**, da dokončate povezavo.

## <a name="configure-an-export"></a>Konfiguriranje izvoza

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite **Dodaj izvoz**.

1. V polju **Povezava za izvoz**, in sicer v razdelku ActiveCampaign, izberite povezavo. Če ni na voljo nobena povezava, se obrnite na skrbnika.

1. Vnesite ime za izvoz.

1. Vpišite **ID seznama ActiveCampaign**.

1. V razdelku **Ujemanje podatkov** v polju **E-poštni naslov** izberite polje, ki predstavlja e-poštni naslov stranke.

1. Po želji izvoz **ime**, **·**, in **Telefon** za ustvarjanje bolj prilagojenih e-poštnih sporočil. Izberite **Dodaj atribut** za preslikavo teh polj.

1. Izberite segmente, ki jih želite izvoziti.

1. Izberite **Shrani**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
