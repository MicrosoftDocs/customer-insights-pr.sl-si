---
title: Uporaba demografskih dimenzij za razdelitev vedenjskih podatkov (obravnavane dimenzije)
description: Uporaba obravnavanih dimenzij v poenotenem profilu za omogočanje vpogledov občinstva v lastnostih profila stranke.
ms.date: 07/27/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 95395e09bc0ba5ba93138957c62105f31c709e91
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/16/2022
ms.locfileid: "8233067"
---
# <a name="use-demographic-dimensions-for-splitting-behavioral-data"></a>Uporaba demografskih dimenzij za razdelitev vedenjskih podatkov

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Z uporabo demografskih dimenzij v poenotenem profilu lahko uporabniki vpogledov v interakcije dostopajo do lastnosti profila vpogledov občinstva. Te lastnosti lahko nato uporabite pri interaktivnih analizah vedenjskih podatkov, vključno s podatki, zajetimi z vpogledi v interakcije na vašem spletnem mestu ali v mobilni aplikaciji.

>[!NOTE]
> Vpogledi v interakcijo vključujejo vnaprej pripravljene razsežnosti za lastnosti dogodka. Več informacij: [Ogled in ustvarjanje dimenzij](dimensions.md)

## <a name="prerequisite"></a>Predpogoj

- Okolje vpogledov v interakcije, v katerem imate podatke o profilu stranke, povezane z okoljem vpogledov občinstva, kjer se ustvarjajo profili strank. Več informacij: [Ustvarjanje povezave med vpogledi občinstva in vpogledi v interakcije](integrate-audience-insights-engagement-insights.md)

> [!NOTE]
> Ko ustvarite povezavo med okolji vpogledov občinstva in vpogledi v interakcije, boste morda želeli le podatke, značilne za lastnosti profila strank, ki so lahko uporabni kot dimenzije pri vpogledih v interakcije. Za več informacij pojdite na [Omogočanje atributov in segmentov poenotenih profilov vpogledov občinstva](integrate-audience-insights-engagement-insights.md#enable-audience-insights-unified-profiles-attributes-and-segments).

## <a name="create-a-new-custom-report"></a>Ustvarjanje novega poročila po meri

1. V levem podoknu izberite **Po meri** > **Novo poročilo** in nato izberite želeno meritev. (Za ta primer smo izbrali **Ogledi strani po uri**.)

    :::image type="content" source="media/curated-dimensions1.png" alt-text="Izbira meritve.":::

2. V urejevalniku ponazoritev izberite **Dimenzije** in nato izberite **Demografski podatki** v spustnem meniju **Vrsta dimenzije**.

    :::image type="content" source="media/curated-dimensions2.png" alt-text="Izberite demografske podatke.":::

3. Izberite dimenzijo **Signal.Stranka.*xxx***. (Ta primer prikazuje Signal.Stranka.Država.)

    :::image type="content" source="media/curated-dimensions3.png" alt-text="Izberite dimenzijo.":::
  
## <a name="limitations"></a>Omejitve

Za razdelitev vedenjskih podatkov lahko trenutno uporabite samo demografske dimenzije.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
