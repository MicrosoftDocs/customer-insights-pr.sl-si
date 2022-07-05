---
title: Obogatite profile podjetij z Leadspace (predogled)
description: Splošne informacije o neodvisni obogatitvi Leadspace.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b58532a541ee22a5e34d0af1a3334ccbd53627b2
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082375"
---
# <a name="enrich-company-profiles-with-leadspace-preview"></a>Obogatite profile podjetij z Leadspace (predogled)

Leadspace je podjetje za podatkovne znanosti, ki ponuja platformo za podatke o strankah »podjetja podjetjem«. Omogoča, da okolja s poenotenimi profili strank na podlagi računov obogatijo njihove podatke. Obogatite *profile strank* z atributi, kot so velikost podjetja, lokacija ali panoga. Obogatite *profile stika* z atributi, kot so preverjanje naslova, osebe ali e-poštnega naslova.

## <a name="prerequisites"></a>Zahteve

- Aktivna licenca Leadspace.
- [Poenoteni profili strank](customer-profiles.md) na podlagi računov.
- Leadspace [povezavo](connections.md) je [konfiguriran](#configure-the-connection-for-leadspace) s strani skrbnika. Za podrobnosti o izdelku stopite v stik neposredno z družbo [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/).

## <a name="configure-the-connection-for-leadspace"></a>Konfiguriranje povezave z Leadspace

Moraš biti [skrbnik](permissions.md#admin) v Customer Insights in imajo "večni ključ" (imenovano **Leadspace žeton**).

1. Izberite **Dodajte povezavo** ko konfigurirate obogatitev ali pojdite na **Admin** > **Povezave** in izberite **Nastaviti** na ploščici Leadspace.

   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Stran za konfiguriranje povezave z Leadscape.":::

1. Vnesite ime za povezavo in veljaven žeton Leadspace.

1. Preglejte in podajte soglasje, tako da v razdelku [Zasebnost in skladnost podatkov](#data-privacy-and-compliance) izberete možnost **Strinjam se**.

1. Izberite **Preverite** da preverite konfiguracijo in nato izberite **Shrani**.

### <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v Leadspace, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Leadspace izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš skrbnik za Dynamics 365 Customer Insights lahko to obogatitev kadarkoli odstrani, s čimer je uporaba te funkcije prekinjena.

## <a name="configure-the-enrichment"></a>Konfiguriranje obogatitve

1. Pojdite v **Podatki** > **Obogatitev** in izberite zavihek **Odkrivanje**.

1. Izberite **Obogatite moje podatke** na **Podatki o podjetju** iz ploščice Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Posnetek zaslona ploščice Leadspace.":::

1. Preglejte pregled in nato izberite **Naslednji**.

1. Izberite povezavo. Obrnite se na skrbnika, če ta ni na voljo.

1. Izberite **Naprej**.

1. Izberite **Stranka nabor podatkov** in izberite profil ali segment, ki ga želite obogatiti s podatki o podjetju iz Leadspacea. The *Stranka* entiteta obogati vse vaše profile strank, medtem ko segment obogati le profile strank, ki jih vsebuje ta segment.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Posnetek zaslona izbire nabora podatkov o strankah.":::

1. Določite, katero vrsto polj iz vaših enotnih profilov želite uporabiti za ujemanje: primarni in/ali sekundarni naslov. Za oba naslova lahko določite preslikavo polj in obogatite profile za vsak naslov posebej. Na primer za domači in poslovni naslov. Izberite **Naprej**.

1. Preslikajte svoja polja na podatke o podjetju iz Leadspacea. Polje **Ime podjetja** je obvezno. Za večjo natančnost ujemanja lahko dodate do dve drugi polji: **Spletno mesto podjetja** in **Lokacija podjetja**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Podokno za preslikavo polja Leadspace.":::

1. Izberite možnost **Naprej**, da dokončate preslikavo polj.

1. Potrdite polje, če bi radi obogatili *profile stika*. Customer Insights bo samodejno preslikal zahtevana polja.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Obogatitev zapisov o stikih Leadspace.":::

1. Izberite **Naprej**.

1. Zagotovite a **ime** za obogatitev in **Ime izhodne entitete**.

1. Po pregledu svoje izbire izberite možnost **Shrani obogatitev**.

1. Izberite **teci** za začetek procesa obogatitve ali blizu vrnitve na **Obogatitve** stran.

## <a name="view-enrichment-results"></a>Oglejte si rezultate obogatitve

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Za več informacij glejte razdelek [API-ji storitve Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Naslednji koraki

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
