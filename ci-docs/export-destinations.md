---
title: Pregled izvozov (predogledna različica)
description: Upravljajte izvoze za skupno rabo podatkov.
ms.date: 08/12/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- ci-connections
- customerInsights
ms.openlocfilehash: 44f58d694b9bd35a8d8c04d487d40743291e0566
ms.sourcegitcommit: ef3e17134d44d2731605381ea0385dbc5aef6120
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 09/09/2022
ms.locfileid: "9460210"
---
# <a name="exports-preview-overview"></a>Pregled izvozov (predogledna različica)

 Izvozi vam omogočajo skupno rabo določenih podatkov z različnimi aplikacijami. Vključujejo lahko profile strank, entitete, sheme in podrobnosti preslikave. Za vsak izvoz je potrebna [povezava, ki jo nastavi skrbnik, za upravljanje preverjanja pristnosti in dostopa](connections.md). Na strani **Izvozi** so prikazani vsi konfigurirani izvozi.

## <a name="export-types"></a>Vrste izvoza

Obstajata dve glavni vrsti izvoza:  

- **Izvoz podatkov** omogočajo izvoz katere koli vrste entitete, ki je na voljo v Customer Insights. Entitete, ki jih izberete za izvoz, se izvozijo z vsemi podatkovnimi polji, metapodatki, shemami in podrobnostmi preslikave.
- **Izvozi segmentov** omogočajo izvoz entitet segmentov iz Customer Insights. Za posamezne potrošnike (B-to-C) segmenti predstavljajo seznam profilov kupcev. Za podjetja (B-to-B), [segmenti lahko predstavljajo seznam računov ali stikov](segment-builder.md#create-a-new-segment-with-segment-builder). Ko konfigurirate izvoz, izberete vključena podatkovna polja, odvisno od ciljnega sistema, v katerega izvažate podatke.

### <a name="export-segments"></a>Izvoz segmentov

**Izvoz segmentov v okolja za poslovne kupce (podjetja podjetjem) ali posamezne potrošnike (prodaja strankam)**  
Večina možnosti izvoza podpira obe vrsti okolij. Izvoz segmentov v različne ciljne sisteme ima posebne zahteve. 

**Izvozi segmenta v okoljih za posamezne potrošnike (prodaja strankam)**  
- Segmenti v kontekstu okolij za posamezne stranke temeljijo na entiteti *poenotenega profila stranke*. Izvoziti je mogoče vsak segment, ki izpolnjuje zahteve ciljnih sistemov (na primer e-poštni naslov).

**Izvozi segmentov v okoljih za poslovne račune (B-to-B)**  
- Segmenti v okviru okolij za poslovne račune so zgrajeni na *račun* subjekt ali *stik* entiteta. Če želite izvoziti segmente računov takšne, kot so, mora ciljni sistem podpirati čiste segmente računov. To velja za [LinkedIn](export-linkedin-ads.md), ko izberete možnost **podjetje** pri definiranju izvoza.
- Vsi drugi ciljni sistemi zahtevajo polja iz entitete stika.
- Z dvema vrstama segmentov (stiki in računi) Customer Insights samodejno prepozna, katere vrste segmentov so primerne za izvoz na podlagi ciljnega sistema. Na primer, za ciljni sistem, osredotočen na stike, kot je Mailchimp, vam Customer Insights omogoča samo izbiro segmentov stikov za izvoz.

**Omejitve pri izvozu segmentov**  
- Ciljni sistemi neodvisnih izdelovalcev lahko omejijo število profilov strank, ki jih lahko izvozite. 
- Za posamezne stranke boste ob izbiri segmenta za izvoz videli dejansko število članov segmenta. Če je segment prevelik, boste prejeli opozorilo. 
- Za poslovne račune boste videli število računov ali stikov, odvisno od segmenta. Če je segment prevelik, boste prejeli opozorilo. Preseganje omejitev rezultatov ciljnih sistemov bo preskočilo izvoz.

## <a name="set-up-a-new-export"></a>Nastavitev novega izvoza

Za nastavitev ali urejanje izvoza potrebujete prave povezave, ki so vam na voljo. Povezave so odvisne od vaše [uporabniške vloge](permissions.md):
- **Skrbniki** imajo dostop do vseh povezav. Pri nastavitvi izvoza lahko ustvarijo tudi nove povezave.
- **Udeleženci** lahko imajo dostop do določenih povezav. Pri konfiguriranju in skupni rabi povezav so odvisni od skrbnikov. Seznam izvozov sodelavcem prikazuje, ali lahko urejajo ali samo ogledujejo izvoz v stolpcu **Vaša dovoljenja**. Za več informacij odprite razdelek [Omogočanje sodelujočim, da uporabljajo povezavo za izvoz](connections.md#allow-contributors-to-use-a-connection-for-exports).
- **Gledalci** si lahko ogledajo samo obstoječe izvoze, ne morejo pa jih ustvariti.

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite možnost **Dodaj izvoz**, da ustvarite nov izvoz.

1. V **Nastavite izvoz** podoknu izberite katero [povezava](connections.md) uporabiti.

1. Navedite zahtevane podrobnosti in izberite **Shrani**, da ustvarite izvoz. Za zahtevane podrobnosti preglejte dokumentacijo Customer Insights za določen izvoz.

## <a name="manage-existing-exports"></a>Upravljajte obstoječe izvoze

Pojdi do **podatki** > **Izvozi** za ogled izvozov, njihovega imena povezave, vrste povezave in stanja. Konfigurirani izvozi so za ogled na voljo vsem uporabniškim vlogam. Seznam izvozov lahko razvrstite po katerem koli stolpcu ali uporabite iskalno polje, da poiščete izvoz, ki ga želite upravljati.

Izberite izvoz za ogled razpoložljivih dejanj.

:::image type="content" source="media/exports_showmore.png" alt-text="Izvozna stran.":::

- **Pogled** oz **Uredi** izvoz. Uporabniki brez dovoljenja za urejanje naj za ogled podrobnosti o izvozu izberejo možnost **Pogled**, ne pa možnosti **Uredi**.
- **Teči** izvoz za izvoz najnovejših podatkov.
- **Ustvari dvojnik** izvoza.
- **[Urnik](#schedule-and-run-exports)** izvoz.
- **Odklopite povezavo** da odstranite povezavo za ta izvoz. Detach ne odstrani povezave, ampak deaktivira izvoz. The **Uporabljena povezava** stolpec prikazuje Ni povezave.
- **Odstrani** izvoz.

## <a name="schedule-and-run-exports"></a>Načrtovanje in zagon izvozov

Vsak izvoz, ki ga konfigurirate, ima urnik osveževanja. Med osveževanjem sistem išče nove ali posodobljene podatke, ki jih bo vključil v izvoz. Izvozi se privzeto izvajajo kot del vsakega [načrtovanega osveževanja sistema](schedule-refresh.md). Za ročni zagon izvozov lahko prilagodite urnik osveževanja ali ga izklopite.

> [!TIP]
> Zmanjšajte čas obdelave izvozov segmentov z naslednjimi najboljšimi praksami:
> - Entitete segmenta porazdelite med več izvozov.
> - Izogibajte se načrtovanju vseh izvozov hkrati. Pustite 30 minut ali eno uro med načrtovanim časom vsakega izvoza.

Urniki izvoza so odvisni od stanja vašega okolja. Če so posodobitve v teku v [odvisnostih](system.md#refresh-processes), ko bi se moral načrtovani izvoz začeti, bo sistem najprej dokončal posodobitve, šele nato pa začel z izvozom. The **Osvežena** stolpec prikazuje, kdaj je bil izvoz nazadnje osvežen.

### <a name="schedule-exports"></a>Načrtovanje izvozov

Določite razporede osveževanja po meri za posamezne izvoze ali več izvozov hkrati. Trenutno določen urnik je naveden v stolpcu **Načrtovanje** na seznamu izvoza. Dovoljenje za spremembo urnika je enako kot [urejanje in definiranje izvozov](export-destinations.md#set-up-a-new-export).

1. Odprite razdelek **Podatki** > **Izvozi**.

1. Izberite izvoz, ki ga želite načrtovati.

1. Izberite **Razporedi**.

1. V podoknu **Načrtovanje izvoza** nastavite **Zagon načrtovanja** na **Vklopljeno**, da samodejno zaženete izvoz. Nastavite ga na **Izklopljeno**, da ga ročno osvežite.

1. Za samodejno osvežene izvoze izberite vrednost **Ponovitev** in določite podrobnosti zanjo. Opredeljeni čas velja za vse primerke ponovitev. To je čas, ko bi se izvoz moral začeti osveževati.

1. Izberite **Shrani**.

Ko urejate razpored za več izvozov, izberite pod **Ohranite ali preglasite urnike**:

- **Držite se individualnih urnikov** : Ohranite predhodno določen urnik za izbrane izvoze in jih samo onemogočite ali omogočite.
- **Določite nov urnik za vse izbrane izvoze**: preglasite obstoječe urnike izbranih izvozov.

### <a name="run-exports-on-demand"></a>Zaženi izvoze na zahtevo

Za izvoz podatkov brez čakanja na načrtovano osvežitev, pojdite na **Podatki** > **Izvozi**.

- Če želite zagnati vse izvoze, izberite **Zaženi vse** v ukazni vrstici. Izvajajo se samo izvozi, ki imajo aktiven urnik. Če želite izvesti izvoz, ki ni aktiven, zaženite en izvoz.
- Če želite zagnati en izvoz, ga izberite na seznamu in kliknite **Zaženi** v ukazni vrstici.

## <a name="troubleshooting"></a>Odpravljanje težav

### <a name="segment-not-eligible-for-export"></a>Segment ni primeren za izvoz

**Težava** V okolju poslovnih računov vaši izvozi ne uspejo s sporočilom o napaki: »Naslednji segment ni primeren za ta cilj izvoza: '{ ime segmenta} '. Izberite samo segmente vrste ContactProfile in poskusite znova."

**Resolucija** Okolja Customer Insights za poslovne račune so bila posodobljena tako, da poleg segmentov računov podpirajo tudi segmente stikov. Zaradi te spremembe izvozi, ki potrebujejo kontaktne podatke, delujejo samo s segmenti, ki temeljijo na stikih.

1. [Ustvarite segment na podlagi kontaktov](segment-builder.md) ki ustreza vašemu prej uporabljenemu segmentu.

1. Ko je ta segment stika zagnan, uredite ustrezni izvoz in izberite nov segment.

1. Izberite **Shrani** da shranite konfiguracijo oz **Shrani in zaženi** da takoj preizkusite ta izvoz.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
