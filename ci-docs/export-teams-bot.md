---
title: Bot Teams za Dynamics 365 Customer Insights (predogled)
description: Poiščite poenotene profile strank v storitvi Microsoft Teams s pomočjo bota.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d140ae72578b48091a41005c4acafe03bac540da
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195862"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Bot Teams za Dynamics 365 Customer Insights (predogled)

Povežite se s storitvijo Microsoft Teams, da bot dovoli iskanje poenotenih profilov strank v kanalih Teams.

:::image type="content" source="media/teams-bot.png" alt-text="Bot za Teams, ki prikazuje zapis stranke":::

## <a name="prerequisites"></a>Zahteve

- Vsaj en [vir podatkov dodano](data-sources.md).
- [Postopek poenotenja](data-unification.md) je dokončan.
- Polja so dodana v [indeks iskanja in filtriranja](search-filter-index.md).
- Aplikaciji Customer Insights in Teams sta v isti organizaciji.
- V vašem okolju je primarno ciljno občinstvo nastavljeno na posamezne stranke. Poslovni računi niso podprti.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Konfiguracija bota

1. Odprite razdelek **Skrbnik** > **Povezave**.
1. Na ploščici Microsoft Teams izberite **Nastavitev**.
1. Preusmerjeni ste v območje **Aplikacije** v aplikaciji Teams. Lahko tudi odprete aplikacijo Teams in izberete **Aplikacije** v spodnjem levem kotu oz. [jo prenesete neposredno iz trgovine AppSource](https://go.microsoft.com/fwlink/?linkid=2124104).
1. Poiščite **Customer Insights** in izberite aplikacijo.
1. Izberite **Dodaj**.
1. Prijavite se v Customer Insights v Teams. Prikaže se pozdravno sporočilo.

## <a name="things-you-can-do-with-the-bot"></a>Stvari, ki jih omogoča bot

Bot ponuja možnosti iskanja za poenotene profile strank.

- Vnesite **Iskanje** sledi ime, e-poštni naslov ali katero koli drugo polje v poenotenem profilu stranke, ki je dodan v indeks iskanja in filtra.

  Prikaže se kartica z največ 15 polji iz pridobljenega profila stranke. Več ujemanj vrne seznam rezultatov, kjer lahko izberete profil. Če želite poiskati natančno ujemanje, dodajte iskalni izraz v dvojnih narekovajih.

- Če vaša organizacija vzdržuje več okolij Customer Insights v isti organizaciji, vnesite **switchinstance** da izberete, s katerim okoljem želite povezati bota.

- Če si želite ogledati seznam ukazov, ki so na voljo za bot, vnesite **pomoč**.  

[!INCLUDE [footer-include](includes/footer-banner.md)]