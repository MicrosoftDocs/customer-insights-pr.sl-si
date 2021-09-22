---
title: Zagon vzorca spletnega kompleta za razvoj programske opreme
description: Preberite več o prilagoditvi in zagonu vzorca spletnega kompleta za razvoj programske opreme.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 97e50a51231bcf05f3e381397f0cf41e49afc10e3c3674d7c709c8f521979e12
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036623"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Zagon vzorca spletnega kompleta za razvoj programske opreme za možnost vpogledov v interakcije storitve Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Knjižnica spletnega kompleta za razvoj programske opreme za možnost vpogledov v interakcije je knjižnica JavaScript z vzorčno kodo, ki jo lahko uporabite na svojem spletnem mestu.

## <a name="prerequisites"></a>Zahteve

- Namestite [kodo storitve Visual Studio](https://code.visualstudio.com/).
- [Namestite razširitev za Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) v kodo storitve Visual Studio in se seznanite z načinom zagona strežnika Live Server.
- Imeti morate [ključ za uvoz](instrument-website.md).

## <a name="run-sample"></a>Zagon vzorca

1. [Prenesite vzorec spletnega kompleta za razvoj programske opreme](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Razširite stisnjeno datoteko `ei_websdk_sample.zip`.

1. Odprite razširjeno mapo v kodi storitve Visual Studio.

1. V datoteki `ei_websdk_sample.html`, zamenjajte niz »INGESTION_KEY« s ključem za uvoz s portala o možnosti za vpoglede v interakcije, niz »NAME« pa z globalnim imenom, za katerega želite, da se ustvari komplet za razvoj programske opreme. Prepričajte se, da ste zamenjali vse pojavitve.

1. S strežnikom Live Server v kodi storitve Visual Studio odprite datoteko `ei_websdk_sample.html` tako, da v vrstici stanja izberete možnost **Objavi**.

1. Ob odprtju strani mora biti dogodek ogleda samodejno poslan. Če kliknete kateri koli gumba na strani, bodo poslani dogodki dejanja. Gumb **Sledi dogodkom** bo poslal tudi dogodke po meri. Z izbiro gumba **Pojdi v Bing** se dogodek dejanja pošlje, preden odprete spletno mesto Bing.

1. Oglejte si dogodke, ki se pretakajo, ko se pomaknete v delovni prostor. Ta delovni prostor je povezan s ključem za uvoz, vnesenim v 4. koraku.


[!INCLUDE[footer-include](../includes/footer-banner.md)]