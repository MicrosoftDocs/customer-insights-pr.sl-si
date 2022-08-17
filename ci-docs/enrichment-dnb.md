---
title: Obogatite profile podjetij z Dun & Bradstreet (predogled)
description: Splošne informacije o obogatitvi tretjih oseb Dun & Bradstreet.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: e89b64774dcb519a071dd3d403473807a50e7f33
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237924"
---
# <a name="enrich-company-profiles-with-dun--bradstreet-preview"></a>Obogatite profile podjetij z Dun & Bradstreet (predogled)

Dun & Bradstreet zagotavlja komercialne podatke, analitiko in vpoglede za podjetja. Strankam omogoča poenoten profil strank, s katerimi podjetja obogatijo svoje podatke. Obogatitve vključujejo atribute, kot so številka DUNS, velikost podjetja, lokacija, panoga in drugo.

## <a name="prerequisites"></a>Zahteve

- Aktiven [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) dovoljenje.
- [Poenoteni profili strank](customer-profiles.md) za podjetja.
- Dun & Bradstreet [projekt](#set-up-your-dun--bradstreet-project) je postavljeno.
- Dun & Bradstreet [povezava](connections.md) je [konfiguriran](#configure-a-connection-for-dun--bradstreet) s strani skrbnika.

## <a name="set-up-your-dun--bradstreet-project"></a>Nastavite svoj projekt Dun & Bradstreet

Kot licencirani uporabnik Dun & Bradstreet lahko nastavite projekt v [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).

1. Prijavite se v [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Če želite pridobiti poverilnice, [obnovite geslo](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Prenesi [našo datoteko predloge csv](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) ki bodo uporabljeni za preslikavo polj Customer Insights v ustrezna polja Dun & Bradstreet.

1. Naložite datoteko v **Nalaganje podatkov** korak izkušnje ustvarjanja projekta Dun & Bradstreet.

1. Izberite vodoravne pike pod ustreznim **vir** v novo ustvarjenem projektu Dun & Bradstreet, da vidite razpoložljive možnosti.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Posnetek zaslona s pikami v projektu Dun & Bradstreet.":::

1. Izberite **Pridobite podrobnosti S3**. Te podatke shranite na varno mesto. Potrebovali ga boste [nastavite povezavo za obogatitev](#configure-a-connection-for-dun--bradstreet) v Customer Insights.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Posnetek zaslona izbora informacij s3 v projektu Dun & Bradstreet.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Konfigurirajte povezavo za Dun & Bradstreet

Morate biti [skrbnik](permissions.md#admin) v Customer Insights in imajo poverilnice Dun & Bradstreet Connect.

1. Izberite **Dodajte povezavo** ko konfigurirate obogatitev ali pojdite na **skrbnik** > **Povezave** in izberite **Nastaviti** na ploščici Dun & Bradstreet.

1. Vnesite ime za povezavo.

1. Navedite veljavne poverilnice Dun & Bradstreet in podrobnosti o projektu Dun & Bradstreet *Regija, pot spustne mape in ime spuščene mape*. Ti [dobiti te informacije](#set-up-your-dun--bradstreet-project) iz projekta Dun & Bradstreet.

1. Preglejte [zasebnost podatkov in skladnost](connections.md#data-privacy-and-compliance) in izberite **strinjam se**.

1. Izberite **Preveri** za potrditev konfiguracije in nato izberite **Shrani**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Stran s konfiguracijo povezave Dun & Bradstreet.":::

## <a name="supported-countries-or-regions"></a>Podprte države ali regije

Trenutno podpiramo naslednje možnosti države/regije: Kanada (angleščina) ali Združene države (angleščina).

## <a name="configure-the-enrichment"></a>Konfiguriranje obogatitve

1. Pojdite v **Podatki** > **Obogatitev** in izberite zavihek **Odkrivanje**.

1. Izberite **Obogati moje podatke** na **Podatki o podjetju** za ploščice Dun & Bradstreet.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Posnetek zaslona ploščice Dun & Bradstreet.":::

1. Preglejte pregled in nato izberite **Naslednji**.

1. Izberite povezavo in potrdite. Če ni na voljo nobena povezava, se obrnite na skrbnika.

1. Izberite **Naprej**.

1. Izberite **Stranka nabor podatkov** in izberite profil ali segment, ki ga želite obogatiti s podatki podjetja Dun & Bradstreet. The *Stranka* entiteta obogati vse vaše profile strank, medtem ko segment obogati samo profile strank v tem segmentu.

1. Določite, katero vrsto polj iz vaših poenotenih profilov boste uporabili za ujemanje podatkov podjetja iz podjetja Dun & Bradstreet. Zahtevano je vsaj eno od naslednjih polj: **Ime in naslov**, **Telefon** ali **E-poštni naslov**.

1. Izberite **Naprej**

1. Preslikajte svoja polja v podatke podjetja Dun & Bradstreet. Bodisi **Številka DUNS** oz **Ime podjetja** in **Država** polja so obvezna.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Podokno za kartiranje polja Dun & Bradstreet.":::

1. Izberite možnost **Naprej**, da dokončate preslikavo polj.

1. Zagotovite a **Ime** za obogatitev in **Ime izhodne entitete**.

1. Po pregledu svoje izbire izberite možnost **Shrani obogatitev**.

1. Izberite **Teči** za začetek procesa obogatitve ali zapiranje za vrnitev v **Obogatitve** strani.

## <a name="view-enrichment-results"></a>Oglejte si rezultate obogatitve

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Naslednji koraki

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
