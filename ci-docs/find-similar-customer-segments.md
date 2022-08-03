---
title: Poiščite podobne stranke z AI (predogled) (vsebuje video)
description: Poiščite podobne segmente strank z umetno inteligenco.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segment-builder
- ci-segment-insights
- customerInsights
ms.openlocfilehash: 09fe36a4da45d114cbfccf8dad1e7b80b4b7e320
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170747"
---
# <a name="find-similar-customers-with-ai-preview"></a>Poiščite podobne stranke z AI (predogled)

Poiščite podobne stranke v vaši bazi strank z umetno inteligenco. Za uporabo te funkcije morate ustvariti vsaj en segment. Razširitev kriterijev obstoječega segmenta pomaga najti stranke, ki so podobne temu segmentu.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Poiščite podobne stranke* uporablja avtomatizirana sredstva za vrednotenje podatkov in napovedovanje na podlagi teh podatkov. Zato se lahko uporablja kot metoda profiliranja, kot je ta izraz opredeljen v Splošni uredbi o varstvu podatkov (»GDPR«). Za strankino uporabo te funkcije za obdelavo podatkov lahko velja GDPR ali drugi zakoni ali predpisi. Sami ste odgovorni za to, da je vaša uporaba storitve Dynamics 365 Customer Insights, vključno s predvidevanji, v skladu z vsemi veljavnimi zakoni in predpisi, vključno z zakoni v zvezi z zasebnostjo, osebnimi podatki, biometričnimi podatki, varstvom podatkov in zaupnostjo komunikacij.

## <a name="find-similar-customers"></a>Poišči podobne stranke

1. Pojdi do **Segmenti** in izberite segment, na katerem želite osnovati svoj novi segment. To je *izvorni segment*.

1. Izberite **Poiščite podobne stranke**.

1. Preglejte predlagano ime za novi segment in ga po potrebi spremenite.

1. Po želji dodajte [oznake](work-with-tags-columns.md#manage-tags) v nov segment.

1. Preglejte polja, ki opredeljujejo novi segment. Ta polja določajo osnovo, na kateri bo sistem skušal najti podobne kupce kot v vašem izvornem segmentu. Sistem privzeto izbere priporočena polja. Po potrebi dodajte več polj.
  Polja, ki lahko znatno zmanjšajo zmogljivost modela, so samodejno izključena:
  
   - Polja z naslednjimi vrstami podatkov: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Polja s kardinalnostjo (število elementov v polju) manjšo od 2 ali večjo kot 30

1. Izberite, če želite vključiti **Vse stranke** razen izvornega segmenta ali le stranke v a **drugačen segment** v vašem novem segmentu.

1. Sistem privzeto predlaga, da v svoj izhod vključite le 20 % velikosti ciljnega občinstva. Ta prag uredite po potrebi. Zvišanje praga bo zmanjšalo natančnost.

1. Vključite stranke v svoj izvorni segment tako, da izberete **Vključite člane iz izvornega segmenta poleg strank s podobnimi atributi** potrditveno polje.

1. Izberite **Teči** na dnu strani za začetek a [naloga binarne klasifikacije](#about-similarity-scores) (metoda Strojno učenje), ki analizira nabor podatkov.

## <a name="view-the-similar-segment"></a>Oglejte si podoben segment

Po obdelavi podobnega segmenta boste novi segment našli na seznamu **Segmenti** stran z vrsto **Razširitev**.

Izberite **Pogled** da si ogledate porazdelitev rezultatov [ocene podobnosti](#about-similarity-scores) in vrednosti ocene podobnosti pod **Predogled članov segmenta**.

:::image type="content" source="media/expanded-segment.png" alt-text="Segment podobnih strank.":::

## <a name="manage-a-similar-segment"></a>Upravljajte podoben segment

[Sodelujte s podobnim segmentom in ga upravljajte](segments.md#manage-existing-segments) tako kot pri drugih segmentih. Na primer: izvozite segment ali sestavite mero.

Uredite, osvežite, preimenujte, prenesite in izbrišite podoben segment. Urejanje podobnega segmenta ponovno obdela vaše podatke. Prejšnji ustvarjeni segment se posodobi z osveženimi podatki.

## <a name="about-similarity-scores"></a>O ocenah podobnosti

Dvojiška razvrstitev modela strojnega učenja dodeli oceno strankam v podobnem segmentu. Rezultat temelji na podobnosti s strankami v izvornem segmentu.

- Ocene podobnosti pod 0,55 so kupci, ki jih sistem uvršča kot *ni podobno* strankam v izvornem segmentu
- Ocene podobnosti med 0,55 – 0,7 so razvrščene kot *nekoliko podobno*
- Ocene podobnosti med 0,7 – 0,85 so razvrščene kot *podobno*
- Ocene podobnosti med 0,85 – 1 so stranke, ki jih sistem uvršča kot *zelo podobno*

Stranke z ocenami podobnosti pod 0,4 niso vključeni v izhod modela. Sistem jih ne zaznava kot dovolj podobne izvornemu segmentu.

[!INCLUDE [footer-include](includes/footer-banner.md)]
