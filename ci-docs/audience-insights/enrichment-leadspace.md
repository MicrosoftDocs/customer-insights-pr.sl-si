---
title: Obogatitev profilov podjetij z neodvisnimi obogatitvami Leadspace
description: Splošne informacije o neodvisni obogatitvi Leadspace.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 34b73b37670ed45e2c31ea164c0788b793bee433829ce21317c83903f3fca1fe
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031723"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Obogatitev profilov podjetja z Leadspace (predogled)

Leadspace je podjetje, ki se ukvarja s podatki in zagotavlja platformo s podatki o strankah za prodajo podjetjem. Strankam omogoča poenoten profil strank, s katerimi podjetja obogatijo svoje podatke. Obogatitve vključujejo več atributov, kot so velikost podjetja, lokacija, panoga in drugo.

## <a name="prerequisites"></a>Zahteve

Za konfiguracijo storitve Leadspace morajo biti izpolnjeni naslednji pogoji:

- Imate aktivno licenco za Leadspace.
- Za podjetja imate [poenotene profile strank](customer-profiles.md).
- Skrbnik je že konfiguriral povezavo z Leadscape oziroma imate vi [skrbniška](permissions.md#administrator) dovoljenja in »trajni ključ« (imenovan žeton **Leadspace**). Za podrobnosti o izdelku stopite v stik neposredno z družbo [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/).

## <a name="configure-the-enrichment"></a>Konfiguriranje obogatitve

1. Pri vpogledih v občinstvo izberite **Podatki** > **Obogatitev**.

1. Na ploščici za Leadspace izberite možnost **Obogatitev podatkov** in izberite možnost **Začetek**.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Posnetek zaslona ploščice Leadspace.":::

1. Na spustnem seznamu izberite možnost [povezava](connections.md). Če ni na voljo nobena povezava, se obrnite na skrbnika. Če ste skrbnik, lahko vzpostavite povezavo z izbiro možnosti **Dodaj povezavo** in izbiro možnosti **Leadscape**. 

1. Izberite možnost **Poveži z Leadscape** za potrditev povezave.

1. Izberite možnost **Naprej** in izberite **nabor podatkov o stranki**, ki ga želite obogatiti s podatki o podjetju družbe Leadspace. Izberete lahko entiteto **Stranka**, da obogatite vse vaše profile strank, ali entiteto segmenta, da obogatite samo profile strank, ki jih vsebuje ta segment.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Posnetek zaslona izbire nabora podatkov o strankah.":::

1. Izberite možnost **Naprej** in določite, katere vrste polj iz vaših poenotenih profilov se uporabljajo za iskanje ustreznih podatkov o podjetju iz storitev Leadspace. Polje **Ime podjetja** je obvezno. Za večjo natančnost ujemanja lahko dodate do dve drugi polji: **Spletno mesto podjetja** in **Lokacija podjetja**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Podokno za preslikavo polja Leadspace.":::

1. Izberite možnost **Naprej**, da dokončate preslikavo polj.

1. Navedite ime obogatitve in po pregledu vaše izbire izberite možnost **Shrani obogatitev**.


## <a name="configure-the-connection-for-leadspace"></a>Konfiguriranje povezave z Leadspace 

Za konfiguriranje povezav morate biti skrbnik. Pri konfiguriranju obogatitve izberite možnost **Dodaj povezavo** *ali* odprite razdelek **Skrbnik** > **Povezave** in na ploščici Leadspace izberite možnost **Nastavitev**.

1. Izberite **Začetek**. 

1. Vnesite ime povezave v polje za **prikazno ime**.

1. Vnesite veljaven žeton za Leadspace.

1. Preglejte in podajte soglasje, tako da v razdelku **Zasebnost in skladnost podatkov** izberete možnost **Strinjam se**.

1. Izberite možnost **Potrdi** za potrditev konfiguracije.

1. Po zaključku potrjevanja izberite možnost **Shrani**.
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Stran za konfiguriranje povezave z Leadscape.":::

## <a name="enrichment-results"></a>Rezultati obogatitve

Po osvežitvi obogatitve lahko pregledate novo obogatene podatke podjetja v razdelku [Moje obogatitve](enrichment-hub.md). Ogledate si lahko čas zadnje posodobitve in število obogatenih profilov.

Do podrobnega prikaza vsakega obogatenega profila lahko dostopate tako, da izberete **Ogled obogatenih podatkov**.

Za več informacij glejte razdelek [API-ji storitve Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Naslednji koraki

Nadgradite svoje obogatene podatke o strankah. Ustvarite [segmente](segments.md) in [mere](measures.md) ter celo [izvozite podatke](export-destinations.md) in tako svojim strankam zagotovite prilagojeno izkušnjo.

## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v Leadspace, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Leadspace izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš skrbnik za Dynamics 365 Customer Insights lahko to obogatitev kadarkoli odstrani, s čimer je uporaba te funkcije prekinjena.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
