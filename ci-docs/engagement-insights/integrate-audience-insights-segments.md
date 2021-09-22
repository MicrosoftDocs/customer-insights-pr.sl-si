---
title: Uporaba segmentov vpogledov občinstva za filtriranje poročil o vpogledih v interakcije
description: Segmente vpogledov občinstva uporabite v interaktivnih analizah vedenjskih podatkov, zajetih z vpogledom v interakcije na spletnem mestu stranke.
ms.date: 07/27/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: bdd5641bb17384725491f22f70ae967ad90b1696
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461078"
---
# <a name="use-audience-insights-segments-to-filter-engagement-insights-reports"></a>Uporaba segmentov vpogledov občinstva za filtriranje poročil o vpogledih v interakcije

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Z vpogledi v interakcije lahko segmente vpogledov občinstva uporabite v interaktivnih analizah vedenjskih podatkov, zajetih z vpogledom v interakcije na vaših spletnih mestih.

## <a name="prerequisite"></a>Predpogoj

- Okolje vpogledov v interakcije, v katerem imate podatke o segmentu vpogledov občinstva, povezane z okoljem vpogledov občinstva, kjer se ustvarjajo segmenti in profili strank. Več informacij: [Ustvarjanje povezave med vpogledi občinstva in vpogledi v interakcije](integrate-audience-insights-engagement-insights.md)

## <a name="create-audience-insights-segments"></a>Ustvarjanje segmentov vpogledov občinstva 

> [!IMPORTANT]
> Če želite, da se segmenti vpogledov občinstva prikažejo v vpogledih v interakcije, morate najprej [zagnati združevanje in postopke iz strežnika](../audience-insights/merge-entities.md). Postopki iz strežnika so pomembni, ker ustvarjajo edinstveno tabelo, ki pripravlja segmente vpogledov občinstva za skupno rabo z vpogledi v interakcije. (Če je načrtovana osvežitev sistema, se bodo samodejno vključili postopki iz strežnika.)

Segmente vpogledov občinstva lahko uporabite v vnaprej pripravljenih poročilih vpogledov v interakcije ali poročilih po meri, ki ste jih ustvarili. Za več informacij pojdite na [Vnaprej pripravljena poročila o profilu](profile-reports.md) in [Ustvarjanje in urejanje poročil po meri](custom-reports.md).

**Za uporabo segmentov vpogledov občinstva v poročilih o vpogledih v interakcije**

1. Na strani **Delovni prostor** izberite **Podatki**, nato pa zavihek **Segmenti**.

    :::image type="content" source="media/integrate-audience-insights-segments1.png" alt-text="Izberite zavihek Segmenti.":::

   >[!NOTE]
   > Če izberete segment vpogledov občinstva, pridete v vpoglede občinstva, kjer lahko ugotovite, kako je bil ta segment ustvarjen v smislu pravil in logike. Za več informacij o segmentih vpogledov občinstva pojdite na [Ogled in ustvarjanje segmentov](../audience-insights/segments.md).

2. Izberite vnaprej pripravljeno poročilo ali [ustvarite poročilo po meri](custom-reports.md) in nato izberite **Dodaj pogoj**. (Za ta primer smo izbrali poročilo **Ogledi strani**.)

    :::image type="content" source="media/integrate-audience-insights-segments2.png" alt-text="Dodajte pogoj.":::

3. Izberite **Filtriraj po segmentih**, razširite seznam **Vrsta segmenta** in nato izberite **Demografski podatki**.

    :::image type="content" source="media/integrate-audience-insights-segments3.png" alt-text="Izberite vrsto demografskega segmenta.":::

4. Razširite seznam **Ime segmenta**, nato pa izberite segment vpogledov občinstva.

    :::image type="content" source="media/integrate-audience-insights-segments4.png" alt-text="Izberite segment.":::

5. Uporabite lahko enega ali več segmentov, vključno z vedenjskimi (vpogledi v interakcije) in demografskimi (vpogledi občinstva) segmenti. 

    :::image type="content" source="media/integrate-audience-insights-segments6.png" alt-text="Poročilo o ogledih strani je omejeno na stranke v ZDA in na segmente domače strani.":::

Na prejšnji sliki sta bila izbrana segmenta **Stranke v ZDA** in **Domača stran**, kar omejuje poročilo **Ogledi strani**, da prikaže le ta dva segmenta. 


>[!NOTE]
> Segmente vpogledov občinstva lahko uporabite za filtriranje vnaprej pripravljenih poročil, poročil po meri in lijakov v vpogledih v interakcije. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]