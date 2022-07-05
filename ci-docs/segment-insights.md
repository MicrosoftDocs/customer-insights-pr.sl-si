---
title: Vpogled v segmente (predogledna različica)
description: Pridobite vpogled v obstoječe segmente, da vidite razlike in skupne značilnosti.
ms.date: 06/10/2020
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-segment-insights
- customerInsights
ms.openlocfilehash: e90bdc523c3f8857c150ccba9d81f055d39f9feb
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051611"
---
# <a name="segment-insights-preview"></a>Vpogled v segmente (predogledna različica)

Odkrijte dodatne informacije in vpogled v obstoječe segmente. Ugotovite, kako se dva segmenta razlikujeta ali kaj imata skupnega.

## <a name="segment-overlap"></a>Prekrivanje segmentov

Analiza prekrivanja segmentov pokaže, koliko strank in katere stranke so skupne dvema ali več segmentom. Kako se na primer segment pogostih strank prekriva s segmentom, ki vsebuje stranke, zadovoljne z vašo storitvijo ali izdelkom.
Analizirate lahko tudi, kako se prekrivanje spreminja za posamezne atribute.

### <a name="run-an-overlap-analysis"></a>Izvedite analizo prekrivanja

1. V razdelku **Segmenti** izberite zavihek **Vpogled (predogled)**.

1. Izberite **Novo** in nato izberite možnost **Prekrivanje** v podoknu **Izbira vrste vpogleda**.

1. Izberite segmente, ki vas zanimajo, nato izberite **Naprej**.

1. Izbirno lahko izberete eno ali več polj, ki vas zanimajo, da analizirate prekrivanje za posamezne vrednosti polj, nato izberite **Naprej**.

1. Navedite ime za analizo prekrivanja, izbirno ime za prikaz in opis.

1. Za začetek analize izberite možnost **Shrani**. Analiza prekrivanja je pripravljena, ko se stanje »Osveževanje« spremeni v stanje »Uspešno«.

### <a name="view-and-optimize-an-overlap-analysis"></a>Ogled in optimizacija analize prekrivanja

Po končani analizi poiščite podrobnosti o tem vpogledu v razdelku **Segmenti** > **Vpogled (predogled)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Podrobnosti vpogleda v prekrivanje segmentov.":::

Izberite vpogled za prikaz rezultatov analize:

- Število članov, ki se prekrivajo v segmentih, izbranih za analizo.
- Število članov, vključenih v enega od segmentov, ne pa v ostale segmente.
- Če ste med konfiguriranjem analize prekrivanja izbrali polja, jih boste našli na ustreznih zavihkih. S pomočjo spustnega seznama filtrov lahko izberete katerokoli pomembno raven zanimanja, pri čemer vam bo tabela na dnu prikazala ustrezne podatke.

## <a name="segment-differentiators"></a>Diferenciatorji segmentov

Diferenciatorji segmentov vam pomagajo ugotoviti, kako se segment razlikuje od ostalih strank ali od drugega segmenta. Samo izberite segment in sistem bo določil atribute profila in mere, po katerih se izbrani segment razlikuje.

### <a name="run-a-differentiator-analysis"></a>Zagon analize diferenciatorjev

1. V razdelku **Segmenti** izberite zavihek **Vpogled (predogled)**.

1. Izberite **Novo** in nato izberite možnost **Prekrivanje** v podoknu **Izbira vrste vpogleda**.

1. Izberite segment, ki ga želite analizirati, kot **Primarni segment** in nato izberite **Naprej**.

1. Izberite **Vse stranke** ali **Sekundarni segment** za primerjavo s primarnim segmentom, nato izberite **Naprej**.

1. Po želji izberite eno ali več področij, ki vas zanimajo, da analizo osredotočite na posamezne atribute, in izberite **Naprej**.

1. Navedite ime za analizo prekrivanja, izbirno ime za prikaz in opis.

1. Za začetek analize izberite možnost **Shrani**. Analiza prekrivanja je pripravljena, ko se stanje »Osveževanje« spremeni v stanje »Uspešno«.

### <a name="view-and-optimize-a-differentiators-analysis"></a>Ogled in optimizacija analize diferenciatorjev

Po končani analizi poiščite podrobnosti o tem vpogledu v razdelku **Segmenti** > **Vpogled (predogled)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Podrobnosti vpogleda v razlikovalnik segmentov.":::

Izberite vpogled za prikaz rezultatov analize. Analiza diferenciatorjev ima dva zavihka. Na zavihku **Atributi** je seznam atributov profila, ki so obravnavani kot diferenciatorji. Na zavihku **Mere** je seznam diferenciatorjev. Oba zavihka vsebuje naslednje podrobnosti:

- Seznam diferenciatorjev, razvrščenih po oceni razlike.
- **Ocena razlike** za posamezne diferenciatorje. Ocena razlike predstavlja stopnjo razlikovanja atributa med dvema segmentoma. Večja kot je ocena razlike, bolj se atributi med dvema segmentoma razlikujejo. Izberite oceno, da odprete podokno **Ocena razlike** s porazdelitvijo vrednosti za želen atribut.

## <a name="manage-segment-insights"></a>Upravljanje vpogledov v segmente

Za vpoglede lahko v ukazni vrstici uporabite naslednje možnosti:

- **Nazaj**, da se vrnete na seznam vpogledov
- **Osveži**, da znova zaženete analizo
- **Izbriši**, da odstranite vpogled


[!INCLUDE [footer-include](includes/footer-banner.md)]
