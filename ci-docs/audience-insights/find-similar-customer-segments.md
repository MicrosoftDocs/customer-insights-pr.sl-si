---
title: Poiščite podobne stranke z AI (vsebuje video)
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
ms.openlocfilehash: 851ea2c3388de603c1beef4a58e359aa989c9c46
ms.sourcegitcommit: e129a1fa8b020b6bfb6efc3c53fa9d89e1614ad1
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 04/12/2022
ms.locfileid: "8561590"
---
# <a name="similar-customers-preview"></a>Podobne stranke (predogled)

Ta funkcija vam omogoča, da z uporabo umetne inteligence v mreži strank najdete podobne stranke. Za uporabo te funkcije morate ustvariti vsaj en segment. Razširjanje meril obstoječega segmenta pomaga najti stranke, ki so podobne temu segmentu.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> Storitev *Poiščite podobne stranke* uporablja avtomatizirana sredstva za ocenjevanje podatkov in delanje prognoze na podlagi teh podatkov, zato se lahko uporabi kot metoda profiliranja, saj je ta izraz opredeljen v Splošni uredbi o varstvu podatkov ("GDPR"). Za strankino uporabo te funkcije za obdelavo podatkov lahko velja GDPR ali drugi zakoni ali predpisi. Sami ste odgovorni za to, da je vaša uporaba storitve Dynamics 365 Customer Insights, vključno s predvidevanji, v skladu z vsemi veljavnimi zakoni in predpisi, vključno z zakoni v zvezi z zasebnostjo, osebnimi podatki, biometričnimi podatki, varstvom podatkov in zaupnostjo komunikacij.

## <a name="finding-similar-customers"></a>Iskanje podobnih strank

1. V razdelku vpogledov v občinstvo odprite možnost **Segmenti** in izberite segment, na katerem želite, da temelji vaš novi segment. To je *izvorni segment*.

1. V vrstici z dejanji izberite **Poišči podobne stranke**.

1. Preglejte predlagano ime za novi segment in ga po potrebi spremenite.

1. Po želji dodajte [oznake](work-with-tags-columns.md#manage-tags) v nov segment.

1. Preglejte polja, ki opredeljujejo novi segment. Ta polja določajo osnovo, na kateri bo sistem skušal najti podobne kupce kot v vašem izvornem segmentu. Sistem bo privzeto izbral priporočena polja.
  Polja, ki lahko znatno zmanjšajo zmogljivost modela, so samodejno izključena:
  
   - Polja z naslednjimi vrstami podatkov: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Polja s kardinalnostjo (število elementov v polju) manjšo od 2 ali večjo kot 30

1. Odločite se, če želite v novi segment vključiti **Vse stranke** ali samo stranke v **Specifičnem obstoječem segmentu**.

1. Sistem privzeto predlaga, da v svoj izhod vključite le 20 % velikosti ciljnega občinstva. Ta prag uredite po potrebi. Zvišanje praga bo zmanjšalo natančnost.

1. Vključite stranke v svoj izvorni segment, tako da izberete **Vključite člane iz izvornega segmenta poleg strank s podobnimi atributi** potrditveno polje.

1. Izberite **Zaženi** na dnu strani, da začnete opravilo dvojiške razvrstitve (metoda strojnega učenja), ki analizira nabor podatkov.

## <a name="view-the-similar-segment"></a>Oglejte si podoben segment

Po obdelavi podobnega segmenta boste novi segment našli na seznamu na strani **Segmenti**.

> [!div class="mx-imgBorder"]
> ![Segment podobnih strank.](media/expanded-segment.png "Segment podobnih strank")

V delovni vrstici izberite **Pogled**, da odprete podrobnosti o segmentu. Ta pogled vsebuje informacije o porazdelitvi rezultatov v [ocenah podobnosti](#about-similarity-scores). Vrednosti ocen podobnosti boste našli tudi v **Predogledu članov segmenta**.

## <a name="use-the-output-of-a-similar-segment"></a>Uporabite izhod podobnega segmenta

Delate lahko [z izhodom podobnega segmenta](segments.md), tako kot pri drugih segmentih. Na primer: izvozite segment ali sestavite mero.

## <a name="refresh-and-edit-a-similar-segment"></a>Osvežite in uredite podoben segment

Če želite osvežiti podoben segment, ga izberite na strani **Segmenti** in izberite **Osveži** v vrstici z dejanji.

Če uredite podoben segment, bodo podatki ponovno obdelani. Prejšnji ustvarjeni segment se posodobi z osveženimi podatki.
Če želite urediti podoben segment, ga izberite na strani **Segmenti** in izberite **Uredi** v vrstici z dejanji. Uporabite spremembe in izberite **Zaženi** za začetek obdelave.

## <a name="delete-a-similar-segment"></a>Izbrišite podoben segment

Izberite segment na strani **Segmenti** in izberite **Izbriši** v vrstici z dejanji. Nato potrdite izbris.

## <a name="about-similarity-scores"></a>O ocenah podobnosti

Dvojiška razvrstitev modela strojnega učenja dodeli oceno strankam v podobnem segmentu. Rezultat temelji na podobnosti s strankami v izvornem segmentu.

- Ocene podobnosti pod 0,55 so kupci, ki jih sistem uvršča kot *ni podobno* strankam v izvornem segmentu
- Ocene podobnosti med 0,55 – 0,7 so razvrščene kot *nekoliko podobno*
- Ocene podobnosti med 0,7 – 0,85 so razvrščene kot *podobno*
- Ocene podobnosti med 0,85 – 1 so stranke, ki jih sistem uvršča kot *zelo podobno*

Stranke z ocenami podobnosti pod 0,4 niso vključeni v izhod modela. Sistem jih ne zaznava kot dovolj podobne izvornemu segmentu.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
