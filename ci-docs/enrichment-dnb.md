---
title: Obogatitev profilov podjetij z Dun & Bradstreet
description: Splošne informacije o obogatitvi tretjih oseb Dun & Bradstreet.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b1038970b6aee3bbdd7f79cc457f79aaf1c38222
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953911"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Obogatitev profilov podjetij z Dun & Bradstreet (predogled)

Dun & Bradstreet ponuja komercialne podatke, analitiko in vpoglede za podjetja. Strankam omogoča poenoten profil strank, s katerimi podjetja obogatijo svoje podatke. Obogatitve vključujejo atribute, kot so številka DUNS, velikost podjetja, lokacija, industrija in drugo.

## <a name="prerequisites"></a>Zahteve

- Aktiven [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) licenco.
- [Poenoteni profili strank](customer-profiles.md) za podjetja.
- Dun & Bradstreet [projekt](#set-up-your-dun--bradstreet-project) je postavljeno.
- Dun & Bradstreet [povezavo](connections.md) je [konfiguriran](#configure-a-connection-for-dun--bradstreet) s strani skrbnika.

## <a name="set-up-your-dun--bradstreet-project"></a>Nastavite svoj projekt Dun & Bradstreet

Kot licencirani uporabnik Dun & Bradstreet lahko nastavite projekt v [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).

1. Prijavite se v [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Za pridobitev poverilnic, [obnovite svoje geslo](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Prenesi [naša datoteka predloge csv](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) ki bo uporabljen za preslikavo polj Customer Insights v ustrezna polja Dun & Bradstreet.

1. Naložite datoteko v **Naložite podatke** korak izkušnje ustvarjanja projekta Dun & Bradstreet.

1. Izberite vodoravne pike pod ustreznimi **vir** v novoustvarjenem projektu Dun & Bradstreet, da si ogledate razpoložljive možnosti.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Posnetek zaslona pik v projektu Dun & Bradstreet.":::

1. Izberite **Pridobite podrobnosti o S3**. Te podatke shranite na varno mesto. Potrebovali boste [vzpostaviti povezavo za obogatitev](#configure-a-connection-for-dun--bradstreet) v Customer Insights.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Posnetek zaslona izbora informacij s3 v projektu Dun & Bradstreet.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Konfigurirajte povezavo za Dun & Bradstreet

Moraš biti [skrbnik](permissions.md#admin) v Customer Insights in imajo poverilnice Dun & Bradstreet Connect.

1. Izberite **Dodajte povezavo** ko konfigurirate obogatitev ali pojdite na **Admin** > **Povezave** in izberite **Nastaviti** na ploščici Dun & Bradstreet.

1. Vnesite ime za povezavo.

1. Navedite veljavne poverilnice Dun & Bradstreet in podrobnosti projekta Dun & Bradstreet *Regija, pot do mape in ime mape spusti*. ti [pridobite te informacije](#set-up-your-dun--bradstreet-project) iz projekta Dun & Bradstreet.

1. Preglejte in podajte soglasje, tako da v razdelku [Zasebnost in skladnost podatkov](#data-privacy-and-compliance) izberete možnost **Strinjam se**.

1. Izberite **Preverite** da preverite konfiguracijo in nato izberite **Shrani**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Stran za konfiguracijo povezave Dun & Bradstreet.":::

### <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v Dun & Bradstreet dovolite prenos podatkov izven meja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo te podatke prenesel po vašem navodilu, vendar ste odgovorni za zagotovitev, da Dun & Bradstreet izpolnjuje morebitne obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš skrbnik za Dynamics 365 Customer Insights lahko to obogatitev kadarkoli odstrani, s čimer je uporaba te funkcije prekinjena.

## <a name="supported-countries-or-regions"></a>Podprte države ali regije

Trenutno podpiramo naslednje možnosti države/regije: Kanada (angleščina) ali Združene države (angleščina).

## <a name="configure-the-enrichment"></a>Konfiguriranje obogatitve

1. Pojdite v **Podatki** > **Obogatitev** in izberite zavihek **Odkrivanje**.

1. Izberite **Obogatite moje podatke** na **Podatki o podjetju** za ploščice Dun & Bradstreet.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Posnetek zaslona ploščice Dun & Bradstreet.":::

1. Preglejte pregled in nato izberite **Naslednji**.

1. Izberite povezavo in potrdite. Obrnite se na skrbnika, če ta ni na voljo.

1. Izberite **Naprej**.

1. Izberite **Stranka nabor podatkov** in izberite profil ali segment, ki ga želite obogatiti s podatki podjetja Dun & Bradstreet. The *Stranka* entiteta obogati vse vaše profile strank, medtem ko segment obogati samo profile strank, ki jih vsebuje ta segment.

1. Določite, katere vrste polj iz svojih enotnih profilov boste uporabili za ujemanje podatkov podjetja Dun & Bradstreet. Zahtevano je vsaj eno od naslednjih polj: **Ime in naslov**, **Telefon** ali **E-poštni naslov**.

1. Izberite **Naprej**

1. Preslikajte svoja polja na podatke podjetja Dun & Bradstreet. bodisi **DUNS številka** oz **Ime podjetja** in **Država** polja so obvezna.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Podokno za preslikavo polj Dun & Bradstreet.":::

1. Izberite možnost **Naprej**, da dokončate preslikavo polj.

1. Zagotovite a **ime** za obogatitev in **Ime izhodne entitete**.

1. Po pregledu svoje izbire izberite možnost **Shrani obogatitev**.

1. Izberite **teci** za začetek procesa obogatitve ali blizu vrnitve na **Obogatitve** stran.

## <a name="enrichment-results"></a>Rezultati obogatitve

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Naslednji koraki

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
