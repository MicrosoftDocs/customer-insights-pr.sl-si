---
title: Pregled obogatitve podatkov (predogled).
description: Uporabite zmogljivosti Microsofta in drugih storitev tretjih oseb, da obogatite svoje podatke o strankah.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-enrichments
- ci-enrichment-details
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: fb747f7adc7d87f30f66c5d0ed20bbe238558fde
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304539"
---
# <a name="data-enrichment-preview-overview"></a>Pregled obogatitve podatkov (predogled).

Za obogatitev podatkov o strankah uporabite podatke iz virov, kot so Microsoft in drugi partnerji. Obogatitve neodvisnih ponudnikov so konfigurirane z uporabo [povezav](connections.md), za katere skrbnik nastavi poverilnice in poda soglasje za prenose podatkov. Povezave lahko za konfiguracijo obogatitev uporabljajo skrbniki in sodelavci.  

## <a name="multiple-enrichments-of-the-same-type"></a>Več obogatitev iste vrste

Entiteta, ki jo je treba obogatiti, je določena med konfiguriranjem obogatitve, ki omogoča obogatiti samo podmnožico vseh profilov. Obogatiti je na primer mogoče samo podatke za točno določeni segment. Konfigurirate lahko več obogatitev iste vrste in znova uporabite isto povezavo. Nekatere obogatitve imajo omejitev števila obogatitev iste vrste, ki jih je mogoče ustvariti. Omejitve in trenutno uporabo lahko vidite na vsaki ploščici na **Odkrij** zavihek od **Obogatitev** strani.

## <a name="enrich-data-sources-before-unification"></a>Obogatite vire podatkov pred poenotenjem

Podatke o strankah lahko obogatite pred poenotenjem podatkov, da povečate kakovost ujemanja podatkov. Za več informacij glejte [vir podatkov obogatitev](data-sources-enrichment.md).

## <a name="create-an-enrichment"></a>Ustvarjanje obogatitve

Imeti morate sodelavec ali skrbnika [dovoljenja](permissions.md) za ustvarjanje ali urejanje obogatitev.

Pomaknite se na možnost **Podatki** > **Obogatitev**. The **Odkrij** zavihek prikazuje vse podprte možnosti obogatitve.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Stran zvezdišča za obogatitev.":::

# <a name="individual-consumers-b-to-c"></a>[Posamezni potrošniki (prodaja strankam)](#tab/b2c)

- [Identiteta AbiliTec](enrichment-liveramp.md) zagotavlja LiveRamp AbiliTec
- [Znamke](enrichment-microsoft.md), ki jih zagotavlja Microsoft
- [Demografski podatki](enrichment-experian.md), ki jih zagotavlja Experian
- [Izboljšani naslovi](enrichment-enhanced-addresses.md), ki jih zagotavlja Microsoft
- [Zanimanja](enrichment-microsoft.md), ki jih zagotavlja Microsoft
- [podatki o lokaciji](enrichment-azure-maps.md) zagotavlja Microsoft Azure Zemljevidi
- [Podatki o lokaciji](enrichment-here.md), ki jih zagotavlja HERE Technologies
- [Podatki po meri SFTP](enrichment-SFTP-custom-import.md) prek protokola za varen prenos datotek (SFTP)

# <a name="business-accounts-b-to-b"></a>[Poslovni računi (podjetja podjetjem)](#tab/b2b)

- [Podatki o dejavnosti računa](enrichment-office.md) zagotavlja Microsoft
- [Podatki o podjetju](enrichment-dnb.md) zagotavlja Dun & Bradstreet
- [Podatki o podjetju](enrichment-leadspace.md), ki jih zagotavlja Leadspace
- [Izboljšani naslovi](enrichment-enhanced-addresses.md), ki jih zagotavlja Microsoft
- [Izboljšani podatki podjetja](enrichment-enhanced-company-data.md) zagotavlja Microsoft
- [podatki o lokaciji](enrichment-azure-maps.md) zagotavlja Microsoft Azure Zemljevidi
- [Podatki o lokaciji](enrichment-here.md), ki jih zagotavlja HERE Technologies
- [Podatki po meri SFTP](enrichment-SFTP-custom-import.md) prek protokola za varen prenos datotek (SFTP)

---

## <a name="manage-existing-enrichments"></a>Upravljanje obstoječih obogatitev

Pomaknite se na možnost **Podatki** > **Obogatitev**. Na **Moje obogatitve** si ogledate konfigurirane obogatitve, njihov status, število obogatenih strank in čas zadnje osvežitve podatkov. Seznam obogatitev lahko razvrstite po katerem koli stolpcu ali uporabite iskalno polje, da poiščete obogatitev, ki jo želite upravljati.

Izberite obogatitev za ogled razpoložljivih dejanj.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Možnosti upravljanja obogatitev na seznamu obogatitev.":::

- **Pogled** podrobnosti o obogatitvi s številom obogatenih profilov kupcev.
- **Urejanje** konfiguracije obogatitve.
- [**Teči**](#run-or-refresh-enrichments) obogatitev za posodobitev profilov strank z najnovejšimi podatki. Zaženite več obogatitev hkrati, tako da jih izberete na seznamu.
- **Aktiviraj** oz **Deaktiviraj** obogatitev. Neaktivne obogatitve se ne bodo osvežile med a [načrtovano osveževanje](schedule-refresh.md).
- **Izbriši** obogatitev.

Lahko tudi ustvarjate [segmenti](segments.md) oz [ukrepe](measures.md) od obogatitev.

## <a name="run-or-refresh-enrichments"></a>Zaženite ali osvežite obogatitve

Ko se zaženejo, je mogoče obogatitve osvežiti po samodejnem urniku ali na zahtevo osvežiti ročno.

1. Če želite ročno osvežiti eno ali več obogatitev, jih izberite in izberite **Teči**. Za [načrtujte samodejno osveževanje](schedule-refresh.md), Pojdi do **skrbnik** > **Sistem** > **Urnik**. Čas obdelave je odvisen od velikosti podatkov o stranki.

1. Po želji, [oglejte si napredek procesa obogatitve](#see-the-progress-of-the-enrichment-process).

1. Ko je postopek obogatitve končan, pojdite na **Moje obogatitve** za pregled na novo obogatenih podatkov o profilih strank, čas zadnje posodobitve in število obogatenih profilov.

1. Izberite obogatitev za ogled [rezultati obogatitve](#view-enrichment-results).

### <a name="see-the-progress-of-the-enrichment-process"></a>Oglejte si napredek postopka obogatitve

Najdete lahko podrobnosti o obdelavi obogatitve, vključno z njenim statusom in morebitnimi težavami med osveževanjem ali po zaključku osveževanja. Spoznajte, kateri postopki so potrebni za osvežitev obogatitve in koliko časa je trajalo, da so se postopki izvedli. Stanje obogatitve je podprto za družbe Experian, Leadspace, HERE Technologies, SFTP Import in storitev Zemljevidi Azure.

1. Pomaknite se na možnost **Podatki** > **Obogatitev**.
1. V **Moje obogatitve** izberite status obogatitve, da odprete stransko podokno.
1. V podoknu **Podrobnosti o napredku** razširite razdelek **Obogatitve**.
1. Pod obogatitvijo, za katero želite videti napredek, izberite **Prikaži podrobnosti**.
1. V podoknu **Podrobnosti opravila** izberite **Pokaži podrobnosti**, da si ogledate postopke, ki so vključeni v posodabljanje obogatitve, in njihovo stanje.

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="view-enrichment-results"></a>Oglejte si rezultate obogatitve

Po končanem postopku obogatitve preglejte rezultate obogatitve.

1. Pomaknite se na možnost **Podatki** > **Obogatitev**.
1. V **Moje obogatitve** izberite obogatitev, ki si jo želite ogledati.

Vse obogatitve prikazujejo osnovne informacije, kot je število obogatenih profilov in število obogatenih profilov skozi čas. The **Obogateni predogled strank** ploščica prikazuje vzorec ustvarjene obogatitvene entitete. Če želite videti podroben pogled, izberite **Poglej več** in izberite **podatki** zavihek.

:::image type="content" source="media/enrichments-results.png" alt-text="Stran z rezultati obogatitev.":::

Če je na voljo, **Število strank, obogatenih po področjih** zagotavlja podrobno analizo pokritosti vsakega obogatenega polja.

Nekatere obogatitve prikazujejo tudi informacije, specifične za vrsto obogatitve. Za več informacij si oglejte povezano dokumentacijo.

[!INCLUDE [footer-include](includes/footer-banner.md)]
