---
title: Ustvarite preproste segmente s hitrimi segmenti
description: Ustvarite preproste segmente strank, da jih združite na podlagi različnih atributov.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 98260371a17ff8a05912cc1bc08c67fbe9755727
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171167"
---
# <a name="create-simple-segments-with-quick-segments"></a>Ustvarite preproste segmente s hitrimi segmenti

Hitri segmenti vam omogočajo hitro izdelavo preprostih segmentov z enim samim operatorjem za hitrejši vpogled. Hitri segmenti so podprti samo v okoljih za **posamezne stranke**.

## <a name="create-a-new-segment-with-quick-segments"></a>Ustvarite nov segment s hitrimi segmenti

1. Izberite **Segmenti**.

1. Izberite **Novo** > **Ustvari iz**.
   - Izberite možnost **Profili**, da ustvarite segment, ki temelji na *poenoteni entiteti stranke*.
   - Izberite možnost **Mere** za gradnjo segmenta okoli mer, ki ste jih že ustvarili.
   - Izberite možnost **Obveščanje**, da sestavite segment okoli ene od izhodnih entitet, ki ste jih ustvarili z zmogljivostmi **Predvidevanja** ali **Modeli po meri**.

1. V pogovornem oknu **Nov hitri segment** izberite atribut s spustnega seznama **Polje**. Na podlagi vaše izbire sistem ponuja različne vrednosti.
   - Pri kategoričnih poljih je prikazanih 10 najboljših strank. Izberite **Vrednost** in **Pregled**.
   - Za številčni atribut sistem prikaže, katera vrednost atributa spada pod percentil posamezne stranke. Izberite **Operator** in **Vrednost** ter nato **Pregled**.

1. Sistem zagotavlja **Ocenjena velikost segmenta**. Izberite, ali želite ustvariti segment, ki ste ga definirali, ali se vrniti in izbrati drugo polje.

   :::image type="content" source="media/quick-segment-name.png" alt-text="Ime in ocena za hitri segment.":::

1. Zagotovite a **Ime** in **Ime izhodne entitete** za vaš segment. Po želji dodajte [oznake](work-with-tags-columns.md#manage-tags).

1. Izberite **Shrani**, da ustvarite segment. The **Segmenti** prikazi strani.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-steps"></a>Naslednji koraki

[Izvozite segment](export-destinations.md) in raziščite [Integracija kartice stranke](customer-card-add-in.md) za uporabo segmentov v drugih aplikacijah.

[!INCLUDE [footer-include](includes/footer-banner.md)]
