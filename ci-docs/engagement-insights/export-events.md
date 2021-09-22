---
title: Izvoz izboljšanih dogodkov
description: Kako izvoziti izboljšane in osnovne dogodke.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: faa0c3afb08d1c0282b2164ed914637ce9aad88117af37ba44fdb81e7610e574
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032405"
---
# <a name="export-events"></a>Izvoz dogodkov

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dogodek predstavlja vedenje uporabnika. Beleži, ko si uporabnik ogleda stran (dogodek ogleda) ali ima interakcijo z vsebino (dogodek dejanja). Ko se lahko odločite, katere lastnosti podatkov želite prikazati v poročilu, se ta navidezni pogled podatkov imenuje *izboljšani dogodek*. 

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

Obstajata dva načina izvoza dogodkov: 
- V razdelku **Podatki** > **Izvozi** izberite **Nov izvoz**.
- Pojdite na možnost **Podatki** > **Dogodki**, izberite možnost **Več [...]** ob dogodku, ki ga želite izvoziti, in v spustnem meniju izberite možnost **Izvozi**. 

Vodeni boste skozi korake za ustvarjanje izvoza:

1. Navedite **Ime izvoza**.

1. Na spustnem seznamu **Izbor dogodkov** izberite osnovne dogodke in natančneje določene dogodke, ki jih želite izvoziti. 

1. Pod možnostjo **Struktura datoteke** izberite zaporedje, da ustvarite nove datoteke v ciljnem pomnilniku. Dogodki se neprestano izvozijo ob prihodu.

1. Izberite obliko za izvoz. Izbirate lahko med oblikami zapisa **Common Data Model**, **CSV** in **JSON**. Za uporabo izvoza z drugimi aplikacijami Dynamics 365 priporočamo uporabo oblike zapisa Common Data Model.

1. Pri koraku **Izbira cilja** določite lokacijo za Azure Data Lake Storage Gen 2.
    1. **Ime računa ADLS Gen 2** je ime računa za shranjevanje, v katerega želite shraniti izvoz. 
    1. **Pot mape** opredeljuje, kje naj bo izvoz shranjen v datotečnem sistemu in strukturi imenika za račun za shranjevanje.
    1. **Ključ v skupni rabi** je na voljo na portalu Azure za račun za shranjevanje.

1. Preglejte in potrdite svoj izbor.

## <a name="view-and-manage-exports"></a>Ogled in upravljanje izvozov

Ko nastavite izvoz, pojdite na **Podatki** > **Izvoz**, da si ga ogledate. Izberite **Več [...]** za kateri koli obstoječi izvoz, da ga uredite ali izbrišete.


[!INCLUDE[footer-include](../includes/footer-banner.md)]