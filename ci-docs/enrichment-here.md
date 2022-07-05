---
title: Obogatite profile strank s HERE Technologies (predogled)
description: Splošne informacije o neodvisni obogatitvi HERE Technologies.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: d88085b6be156dd1c895e9e5b38cc9d77acbdb95
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052071"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>Obogatite profile strank s HERE Technologies (predogled)

HERE Technologies je podjetje z lokacijsko platformo, ki ponuja lokacijsko usmerjene podatke in storitve. Storitve obogatitve podatkov HERE Technologies izboljšujejo natančnost informacij o lokaciji vaših strank. Zagotavlja normalizacijo naslova, ekstrakcijo zemljepisne širine in dolžine in še več.

## <a name="prerequisites"></a>Zahteve

- Aktivna naročnina na HERE Technologies. Če želite dobiti naročnino, [prijavi se tukaj](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) oz [kontaktirajte TUKAJ Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) neposredno. [Preberite več o obogatitvi lokacije HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- A TUKAJ [povezavo](connections.md) je [konfiguriran](#configure-the-connection-for-here-technologies) s strani skrbnika.

## <a name="configure-the-connection-for-here-technologies"></a>Konfigurirajte povezavo za HERE Technologies.

Moraš biti [skrbnik](permissions.md#admin) v Customer Insights in imeti aktiven ključ API-ja HERE Technologies.

1. Izberite **Dodajte povezavo** ko konfigurirate obogatitev, ali pojdite na **Admin** > **Povezave** in izberite **Nastaviti** na ploščici HERE Technologies.

1. Vnesite ime za povezavo in veljaven ključ API-ja HERE Technologies.

1. Preglejte in podajte soglasje, tako da v razdelku [Zasebnost in skladnost podatkov](#data-privacy-and-compliance) izberete možnost **Strinjam se**.

1. Izberite **Preverite** da preverite konfiguracijo in nato izberite **Shrani**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="Stran za konfiguriranje povezave z družbo HERE technologies.":::

### <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v HERE Technologies, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da HERE Technologies izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš skrbnik za Dynamics 365 Customer Insights lahko to obogatitev kadarkoli odstrani, s čimer je uporaba te funkcije prekinjena.

## <a name="configure-the-enrichment"></a>Konfiguriranje obogatitve

1. Pojdite v **Podatki** > **Obogatitev** in izberite zavihek **Odkrivanje**.

1. Izberite **Obogatite moje podatke** na **Lokacija** iz ploščice TUKAJ Technologies.

   :::image type="content" source="media/HERE-tile.png" alt-text="Ploščica HERE Technologies.":::

1. Preglejte pregled in nato izberite **Naslednji**.

1. Izberite povezavo. Obrnite se na skrbnika, če ta ni na voljo.

1. Izberite **Naprej**.

1. Izberite **Stranka nabor podatkov** in izberite profil ali segment, ki ga želite obogatiti s podatki HERE Technologies. The *Stranka* entiteta obogati vse vaše profile strank, medtem ko segment obogati le profile strank, ki jih vsebuje ta segment.

1. Določite, katero vrsto polj iz vaših enotnih profilov želite uporabiti za ujemanje: primarni in/ali sekundarni naslov. Za oba naslova lahko določite preslikavo polj in obogatite profile za vsak naslov posebej. Na primer za domači in poslovni naslov. Izberite **Naprej**.

1. Preslikajte svoja polja na podatke HERE Technologies. Polji **Ulica 1** in **Poštna številka** sta obvezni za izbrani primarni in/ali sekundarni naslov. Za večjo natančnost ujemanja dodajte več polj.

1. Izberite možnost **Naprej**, da dokončate preslikavo polj.

1. Zagotovite a **ime** za obogatitev in **Ime izhodne entitete**.

1. Po pregledu svoje izbire izberite možnost **Shrani obogatitev**.

1. Izberite **teci** za začetek procesa obogatitve ali blizu vrnitve na **Obogatitve** stran.

## <a name="view-enrichment-results"></a>Oglejte si rezultate obogatitve

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

The **Število strank, obogatenih po področjih** zagotavlja pregled pokritosti vsakega obogatenega polja.

## <a name="next-steps"></a>Naslednji koraki

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
