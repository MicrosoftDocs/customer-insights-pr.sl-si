---
title: Profile strank obogatite z demografskimi podatki iz storitve Experian (predogled)
description: Splošne informacije o neodvisni obogatitvi Experian.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 876853ab42e8c08ad1abacb8d8a205c0aadabcf7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195956"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Profile strank obogatite z demografskimi podatki iz storitve Experian (predogled)

Experian je vodilno podjetje v svetu na področju poročanja o potrošniških in poslovnih kreditih in na področju trženjskih storitev. S pomočjo storitev za obogatitev podatkov Experian lahko poglobite razumevanje svojih strank, in sicer tako, da njihove profile obogatite s pomočjo demografskih podatkov, kot so velikost gospodinjstva, dohodek itd.

## <a name="supported-countriesregions"></a>Podprte države/regije

Obogatitev profilov strank trenutno omogočamo samo v ZDA.

## <a name="prerequisites"></a>Zahteve

- Aktiven Experian naročnina. Če se želite naročiti, [se obrnite neposredno na Experian](https://www.experian.com/marketing-services/contact). [Več informacij o obogatitvi podatkov Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- An Experian [povezava](connections.md) je [konfiguriran](#configure-the-connection-for-experian) s strani skrbnika.

- Experian ID uporabnika, ID stranke in številka modela za vaš račun varnega transporta (ST), ki podpira SSH Experian ustvarjen za vas.

## <a name="configure-the-connection-for-experian"></a>Konfigurirajte povezavo za Experian

Morate biti [skrbnik](permissions.md#admin) v Customer Insights in imate an Experian ID uporabnika, ID stranke in številka modela.

1. Izberite **Dodajte povezavo** ko konfigurirate obogatitev, ali pojdite na **skrbnik** > **Povezave** in izberite **Nastaviti** na Experian ploščica.

   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian podokno konfiguracije povezave.":::

1. Vnesite ime za povezavo in veljavno ID uporabnika, ID stranke in številko modela za vašo Experian Varen prometni račun.

1. Preglejte in podajte soglasje, tako da v razdelku [Zasebnost in skladnost podatkov](#data-privacy-and-compliance) izberete možnost **Strinjam se**.

1. Izberite **Preveri** za potrditev konfiguracije in nato izberite **Shrani**.

### <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

S tem ko dovolite, da Dynamics 365 Customer Insights podatke prenese storitvi Experian, omogočite prenos podatkov zunaj omejitve skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo take podatke prenesel skladno z vašimi navodili, vendar ste vi odgovorni za to, da Experian izpolnjuje morebitne obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732). Vaš skrbnik za Dynamics 365 Customer Insights lahko to obogatitev kadarkoli odstrani, s čimer je uporaba te funkcije prekinjena.

## <a name="configure-the-enrichment"></a>Konfiguriranje obogatitve

1. Pojdite v **Podatki** > **Obogatitev** in izberite zavihek **Odkrivanje**.

1. Izberite **Obogati moje podatke** na **Demografija** od Experian ploščica.

   :::image type="content" source="media/experian-tile.png" alt-text="Experian ploščico na strani s pregledom obogatitve.":::

1. Preglejte pregled in nato izberite **Naslednji**.

1. Izberite povezavo. Če ni na voljo nobena povezava, se obrnite na skrbnika.

1. Izberite **Naprej**.

1. Izberite **Stranka nabor podatkov** in izberite profil ali segment, ki ga želite obogatiti z demografskimi podatki Experian. The *Stranka* entiteta obogati vse vaše profile strank, medtem ko segment obogati samo profile strank v tem segmentu.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Posnetek zaslona izbire nabora podatkov o strankah.":::

1. Določite, katero vrsto polj iz vaših poenotenih profilov želite uporabiti za ujemanje demografskih podatkov Experian. Zahtevano je vsaj eno od naslednjih polj: **Ime in naslov**, **Telefon** ali **E-poštni naslov**. Za večjo natančnost ujemanja dodajte druga polja. Izberite **Naprej**.

1. Preslikajte svoja polja v demografske podatke iz Experian.

1. Izberite možnost **Naprej**, da dokončate preslikavo polj.

1. Zagotovite a **Ime** za obogatitev in **Ime izhodne entitete**.

1. Po pregledu svoje izbire izberite možnost **Shrani obogatitev**.

1. Izberite **Teči** za začetek procesa obogatitve ali zapiranje za vrnitev v **Obogatitve** strani.

## <a name="view-enrichment-results"></a>Oglejte si rezultate obogatitve

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

The **Število strank, obogatenih po področjih** zagotavlja podrobno analizo pokritosti vsakega obogatenega polja.

## <a name="next-steps"></a>Naslednji koraki

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
