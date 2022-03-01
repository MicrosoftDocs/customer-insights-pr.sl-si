---
title: Povezovalnik Power Automate | Microsoftovo gradivo
description: Ustvarite poteke v storitvi Microsoft Power Automate iz Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406947"
---
# <a name="power-automate-connector-preview"></a>Povezovalnik za Power Automate (predogled)

Nastavite sprožilnike za samodejno izvajanje določenih dogodkov, ko se podatki spremenijo, in upravljajte zahtevnejše poteke v storitvi [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Sprožilci za Power Automate

Uporabite lahko različne sprožilce, ki vam omogočajo ustvarjanje potekov za avtomatizacijo ponavljajočih se opravil, kot so obvestila ali naprednejša dejanja. 

- Sproži, ko osvežitev vira podatkov ne uspe. 
- Sproži, ko osvežitev vira podatkov uspe.
- Sproži, ko je prag segmenta presežen. Sprožilec je omejen na preseganje praga.
- Sproži, ko je prag presežen v poslovni meri. Sprožilec je omejen s preseganjem praga.
- Sprožilec, ko je opravljeno polno osveževanje (viri podatkov, segmenti, mere, ...).
- Sproži, ko je dokončana osvežitev postopka poenotenja (preslikava, ujemanje, spajanje).

[Konfigurirajte sprožilce v storitvi Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Dejanja Power Automate
Povezovalnik za Power Automate poleg razpoložljivih sprožilcev zagotavlja še druga dejanja. Če želite več informacij, glejte [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow-in-audience-insights"></a>Ustvarjanje poteka Power Automate pri vpogledih v občinstvo

1. Pri vpogledih v občinstvo izberite **Skrbnik** > **Sistem**.

1. Na strani **Sistem** izberite zavihek **Stanje**.

1. V razdelku **Viri podatkov** izberite možnost **Poteki** in **Ustvari potek** na spustnem seznamu.
   > [!div class="mx-imgBorder"]
   > ![Povezovalnik Power Automate s prikazom dejanja ustvarjanja poteka](media/power-automate-connector-create-flow.png "Povezovalnik Power Automate s prikazom dejanja ustvarjanja poteka")

1. V povezovalniku Power Automate izberite enega od sprožilcev, ki so na voljo, da ustvarite želeni pretok. Če ustvarjate prvi potek, morate najprej preveriti pristnost s povezovalnikom Power Automate.
