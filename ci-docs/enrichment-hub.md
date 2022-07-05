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
ms.openlocfilehash: 6b6daab480db5e37830ff58b71dcdd3bbdbe46da
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053900"
---
# <a name="data-enrichment-preview-overview"></a>Pregled obogatitve podatkov (predogled).

Za obogatitev podatkov o strankah uporabite podatke iz virov, kot so Microsoft in drugi partnerji. Obogatitve neodvisnih ponudnikov so konfigurirane z uporabo [povezav](connections.md), za katere skrbnik nastavi poverilnice in poda soglasje za prenose podatkov. Povezave lahko za konfiguracijo obogatitev uporabljajo skrbniki in sodelavci.  

## <a name="multiple-enrichments-of-the-same-type"></a>Več obogatitev iste vrste

Entiteta, ki jo je treba obogatiti, je določena med konfiguriranjem obogatitve, ki omogoča obogatiti samo podmnožico vseh profilov. Obogatiti je na primer mogoče samo podatke za točno določeni segment. Konfigurirate lahko več obogatitev iste vrste in znova uporabite isto povezavo. Nekatere obogatitve imajo omejitev števila obogatitev iste vrste, ki jih je mogoče ustvariti. Omejitve in trenutna uporaba so vidne na vsaki ploščici na **Odkrijte** zavihek na **Obogatitev** stran.

## <a name="enrich-data-sources-before-unification"></a>Obogatite vire podatkov pred poenotenjem

Podatke o strankah lahko obogatite pred združevanjem podatkov, da izboljšate kakovost ujemanja podatkov. Za več informacij glejte [vir podatkov obogatitev](data-sources-enrichment.md).

## <a name="create-an-enrichment"></a>Ustvarjanje obogatitve

Imeti morate sodelavec ali skrbnika [dovoljenja](permissions.md) za ustvarjanje ali urejanje obogatitev.

Pomaknite se na možnost **Podatki** > **Obogatitev**. The **Odkrijte** zavihek prikazuje vse podprte možnosti obogatitve.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Stran zvezdišča za obogatitev.":::

# <a name="individual-consumers-b-to-c"></a>[Posamezni potrošniki (prodaja strankam)](#tab/b2c)

- [AbiliTec Identity](enrichment-liveramp.md) zagotavlja LiveRamp AbiliTec
- [Znamke](enrichment-microsoft.md), ki jih zagotavlja Microsoft
- [Demografski podatki](enrichment-experian.md), ki jih zagotavlja Experian
- [Izboljšani naslovi](enrichment-enhanced-addresses.md), ki jih zagotavlja Microsoft
- [Zanimanja](enrichment-microsoft.md), ki jih zagotavlja Microsoft
- [podatki o lokaciji](enrichment-azure-maps.md) zagotavlja Microsoft Azure Zemljevidi
- [Podatki o lokaciji](enrichment-here.md), ki jih zagotavlja HERE Technologies
- [Podatki po meri SFTP](enrichment-SFTP-custom-import.md) prek protokola za varen prenos datotek (SFTP)

# <a name="business-accounts-b-to-b"></a>[Poslovni računi (podjetja podjetjem)](#tab/b2b)

- [Podatki o udeležbi na računu](enrichment-office.md) zagotavlja Microsoft
- [Podatki o podjetju](enrichment-dnb.md) zagotavlja Dun & Bradstreet
- [Podatki o podjetju](enrichment-leadspace.md), ki jih zagotavlja Leadspace
- [Izboljšani naslovi](enrichment-enhanced-addresses.md), ki jih zagotavlja Microsoft
- [Izboljšani podatki o podjetju](enrichment-enhanced-company-data.md) zagotavlja Microsoft
- [podatki o lokaciji](enrichment-azure-maps.md) zagotavlja Microsoft Azure Zemljevidi
- [Podatki o lokaciji](enrichment-here.md), ki jih zagotavlja HERE Technologies
- [Podatki po meri SFTP](enrichment-SFTP-custom-import.md) prek protokola za varen prenos datotek (SFTP)

---

## <a name="manage-existing-enrichments"></a>Upravljanje obstoječih obogatitev

Pomaknite se na možnost **Podatki** > **Obogatitev**. Na **Moje obogatitve** zavihek, si oglejte konfigurirane obogatitve, njihov status, število obogatenih strank in zadnjič osvežitev podatkov. Seznam obogatitev lahko razvrstite po katerem koli stolpcu ali uporabite iskalno polje, da poiščete obogatitev, ki jo želite upravljati.

Izberite obogatitev za ogled razpoložljivih dejanj.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Možnosti upravljanja obogatitev na seznamu obogatitev.":::

- **Pogled** podrobnosti o obogatitvi s številom obogatenih profilov kupcev.
- **Urejanje** konfiguracije obogatitve.
- [**teci**](#run-or-refresh-enrichments) obogatitev za posodobitev profilov strank z najnovejšimi podatki. Zaženite več obogatitev hkrati, tako da jih izberete na seznamu.
- **Aktiviraj** oz **Deaktiviraj** obogatitev. Neaktivne obogatitve se ne bodo osvežile med a [načrtovana osvežitev](system.md#schedule-tab).
- **Izbriši** obogatitev.

Lahko tudi ustvarjate [segmentih](segments.md) oz [ukrepe](measures.md) od obogatitev.

## <a name="run-or-refresh-enrichments"></a>Zaženite ali osvežite obogatitve

Po zagonu je mogoče obogatitve osvežiti po samodejnem urniku ali ročno na zahtevo.

1. Če želite ročno osvežiti eno ali več obogatitev, jih izberite in izberite **teci**. Za [načrtujte samodejno osvežitev](system.md#schedule-tab), Pojdi do **Admin** > **sistem** > **Urnik**. Čas obdelave je odvisen od velikosti podatkov o stranki.

1. Po želji, [videti napredek procesa obogatitve](#see-the-progress-of-the-enrichment-process).

1. Ko je postopek obogatitve končan, pojdite na **Moje obogatitve** za pregled podatkov o novo obogatenih profilih strank, času zadnje posodobitve in številu obogatenih profilov.

1. Izberite obogatitev za ogled [rezultate obogatitve](#view-enrichment-results).

### <a name="see-the-progress-of-the-enrichment-process"></a>Oglejte si napredek postopka obogatitve

Podrobnosti o obdelavi obogatitve, vključno s stanjem in možnimi težavami, lahko najdete med osveževanjem ali po končani osvežitvi. Spoznajte, kateri postopki so potrebni za osvežitev obogatitve in koliko časa je trajalo, da so se postopki izvedli. Stanje obogatitve je podprto za družbe Experian, Leadspace, HERE Technologies, SFTP Import in storitev Zemljevidi Azure.

1. Pomaknite se na možnost **Podatki** > **Obogatitev**.
1. V **Moje obogatitve** zavihku, izberite stanje obogatitve, da odprete stransko podokno.
1. V podoknu **Podrobnosti o napredku** razširite razdelek **Obogatitve**.
1. Pod obogatitvijo, za katero želite videti napredek, izberite **Prikaži podrobnosti**.
1. V podoknu **Podrobnosti opravila** izberite **Pokaži podrobnosti**, da si ogledate postopke, ki so vključeni v posodabljanje obogatitve, in njihovo stanje.

## <a name="view-enrichment-results"></a>Oglejte si rezultate obogatitve

Po končani obogatitvi preglejte rezultate obogatitve.

1. Pomaknite se na možnost **Podatki** > **Obogatitev**.
1. V **Moje obogatitve** zavihku izberite obogatitev, ki si jo želite ogledati.

Vse obogatitve prikazujejo osnovne informacije, kot so število obogatenih profilov in število obogatenih profilov skozi čas. The **Obogaten predogled strank** ploščica prikazuje vzorec ustvarjene entitete obogatitve. Če si želite ogledati podroben pogled, izberite **Poglej več** in izberite **Podatki** zavihek.

:::image type="content" source="media/enrichments-results.png" alt-text="Stran z rezultati obogatitve.":::

Če je na voljo, **Število strank, obogatenih po področjih** zagotavlja pregled pokritosti vsakega obogatenega polja.

Nekatere obogatitve prikazujejo tudi informacije, specifične za vrsto obogatitve. Za več informacij si oglejte povezano dokumentacijo.

[!INCLUDE [footer-include](includes/footer-banner.md)]
