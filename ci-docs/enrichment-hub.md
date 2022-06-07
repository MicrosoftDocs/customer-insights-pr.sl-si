---
title: Obogatitev poenotenih profilov strank
description: Uporabite zmogljivosti za obogatitev podatkov o strankah.
ms.date: 03/29/2022
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
ms.openlocfilehash: abc1b6af80e8854ee3bc930453634ef67376c4af
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800625"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Obogatitev profilov strank (predogled)

Za obogatitev podatkov o strankah uporabite podatke iz virov, kot so Microsoft in drugi partnerji.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Stran zvezdišča za obogatitev.":::

Pojdi do **Podatki** > **Obogatitev** za delo z možnostmi obogatitve.  

Za ustvarjanje ali urejanje obogatitev morate imeti dovoljenje »Sodelavec« ali »Skrbnik«. Za več informacij glejte razdelek [Dovoljenja](permissions.md).

V zavihku **Odkrivanje** boste našli vse podprte možnosti obogatitve.

# <a name="individual-consumers-b-to-c"></a>[Posamezni potrošniki (prodaja strankam)](#tab/b2c)

- [Znamke](enrichment-microsoft.md), ki jih zagotavlja Microsoft
- [Zanimanja](enrichment-microsoft.md), ki jih zagotavlja Microsoft
- [Izboljšani naslovi](enrichment-enhanced-addresses.md), ki jih zagotavlja Microsoft 
- [Demografski podatki](enrichment-experian.md), ki jih zagotavlja Experian
- [Podatki po meri](enrichment-SFTP-custom-import.md) s protokolom za varen prenos datotek (SFTP) 
- [Storitev Zemljevidi Azure](enrichment-azure-maps.md) zagotavlja Microsoft
- [Podatki o lokaciji](enrichment-here.md), ki jih zagotavlja HERE Technologies 
- [Identiteta](enrichment-liveramp.md) zagotavlja LiveRamp AbiliTec

# <a name="business-accounts-b-to-b"></a>[Poslovni računi (podjetja podjetjem)](#tab/b2b)

- [Podatki o podjetju](enrichment-leadspace.md), ki jih zagotavlja Leadspace
- [Izboljšani naslovi](enrichment-enhanced-addresses.md), ki jih zagotavlja Microsoft 
- [Izboljšani podatki o podjetju](enrichment-enhanced-company-data.md) zagotavlja Microsoft
- [Podatki o lokaciji](enrichment-here.md), ki jih zagotavlja HERE Technologies 
- [Podatki po meri](enrichment-SFTP-custom-import.md) s protokolom za varen prenos datotek (SFTP) 
- [Storitev Zemljevidi Azure](enrichment-azure-maps.md) zagotavlja Microsoft
- [Podatki o podjetju](enrichment-dnb.md) zagotavlja Dun & Bradstreet
- [Podatki o udeležbi na računu](enrichment-office.md) zagotavlja Microsoft

---

Na zavihku **Moje obogatitve** si lahko ogledate obogatitve, ki ste jih konfigurirali, in uredite njihove lastnosti.

## <a name="manage-existing-enrichments"></a>Upravljanje obstoječih obogatitev

Za ogled vseh konfiguriranih obogatitev odprite zavihek **Moje obogatitve**. Vsaka obogatitev je predstavljena kot vrstica, ki vključuje dodatne informacije o obogatitvi.

Izberite obogatitev, da si ogledate razpoložljive možnosti. Izberete lahko tudi navpično elipso (&vellip;) na element seznama, da si ogledate možnosti. Če ste konfigurirali več obogatitev, jih lahko hitro poiščete v polju za iskanje.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Možnosti upravljanja obogatitev na seznamu obogatitev.":::

- **Pogled** podrobnosti o obogatitvi s številom obogatenih profilov kupcev.
- **Urejanje** konfiguracije obogatitve.
- **Zaženite** obogatitev za posodobitev profilov strank z najnovejšimi podatki.
- **Deaktiviranje** obstoječe obogatitve za preprečitev samodejnega osveževanja z vsako načrtovano osvežitvijo. Podatki iz zadnje uspešne osvežitve bodo še naprej na voljo. **Aktivacija** neaktivne obogatitve za ponovni zagon samodejnega osveževanja z vsako načrtovano osvežitvijo.
- **Izbriši** obogatitev.

Zaženite ali deaktivirajte več obogatitev naenkrat, tako da jih izberete na seznamu. Možnosti ogleda in urejanja niso na voljo kot množično dejanje. Delujejo samo za eno obogatitev naenkrat.

## <a name="enrichments-and-connections"></a>Obogatitve in povezave

Obogatitve neodvisnih ponudnikov so konfigurirane z uporabo [povezav](connections.md), za katere skrbnik nastavi poverilnice in poda soglasje za prenose podatkov. Povezave lahko za konfiguracijo obogatitev uporabljajo skrbniki in sodelavci.  

## <a name="multiple-enrichments-of-the-same-type"></a>Več obogatitev iste vrste

Entiteta, ki jo je treba obogatiti, je določena med konfiguriranjem obogatitve, ki omogoča obogatiti samo podmnožico vseh profilov. Obogatiti je na primer mogoče samo podatke za točno določeni segment. Konfigurirate lahko več obogatitev iste vrste in znova uporabite isto povezavo. Nekatere obogatitve imajo omejitev števila obogatitev iste vrste, ki jih je mogoče ustvariti. Omejitve in trenutno uporabo si lahko ogledate na strani **Obogatitev**.

## <a name="enrich-data-sources-before-unification"></a>Obogatite vire podatkov pred poenotenjem

Podatke o strankah lahko obogatite pred poenotenjem podatkov, da izboljšate kakovost ujemanja podatkov. Za več informacij glejte [vir podatkov obogatitev](data-sources-enrichment.md).

## <a name="see-the-progress-of-the-enrichment-process"></a>Oglejte si napredek postopka obogatitve

Podrobnosti o obdelavi obogatitve, vključno s stanjem in možnimi težavami, lahko najdete med osveževanjem ali po končani osvežitvi. Spoznajte, kateri postopki so potrebni za osvežitev obogatitve in koliko časa je trajalo, da so se postopki izvedli. Stanje obogatitve je podprto za družbe Experian, Leadspace, HERE Technologies, SFTP Import in storitev Zemljevidi Azure.

Če si želite ogledati stanje obogatitve:

1. Pomaknite se na možnost **Podatki** > **Obogatitev**. 
1. V zavihku **Moje obogatitve** izberite stanje obogatitve, da odprete stransko podokno. 
1. V podoknu **Podrobnosti o napredku** razširite razdelek **Obogatitve**. 
1. Pod obogatitvijo, za katero želite videti napredek, izberite **Prikaži podrobnosti**. 
1. V podoknu **Podrobnosti opravila** izberite **Pokaži podrobnosti**, da si ogledate postopke, ki so vključeni v posodabljanje obogatitve, in njihovo stanje. 

## <a name="enrichment-results"></a>Rezultati obogatitve

Po končani obogatitvi lahko pregledate rezultate obogatitve.

1. Pomaknite se na možnost **Podatki** > **Obogatitev**. 
1. Izberite obogatitev, o kateri želite informacije.

Vse obogatitve prikazujejo osnovne informacije, kot so število obogatenih profilov, predogled ustvarjene entitete obogatitve in število obogatenih profilov skozi čas. Če je na voljo, **Število kupcev, obogatenih po področjih** zagotavlja pregled pokritosti vsakega obogatenega polja.

:::image type="content" source="media/enrichments-results.png" alt-text="Stran z rezultati obogatitve.":::

Nekatere obogatitve prikazujejo tudi informacije, specifične za vrsto obogatitve. Za več informacij glejte dokumentacijo za ustrezno obogatitev.


[!INCLUDE [footer-include](includes/footer-banner.md)]
