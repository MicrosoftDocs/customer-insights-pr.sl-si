---
title: Obogatite profile podjetij z Leadspace (predogled)
description: Splošne informacije o neodvisni obogatitvi Leadspace.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f45fabc036775e11fc439f69513678d0607729d0
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237970"
---
# <a name="enrich-company-profiles-with-leadspace-preview"></a>Obogatite profile podjetij z Leadspace (predogled)

Leadspace je podjetje za podatkovne znanosti, ki ponuja platformo za podatke o strankah »podjetja podjetjem«. Omogoča, da okolja s poenotenimi profili strank na podlagi računov obogatijo njihove podatke. Obogatite *profile strank* z atributi, kot so velikost podjetja, lokacija ali panoga. Obogatite *profile stika* z atributi, kot so preverjanje naslova, osebe ali e-poštnega naslova.

## <a name="prerequisites"></a>Zahteve

- Aktivna licenca Leadspace.
- [Poenoteni profili strank](customer-profiles.md) na podlagi računov.
- Leadspace [povezava](connections.md) je [konfiguriran](#configure-the-connection-for-leadspace) s strani skrbnika. Za podrobnosti o izdelku stopite v stik neposredno z družbo [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/).

## <a name="configure-the-connection-for-leadspace"></a>Konfiguriranje povezave z Leadspace

Morate biti [skrbnik](permissions.md#admin) v Customer Insights in imajo "večni ključ" (v nadaljevanju **Žeton Leadspace**).

1. Izberite **Dodajte povezavo** ko konfigurirate obogatitev ali pojdite na **skrbnik** > **Povezave** in izberite **Nastaviti** na ploščici Leadspace.

   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Stran za konfiguriranje povezave z Leadscape.":::

1. Vnesite ime za povezavo in veljaven žeton Leadspace.

1. Preglejte [zasebnost podatkov in skladnost](connections.md#data-privacy-and-compliance) in izberite **strinjam se**.

1. Izberite **Preveri** za potrditev konfiguracije in nato izberite **Shrani**.

## <a name="configure-the-enrichment"></a>Konfiguriranje obogatitve

1. Pojdite v **Podatki** > **Obogatitev** in izberite zavihek **Odkrivanje**.

1. Izberite **Obogati moje podatke** na **Podatki o podjetju** iz ploščice Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Posnetek zaslona ploščice Leadspace.":::

1. Preglejte pregled in nato izberite **Naslednji**.

1. Izberite povezavo. Če ni na voljo nobena povezava, se obrnite na skrbnika.

1. Izberite **Naprej**.

1. Izberite **Stranka nabor podatkov** in izberite profil ali segment, ki ga želite obogatiti s podatki podjetja Leadspace. The *Stranka* entiteta obogati vse vaše profile strank, medtem ko segment obogati samo profile strank v tem segmentu.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Posnetek zaslona izbire nabora podatkov o strankah.":::

1. Določite, katero vrsto polj iz vaših poenotenih profilov boste uporabili za ujemanje: primarni in/ali sekundarni naslov. Za oba naslova lahko določite preslikavo polj in obogatite profile za vsak naslov posebej. Na primer za domači in poslovni naslov. Izberite **Naprej**.

1. Preslikajte svoja polja v podatke podjetja iz Leadspace. Polje **Ime podjetja** je obvezno. Za večjo natančnost ujemanja lahko dodate do dve drugi polji: **Spletno mesto podjetja** in **Lokacija podjetja**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Podokno za preslikavo polja Leadspace.":::

1. Izberite možnost **Naprej**, da dokončate preslikavo polj.

1. Potrdite polje, če bi radi obogatili *profile stika*. Customer Insight bo samodejno preslikal zahtevana polja.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Obogatitev zapisov o stikih Leadspace.":::

1. Izberite **Naprej**.

1. Zagotovite a **Ime** za obogatitev in **Ime izhodne entitete**.

1. Po pregledu svoje izbire izberite možnost **Shrani obogatitev**.

1. Izberite **Teči** za začetek procesa obogatitve ali zapiranje za vrnitev v **Obogatitve** strani.

## <a name="view-enrichment-results"></a>Oglejte si rezultate obogatitve

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Za več informacij glejte razdelek [API-ji storitve Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Naslednji koraki

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
