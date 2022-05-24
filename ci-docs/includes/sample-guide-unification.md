---
ms.openlocfilehash: 1d79987893986148421c316193b27d268cfe0a0b
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755564"
---
Po zaužitju podatkov začnite postopek združevanja podatkov, da ustvarite enoten profil stranke. Če želite več informacij, glejte [Poenotenje podatkov](../data-unification.md).

### <a name="select-source-fields"></a>Izberite izvorna polja

1. Po vnosu podatkov preslikajte stike iz podatkov o elektronskem poslovanju in zvestobi v običajne vrste podatkov. Pojdi do **Podatki** > **Združite**.

1. Izberite entitete, ki predstavljajo profil stranke – **StikiEPoslovanja** in **zvesteStranke**.

   ![Poenotenje virov podatkov o elektronskem poslovanju in zvestobi.](../media/unify-ecommerce-loyalty.png)

1. Izberite **IDstika** kot primarni ključ za **StikiEPoslovanja** in **ID zvestobe** kot primarni ključ za **zvesteStranke**.

1. Izberite **Naprej**. Preskočite podvojene zapise in izberite **Naslednji**.

### <a name="match-conditions"></a>Pogoji tekme

1. Izberite **Kontakti za e-trgovino: e-trgovina** kot primarni subjekt in vključuje vse zapise.

1. Izberite **loyCustomers: Shema zvestobe** in vključuje vse zapise.

1. Dodajte pravilo:
   - Izberite **Polno ime** za kontakte e-trgovine in loyCustomers.
   - Izberite **Vrsta (telefon, ime, naslov, ...)** za **Normalizirajte**.
   - Nastavite **Raven natančnosti**: **Osnovno** in **Vrednost**: **Visoko**.
   - Vnesite **Polno ime, e-pošta** za ime.

1. Dodajte drugi pogoj za e-poštni naslov:
   - Izberite **E-naslov** za kontakte e-trgovine in loyCustomers.
   - Pustite polje Normaliziraj prazno.
   - Nastavite **Raven natančnosti**: **Osnovno** in **Vrednost**: **Visoko**.

   ![Poenotenje pravila ujemanja za ime in e-pošto.](../media/unify-match-rule.png)

1. Izberite **Dokončano**.

1. Izberite **Naprej**.

### <a name="unify-fields"></a>Poenoti polja

1. Preimenujte **ContactId** za **loyCustomers** subjekt za **ContactIdLOYALTY** da se razlikuje od drugih zaužitih ID-jev.

1. Izberite **Naslednji** pregledati in nato izbrati **Ustvarite profile strank**.
