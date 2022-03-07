---
title: Zagon vzorca spletnega kompleta za razvoj programske opreme
description: Preberite več o prilagoditvi in zagonu vzorca spletnega kompleta za razvoj programske opreme.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a50a10db784ec7c1943c94e74000713309787e5c
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225351"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Zagon vzorca spletnega kompleta za razvoj programske opreme za možnost vpogledov v interakcije storitve Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Knjižnica spletnega kompleta za razvoj programske opreme za možnost vpogledov v interakcije je knjižnica JavaScript z vzorčno kodo, ki jo lahko uporabite na svojem spletnem mestu.

## <a name="prerequisites"></a>Zahteve

- Namestite [kodo storitve Visual Studio](https://code.visualstudio.com/).
- [Namestite razširitev za Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) v kodo storitve Visual Studio in se seznanite z načinom zagona strežnika Live Server.
- Imeti morate [delovni prostor za vpoglede v interakcije](create-workspace.md).

## <a name="run-sample"></a>Zagon vzorca

1. [Prenesite vzorec spletnega kompleta za razvoj programske opreme](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Razširite stisnjeno datoteko `ei_websdk_sample.zip`.

1. Odprite razširjeno mapo v kodi storitve Visual Studio.

1. Pojdite na portal za vpogled v interakcije za svoj delovni prostor. Izberite **Skrbnik** > **Delovni prostor** in nato **Vodnik za namestitev**. Sledite prvi možnosti in izberite **Kopiraj kodo**, da kopirate izrezek kode JavaScript.

1. V datoteki `ei_websdk_sample.html` prilepite izrezek kode, ki ste ga pravkar kopirali pod to vrstico:

   - <-- PRILEPITE IZREZEK KODE JAVASCRIPT IZ PORTALA ZA VPOGLEDE V INTERAKCIJE POD TO VRSTICO -->

1. S strežnikom Live Server v kodi storitve Visual Studio odprite datoteko `ei_websdk_sample.html` tako, da v vrstici stanja izberete možnost **Objavi**.

1. Ob odprtju strani mora biti dogodek ogleda samodejno poslan. Če kliknete kateri koli gumba na strani, bodo poslani dogodki dejanja. Gumb **Sledi dogodkom** bo poslal tudi dogodke po meri. Z izbiro gumba **Pojdi v Bing** se dogodek dejanja pošlje, preden odprete spletno mesto Bing.

1. Oglejte si dogodke, ki se pretakajo, ko se pomaknete v delovni prostor. Ta delovni prostor je povezan s ključem za uvoz, vnesenim v 4. koraku.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
