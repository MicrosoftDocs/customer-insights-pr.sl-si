---
title: Obogatitev z neodvisno obogatitvijo Experian
description: Splošne informacije o neodvisni obogatitvi Experian.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 735da18e584b0d9db76b557f4d16dbdf1757f33c
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954107"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Profile strank obogatite z demografskimi podatki iz storitve Experian (predogled)

Experian je vodilno podjetje v svetu na področju poročanja o potrošniških in poslovnih kreditih in na področju trženjskih storitev. S pomočjo storitev za obogatitev podatkov Experian lahko poglobite razumevanje svojih strank, in sicer tako, da njihove profile obogatite s pomočjo demografskih podatkov, kot so velikost gospodinjstva, dohodek itd.

## <a name="supported-countriesregions"></a>Podprte države/regije

Obogatitev profilov strank trenutno omogočamo samo v ZDA.

## <a name="prerequisites"></a>Zahteve

- Aktiven Experian naročnina. Če se želite naročiti, [se obrnite neposredno na Experian](https://www.experian.com/marketing-services/contact). [Več informacij o obogatitvi podatkov Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- An Experian [povezavo](connections.md) je [konfiguriran](#configure-the-connection-for-experian) s strani skrbnika.

- Experian ID uporabnika, ID stranke in številka modela za vaš račun za varni transport (ST), ki podpira SSH Experian ustvarjeno za vas.

## <a name="configure-the-connection-for-experian"></a>Konfigurirajte povezavo za Experian

Moraš biti [skrbnik](permissions.md#admin) v Customer Insights in imajo Experian ID uporabnika, ID stranke in številka modela.

1. Izberite **Dodajte povezavo** ko konfigurirate obogatitev, ali pojdite na **Admin** > **Povezave** in izberite **Nastaviti** na Experian ploščice.

   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian podokno konfiguracije povezave.":::

1. Vnesite ime za povezavo in veljaven ID uporabnika, ID stranke in številko modela za vašo Experian Varen prometni račun.

1. Preglejte in podajte soglasje, tako da v razdelku [Zasebnost in skladnost podatkov](#data-privacy-and-compliance) izberete možnost **Strinjam se**.

1. Izberite **Preverite** da preverite konfiguracijo in nato izberite **Shrani**.

### <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

S tem ko dovolite, da Dynamics 365 Customer Insights podatke prenese storitvi Experian, omogočite prenos podatkov zunaj omejitve skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo take podatke prenesel skladno z vašimi navodili, vendar ste vi odgovorni za to, da Experian izpolnjuje morebitne obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732). Vaš skrbnik za Dynamics 365 Customer Insights lahko to obogatitev kadarkoli odstrani, s čimer je uporaba te funkcije prekinjena.

## <a name="configure-the-enrichment"></a>Konfiguriranje obogatitve

1. Pojdite v **Podatki** > **Obogatitev** in izberite zavihek **Odkrivanje**.

1. Izberite **Obogatite moje podatke** na **Demografija** od Experian ploščice.

   :::image type="content" source="media/experian-tile.png" alt-text="Experian ploščico na strani s pregledom obogatitve.":::

1. Preglejte pregled in nato izberite **Naslednji**.

1. Izberite povezavo. Obrnite se na skrbnika, če ta ni na voljo.

1. Izberite **Naprej**.

1. Izberite **Stranka nabor podatkov** in izberite profil ali segment, iz katerega želite obogatiti z demografskimi podatki Experian. The *Stranka* entiteta obogati vse vaše profile strank, medtem ko segment obogati samo profile strank, ki jih vsebuje ta segment.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Posnetek zaslona izbire nabora podatkov o strankah.":::

1. Določite, katero vrsto polj iz svojih enotnih profilov želite uporabiti za ujemanje demografskih podatkov Experian. Zahtevano je vsaj eno od naslednjih polj: **Ime in naslov**, **Telefon** ali **E-poštni naslov**. Za večjo natančnost ujemanja dodajte druga polja. Izberite **Naprej**.

1. Preslikajte svoja polja na demografske podatke iz Experian.

1. Izberite možnost **Naprej**, da dokončate preslikavo polj.

1. Zagotovite a **ime** za obogatitev in **Ime izhodne entitete**.

1. Po pregledu svoje izbire izberite možnost **Shrani obogatitev**.

1. Izberite **teci** za začetek procesa obogatitve ali blizu vrnitve na **Obogatitve** stran.

## <a name="enrichment-results"></a>Rezultati obogatitve

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

The **Število kupcev, obogatenih po področjih** zagotavlja pregled pokritosti vsakega obogatenega polja.

## <a name="next-steps"></a>Naslednji koraki

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
