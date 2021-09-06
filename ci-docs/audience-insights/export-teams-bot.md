---
title: Bot za Microsoft Teams
description: Poiščite poenotene profile strank v storitvi Microsoft Teams s pomočjo bota.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 9bf401124b0ffb21b046954056141e7703386d4911f89f34ffc0fcb84bf0f4be
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032502"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Bot Teams za Dynamics 365 Customer Insights (predogled)

Povežite se s storitvijo Microsoft Teams, da bot dovoli iskanje poenotenih profilov strank v kanalih Teams.

> [!div class="mx-imgBorder"]
> ![Bot za Teams, ki prikazuje zapis stranke.](media/teams-bot.png "Bot za Teams, ki prikazuje zapis stranke")

## <a name="prerequisites"></a>Zahteve

Za nastavitev in konfiguracijo bota morajo biti izpolnjeni ti pogoji:

- Dodan je najmanj en [vir podatkov](data-sources.md).
- [Postopek poenotenja](data-unification.md) je dokončan.
- Polja so dodana v [kazalo za iskanje in filtriranje](search-filter-index.md).
- Aplikaciji Customer Insights in Teams sta v isti organizaciji.

## <a name="configure-the-bot"></a>Konfiguracija bota

1. Pri vpogledih v občinstvo izberite **Skrbnik** > **Cilji za izvoz**.
1. Na ploščici Microsoft Teams izberite **Nastavitev**.
1. Preusmerjeni ste v območje **Aplikacije** v aplikaciji Teams. Lahko tudi odprete aplikacijo Teams in izberete **Aplikacije** v spodnjem levem kotu oz. [jo prenesete neposredno iz trgovine AppSource](https://go.microsoft.com/fwlink/?linkid=2124104).
1. Poiščite **Customer Insights** in izberite aplikacijo.
1. Izberite **Dodaj**.
1. Ko se vpišete v Customer Insights v aplikaciji Teams, vidite pozdravno sporočilo in lahko začnete.

## <a name="things-you-can-do-with-the-bot"></a>Stvari, ki jih omogoča bot

Bot ponuja možnosti iskanja za poenotene profile strank.

- Vnesite **iskanje** in nato ime, e-poštni naslov ali katero koli drugo polje v poenotenem profilu stranke, ki je dodano kazalu za iskanje in filtriranje.

  Prikaže se kartica z največ 15 polji iz pridobljenega profila stranke. Več ujemanj vrne seznam rezultatov, kjer lahko izberete profil. Iskalni izraz lahko dodate v dvojne narekovaje, da poiščete natančno ujemanje.

- Če vaša organizacija ohranja več okolij Customer Insights v isti organizaciji, lahko vnesete **switchinstance**, da izberete, v katero okolje želite povezati bot.

- Če si želite ogledati seznam ukazov, ki so na voljo za bot, vnesite **pomoč**.  


[!INCLUDE[footer-include](../includes/footer-banner.md)]