---
title: Povezovalnik Power Automate | Microsoftovo gradivo
description: Ustvarjajte tokove v storitvi Microsoft Power Automate iz storitve Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dd90ef4576246b49d4a9c74005196ee9813a6744
ms.sourcegitcommit: d168a738a08adb8b4b2e410bdaa3716d7b63cc9b
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 03/17/2022
ms.locfileid: "8455931"
---
# <a name="power-automate-connector-preview"></a>Povezovalnik za Power Automate (predogled)

Nastavite sprožilnike za samodejno izvajanje določenih dogodkov, ko se podatki spremenijo, in upravljajte zahtevnejše poteke v storitvi [Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Znane omejitve

- Opravite lahko največ 100 klicev na 60 sekund. API končna točka lahko pokličete večkrat z uporabo parametra $skip. [Preberite več o parametru $skip](/connectors/customerinsights/#get-items-from-an-entity).

## <a name="power-automate-triggers"></a>Sprožilci za Power Automate

Uporabite sprožilce za ustvarjanje tokov za oblake in avtomatizacijo ponavljajočih se opravil, kot so obvestila ali naprednejša dejanja. 

- Sproži, ko osvežitev vira podatkov ne uspe. 
- Sproži, ko osvežitev vira podatkov uspe.
- Sproži, ko je prag segmenta presežen. Sprožilec je omejen na preseganje praga.
- Sproži, ko je prag presežen v poslovni meri. Podprte so samo poslovne mere brez razsežnosti. Sprožilec je omejen na preseganje praga.
- Sproži po končanem polnem osveževanju (virov podatkov, segmentov, mer, ...).
- Sproži, ko je dokončana osvežitev postopka poenotenja (preslikava, ujemanje, spajanje).

[Svoje sprožilce konfigurirajte v storitvi Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Dejanja Power Automate

Povezovalnik za Power Automate poleg razpoložljivih sprožilcev zagotavlja še druga dejanja. Če želite več informacij, glejte [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Ustvarjanje toka storitve Power Automate

1. Pri vpogledih v občinstvo izberite **Skrbnik** > **Cilji izvoza**.

1. Na ploščici **Power Automate** izberite možnost **Nastavitev**.

1. V storitvi Power Automate se odpre Customer Insights Connector (predogled). **Vpišite se** v storitev Power Automate.

1. Izberite enega od razpoložljivih sprožilcev in dodajte več korakov v novi tok. Za več informacij glejte razdelek [Ustvarjanje toka za oblak v storitvi Power Automate](/power-automate/get-started-logic-flow).

Primeri uporabe tokov: 
- Pošljite sporočilo v kanal storitve Microsoft Teams, če osvežitev vira podatkov ne uspe. 
- Ko je prag na segmentu presežen, pošljite e-pošto lastnikom podatkov.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
