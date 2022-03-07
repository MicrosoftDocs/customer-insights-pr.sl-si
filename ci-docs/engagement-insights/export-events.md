---
title: Izvoz izboljšanih dogodkov
description: Kako izvoziti izboljšane in osnovne dogodke.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: d062e2982c1041454b083630404f2b68f0da9669
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232908"
---
# <a name="export-events"></a>Izvoz dogodkov

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dogodek predstavlja vedenje uporabnika. Beleži, ko si uporabnik ogleda stran (dogodek ogleda) ali ima interakcijo z vsebino (dogodek dejanja). Ko se lahko odločite, katere lastnosti podatkov želite prikazati v poročilu, se ta navidezni pogled podatkov imenuje *izboljšani dogodek*. Za več informacij glejte razdelek [Ustvarjanje in spreminjanje segmentov](refined-events.md).

- Dogodke in izboljšane dogodke lahko izvozite v zunanji pomnilnik. 
- Izvoz je tok podatkov, ki se giba naprej. Ne morete napolniti toka. 
- Izvoz ima fiksne sheme. Če dogodku dodate lastnosti po meri, ne bodo vključene. Ustvariti boste morali nov izvoz.

## <a name="prerequisites"></a>Zahteve

Preden nastavite izvoz, morate imeti dostop in aktivno naročnino na portal Azure. Med izvozom boste potrebovali podatke o računu za shranjevanje. 

### <a name="create-an-azure-data-lake-storage-gen-2-accounts"></a>Ustvarjanje računov Azure Data Lake Storage Gen 2

1. Vpišite se na portal Azure in [ustvarite nov račun za shranjevanje](/azure/storage/common/storage-account-create). 

1. Prepričajte se, da ste omogočili **hierarhični imenski prostor** na zavihku **Napredno**. 

   :::image type="content" source="media/enable-hierarchical-namespace.png" alt-text="Omogočite hierarhični imenski prostor na zavihku Napredno.":::

1. Po uvedbi pojdite na novo ustvarjeni račun za shranjevanje. V podoknu za krmarjenje izberite **Nastavitve** > **Ključi za dostop**. 

1. Kopirajte **Ime računa** in **Ključ**, da ju uporabite pri ustvarjanju novega izvoza.
   :::image type="content" source="media/storage-account-access-keys.png" alt-text="Ključi za dostop v računu za shrambo.":::

## <a name="export-events"></a>Izvozi dogodke

Obstajata dva načina za priklic pogovornega okna **Izvoz dogodkov**: 
- V razdelku **Podatki** > **Izvozi** izberite **Nov izvoz**.
- Pojdite na možnost **Podatki** > **Dogodki**, izberite možnost **Več [...]** ob dogodku, ki ga želite izvoziti, in v spustnem meniju izberite možnost **Izvozi**. 

:::image type="content" source="media/new-export.png" alt-text="Ustvarjanje novega izvoza":::

Vodeni boste skozi korake za ustvarjanje izvoza:

1. Zagotovite **Izvozno ime** in nato izberite možnost **Naprej**.

1. Na spustnem seznamu **Izbor dogodkov** izberite osnovne dogodke in natančneje določene dogodke, ki jih želite izvoziti. 

1. V razdelku **Struktura datoteke** izberite kadence (urno ali dnevno) za ustvarjanje novih datotek v ciljnem pomnilniku in nato izberite možnost **Naprej**. Dogodki se neprestano izvozijo ob prihodu.

1. V pogovornem oknu **Izbira oblike zapisa**, izberite obliko zapisa za izvoz. Izbirajte med oblikami zapisa **Common Data Model**, **CSV** in **JSON**. Če želite izvoz uporabiti z drugimi aplikacijami Dynamics 365, priporočamo obliko zapisa **Common Data Model**.

1. V pogovornem oknu **Izbira cilja** določite lokacijo za Azure Data Lake Storage Gen 2.
    1. **Ime računa ADLS Gen 2** je ime računa za shranjevanje, v katerega želite shraniti izvoz. 
    1. **Pot mape** opredeljuje, kje naj bo izvoz shranjen v datotečnem sistemu in strukturi imenika za račun za shranjevanje.
    1. **Ključ v skupni rabi** je na voljo na portalu Azure za račun za shranjevanje.

1. Za dokončanje preglejte in potrdite svoje izbire.

## <a name="view-and-manage-exports"></a>Ogled in upravljanje izvozov

Ko nastavite izvoz, pojdite na **Podatki** > **Izvoz**, da si ga ogledate. Izberite **Več [...]** za kateri koli obstoječi izvoz, da ga uredite ali izbrišete.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
