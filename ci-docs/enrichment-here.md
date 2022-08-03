---
title: Obogatite profile strank s tehnologijami HERE (predogled)
description: Splošne informacije o neodvisni obogatitvi HERE Technologies.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 26de9fce863c9832b70adf3ce39cb2ae0ce43d0e
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196276"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>Obogatite profile strank s tehnologijami HERE (predogled)

HERE Technologies je podjetje z lokacijsko platformo, ki ponuja lokacijsko usmerjene podatke in storitve. Storitve obogatitve podatkov HERE Technologies izboljšajo natančnost lokacijskih informacij o vaših strankah. Omogoča normalizacijo naslova, ekstrakcijo zemljepisne širine in dolžine in še več.

## <a name="prerequisites"></a>Zahteve

- Aktivna naročnina na HERE Technologies. Če želite pridobiti naročnino, [prijavite se tukaj](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) oz [kontaktirajte HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) neposredno. [Preberite več o obogatitvi lokacije HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- A TUKAJ [povezava](connections.md) je [konfiguriran](#configure-the-connection-for-here-technologies) s strani skrbnika.

## <a name="configure-the-connection-for-here-technologies"></a>Konfigurirajte povezavo za HERE Technologies.

Morate biti [skrbnik](permissions.md#admin) v Customer Insights in imeti aktiven ključ API-ja HERE Technologies.

1. Izberite **Dodajte povezavo** ko konfigurirate obogatitev, ali pojdite na **skrbnik** > **Povezave** in izberite **Nastaviti** na ploščici HERE Technologies.

1. Vnesite ime za povezavo in veljaven ključ API-ja HERE Technologies.

1. Preglejte in podajte soglasje, tako da v razdelku [Zasebnost in skladnost podatkov](#data-privacy-and-compliance) izberete možnost **Strinjam se**.

1. Izberite **Preveri** za potrditev konfiguracije in nato izberite **Shrani**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="Stran za konfiguriranje povezave z družbo HERE technologies.":::

### <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v HERE Technologies, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da HERE Technologies izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš skrbnik za Dynamics 365 Customer Insights lahko to obogatitev kadarkoli odstrani, s čimer je uporaba te funkcije prekinjena.

## <a name="configure-the-enrichment"></a>Konfiguriranje obogatitve

1. Pojdite v **Podatki** > **Obogatitev** in izberite zavihek **Odkrivanje**.

1. Izberite **Obogati moje podatke** na **Lokacija** iz ploščice HERE Technologies.

   :::image type="content" source="media/HERE-tile.png" alt-text="Ploščica HERE Technologies.":::

1. Preglejte pregled in nato izberite **Naslednji**.

1. Izberite povezavo. Če ni na voljo nobena povezava, se obrnite na skrbnika.

1. Izberite **Naprej**.

1. Izberite **Stranka nabor podatkov** in izberite profil ali segment, ki ga želite obogatiti s podatki podjetja HERE Technologies. The *Stranka* entiteta obogati vse vaše profile strank, medtem ko segment obogati samo profile strank v tem segmentu.

1. Določite, katero vrsto polj iz vaših poenotenih profilov boste uporabili za ujemanje: primarni in/ali sekundarni naslov. Za oba naslova lahko določite preslikavo polj in obogatite profile za vsak naslov posebej. Na primer za domači in poslovni naslov. Izberite **Naprej**.

1. Preslikajte svoja polja v podatke iz HERE Technologies. Polji **Ulica 1** in **Poštna številka** sta obvezni za izbrani primarni in/ali sekundarni naslov. Za večjo natančnost ujemanja dodajte več polj.

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
