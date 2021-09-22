---
title: Upravljanje piškotkov in soglasje uporabnika za shranjevanje uporabniških podatkov
description: Preberite, kako se uporabljajo piškotki in soglasja uporabnikov za prepoznavanje obiskovalcev spletnega mesta.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7b3195a92c969ab36e5b43f4c2e4221ff477a0a8958838e1256528f58fe13dce
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: sl-SI
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036758"
---
# <a name="manage-cookies-and-user-consent"></a>Upravljanje piškotkov in soglasje uporabnikov

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Možnost vpogledov v interakcije storitve Dynamics 365 Customer Insights uporablja piškotke in lokalni prostor za shranjevanje (`localStorage`) za prepoznavanje obiskovalcev spletnega mesta.

Piškotki so majhne datoteke, ki shranjujejo delčke informacij o interakcijah uporabnika s spletnim mestom. Shranjeni so v spletnih brskalnikih. Ko uporabniki obiščejo spletno mesto, za katerega imajo shranjene piškotke, brskalnik te podatke pošlje strežniku, ki vrne informacije, edinstvene za uporabnika. To je tehnologija, ki omogoča na primer, da spletni nakupovalni voziček obdrži izbrane predmete, tudi če uporabnik zapusti spletno mesto.

## <a name="user-consent"></a>Soglasje uporabnika

[Splošna uredba o varstvu podatkov (GDPR)](/dynamics365/get-started/gdpr/) je uredba Evropske unije (EU), ki določa, kako naj organizacije ravnajo z zasebnostjo in varnostjo svojih uporabnikov. Piškotki pogosto shranjujejo ali zbirajo »osebne podatke«, kot je spletni identifikator, ki ga ureja GDPR. Če vaše podjetje zaposluje in/ali prodaja posameznikom v EU, na katere se nanašajo podatki, GDPR vpliva na vas. [Preberite več o tem, kako vam lahko Microsoft pomaga pri skladnosti z GDPR](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Če želite kompletu za razvoj programske opreme za vpoglede v interakcije dovoliti shranjevanje piškotkov ali drugih občutljivih informacij, morate navesti, ali so uporabniki podali soglasje. To se zgodi ob inicializaciji kompleta za razvoj programske opreme.

Če navedete, da ni soglasja uporabnika, komplet za razvoj programske opreme ne bo shranil nobenih podatkov in ne bo pošiljal dogodkov, ki jih je mogoče uporabiti za sledenje vedenju uporabnikov. Vsi predhodno shranjeni podatki bodo izbrisani iz brskalnika.

Če vrednost soglasja uporabnika ni določena, bo komplet za razvoj programske opreme domneval, da je uporabnik podal soglasje. To pomeni, da bodo podatki zbrani, če (kot naša stranka) v kompletu za razvoj programske opreme ne navedete vrednosti za soglasje uporabnika. Če pa navedete, da mora biti vrednost za soglasje uporabnika »true«, se podatki ne bodo zbirali, če uporabnik zavrne ali ne poda izrecnega soglasja.

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Shranjevanje podatkov o obiskovalcih v možnosti vpogledov v interakcije

### <a name="cookies"></a>Piškotki

- _msei
    - Shrani anonimni ID uporabnika. Ta piškotek se nastavi v domeni stranke in poteče v 365 dneh.

### <a name="local-storage"></a>Lokalna shramba

Možnost vpogledov v interakcije uporablja tudi lokalni prostor za shranjevanje (`localStorage`) za sledenje neobčutljivim podatkom. Ti podatki so v celoti shranjeni v samem brskalniku, promet pa se ne pošilja na vaše strežnike ali z njih.

- *EISession.Id* 
    - Shrani informacije o trenutni seji uporabnika, kot so ID seje, kdaj se je začela in kdaj poteče.
- *EISession.Previous*
    - Shrani URL prej obiskane strani v trenutni seji.
    
Ključi v lokalnem prostoru za shranjevanje ne potečejo samodejno. Med naslednjo sejo jih bo ponastavil komplet za razvoj programske opreme.

## <a name="deleting-cookies"></a>Brisanje piškotkov

Stranke lahko v nastavitvah svojih brskalnikov kadar koli ročno izbrišejo piškotke in lokalne ključe shrambe.


[!INCLUDE[footer-include](../includes/footer-banner.md)]