---
title: Obogatitev poenotenih profilov strank
description: Uporabite zmogljivosti za obogatitev podatkov o strankah.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c35e73b366fcd5db2ba5a757295ddda6db30efa0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305268"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Obogatitev profilov strank (predogled)

Za obogatitev podatkov o strankah uporabite podatke iz virov, kot so Microsoft in drugi partnerji.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Stran zvezdišča za obogatitev":::

V razdelku vpogledov v občinstvo odprite **Podatki** > **Obogatitev** za delo z možnostmi obogatitve.  

Za ustvarjanje ali urejanje obogatitev morate imeti dovoljenje »Sodelavec« ali »Skrbnik«. Za več informacij glejte razdelek [Dovoljenja](permissions.md).

Na zavihku **Odkrivanje** so na voljo te obogatitve:

- [Znamke](enrichment-microsoft.md), ki jih zagotavlja Microsoft
- [Zanimanja](enrichment-microsoft.md), ki jih zagotavlja Microsoft
- [Izboljšani naslovi](enrichment-enhanced-addresses.md), ki jih zagotavlja Microsoft
- [Podatki o podjetju](enrichment-leadspace.md), ki jih zagotavlja Leadspace
- [Demografski podatki](enrichment-experian.md), ki jih zagotavlja Experian
- [Podatki o lokaciji](enrichment-here.md), ki jih zagotavlja HERE Technologies
- [Podatki po meri](enrichment-SFTP-custom-import.md) s protokolom za varen prenos datotek (SFTP)

Na zavihku **Moje obogatitve** si lahko ogledate obogatitve, ki ste jih konfigurirali, in uredite njihove lastnosti.

## <a name="manage-existing-enrichments"></a>Upravljanje obstoječih obogatitev

Za ogled vseh konfiguriranih obogatitev odprite zavihek **Moje obogatitve**. Vsaka obogatitev je predstavljena kot vrstica, ki vključuje dodatne informacije o obogatitvi.

Izberite obogatitev in si oglejte razpoložljive možnosti. Za ogled možnosti lahko izberete tudi treh pik (...) na elementu seznama.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Možnosti upravljanja obogatitev na seznamu obogatitev":::

- **Pogled** podrobnosti o obogatitvi s številom obogatenih profilov kupcev.
- **Urejanje** konfiguracije obogatitve.
- **Zaženite** obogatitev za posodobitev profilov strank z najnovejšimi podatki.
- **Deaktiviranje** obstoječe obogatitve za preprečitev samodejnega osveževanja z vsako načrtovano osvežitvijo. Podatki iz zadnje uspešne osvežitve bodo še naprej na voljo. **Aktivacija** neaktivne obogatitve za ponovni zagon samodejnega osveževanja z vsako načrtovano osvežitvijo.
- **Brisanje** obogatitve.

Več obogatitev lahko zaženete ali deaktivirate hkrati, tako da jih izberete na seznamu. Možnosti pogleda in urejanja niso na voljo kot množično dejanje in delujejo le za eno obogatitev na enkrat.

## <a name="enrichments-and-connections"></a>Obogatitve in povezave

Obogatitve neodvisnih ponudnikov so konfigurirane z uporabo [povezav](connections.md), za katere skrbnik nastavi poverilnice in poda soglasje za prenose podatkov. Za konfiguriranje obogatitev lahko povezavo uporabijo skrbniki in sodelavci.  

## <a name="multiple-enrichments-of-the-same-type"></a>Več obogatitev iste vrste

Entiteta, ki jo je treba obogatiti, je določena med konfiguriranjem obogatitve, ki omogoča obogatiti samo podmnožico vseh profilov. Obogatiti je na primer mogoče samo podatke za točno določeni segment. Konfigurirate lahko več obogatitev iste vrste in znova uporabite isto povezavo. Nekatere obogatitve imajo omejitev števila obogatitev iste vrste, ki jih je mogoče ustvariti. Omejitve in trenutno uporabo si lahko ogledate na strani **Obogatitev**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
