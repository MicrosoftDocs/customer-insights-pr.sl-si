---
ms.openlocfilehash: a67714de5aae80a0080c0e631ae6f8986eb2a003
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 09/30/2022
ms.locfileid: "9611137"
---
- **Učinkovitost modela usposabljanja** : Ocene A, B ali C označujejo uspešnost predvidevanje in vam lahko pomagajo pri odločitvi za uporabo rezultatov, shranjenih v izhodni entiteti.

  Ocene so določene na podlagi naslednjih pravil:
  - **A**, ko je model natančno napovedal vsaj 50 % vseh predvidevanj in ko je odstotek natančnih predvidevanj za stranke, ki so bile izgubljene, večji od izhodiščne stopnje za vsaj 10 %.
  - **B**, ko je model natančno napovedal vsaj 50 % vseh predvidevanj in ko je odstotek natančnih predvidevanj za stranke, ki so bile izgubljene, do 10 % večji od izhodiščne stopnje.
  - **C** ko je model natančno predvidel manj kot 50 % skupnih napovedi ali ko je odstotek natančnih napovedi za stranke, ki so odpadle, nižji od izhodišča.
  - **Izhodišče** vzame predvidevanje vnos časovnega okna za model (na primer eno leto) in ustvari različne dele časa tako, da ga deli z 2, dokler ne doseže enega meseca ali manj. Te delce uporablja za ustvarjanje poslovnega pravila za stranke, ki niso opravile nakupa v tem časovnem okviru. Te stranke se štejejo za izgubljene. Za osnovni model je izbrano časovno zasnovano poslovno pravilo z najvišjo zmožnostjo predvidevanja, kdo bo verjetno odšel.

- **Verjetnost izgube (število strank)**: skupine strank na podlagi predvidenega tveganja za izgubo. Po želji, [ustvarite segmente strank](../prediction-based-segment.md) z velikim tveganjem odliva. Takšni segmenti vam pomagajo razumeti, kako mora biti nastavljena vaša prekinitev za članstvo v segmentu.

- **Najvplivnejši dejavniki**: ob ustvarjanju predvidevanja se upošteva veliko dejavnikov. Vsak od dejavnikov ima svoj pomen, izračunan za združena predvidevanja, ki jih ustvari model. Uporabite te dejavnike za pomoč pri potrditvi rezultatov predvidevanje. Ali pa te informacije uporabite pozneje za [ustvarjanje segmentov](../prediction-based-segment.md) ki bi lahko pomagali vplivati na tveganje odliva strank.