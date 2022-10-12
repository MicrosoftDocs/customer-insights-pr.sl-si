---
title: Načrtujte osvežitev sistema
description: Določite čas, ko naj se sistem osveži
ms.date: 09/27/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 4aac02b570357d2086f7a9d7340b0e4837157a0b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610348"
---
# <a name="schedule-system-refresh"></a>Načrtujte osvežitev sistema

Načrtujte samodejno osveževanje vseh vaših [zaužite vire podatkov](data-sources.md). Samodejno osveževanje pomaga zagotoviti, da se posodobitve iz virov podatkov odražajo v vaših poenotenih profilih strank.

> [!NOTE]
> Power Query viri podatkov, ki jih upravljate, osvežujejo po lastnih urnikih. Za načrtovanje osveževanja teh Power Query podatkovnih virov, konfigurirajte nastavitve osveževanja na tem določenem vir podatkov iz **Viri podatkov** strani. Uskladite časovni razpored z razporedom osveževanja podatkov navzgor, tako da se ne bodo vse osvežitve zgodile hkrati.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Nastavitve osveževanja toka podatkov.":::

## <a name="set-system-refresh-schedule"></a>Nastavite urnik osveževanja sistema

1. Pojdi do **skrbnik** > **Sistem** in izberite **Urnik** zavihek.

   :::image type="content" source="media/schedule_refresh.png" alt-text="Zavihek Načrtovanje osveževanja na strani Sistem.":::

1. Privzeto stanje za načrtovano osvežitev je **Izklopljeno**. Če želite omogočiti razporejena osveževanja, spremenite preklop na vrhu zaslona na **Vklopljeno**.

1. Za osveževanja lahko izberete **Tedensko** (privzeto) in **Dnevno**. Če nameravate razporediti tedenska osveževanja, izberite en ali več dni, ko želite zagnati osveževanje.

1. Nastavite svoj **Časovni pas**, nato uporabite spustni meni **Ura**, da nastavite uro osveževanja. Če želite razporediti več osveževanj v enem dnevu, izberite **Dodajte drug čas**. Dodate lahko do štiri osvežitve.

1. Če želite uporabiti spremembe, izberite **Shrani**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
