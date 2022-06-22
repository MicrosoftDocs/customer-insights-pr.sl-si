---
title: Obogatitev podatkov o identiteti LiveRamp
description: Obogatite profile strank s podatki LiveRamp.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e8a130865267b57c89157b44be3d4bba3dc2fb4e
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954015"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Obogatite profile strank s podatki o identiteti iz LiveRamp (predogled)

LiveRamp zagotavlja deterministično ločevanje identitete brez povezave in konsolidacijo podatkov strank. Osebne identifikatorje v svojih podatkih o strankah lahko preslikate v graf identitete AbiliTec in prejmete AbiliTec ID-je. Te ID-je lahko nato uporabite za boljše poenotenje podatkov vaših strank.

## <a name="supported-countriesregions"></a>Podprte države/regije

Trenutno podpiramo obogatitev profilov strank s podatki LiveRamp samo v Združenih državah.

## <a name="prerequisites"></a>Zahteve

- Aktivna naročnina na LiveRamp. Za naročnino se obrnite na svojo ekipo za račun LiveRamp ali na [dynamics@liveramp.com](mailto:dynamics@liveramp.com) za več informacij.

- Aktivna naročnina AbiliTec z ID-jem odjemalca in skrivnostjo za dostop do API-ja. Za več informacij glejte [AbiliTec API Developer Hub](https://developers.liveramp.com/abilitec-api/).

- LiveRamp [povezavo](connections.md) je [konfiguriran](#configure-the-connection-for-liveramp) s strani skrbnika.

## <a name="configure-the-connection-for-liveramp"></a>Konfigurirajte povezavo za LiveRamp

Moraš biti [skrbnik](permissions.md#admin) v Customer Insights in imajo aktivni ID odjemalca LiveRamp in skrivnost.

1. Izberite **Dodajte povezavo** ko konfigurirate obogatitev, ali pojdite na **Admin** > **Povezave** in izberite **Nastaviti** na ploščici LiveRamp.

   :::image type="content" source="media/liveramp-connection.png" alt-text="Konfiguracijsko podokno za nastavitev povezave s storitvijo LiveRamp AbiliTec.":::

1. Vnesite ime za povezavo in veljaven ID odjemalca LiveRamp ter skrivnost.

1. Preglejte in podajte soglasje, tako da v razdelku [Zasebnost in skladnost podatkov](#data-privacy-and-compliance) izberete možnost **Strinjam se**.

1. Izberite **Preverite** da preverite konfiguracijo in nato izberite **Shrani**.

### <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v LiveRamp dovolite prenos podatkov izven meja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo te podatke prenesel po vašem navodilu, vendar ste odgovorni za zagotovitev, da LiveRamp izpolnjuje vse vaše obveznosti glede zasebnosti ali varnosti. Za več informacij si oglejte [Microsoftova izjava o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732). Vaš skrbnik za Dynamics 365 Customer Insights lahko to obogatitev kadar koli odstrani in s tem prekini uporabo te funkcije.

## <a name="configure-the-enrichment"></a>Konfiguriranje obogatitve

1. Pojdite v **Podatki** > **Obogatitev** in izberite zavihek **Odkrivanje**.

1. Izberite **Obogatite moje podatke** na **Identiteta** iz ploščice LiveRamp.

   :::image type="content" source="media/liveramp-tile.png" alt-text="Ploščica identitete na strani s pregledom obogatitve.":::

1. Preglejte pregled in nato izberite **Naslednji**.

1. Izberite povezavo. Obrnite se na skrbnika, če ta ni na voljo.

1. Izberite **Naprej**.

1. Izberite **Stranka nabor podatkov** in izberite profil ali segment, ki ga želite obogatiti s podatki o identiteti iz LiveRamp. The *Stranka* entiteta obogati vse vaše profile strank, medtem ko segment obogati samo profile strank, ki jih vsebuje ta segment.

1. Določite, katero vrsto polj iz svojih enotnih profilov želite uporabiti za ujemanje podatkov o identiteti iz LiveRamp. Vsaj eno od polj **Ime in naslov**, **-naslov**, oz **Telefon** je potrebno. Za večjo natančnost ujemanja dodajte druga polja. Izberite **Naprej**.

1. Preslikajte svoja polja na identifikacijske podatke iz LiveRamp.

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Možnosti preslikave podatkov za obogatitev LiveRamp.":::

1. Izberite možnost **Naprej**, da dokončate preslikavo polj.

1. Zagotovite a **ime** za obogatitev in **Ime izhodne entitete**.

1. Po pregledu svoje izbire izberite možnost **Shrani obogatitev**.

1. Izberite **teci** za začetek procesa obogatitve ali blizu vrnitve na **Obogatitve** stran.

## <a name="enrichment-results"></a>Rezultati obogatitve

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

The **Število kupcev, obogatenih po področjih** zagotavlja pregled pokritosti vsakega obogatenega polja.

## <a name="next-steps"></a>Naslednji koraki

Nadgradite svoje obogatene podatke o strankah. Uporabite ID-je AbiliTec za konsolidacijo profilov strank v osebni pogled.
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
