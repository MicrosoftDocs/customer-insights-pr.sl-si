---
title: Obogatitev poenotenih profilov strank
description: Uporabite zmogljivosti za obogatitev podatkov o strankah.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5d5e12ee44dfa40c470738eaee5c68fdf23d1b2d
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 10/08/2021
ms.locfileid: "7617575"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Obogatitev profilov strank (predogled)

Za obogatitev podatkov o strankah uporabite podatke iz virov, kot so Microsoft in drugi partnerji.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Stran zvezdišča za obogatitev.":::

V razdelku vpogledov v občinstvo odprite **Podatki** > **Obogatitev** za delo z možnostmi obogatitve.  

Za ustvarjanje ali urejanje obogatitev morate imeti dovoljenje »Sodelavec« ali »Skrbnik«. Za več informacij glejte razdelek [Dovoljenja](permissions.md).

V zavihku **Odkrivanje** boste našli vse podprte možnosti obogatitve.

# <a name="individual-customers-b2c"></a>[Posamezne stranke (B2C)](#tab/b2c)

- [Znamke](enrichment-microsoft.md), ki jih zagotavlja Microsoft
- [Zanimanja](enrichment-microsoft.md), ki jih zagotavlja Microsoft
- [Izboljšani naslovi](enrichment-enhanced-addresses.md), ki jih zagotavlja Microsoft 
- [Demografski podatki](enrichment-experian.md), ki jih zagotavlja Experian
- [Podatki po meri](enrichment-SFTP-custom-import.md) s protokolom za varen prenos datotek (SFTP) 
- [Storitev Zemljevidi Azure](enrichment-azure-maps.md) zagotavlja Microsoft

# <a name="business-accounts-b2b"></a>[Poslovni računi (B2B)](#tab/b2b)

- [Podatki o podjetju](enrichment-leadspace.md), ki jih zagotavlja Leadspace
- [Izboljšani naslovi](enrichment-enhanced-addresses.md), ki jih zagotavlja Microsoft 
- [Podatki o lokaciji](enrichment-here.md), ki jih zagotavlja HERE Technologies 
- [Podatki po meri](enrichment-SFTP-custom-import.md) s protokolom za varen prenos datotek (SFTP) 
- [Storitev Zemljevidi Azure](enrichment-azure-maps.md) zagotavlja Microsoft

---

Na zavihku **Moje obogatitve** si lahko ogledate obogatitve, ki ste jih konfigurirali, in uredite njihove lastnosti.

## <a name="manage-existing-enrichments"></a>Upravljanje obstoječih obogatitev

Za ogled vseh konfiguriranih obogatitev odprite zavihek **Moje obogatitve**. Vsaka obogatitev je predstavljena kot vrstica, ki vključuje dodatne informacije o obogatitvi.

Izberite obogatitev, da si ogledate razpoložljive možnosti. Za ogled možnosti lahko izberete tudi treh pik (...) na elementu seznama. Če ste konfigurirali več obogatitev, jih lahko hitro poiščete v polju za iskanje.

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

## <a name="see-the-progress-of-the-enrichment-process"></a>Oglejte si napredek postopka obogatitve

Podrobnosti o obdelavi obogatitve, vključno s stanjem in možnimi težavami, lahko najdete med osveževanjem ali po končani osvežitvi. Spoznajte, kateri postopki so potrebni za osvežitev obogatitve in koliko časa je trajalo, da so se postopki izvedli. Stanje obogatitve je podprto za družbe Experian, Leadspace, HERE Technologies, SFTP Import in storitev Zemljevidi Azure.

Če si želite ogledati stanje obogatitve:

1. Pomaknite se na možnost **Podatki** > **Obogatitev**. 
1. V zavihku **Moje obogatitve** izberite stanje obogatitve, da odprete stransko podokno. 
1. V podoknu **Podrobnosti o napredku** razširite razdelek **Obogatitve**. 
1. Pod obogatitvijo, za katero želite videti napredek, izberite **Prikaži podrobnosti**. 
1. V podoknu **Podrobnosti opravila** izberite **Pokaži podrobnosti**, da si ogledate postopke, ki so vključeni v posodabljanje obogatitve, in njihovo stanje. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
