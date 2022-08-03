---
title: Pregled izvozov (predogledna različica)
description: Upravljajte izvoze za skupno rabo podatkov.
ms.date: 07/25/2022
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
ms.openlocfilehash: a70aadda4fc0eff3ddb4c89665506762613c291a
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: sl-SI
ms.lasthandoff: 07/27/2022
ms.locfileid: "9194988"
---
# <a name="exports-preview-overview"></a>Pregled izvozov (predogledna različica)

 Izvozi vam omogočajo skupno rabo določenih podatkov z različnimi aplikacijami. Vključujejo lahko profile strank, entitete, sheme in podrobnosti preslikave. Za vsak izvoz je potrebna [povezava, ki jo nastavi skrbnik, za upravljanje preverjanja pristnosti in dostopa](connections.md). Na strani **Izvozi** so prikazani vsi konfigurirani izvozi.

## <a name="export-types"></a>Vrste izvoza

Obstajata dve glavni vrsti izvoza:  

- **Izvoz podatkov** : izvoz katere koli vrste entitete, ki je na voljo v Customer Insights. Entitete, ki jih izberete za izvoz, se izvozijo z vsemi podatkovnimi polji, metapodatki, shemami in podrobnostmi preslikave.
- **Izvozi segmentov** : izvoz entitet segmenta iz storitve Customer Insights. Segmenti predstavljajo seznam profilov strank. Ko konfigurirate izvoz, izberete vključena podatkovna polja, odvisno od ciljnega sistema, v katerega izvažate podatke.

### <a name="export-segments"></a>Izvoz segmentov

**Izvoz segmentov v okolja za poslovne kupce (podjetja podjetjem) ali posamezne potrošnike (prodaja strankam)**  
Večina možnosti izvoza podpira obe vrsti okolij. Izvoz segmentov v različne ciljne sisteme ima posebne zahteve. 

**Izvozi segmenta v okoljih za posamezne potrošnike (prodaja strankam)**  
- Segmenti v kontekstu okolij za posamezne stranke temeljijo na entiteti *poenotenega profila stranke*. Izvoziti je mogoče vsak segment, ki izpolnjuje zahteve ciljnih sistemov (na primer e-poštni naslov).

**Izvozi segmenta v okoljih za poslovne kupce (podjetja podjetjem)**  
- Segmenti v kontekstu okolij za poslovne račune temeljijo na entiteti *računa*. Če želite izvoziti segmente računov takšne, kot so, mora ciljni sistem podpirati čiste segmente računov. To velja za [LinkedIn](export-linkedin-ads.md), ko izberete možnost **podjetje** pri definiranju izvoza.
- Vsi drugi ciljni sistemi zahtevajo polja iz entitete stika. Če želite zagotoviti, da lahko segmenti računa pridobivajo podatke iz povezanih stikov, mora vaša definicija segmenta projicirati atribute entitete stika. Preberite več o tem, kako [konfigurirati segmente in atribute projekta](segment-builder.md).

**Omejitve pri izvozu segmentov**  
- Ciljni sistemi neodvisnih izdelovalcev lahko omejijo število profilov strank, ki jih lahko izvozite. 
- Za posamezne stranke boste ob izbiri segmenta za izvoz videli dejansko število članov segmenta. Če je segment prevelik, boste prejeli opozorilo. 
- Pri poslovnih računih boste videli število računov v segmentu; vendar se število projiciranih stikov ne prikaže. V nekaterih primerih bi to lahko pripeljalo do tega, da izvoženi segment dejansko vsebuje več profilov strank, kot jih ciljni sistem sprejme. Če so omejitve ciljnega sistema presežene, se izvoz preskoči.

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

Vsak izvoz, ki ga konfigurirate, ima urnik osveževanja. Med osveževanjem sistem išče nove ali posodobljene podatke, ki jih bo vključil v izvoz. Izvozi se privzeto izvajajo kot del vsakega [načrtovanega osveževanja sistema](system.md#schedule-tab). Za ročni zagon izvozov lahko prilagodite urnik osveževanja ali ga izklopite.

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

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
