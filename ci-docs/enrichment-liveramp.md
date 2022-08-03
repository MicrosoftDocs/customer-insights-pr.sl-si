---
title: Obogatite profile strank z identitetnimi podatki iz LiveRamp (predogled)
description: Obogatite profile strank s podatki LiveRamp.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 49bf558209ca91ab9d8db945862a57adccee1f6b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196368"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Obogatite profile strank z identitetnimi podatki iz LiveRamp (predogled)

LiveRamp zagotavlja deterministično razrešitev identitete brez povezave in konsolidacijo podatkov o strankah. Osebne identifikatorje v svojih podatkih o strankah lahko preslikate v graf identitete AbiliTec in prejmete ID-je AbiliTec. Te ID-je lahko nato uporabite za boljše poenotenje podatkov o strankah.

## <a name="supported-countriesregions"></a>Podprte države/regije

Trenutno podpiramo obogatitev profilov strank s podatki LiveRamp samo v Združenih državah.

## <a name="prerequisites"></a>Zahteve

- Aktivna naročnina na LiveRamp. Če želite pridobiti naročnino, se obrnite na svojo ekipo za račun LiveRamp ali na [dynamics@liveramp.com](mailto:dynamics@liveramp.com) za več informacij.

- Aktivna naročnina na AbiliTec z ID-jem odjemalca in skrivnostjo za dostop do API-ja. Za več informacij glejte [Središče za razvijalce API-ja AbiliTec](https://developers.liveramp.com/abilitec-api/).

- LiveRamp [povezava](connections.md) je [konfiguriran](#configure-the-connection-for-liveramp) s strani skrbnika.

## <a name="configure-the-connection-for-liveramp"></a>Konfigurirajte povezavo za LiveRamp

Morate biti [skrbnik](permissions.md#admin) v Customer Insights in imajo aktiven ID in skrivnost odjemalca LiveRamp.

1. Izberite **Dodajte povezavo** ko konfigurirate obogatitev, ali pojdite na **skrbnik** > **Povezave** in izberite **Nastaviti** na ploščici LiveRamp.

   :::image type="content" source="media/liveramp-connection.png" alt-text="Konfiguracijsko podokno za nastavitev povezave s storitvijo LiveRamp AbiliTec.":::

1. Vnesite ime za povezavo ter veljaven ID odjemalca LiveRamp in skrivnost.

1. Preglejte in podajte soglasje, tako da v razdelku [Zasebnost in skladnost podatkov](#data-privacy-and-compliance) izberete možnost **Strinjam se**.

1. Izberite **Preveri** za potrditev konfiguracije in nato izberite **Shrani**.

### <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v LiveRamp dovolite prenos podatkov izven meje skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo prenesel take podatke po vaših navodilih, vendar ste odgovorni za zagotovitev, da LiveRamp izpolnjuje morebitne obveznosti glede zasebnosti ali varnosti. Za več informacij si oglejte [Microsoftova izjava o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732). Vaš skrbnik za Dynamics 365 Customer Insights lahko to obogatitev kadar koli odstrani in s tem prekini uporabo te funkcije.

## <a name="configure-the-enrichment"></a>Konfiguriranje obogatitve

1. Pojdite v **Podatki** > **Obogatitev** in izberite zavihek **Odkrivanje**.

1. Izberite **Obogati moje podatke** na **Identiteta** s ploščice LiveRamp.

   :::image type="content" source="media/liveramp-tile.png" alt-text="Ploščica identitete na strani s pregledom obogatitve.":::

1. Preglejte pregled in nato izberite **Naslednji**.

1. Izberite povezavo. Če ni na voljo nobena povezava, se obrnite na skrbnika.

1. Izberite **Naprej**.

1. Izberite **Stranka nabor podatkov** in izberite profil ali segment, ki ga želite obogatiti z identitetnimi podatki iz LiveRamp. The *Stranka* entiteta obogati vse vaše profile strank, medtem ko segment obogati samo profile strank v tem segmentu.

1. Določite, katero vrsto polj iz vaših poenotenih profilov boste uporabili za ujemanje podatkov o identiteti iz LiveRampa. Vsaj eno od polj **Ime in naslov**, **-naslov**, oz **Telefon** je potrebno. Za večjo natančnost ujemanja dodajte druga polja. Izberite **Naprej**.

1. Preslikajte svoja polja v identifikacijske podatke iz LiveRamp.

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Možnosti preslikave podatkov za obogatitev LiveRamp.":::

1. Izberite možnost **Naprej**, da dokončate preslikavo polj.

1. Zagotovite a **Ime** za obogatitev in **Ime izhodne entitete**.

1. Po pregledu svoje izbire izberite možnost **Shrani obogatitev**.

1. Izberite **Teči** za začetek procesa obogatitve ali zapiranje za vrnitev v **Obogatitve** strani.

## <a name="view-enrichment-results"></a>Oglejte si rezultate obogatitve

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

The **Število strank, obogatenih po področjih** zagotavlja podrobno analizo pokritosti vsakega obogatenega polja.

## <a name="next-steps"></a>Naslednji koraki

Nadgradite svoje obogatene podatke o strankah. Uporabite ID-je AbiliTec za konsolidacijo profilov strank v pogled, ki temelji na osebah.
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
