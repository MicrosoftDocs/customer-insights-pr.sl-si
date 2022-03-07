---
title: Poročila o lijakih
description: Kako uporabiti poročila o lijakih, da bi razumeli, kako občinstvo sprejema odločitve.
ms.reviewer: mhart
ms.author: kamacdon
author: kamacdon
ms.date: 09/21/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 7bb961c5ba8d42f704eefe0dcb22e561367f3efb
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226281"
---
# <a name="create-and-manage-funnel-reports"></a>Ustvarjanje in upravljanje poročil o lijakih

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

V poročilo o lijakih so zbrane informacije o korakih, ki nastopijo med dejavnostmi strank na vaši spletni strani ali v vaši mobilni aplikaciji. Pomaga vam razumeti, kako občinstvo napreduje skozi postopek in prepozna odstopne točke. Poročilo o lijaku lahko na primer uporabite za določitev poti, za katere se odločijo vaše stranke, preden opravijo nakup. Poročilo o lijaku vsebuje podatke za informiranje o odločitvah in opredelitev območij za optimizacijo in izboljšave postopkov.

## <a name="create-a-funnel-report"></a>Ustvarjanje poročila o lijaku

Če želite ustvariti poročilo o lijaku, določite korake, ki jih želite vključiti, in aktivnost za vsak korak. Dejavnost je [dogodek](glossary.md), ki predstavlja vedenje uporabnika. Poročilo o lijaku prikazuje število uporabnikov, ki so zaključili vsak določen korak. 

1. Odprite razdelek **Lijaki** in izberite **+ Nov lijak** za začetek poročila o lijaku.

1. Pri možnosti **Urejevalnik lijakov** pod možnostjo **Koraki** izberite **+ Dodaj korak.** 

1. Vnesite ime v **Naziv koraka**.

   :::image type="content" source="media/new-funnel-report.png" alt-text="Novo poročilo o lijaku.":::

1. Izberite **Dejavnost**. Dejavnost beleži, ko si uporabnik ogleda stran (dejavnost **Ogled**) ali ima interakcijo z vsebino (dejavnost **Dejanje**).

1. Uporabite **Merila koraka**, da določite razsežnost dejavnosti. [Razsežnosti](dimensions.md) so atributi, ki lahko opisujejo, filtrirajo ali združujejo podatke.

1. Po želji lahko konfigurirate korake za lijak z več pogoji. Izberite **Dodaj pogoj**, da določite več razsežnosti v koraku. Dodatna merila morajo uporabljati isto vrsto dejavnosti. Izberete lahko, ali je z operaterjem AND ali OR povezanih več pogojev.

   :::image type="content" source="media/funnel-add-condition.png" alt-text="Urejevalnik lijaka prikazuje konfiguracijo korakov z več pogoji.":::

1. Izberite **Dodaj korak**, dokler ne zaključite vseh korakov, ki jih želite v poročilu.

1. Izberite **Shrani**, poimenujte poročilo in znova izberite **Shrani**. 

### <a name="example-fourth-coffee-company-funnel-report"></a>Primer: poročilo o lijaku podjetja Fourth Coffee

Naslednji scenarij prikazuje en način uporabe poročila o lijaku. Analitik podjetja Fourth Coffee želi razumeti vpliv nedavne promocije na cene naročnin. Analitik ustvari poročilo o lijaku za prepoznavanje dejavnosti strank. Začne se, ko stranke pridejo na domačo stran podjetja, dokler ne uporabijo promocijske kode za naročnino. Analitik ustvari poročilo o lijaku z naslednjimi koraki:

1. korak: Stranke, ki pristanejo na domači strani   
2. korak: Stranke, ki opravijo nakup   
3. korak: Stranke, ki s promocijsko kodo dobijo popust na naročnino   
4. korak: Prijava na naročnino   

:::image type="content" source="media/funnel-report-example.png" alt-text="primer poročila o lijaku.":::
  
Ta lijak vam omogoča, da vidite število uporabnikov, ki so promocijsko kodo po enkratnem nakupu uporabili za prijavo v naročniški program.

### <a name="configure-advanced-settings"></a>Konfiguriranje naprednih nastavitev 

Poročila o lijaku vam omogočajo, da določite omejitev časa, potrebnega za dokončanje lijaka. Čas za dokončanje lijaka lahko na primer nastavite na štiri dni. Ta nastavitev bo štela samo uspešne prijave na naročnino, ki so bile opravljene v štirih dneh od obiska domače strani s strani uporabnika.

1. Odprite razdelek **Lijaki**, da odprete **Knjižnica lijakov**.

1. Izberite ime, da odprete poročilo. 

1. V podoknu **Urejevalnik lijakov** izberite **Napredne nastavitve**. 

1. Omejite čas za dokončanje lijaka na **Vklopljeno**.

   :::image type="content" source="media/funnel-limit-time.png" alt-text="Urejevalnik lijaka prikazuje napredne nastavitve in možnosti za omejitev časa za dokončanje lijaka.":::

1. Čas, v katerem mora biti lijak dokončan, izberite na spustnem seznamu **Nastavite omejitev na**.

1. Če želite uporabiti spremembe, izberite **Shrani**.


## <a name="cross-channel-funnel-reports"></a>Poročila o lijakih v različnih kanalih 

Vpogledi v interakcije omogočajo zbiranje podatkov o vedenju strank v vaši mobilni aplikaciji. Ko ste svojo mobilno aplikacijo opremili z vpogledi v interakcije [kompleta za razvoj programske opreme za Android](get-started-android.md) ali [kompleta za razvoj programske opreme za iOS](get-started-ios.md), lahko pripravite poročila o lijakih v različnih kanalih. 

### <a name="create-a-cross-channel-funnel-report"></a>Pripravite poročila o lijakih v različnih kanalih 

1. Sledite korakom in [pripravite poročilo o lijakih](#create-a-funnel-report).    

1. Če želite spremljati interakcije svojih strank z vašo blagovno znamko tako na svojem spletnem mestu kot v mobilni aplikaciji ali na več spletnih mestih, uporabite preklopnik med delovnimi okolji in ustvarite korake za lijak s podatki iz drugih delovnih prostorov. V **Urejevalniku lijakov** pod možnostjo **Koraki** izberite, iz katerega delovnega prostora naj bodo podatki vašega koraka za lijak.

## <a name="manage-funnel-reports"></a>Upravljanje poročil o lijakih

Poročila o lijakih lahko pregledate, da analizirate podatke, spremljate uspešnost in zbirate vpoglede.

> [!NOTE]
> - Poročila o lijakih za vpoglede v interakcije trenutno podpirajo scenarije, v katerih so vsi uporabniki v lijaku anonimni ali pa je bila pri vseh uporabnikih preverjena pristnost. 
> - Zgodovinski podatki v poročilih o lijakih so na voljo za zadnjih 30 dni.

### <a name="view-funnel-reports"></a>Ogled poročil o lijakih

1. Odprite razdelek **Lijaki**, da odprete **Knjižnica lijakov**.
1. Izberite ime, da odprete poročilo.    

### <a name="see-the-data-collected-for-a-report"></a>Oglejte si zbrane podatke za poročilo   

Za ogled informacij o fazi

- Kažite na korak v poročilu.

:::image type="content" source="media/funnel-step-data.png" alt-text="podatki lijaka.":::

### <a name="change-the-date-range-for-the-funnel-report"></a>Spremenite časovno obdobje za poročilo o lijaku

1. Odprite razdelek **Lijaki**, da odprete **Knjižnica lijakov**.

1. Izberite ime, da odprete poročilo.

1. Odprite razdelek **časovno obdobje** in s seznama izberite novo časovno obdobje oz. **Fiksno časovno obdobje**, da določite časovno obdobje.

## <a name="edit-or-delete-funnel-reports"></a>Urejanje ali brisanje poročil o lijakih

Lahko spremenite ime poročila o lijakih, ga izbrišete ali spremenite korake v poročilu.

### <a name="rename-or-delete-a-funnel-report"></a>Preimenovanje ali brisanje poročila o lijaku

1. Odprite razdelek **Lijaki**, da odprete **Knjižnica lijakov**. 

1. Izberite **Več** poleg poročila, ki ga želite spremeniti, in izberite **Uredi ime** ali **Izbriši**.

### <a name="edit-a-funnel-step"></a>Urejanje koraka pri lijaku  

1. Odprite razdelek **Lijaki**, da odprete **Knjižnica lijakov**. 

1. Izberite ime, da odprete poročilo.

1. Izberite korak, ki ga želite urediti.

1. Izberite **Uredi**.

1. V **urejevalniku lijakov** posodobite podatke, ki jih želite spremeniti.  

1. Izberite **Shrani**.

### <a name="reorder-a-funnel-step"></a>Spreminjanje vrstnega reda koraka pri lijaku

1. Odprite razdelek **Lijaki**, da odprete **Knjižnica lijakov**. 

1. Izberite ime, da odprete poročilo.

1. Izberite korak, ki mu želite spremeniti vrstni red.

1. Izberite **Premik** in potem **Gor**, **Dol**, **Na vrh** ali **Spodaj**, da premaknete korak.

### <a name="delete-a-funnel-step"></a>Brisanje koraka pri lijaku

1. Odprite **Lijaki**, da odprete **Knjižnica lijakov**. 

1. Izberite ime, da odprete poročilo.

1. Izberite korak, ki ga želite odstraniti, in izberite **Izbriši**.

## <a name="funnel-insights"></a>Vpogledi v lijake 

Vpogledi v interakcije zdaj strankam ponujajo vpoglede v lijake. S vpogledi v lijake pridobite podrobnejši vpogled v vedenje strank glede korakov v vašem poročilu o lijaku. Ko ustvarite in shranite novo poročilo o lijaku, se za vaše poročilo samodejno ustvarijo vpogledi v lijake. 

:::image type="content" source="media/funnel-insights.png" alt-text="Vpogledi v lijake.":::

> [!NOTE]
> Vpoglede v lijake je mogoče ustvariti samo za korake za lijak, ki **ne** vključujejo razsežnosti po meri. Če želite ustvariti vpoglede v lijake za vse korake v svojem lijaku, uporabite pripravljene razsežnosti vpogledov v interakcije, da ustvarite korake za lijak. 

Vpoglede v lijake si lahko ogledate v naslednjih kategorijah, tako na glavni ravni kot v korakih: 

 - Stopnja konverzije
 -    Stopnja konverzije med možnostma »Dokončanje nakupa« in »Nakup« je 22 %.
 - Čas prehoda 
 -    Povprečen čas prehoda med možnostma »Voziček« in »Dokončanje nakupa« je 23 minut. 
 - Čas zaključka 
 -    Povprečni čas, ki ga stranke porabijo za dokončanje lijaka, je 47 minut. 

Uporabite te vpoglede za podrobnejše raziskovanje vedenja strank ter boljše razumevanje točke oddaje in pretvorb za poročilo o lijaku. 

Če želite primerjati vpoglede v različnih korakih, izberite **Prikaži razčlenitev korakov** ali **Primerjaj z drugimi koraki** s kartic vpogledov. Te bodo prikazale palični grafikon, ki primerja meritve za vsak korak lijaka. 

Vpogledi v lijake se vnovično izračunajo vsakih 24 ur ali ko izberete **Shrani** in shranite svoje poročilo o lijaku. 

> [!NOTE]
> Če si želite ogledati vpoglede za svoj lijak, morate poročilo shraniti vsakič, ko ga spremenite. 

