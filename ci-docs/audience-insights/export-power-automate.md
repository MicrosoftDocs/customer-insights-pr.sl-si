---
title: Povezovalnik Power Automate | Microsoftovo gradivo
description: Ustvarite poteke v storitvi Microsoft Power Automate iz Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: fb1df4e9ab1f78300b8ec1f8dfdfbfbac0e71447
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268844"
---
# <a name="power-automate-connector-preview"></a>Povezovalnik za Power Automate (predogled)

Nastavite sprožilnike za samodejno izvajanje določenih dogodkov, ko se podatki spremenijo, in upravljajte zahtevnejše poteke v storitvi [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Sprožilci za Power Automate

Uporabite sprožilce za ustvarjanje tokov za oblake in avtomatizacijo ponavljajočih se opravil, kot so obvestila ali naprednejša dejanja. 

- Sproži, ko osvežitev vira podatkov ne uspe. 
- Sproži, ko osvežitev vira podatkov uspe.
- Sproži, ko je prag segmenta presežen. Sprožilec je omejen na preseganje praga.
- Sproži, ko je prag presežen v poslovni meri. Sprožilec je omejen s preseganjem praga.
- Sprožilec, ko je opravljeno polno osveževanje (viri podatkov, segmenti, mere, ...).
- Sproži, ko je dokončana osvežitev postopka poenotenja (preslikava, ujemanje, spajanje).

[Konfigurirajte sprožilce v storitvi Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Dejanja Power Automate
Povezovalnik za Power Automate poleg razpoložljivih sprožilcev zagotavlja še druga dejanja. Če želite več informacij, glejte [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Ustvarjanje toka storitve Power Automate

1. Pri vpogledih v občinstvo izberite **Skrbnik** > **Cilji izvoza**.

1. Na ploščici **Power Automate** izberite možnost **Nastavitev**.

1. V storitvi Power Automate se odpre Customer Insights Connector (predogled). **Vpišite se** v storitev Power Automate.

1. Izberite enega od razpoložljivih sprožilcev in dodajte več korakov v novi tok. Za več informacij glejte razdelek [Ustvarjanje toka za oblak v storitvi Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow).

Primeri uporabe tokov: 
- Pošljite sporočilo v kanal storitve Microsoft Teams, če osvežitev vira podatkov ne uspe. 
- Ko je prag na segmentu presežen, pošljite e-pošto lastnikom podatkov.



[!INCLUDE[footer-include](../includes/footer-banner.md)]