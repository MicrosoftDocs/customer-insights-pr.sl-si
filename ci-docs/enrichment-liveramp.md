---
title: Obogatite profile strank z identitetnimi podatki iz LiveRamp (predogled)
description: Obogatite profile strank s podatki LiveRamp.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0aa6dc144602741b87843a5373779855ee3e334c
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237833"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Obogatite profile strank z identitetnimi podatki iz LiveRamp (predogled)

LiveRamp zagotavlja deterministično razrešitev identitete brez povezave in konsolidacijo podatkov o strankah. Osebne identifikatorje v svojih podatkih o strankah lahko preslikate v graf identitete AbiliTec in prejmete ID-je AbiliTec. Te ID-je lahko nato uporabite za boljše poenotenje podatkov o strankah.

## <a name="supported-countriesregions"></a>Podprte države/regije

Trenutno podpiramo obogatitev profilov strank s podatki LiveRamp samo v Združenih državah.

## <a name="prerequisites"></a>Zahteve

- Aktivna naročnina na LiveRamp. Če želite pridobiti naročnino, se obrnite na svojo skupino za račun LiveRamp ali na [dynamics@liveramp.com](mailto:dynamics@liveramp.com) za več informacij.

- Aktivna naročnina na AbiliTec z ID-jem odjemalca in skrivnostjo za dostop do API-ja. Za več informacij glejte [Središče za razvijalce API-ja AbiliTec](https://developers.liveramp.com/abilitec-api/).

- LiveRamp [povezava](connections.md) je [konfiguriran](#configure-the-connection-for-liveramp) s strani skrbnika.

## <a name="configure-the-connection-for-liveramp"></a>Konfigurirajte povezavo za LiveRamp

Morate biti [skrbnik](permissions.md#admin) v Customer Insights in imajo aktiven ID in skrivnost odjemalca LiveRamp.

1. Izberite **Dodajte povezavo** ko konfigurirate obogatitev, ali pojdite na **skrbnik** > **Povezave** in izberite **Nastaviti** na ploščici LiveRamp.

   :::image type="content" source="media/liveramp-connection.png" alt-text="Konfiguracijsko podokno za nastavitev povezave s storitvijo LiveRamp AbiliTec.":::

1. Vnesite ime za povezavo ter veljaven ID odjemalca LiveRamp in skrivnost.

1. Preglejte [zasebnost podatkov in skladnost](connections.md#data-privacy-and-compliance) in izberite **strinjam se**.

1. Izberite **Preveri** za potrditev konfiguracije in nato izberite **Shrani**.

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
