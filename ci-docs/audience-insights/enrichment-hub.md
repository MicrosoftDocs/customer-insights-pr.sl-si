---
title: Obogatitev poenotenih profilov strank
description: Uporabite zmogljivosti za obogatitev podatkov o strankah.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c25cfbf3808fc1534b54d2d834f1c63ff4c9fe0a
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667114"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Obogatitev profilov strank (predogled)

Za obogatitev podatkov o strankah uporabite podatke iz virov, kot so Microsoft in drugi partnerji.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Stran zvezdišča za obogatitev":::

V razdelku vpogledov v občinstvo odprite **Podatki** > **Obogatitev** za delo z možnostmi obogatitve.    
Za ustvarjanje ali urejanje obogatitev morate imeti dovoljenje »Sodelavec« ali »Skrbnik«. Za več informacij glejte razdelek [Dovoljenja](permissions.md).

Na zavihku **Odkrivanje** so na voljo te obogatitve:

- [Blagovne znamke](enrichment-microsoft-graph.md) zagotavlja Microsoft Graph.
- [Zanimanja](enrichment-microsoft-graph.md) zagotavlja Microsoft Graph.
- [Podatki o podjetju](enrichment-leadspace.md), ki jih zagotavlja Leadspace
- [Demografski podatki](enrichment-experian.md), ki jih zagotavlja Experian
- [Podatki o lokaciji](enrichment-here.md), ki jih zagotavlja HERE Technologies
- [Podatki po meri](enrichment-SFTP-custom-import.md) s protokolom za varen prenos datotek (SFTP)

Na zavihku **Moje obogatitve** si lahko ogledate obogatitve, ki ste jih konfigurirali, in uredite njihove lastnosti.

## <a name="manage-existing-enrichments"></a>Upravljanje obstoječih obogatitev

Pojdite na razdelek **Moje obogatitve** za ogled vseh konfiguriranih obogatitev. Vsaka obogatitev je predstavljena kot vrstica, ki vključuje dodatne informacije o obogatitvi.

Izberite obogatitev in si oglejte razpoložljive možnosti. Lahko pa izberete elipso (...) na elementu s seznama in si tako ogledate možnosti.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Možnosti upravljanja obogatitev na seznamu obogatitev":::

- **Pogled** podrobnosti o obogatitvi s številom obogatenih profilov kupcev.
- **Urejanje** konfiguracije obogatitve.
- **Zaženite** obogatitev za posodobitev profilov strank z najnovejšimi podatki.
- **Deaktiviranje** obstoječe obogatitve za preprečitev samodejnega osveževanja z vsako načrtovano osvežitvijo. Podatki iz zadnje uspešne osvežitve bodo še naprej na voljo. **Aktivacija** neaktivne obogatitve za ponovni zagon samodejnega osveževanja z vsako načrtovano osvežitvijo.
- **Brisanje** obogatitve.

Več obogatitev lahko zaženete ali deaktivirate hkrati, tako da jih izberete na seznamu. Možnosti pogleda in urejanja niso na voljo kot množično dejanje in delujejo le za eno obogatitev na enkrat.
