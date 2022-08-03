---
title: Power Automate priključek (predogled) | Microsoftovi dokumenti
description: Ustvarjajte tokove v storitvi Microsoft Power Automate iz storitve Dynamics 365 Customer Insights.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f87bd6db7143294a264813f6c5c7d7963f303628
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196138"
---
# <a name="power-automate-connector-preview"></a>Povezovalnik za Power Automate (predogled)

Nastavite sprožilnike za samodejno izvajanje določenih dogodkov, ko se podatki spremenijo, in upravljajte zahtevnejše poteke v storitvi [Microsoft Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Znane omejitve

- Največ 100 klicev na 60 sekund. Uporabi [$skip parameter](/connectors/customerinsights/#get-items-from-an-entity) da večkrat pokličete API končna točka.

## <a name="power-automate-triggers"></a>Sprožilci za Power Automate

Uporabite sprožilce za ustvarjanje tokov za oblake in avtomatizacijo ponavljajočih se opravil, kot so obvestila ali naprednejša dejanja. Uporabite sprožilce, ko:

- Osvežitev vir podatkov ne uspe.
- Osvežitev vir podatkov uspe.
- Na segmentu je presežen prag. Sprožilec je omejen na preseganje praga.
- Na poslovnem merilu je presežen prag. Podprte so samo poslovne mere brez razsežnosti. Sprožilec je omejen na preseganje praga.
- Popolna načrtovana osvežitev je končana. Ta sprožilec ne deluje pri ročno zagnanih osveževanjih.
- Osvežitev postopka združevanja je končana.

[Svoje sprožilce konfigurirajte v storitvi Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Dejanja Power Automate

Povezovalnik za Power Automate poleg razpoložljivih sprožilcev zagotavlja še druga dejanja. Če želite več informacij, glejte [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Ustvarjanje toka storitve Power Automate

1. Odprite razdelek **Skrbnik** > **Povezave**.

1. Na ploščici **Power Automate** izberite možnost **Nastavitev**.

1. V storitvi Power Automate se odpre Customer Insights Connector (predogled). **Vpišite se** v storitev Power Automate.

1. Izberite enega od razpoložljivih sprožilcev in dodajte več korakov v novi tok. Za več informacij glejte razdelek [Ustvarjanje toka za oblak v storitvi Power Automate](/power-automate/get-started-logic-flow).

Primeri uporabe tokov: 
- Pošljite sporočilo v kanal storitve Microsoft Teams, če osvežitev vira podatkov ne uspe. 
- Ko je prag na segmentu presežen, pošljite e-pošto lastnikom podatkov.

[!INCLUDE [footer-include](includes/footer-banner.md)]
