---
title: Obogatitev profilov podjetij z neodvisnimi obogatitvami Leadspace
description: Splošne informacije o neodvisni obogatitvi Leadspace.
ms.date: 11/24/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 41c56aece043c2d7658fd2655713e1e98775edec
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597669"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Obogatitev profilov podjetja z Leadspace (predogled)

Leadspace je podjetje, ki se ukvarja s podatki in zagotavlja platformo s podatki o strankah za prodajo podjetjem. Strankam omogoča poenoten profil strank, s katerimi podjetja obogatijo svoje podatke. Obogatitve vključujejo dodatne atribute, kot je velikost podjetja, lokacija, panoga in druge.

## <a name="prerequisites"></a>Zahteve

Za konfiguracijo storitve Leadspace morajo biti izpolnjeni naslednji pogoji:

- Imate aktivno licenco Leadspace in časovno neomejen ključ (imenovan **žeton za Leadspace**). Za podrobnosti o izdelku se obrnite neposredno na [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/).
- Imate [skrbniška](permissions.md#administrator) dovoljenja.
- Za podjetja imate [poenotene profile strank](customer-profiles.md).

## <a name="configuration"></a>Konfiguracija

1. Pri vpogledih v občinstvo izberite **Podatki** > **Obogatitev**.

1. Izberite **Obogatite moje podatke** na ploščici Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Posnetek zaslona ploščice Leadspace.":::

1. Izberite **Začetek** in nato vnesite aktiven **žeton za Leadspace** (časovno neomejen ključ). Preberite in podajte soglasje za **Zasebnost podatkov in skladnost** tako, da potrdite polje **Strinjam se**. Potrdite oba vnosa z izbiro možnosti **Vzpostavi povezavo z Leadspace**.

1. Izberite možnost **Preslikaj podatke** in izberite nabor podatkov, ki ga želite obogatiti s podatki o podjetju Leadspace. Izberete lahko entiteto *Stranka*, da obogatite vse vaše profile strank, ali entiteto segmenta, da obogatite samo profile strank, ki jih vsebuje ta segment.

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="Izbira med obogatitvijo profila strank in obogatitvijo segmenta.":::

1. Izberite možnost **Naprej** in določite, katera polja iz vaših poenotenih profilov naj bodo uporabljena za iskanje ustreznih podatkov o podjetju Leadspace. Polje **Ime podjetja** je obvezno. Za večjo natančnost ujemanja lahko dodate do dve drugi polji: **Spletno mesto podjetja** in **Lokacija podjetja**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Podokno za preslikavo polja Leadspace.":::
   
1. Izberite **Uporabi** za dokončanje preslikave polja.

1. Izberite **Zagon** za obogatitev profilov podjetja. Kako dolgo traja obogatitev, je odvisno od števila poenotenih profilov strank.

## <a name="enrichment-results"></a>Rezultati obogatitve

Po osvežitvi obogatitve lahko pregledate novo obogatene podatke podjetja v razdelku [Moje obogatitve](enrichment-hub.md). Ogledate si lahko čas zadnje posodobitve in število obogatenih profilov.

Do podrobnega prikaza vsakega obogatenega profila lahko dostopate tako, da izberete **Ogled obogatenih podatkov**.

Za več informacij glejte razdelek [API-ji storitve Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Naslednji koraki

Nadgradite svoje obogatene podatke o strankah. Ustvarite [Segmente](segments.md), [Mere](measures.md) in pa [izvozite podatke](export-destinations.md), da svojim strankam zagotovite prilagojeno izkušnjo.

## <a name="data-privacy-and-compliance"></a>Zasebnost podatkov in skladnost

Ko omogočite Dynamics 365 Customer Insights za prenos podatkov v Leadspace, dovoljujete prenos podatkov izven meje zagotavljanja skladnosti za Dynamics 365 Customer Insights, vključno s potencialno občutljivimi podatki, kot so osebni podatki. Microsoft bo take podatke prenesel po vašem navodilu, vi pa ste odgovorni za to, da Leadspace izpolnjuje kakršne koli obveznosti glede zasebnosti ali varnosti. Več informacij glejte [Microsoftovo izjavo o zasebnosti](https://go.microsoft.com/fwlink/?linkid=396732).
Vaš skrbnik za Dynamics 365 Customer Insights lahko to obogatitev kadar koli odstrani in s tem prekini uporabo te funkcije.


[!INCLUDE[footer-include](../includes/footer-banner.md)]